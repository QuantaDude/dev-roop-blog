---
title: "Abhirup Bhattacharyya"
subtitle: "Software Development Engineer · Back-End Developer"
layout: "resume"
date: 2026-09-30
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

MCA graduate with experience building back-end systems in TypeScript, C++, and WebAssembly. Open-source contributor to Academy Software Foundation projects. Interested in full-stack, computer graphics, and low-level software engineering.

## Technical Skills

**Languages & Runtime:** TypeScript, C++, C, JavaScript, WASM, Node.js

**Frameworks & Data:** Nest.js, React, PostgreSQL, Redis, BullMQ

**Tooling:** CMake, Vitest, AWS, Git, GitHub CI/CD

## Experience

### Open-Source Contributor, OpenImageIO  *— Academy Software Foundation*

September 2026 

- Added `LJ2K` and `ZSTD` compression support to the OpenEXR plugin across the C++ and Core read and write paths, with LJ2K quality and ZSTD level handling [(#5495)](https://github.com/AcademySoftwareFoundation/OpenImageIO/pull/5495).
- Added version-gated regression tests to OpenImageIO with reference files, HTJ2K coverage, and updated docs; bumped the bundled OpenEXR build to v3.5.0 [(#5495)](https://github.com/AcademySoftwareFoundation/OpenImageIO/pull/5495).

### Open-Source Contributor, OpenEXR *— Academy Software Foundation*

DevDays | September 2026

- Removed the aggregation workaround from the docs build process: made each example compile standalone and switched to a CMake OBJECT library so missing headers fail in CI [(#2647)](https://github.com/AcademySoftwareFoundation/openexr/pull/2647).
- Investigated two bugs: Corrupted LJ2K encoder output on the 4.0.0-dev branch [(#2675)](https://github.com/AcademySoftwareFoundation/openexr/issues/2675), and found a data race in OpenEXRCore `unpack.c` [(#2670)](https://github.com/AcademySoftwareFoundation/openexr/issues/2670).
- Redesigned the OpenEXR documentation website with a navigation-card homepage, light/dark theming, version switching, and reformatted documentation files. [(#2657](https://github.com/AcademySoftwareFoundation/openexr/pull/2657) ,[#2652)](https://github.com/AcademySoftwareFoundation/openexr/pull/2652)

### Back End Intern — PerlThoughts *(Remote)*

July 2025 – August 2025 | [Certificate](https://www.linkedin.com/in/abroop/overlay/1768791489146/single-media-viewer/?profileId=ACoAADBdaAcBNc2_QYAInFmz8sQhSshZ3Y2uUo8)

- Designed and built a TypeScript + Nest.js API letting patients book doctor appointments via a front-end, with minimal endpoints, strong validation, and consistent query/mutation semantics.
- Implemented an automated rescheduling algorithm for doctor schedule changes and emergencies, reducing manual clinic staff intervention.

## Projects

### Codebase Search Engine (RAG) *— TypeScript, Node.js, PostgreSQL, pgvector, React, PNPM*

2026 – Ongoing | [GitHub](https://github.com/QuantaDude/RAG-codebase)

- Chunks code by structure (functions, classes, methods), embeds each chunk, and stores it in PostgreSQL with pgvector.
- Query pipeline pairs a decoder transformer (structure) with a code-embedding model (semantics) to narrow candidates before pgvector cosine search.

### Algorithm Visualizer *— C++, TypeScript, React, WASM, WebGL*

[Deployed App](https://quantadude.github.io/algoplex/) | [GitHub](https://github.com/QuantaDude/algoplex)

- Built an interactive algorithm visualizer with TypeScript, C++, WebAssembly, and Pyodide, including a scripting engine that runs user Python graph algorithms step-by-step against a native C++ graph engine.
- Implemented a JavaScript bridge between python execution environment and C++ WebAssembly code supporting async execution, pause/resume, and live state sync.
- Developed an interactive user interface with execution controls and runtime visualization of stacks, queues, and traversal state.

### Shopify Inventory Management App *— Nest.js, Redis, BullMQ, GraphQL, PostgreSQL*

[GitHub](https://github.com/QuantaDude/shopify_app)

- Built an inventory app for Shopify stores with role-based authorization, JWT authentication, and BullMQ background jobs for data sync.
- Designed cron jobs to keep Redis, PostgreSQL, and Shopify data consistent; integrated Shopify Payments with a credits-based billing system.

## Education

### Master of Computer Applications *— Galgotia’s College of Engineering & Technology*

Nov 2022 – Jul 2024 | CGPA: 8.08

### Bachelor of Computer Applications *— Greater Noida Institute of Management*

Aug 2019 – Jun 2022 | 65.47%

## Hackathons & Competitions

### IGDC BYOG 2025 Game Jam *— C++, WASM, Raylib, Emscripten*

October 9–12, 2025 | [Submission](https://itch.io/jam/byog/rate/3953906)

- Built *Cavesweeper*, a top-down survival game, in 72 hours, with procedural map generation, AI pathfinding, tile-based collision, and gameplay balancing.

## Other Open-Source Contributions

### AI Generated Music Detection API SDK *— TypeScript, Vitest*

Dec 2025 – Jan 2026 | [GitHub](https://github.com/TtesseractT/uhmbrella-api)

- Built a runtime-agnostic JavaScript SDK with client initialization, retries, validation, and error handling; added runtime assertions, Vitest tests, and JSDoc, and reported a Jobs API bug.

## Certificates

JavaScript, HackerRank (July 2025) — [Certificate](https://www.hackerrank.com/certificates/946b9a753cb1) | Node.js Developer, Udemy (June 2023) — ID 0010f74970a9
