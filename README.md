About This Guide & Cadify.no Transition

Cadify.no is working towards implementing Zoo.dev, as a modern, equal-option 3D CAD system to our existing SolidWorks environment. Zoo.dev’s open-source modeling app delivers programmable, version-controlled hybrid design (point-and-click + KCL code) on a GPU-native geometry engine, giving us the best of both worlds.

This public guide standardizes how Cadify Zoo.dev contributors track and report work during the transition. It ensures full traceability, follows Zoo.dev’s official rules, and creates clean, searchable records optimized for future AI retrieval.

 

Key People

Founder & Owner of KODE15 AS (Norway): Jørn Watvedt

Lead Developer: Hervai-d'Elhoungne András, PhD

 

Note: The cadify.no website is currently in Norwegian. Right-click anywhere on the page and choose “Translate to [your language]” for full readability.

 

Introduction

This guide standardizes how external contributors (like Andras) track work on the open-source Zoo Design Studio. It ensures full traceability, satisfies Zoo.dev rules, and creates clean, searchable records for future AI retrieval. Every major task uses GitHub issues with a mandatory structured summary when closed.

 

Zoo.dev Official Recommendations (from CONTRIBUTING.md)

 

Always create a corresponding issue before starting any PR or significant work.
Use clear labels and keep issues focused.
Separate refactoring from feature commits.
Follow existing patterns: issues for features, bugs, releases, and developer-experience topics.
 

Recommended Workflow (Hybrid – Clean & Scalable)

 

Open one parent issue per major workstream (e.g., “Andras – Dev Environment Setup & First Annotation Contribution”).
Use a Markdown task list inside the issue for sub-tasks.
Update progress via comments (or linked child issues for very large items).
When the workstream is complete → close the issue with the AI Reference Summary (see template below).
Add these labels: external-contributor, setup, windows, annotations/gdt, meta/developer-experience.
 

This approach avoids repo clutter while meeting Zoo.dev’s “corresponding issue” requirement and delivering perfect long-term AI memory.

 

Mandatory AI Reference Summary Requirement

Every closed issue must end with the exact “AI Reference Summary” block. This format is optimized for future LLM searches and must be included in the final comment or issue body.

 

Copy-Paste AI Reference Summary Template as example

 

Markdown

## ✅ AI Reference Summary

 

**Task:** [One-line title, e.g. "Windows dev environment setup for modeling-app"]

 

**Problems Encountered:**

- link.exe not found → missing Visual Studio C++ workload

- dlltool.exe confusion (GNU vs MSVC target)

- `npm run build:wasm:windows` → Biome error 123

- `electron-builder` symlink error in cache (required admin)

- Official desktop build shows flatness/datum UI; local build does not

- `npm run tron:start` only launches minimal shell (depends on non-public dev.zoo.dev)

 

**How Solved:**

- Installed “Desktop development with C++” workload

- Confirmed MSVC toolchain (not GNU) for Windows Rust

- Verified .wasm artifacts were still produced despite Biome error

- Ran PowerShell as Administrator for packaging

- Documented that annotation UI is likely gated behind app-level config / release flags (not just `@settings(experimentalFeatures = allow)`)

 

**Outcome:** Environment fully functional. Main remaining blocker = annotation UI parity with released build. Ready for first KCL/GDT contribution.

 

**References:**

- Official: CONTRIBUTING.md + rust/kcl-lib/src/std/mod.rs

- This issue: #XXXX

- Related branches: jtran/gdt-annotation, andrewvarga/9731/distance-dimension

 

**Closed by:** Andras – 2026/04/26
