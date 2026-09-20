---
title: "Abhirup Bhattacharyya"
subtitle: "Software Development Engineer · Back-End Developer"
layout: "resume"
date: 2026-09-20
location: "Uttar Pradesh, India"
phone: "(+91) 89-2974-1066"
email: "abhirup27022001@outlook.com"
portfolio: "https://quantadude.github.io/dev-roop-blog"
github: "https://github.com/quantadude"
linkedin: "https://linkedin.com/in/abroop"
codewars: "https://www.codewars.com/users/QuantaDude/"
leetcode: "https://leetcode.com/u/abhirup27/"
techstack: "TypeScript | C++ | WASM | Node.js | JavaScript | Nest.js | Redis | BullMQ | Vitest |  AWS | PostgreSQL | React | Git | Github CI/CD"
download: "/files/resume.pdf"
---

## Summary

MCA graduate with experience building back-end systems in TypeScript, C++, and WebAssembly. Interested in full-stack, distributed systems, computer graphics, and low-level software engineering.

## Work Experience

### Back End Intern
**PerlThoughts** | *Remote* | July 2025 - August 2025 | [Certificate](https://www.linkedin.com/in/abroop/overlay/1768791489146/single-media-viewer/?profileId=ACoAADBdaAcBNc2_QYAInFmz8sQhSshZ3Y2uUo8)

- Designed and implemented a TypeScript + Nest.js API enabling patients to book doctor appointments via a front-end.
- Designed the API with minimal endpoints, strong validation, and consistent query and mutation semantics between front-end and back-end.
- Implemented an automated rescheduling algorithm to handle doctor schedule changes and emergencies, reducing manual clinic staff intervention.

## Open-Source Contributions

### OpenEXR (Academy Software Foundation)
**C++, CMake, Sphinx/reStructuredText, CI** | *DevDays 2026* | [PR #2647](https://github.com/AcademySoftwareFoundation/openexr/pull/2647) · [PR #2652](https://github.com/AcademySoftwareFoundation/openexr/pull/2652) · [PR #2649](https://github.com/AcademySoftwareFoundation/openexr/pull/2649) · [PR #2657](https://github.com/AcademySoftwareFoundation/openexr/pull/2657)

- Eliminated the `all.cpp` aggregation workaround in the documentation build: fixed the examples so each compiles standalone (added missing `#include`s, split `MemoryMappedIStream` into independent sources), and replaced the aggregation with a CMake OBJECT library so missing-header errors surface in CI instead of being masked.
- Migrated the documentation site to a better layout structure, redesigned the homepage with navigation cards, added light/dark theming, and implemented Read the Docs version switching via `READTHEDOCS_VERSION` and a `switcher.json`.
- Improved documentation formatting across 13 files and documented the missing `LJ2K_COMPRESSION` attribute.

### AI Generated Music Detection API SDK
**TypeScript, Vitest, PNPM workspaces, NPM** | *December 2025 - January 2026* | [GitHub](https://github.com/TtesseractT/uhmbrella-api)

- Built a runtime-agnostic JavaScript SDK for an AI music detection API with client initialization, retries, validation, and error handling.
- Implemented runtime assertions, authored Vitest tests, reported a Jobs API bug, and documented the public API with JSDoc.

## Projects

### Codebase Search Engine (RAG)
**TypeScript, Node.js, Express, PostgreSQL, pgvector, Drizzle ORM** | *2026 - Ongoing* | [GitHub](https://github.com/QuantaDude/RAG-codebase)

- Built a retrieval-augmented search engine for source code: chunks code by structure (functions, classes, methods, variables), embeds each chunk, and stores it in PostgreSQL with pgvector through Drizzle ORM.
- Implemented an end-to-end query pipeline: a decoder transformer extracts structural meaning and a code-embedding model extracts semantic meaning, together narrowing the candidate chunks before a pgvector cosine-similarity search returns the best-matching code body.
- Currently adding guest zip-upload indexing with live chunk-embedding progress.

### Algorithm Visualizer (Algoplex)
**C++, WASM, JavaScript, WebGL** | [Deployed App](https://quantadude.github.io/algoplex/) | [GitHub](https://github.com/QuantaDude/algoplex)

- Built an interactive algorithm visualizer using C++, WebAssembly, WebGL, and Pyodide.
- Designed a scripting engine allowing users to execute Python graph algorithms step-by-step against a native C++ graph engine.
- Implemented a JS bridge between Pyodide and Emscripten supporting async execution, pause/resume, and live state synchronization.
- Developed an interactive graph editor with execution controls and runtime visualization of stacks, queues, and traversal state.

### Shopify Inventory Management App
**TypeScript, Node.js, Nest.js, Redis, BullMQ, GraphQL, PostgreSQL, JWT** | [GitHub](https://github.com/QuantaDude/shopify_app)

- Built an inventory management app for Shopify stores.
- Implemented role-based authorization and JWT authentication, and background jobs using Redis and BullMQ for data synchronization.
- Designed cron jobs to keep Redis, PostgreSQL, and Shopify data consistent.
- Integrated Shopify Payments with a credits-based billing system.

## Hackathons and Competitions

### IGDC BYOG 2025 Game Jam
**C++, WASM, Raylib, Emscripten** | *October 9-12, 2025* | [Submission Link](https://itch.io/jam/byog/rate/3953906)

- Built Cavesweeper, a top-down survival game in 72 hours using C++, Raylib, WebAssembly, and Emscripten.
- Implemented procedural map generation, AI pathfinding, tile-based collision, and gameplay balancing.


## Education

### Master of Computer Applications
**Galgotia's College of Engineering and Technology** | *Greater Noida, Uttar Pradesh* | November 2022 - July 2024 | **CGPA: 8.08**

### Bachelor of Computer Applications
**Greater Noida Institute of Management** | *Greater Noida, Uttar Pradesh* | August 2019 - June 2022 | **Percentage: 65.47%**

## Certificates

- **JavaScript** | HackerRank | July 2025 | [Certificate](https://www.hackerrank.com/certificates/946b9a753cb1)
- **Node.js Developer** | Udemy | June 2023 | Certificate ID: 0010f74970a9 
