---
title: "Abhirup Bhattacharyya"
subtitle: "Software Development Engineer · Back-End Developer"
layout: "resume"
date: 2026-11-07
location: "Uttar Pradesh, India"
phone: "(+91) 89-2974-1066"
email: "abhirup27022001@outlook.com"
portfolio: "https://quantadude.github.io/dev-roop-blog"
github: "https://github.com/quantadude"
linkedin: "https://linkedin.com/in/abroop"
codewars: "https://www.codewars.com/users/QuantaDude/"
leetcode: "https://leetcode.com/u/abhirup27/"
download: "/files/resume.pdf"
---

## Summary

MCA graduate and software developer focused on backend engineering and AI-powered systems. Experience building TypeScript/Node.js APIs, asynchronous job processing, database-backed applications, and local LLM-powered code search systems. Open-source contributor to Academy Software Foundation projects, with experience in C++, CI/CD, debugging, and software testing. Interested in building scalable, reliable AI infrastructure.

## Technical Skills

**Languages:** TypeScript, JavaScript, C++, C, Python

**Backend:** Node.js, NestJS, Express.js, REST APIs, GraphQL

**Databases & Messaging:** PostgreSQL, pgvector, Redis, BullMQ

**AI & ML:** LLM inference, RAG, embeddings, vector similarity search, node-llama-cpp

**Infrastructure & Tooling:** Linux, Git, GitHub Actions, CMake, Vitest, AWS, WebAssembly

## Experience

### Open-Source Contributor, OpenImageIO — Academy Software Foundation

September 2026

- Implemented LJ2K and ZSTD compression support in the OpenEXR plugin across the C++ and Core APIs, including compression quality-level handling. [PR #5495](https://github.com/AcademySoftwareFoundation/OpenImageIO/pull/5495).
- Added version-gated regression tests for three compression formats, updated the bundled OpenEXR version in GitHub Actions CI, and updated documentation.

### Open-Source Contributor, OpenEXR — Academy Software Foundation

September 2026

- Refactored documentation examples to compile as standalone CMake OBJECT libraries, allowing CI to detect missing headers and ensuring examples explicitly include their dependencies. [PR #2647](https://github.com/AcademySoftwareFoundation/openexr/pull/2647).
- Investigated encoder corruption in the LJ2K development branch and a potential data race in OpenEXRCore's `unpack.c`. [Issue #2675](https://github.com/AcademySoftwareFoundation/openexr/issues/2675) · [Issue #2670](https://github.com/AcademySoftwareFoundation/openexr/issues/2670).
- Redesigned the documentation website with navigation cards, light/dark themes, version switching, and improved documentation structure. [PR #2657](https://github.com/AcademySoftwareFoundation/openexr/pull/2657).

### Backend Intern, Pearl Thoughts — Remote

July 2025 – August 2025

- Designed and implemented a TypeScript/NestJS API for patient doctor-appointment booking, with request validation and consistent query/mutation semantics.
- Developed an automated appointment-rescheduling algorithm to handle doctor schedule changes and emergencies, reducing manual intervention by clinic staff.

## Projects

### Codebase Search Engine (RAG) — AI Systems

**TypeScript, Node.js, PostgreSQL, pgvector, React, node-llama-cpp**

2026 – Ongoing | [GitHub](https://github.com/QuantaDude/RAG-codebase)

- Built a codebase search system combining structural code parsing with semantic search, chunking source code into functions, classes, and methods.
- Implemented a local LLM-powered query parser to extract structural constraints and a code-embedding model to generate semantic representations.
- Integrated PostgreSQL with pgvector for cosine-similarity search and HNSW indexing to retrieve relevant code chunks.
- Used local GGUF models for query understanding and code embeddings through node-llama-cpp.

### Shopify Inventory Management App

**NestJS, TypeScript, Redis, BullMQ, GraphQL, PostgreSQL**

[GitHub](https://github.com/QuantaDude/shopify_app)

- Developed an inventory management application for Shopify stores with JWT authentication and role-based authorization.
- Implemented BullMQ background jobs and scheduled tasks for synchronizing inventory data across Redis, PostgreSQL, and Shopify.
- Integrated Shopify Payments with a credits-based billing system.

### Algorithm Visualizer

**C++, TypeScript, React, WebAssembly, Pyodide**

[Deployed Application](https://quantadude.github.io/algoplex/) | [GitHub](https://github.com/QuantaDude/algoplex)

- Built an interactive algorithm visualization platform combining a native C++ graph engine with Python execution through Pyodide.
- Implemented a JavaScript bridge between Python and WebAssembly supporting asynchronous execution, pause/resume, and live state synchronization.
- Developed interactive execution controls and visualizations for graph algorithms, stacks, and queues.

### AI-Generated Music Detection API SDK

**TypeScript, Vitest**

December 2025 – January 2026 | [GitHub](https://github.com/TtesseractT/uhmbrella-api)

- Developed a runtime-agnostic JavaScript SDK with client initialization, retries, request validation, and error handling.
- Added runtime assertions, automated Vitest tests, and JSDoc documentation; reported a Jobs API bug.

## Education

### Master of Computer Applications — Galgotia's College of Engineering & Technology

November 2022 – July 2024 | CGPA: 8.08

### Bachelor of Computer Applications — Greater Noida Institute of Management

August 2019 – June 2022 | 65.47%
