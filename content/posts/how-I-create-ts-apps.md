+++
date = '2026-01-10T15:17:40+05:30'
draft = false 
title = 'My "Opionated" Way of Making TypeScript Applications'
description = "A guide to TypeScript development."
tags = [
    "TypeScript",
    "software",
    "functional composition"
]
+++

## Introduction


In this article, I'll share what I've been learning for the past one year - which is how to create **clean**, easy to **test** TypeScript back-end code.
If you're someone who is about to get into web development, specifically back-end or someone who has made one or two projects using express.js, then this article is for you.

## Why this article? and what's in it?

I am writing this article because I care about my craft, how I make software. If you do that too, then you're free to read along. 
This article also partly serves me as a note which I can refer to from time to time.


This is **not** an end to end tutorial. I'll go over workspaces, project configuration, the actual development, which also includes functional composition, closures, how to think about what you're making, and then lastly testing.  


But first...
## What not to do

### - Start off by using a framework

Beginners are susceptible to this mistake, most are. I am not saying that frameworks are bad, they make developing big projects a bit easier. If you do end up starting off learning a framework, ask yourself "why is it done this way?".
But most Beginners do not do this, what they do is....

### - Keep watching tutorials endlessly

Most students fall into this 'trap' through a grapevine, they hear that a certain YouTube tutorial or a paid course is great, and they pick it up, they keep following it. Unless it's a tutorial about a concept which is alien to you; don't watch it.
On top  of watching those tutorials about some programming language or frameworks, most beginners...

### - Do not learn to use the tools better

What tools you might ask?
 - Your IDE.
 - Knowledge of computer networks, security.

Trust me, learning to navigate a big codebase goes a long way, and you learn much more than some tutorial. Learn how you can jump to a symbol. VS Code has built in TypeScript support but I encourage you to move to a keyboard centric editor or atleast a better IDE. If you have extra time, I recommend Neovim.

### - Have AI in your IDE

Instead of having AI directly write your code in your IDE, I recommend querying them for ideas, and ways to approach a given problem. See what it writes and try to understand what it is doing.
They are trained on stack overflow and other forums data, but you shouldn't blindly trust them, cross check what the LLM says with other sources.

I suggest you to **remove them** from your IDE immediately.


## Workspaces

If you've made a project with atleast one dependency like express.js, then you've probably used npm or yarn or pnpm.
You initialize your workspace my running the following command:
```bash
npm init
```
What this does is create a package.json in your directory after it prompts you for some inputs. When you write your code in your IDE, it looks for all the symbols within this root directory.


While this is good for small projects, what I recommend doing is creating workspaces; a monorepo. A monorepo contains more than one 'package'.
I recommend you to use the [pnpm package manager](https://pnpm.io/) to manage your monorepo and dependencies, it's much faster than npm and can potentially save you a lot of disk space.

| npm command | pnpm command |
| -------------- | --------------- |
| ``npm init`` | ``pnpm init`` |
| ``npm install`` | ``pnpm install`` |
| ``npm i <pkg>`` | ``pnpm add <pkg>`` |
| ``npm run <cmd>``| ``pnpm <cmd>`` |

The directory which you've created after ``npm init`` or ``pnpm init`` is the workspace root. notice that inside the package.json, the scripts contains all the commands you can run using the ``pnpm <cmd>`` command.


Obviously to create sub-workspaces, you need directories.
```
monorepo-root/
├── apps/         //(packages)
│   ├── front-end/
│   │   ├── src/
│   │   └── package.json
│   │   
│   └── back-end/
│       ├── src/
│       └── package.json
├── common/
│   ├── src/
│   └── package.json
├── package.json
└── README.md
```
After you've this monorepo structure, create a file called ``pnpm-workspace.yaml`` in the root of your workspace directory and add the following:
```yaml
packages:
    #all direct sub-directories / folders under apps will be a package
    - "app/*"
    # the common package will be shared among the app packages
    - "common"
```

Mathematical notation in a Hugo project can be enabled by using third party JavaScript libraries.
<!--more-->

In this example we will be using [$\KaTeX$](https://katex.org/)

- Create a partial under `/layouts/partials/math.html`
- Within this partial reference the [Auto-render Extension](https://katex.org/docs/autorender.html) or host these scripts locally.
- Include the partial in your templates like so:

```bash
{{ if or .Params.math .Site.Params.math }}
{{ partial "math.html" . }}
{{ end }}
```

- To enable $\KaTeX$ globally set the parameter `math` to `true` in a project's configuration
- To enable $\KaTeX$ on a per page basis include the parameter `math: true` in content files

**Note:** Use the online reference of [Supported $\TeX$ Functions](https://katex.org/docs/supported.html)

<p>
Inline math: $\varphi = 1+\frac{1}{1+\frac{1}{1+\cdots}}$
</p>

Block math:
$$
\mathcal L_{\mathcal T}(\vec{\lambda})
= \sum_{(\mathbf{x},\mathbf{s})\in \mathcal T}
    \log P(\mathbf{s}\mid\mathbf{x}) - \sum_{i=1}^m
    \frac{\lambda_i^2}{2\sigma^2}
$$
