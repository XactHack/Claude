# Personal Operating System

This repository is the user's personal "operating system" — a structured workspace for knowledge, reusable skills, and active projects. Use this file to understand the layout and load relevant context at the start of every session.

## Folder Structure

### `Knowledge/`
Reference material and context that informs how Claude should think and respond. Treat files here as background knowledge, not tasks to complete.

- **`Knowledge/me/`** — Personal context: goals, preferences, working style, bio, role, recurring constraints. Read this to understand who the user is and how they like to work.
- **`Knowledge/LeapLab/`** — Information specific to LeapLab (the user's company/project): products, team, processes, terminology, ongoing initiatives.
- **`Knowledge/Frameworks/`** — Mental models, methodologies, and decision-making frameworks the user relies on. Apply these when giving advice or structuring work.
- **`Knowledge/General/`** — Miscellaneous reference notes that don't fit the above categories.

### `Skills/`
Reusable, task-specific instructions Claude can follow to perform recurring work consistently.

- **`Skills/skill.md`** — Template for new skills. Copy this file, rename it, and fill in the sections (purpose, triggers, instructions, inputs, output) when defining a new skill.

### `projects/`
Active and archived work. Each project should live in its own subfolder with its own files, notes, and deliverables. Create a new subfolder per project as work begins.

## How Claude Should Use This
1. At the start of a session, check `Knowledge/me/` for personal context and `Knowledge/Frameworks/` for how the user likes to approach problems.
2. If the task relates to LeapLab, also read `Knowledge/LeapLab/`.
3. If a recurring task matches an existing skill in `Skills/`, follow it. If a new recurring task emerges, offer to create a new skill using `Skills/skill.md` as the template.
4. Keep project work scoped to its folder under `projects/`.
