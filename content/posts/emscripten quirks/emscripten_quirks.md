+++
date = '2026-06-03T19:08:41+05:30'
draft = false 
title = "The Two Things That Bit Me In Emscripten"
description = "Solving linker problems with the Emscripten/clang compiler."
categories = ["Emscripten", "C/CPP", "WASM", "Web Assembly"]
tags = ["WASM", "web assembly", "cpp", "emscripten"]
+++

## Emscripten's Quirks

While building a [web application](https://github.com/QuantaDude/algo-visualizer/tree/master) using React, TypeScript, C++, Emscripten, and Raylib, I ran into two linker-related issues that took far longer to diagnose than they should have.

This is a short article on two problems that I have faced, I am sharing this so that developers who are exploring Web Assembly using Emscripten can easily avoid these issues as I'll also cover the workarounds that solved them for me.

I'll start with the major one.

## Link-Time Optimization and EM_JS

The problem appears when Link Time Optimization `(-flto)` is enabled and an `EM_JS(ret, name, params, ...)` macro function is invoked in one translation unit but called from another.

You'll find that the linker complains that the function symbol you're trying to call is undefined.

The `EM_JS` macro defines a C interface to call the JS function. So if you have your EM_JS macros in a `js_layer.cpp` source file, then you need to wrap the macro invocation as

```cpp
extern "C" {

    EM_JS(void, add, (int a, int b), {
            //your JS code;
          });
}

```

The same applies to the function declaration in `js_layer.hpp` file.

I'll briefly go through the three workarounds or 'solutions' before bringing up the last quirk.

## The Three Workarounds

### If performance isn't of any concern

Well the first one is obvious, just don't use `-flto` in your release builds. The downside is that your binaries (the .data and .wasm compiler outputs in this case) will be larger.
Without LTO, the linker has fewer opportunities for whole-program optimization and dead-code elimination, which can increase the size of the generated .wasm and potentially reduce performance.

### Write a wrapper

You can simply have a wrapper function in the same translation unit which calls the C function interfacing with the JS function, `add()` if you take the above example. The wrapper can simply be:

```cpp
// In js_layer.hpp
void add_wrapper(int , int);
// In js_layer.cpp
void add_wrapper(int a, int b){
    add(a,b);
}
```

Now you can call `add_wrapper()` from any source file just by including `js_layer.hpp`.

### Use the macro in a header or same source

You won't get any undefined symbols or other linking errors if you declare the JS and C functions in the same source file, or use the `EM_JS` macro in a header file.

Since EM_JS emits a function definition rather than a declaration, placing it in a header can lead to multiple-definition problems if the header is included from more than one translation unit.

## The other quirk

The `EXPORTED_FUNCTIONS` linker flag in emscripten allows you to export your C/C++ functions so that your JavaScript code in the browser can invoke and run your C code.

The issue arises when you try to expose an EM_JS function through Emscripten's export mechanism so that it can be called from JavaScript after the module has loaded.

The linker will simply complain that it can't find the xyz symbol even though it should exist as the `EM_JS` macro defines a C function which you can call.

I don't really know why this is the case as I don't know about Emscripten's implementation deeply enough to explain why this happens. Maybe I just need to include some flag in my `CMakeLists.txt` but ultimately it isn't much of a problem as you can simply do the following in your C function declaration:

```cpp
// In js_layer.hpp

extern "C" void add(int, int) __attribute__((used)) __attribute__((visibility("default")));
// or simply
extern "C" void EMSCRIPTEN_KEEPALIVE add(int, int);
```

After this you can call the JS function in your JavaScript/TypeScript code after you import the file.

## Closing Thoughts and Takeaways

The first linker issue bothered me for quite a while. I couldn't find any resources describing this particular problem, which made it especially frustrating to diagnose. In hindsight, I probably would have discovered the cause much sooner if I had tested a debug build instead of focusing exclusively on release builds.

I had no idea that enabling Link Time Optimization (`-flto`) could affect code using the `EM_JS` macro in this way. I knew about the wrapper workaround for quite some time but recently came to know about the root cause.

If there's one takeaway from this article, it's this: test your release build configuration early. Some issues only appear when optimization flags are enabled, and linker-related problems can be particularly difficult to track down because the source of the error is often far removed from the code that triggered it.

WebAssembly development has a few other sharp edges as well. Running out of stack space, memory limits, or misconfigured build flags can all lead to confusing bugs. In my experience, however, those issues are generally easier to understand and solve than linker problems like the ones described here.

Hopefully this saves someone else a few hours of debugging.

