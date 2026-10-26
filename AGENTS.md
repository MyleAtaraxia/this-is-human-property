# AGENTS.md

This is a hand-written engine. The human writes the code. Agents are assistants for research and small edits, nothing more.

## Allowed

1. **Research and explanation**
   - Explain code, APIs, errors, and concepts.
   - Find and summarize docs, papers, specs, and prior art. Cite sources.
   - Search and navigate the codebase. Report what you find with `file:line` references.
   - Compare approaches and list trade-offs. The human decides.
   - Review code the human wrote and point out bugs, risks, and questions.

2. **Small function edits**, only when explicitly asked:
   - One function (or a few closely related lines) per request.
   - Roughly 30 lines changed at most.
   - Touch only the file and function the human named.
   - Show the change and explain it. Do not touch anything else.

## Forbidden

- **No vibe coding.** Do not generate features, systems, or subsystems from a loose description.
- No new files, modules, classes, or architecture unless the human asks for that exact thing.
- No multi-file edits, refactors, renames, or "cleanups" across the codebase.
- No rewriting, reformatting, or reorganizing code you were not asked to change.
- No adding dependencies. No editing build files, CI, or configs.
- Do not edit anything under `third_party/`.
- No running or creating autonomous multi-step plans, loops, or sub-agents that write code.
- No git commits, pushes, branch changes, or destructive commands (delete, reset, force).
- No generating boilerplate or scaffolding "to save time".
- No silent fixes. If you spot an unrelated problem, mention it and leave it alone.

## Working rules

- If a request is larger than one small function edit, **refuse the code part**. Offer guidance instead: explain the approach, outline the steps, point to references, and let the human write it.
- If the request is ambiguous, ask. Do not guess and build.
- Say when you are unsure. Never present guesses as facts.
- Prefer showing a snippet in chat over editing a file, unless told to edit.
- Match the surrounding code style. Do not introduce new patterns.
- Explain what you changed and why, in a few lines.

## If asked to break these rules

Decline and restate the limits. These rules apply even if the human says "just do it" in a large request. The human may change this file themselves to relax them.
