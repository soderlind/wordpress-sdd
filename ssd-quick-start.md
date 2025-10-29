# SSD Quick Start

A short, practical guide to running **Spec‑Driven Development (SSD)** with GitHub Spec Kit—plus how to adopt the **WordPress SDD `constitution.md`** as your project’s source of truth.

Learn more by watching [The ONLY guide you'll need for GitHub Spec Kit](https://www.youtube.com/watch?v=a9eR1xsfvHg)

---

## Quick Start (≈5 minutes)

### 1) Install `uv` (once)
`uv` is a lightweight Python tool runner used by Spec Kit’s CLI.
- macOS/Linux/Windows: see the official install instructions for `uv`.

### 2) Install the Specify CLI (once)
```bash
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
specify check
```

### 3) Bootstrap a project
```bash
# New project
specify init my-project

# Or initialize the current folder
specify init . --here --force
```
This scaffolds the `.specify` directory used by Spec Kit.

### 4) Open your AI coding agent in the project
You should see Spec Kit slash commands appear in chat, such as:
```
/speckit.constitution
/speckit.specify
/speckit.plan
/speckit.tasks
/speckit.implement
```

> **Tip:** Prefer committing early. `specify init` can create a branch; keep those commits small and focused.

---

## Add the WordPress SDD Constitution

Spec Kit reads the project constitution from **`.specify/memory/constitution.md`**. To use the **WordPress SDD** version, place that file there.

### Option A — macOS/Linux (curl)
```bash
mkdir -p .specify/memory
curl -fsSL https://raw.githubusercontent.com/soderlind/wordpress-sdd/main/constitution.md   -o .specify/memory/constitution.md
git add .specify/memory/constitution.md
git commit -m "Adopt WordPress SDD constitution"
```

### Option B — Windows PowerShell
```powershell
New-Item -ItemType Directory -Force -Path .specify/memory | Out-Null
Invoke-WebRequest `
  -Uri https://raw.githubusercontent.com/soderlind/wordpress-sdd/main/constitution.md `
  -OutFile .specify/memory/constitution.md
git add .specify/memory/constitution.md
git commit -m "Adopt WordPress SDD constitution"
```

You can (and should) tailor this file to your team—treat it as a **living artifact**.

---

## The 5‑Step SSD Loop (repeat per feature)

### 1) Constitution — principles & non‑negotiables
In your agent chat:
```
/speckit.constitution
```
The agent will use `.specify/memory/constitution.md` as the project’s source of truth.

**Good prompts:**
- “Establish principles for tests (coverage thresholds), UX consistency, error handling, security, and performance budgets.”
- “Add naming and folder conventions we must follow before merging.”

### 2) Specify — the *what* and *why*
```
/speckit.specify
```
Describe user outcomes and constraints without choosing implementation details yet.

**Example prompt:**
> “Build a simple podcast site: list episodes, highlight a featured episode on the home page, and provide category filters. No auth in v1.”

### 3) Plan — the *how*
```
/speckit.plan
```
Choose stack, architecture, data contracts, and integration points.

**Example prompt:**
> “Use WordPress as a headless CMS, Next.js for the frontend, WP REST API for content, and image optimization. CI with GitHub Actions.”

### 4) Tasks — break it down
```
/speckit.tasks
```
Generates a sequenced task list (with dependencies and validation notes). Usually saved to something like `tasks.md` in the spec folder.

### 5) Implement — ship
```
/speckit.implement
```
The agent executes tasks in order, runs local CLIs as needed (e.g., `npm`, `composer`), and follows your plan and constitution. Test locally and paste any runtime errors back into chat to iterate quickly.

---

## Everyday Workflow

- **Iterate fast:** Update the spec or plan → re‑run `/speckit.tasks` → `/speckit.implement`.
- **Keep the constitution sharp:** As you learn, refine `constitution.md`. It’s your team’s **source of truth**.
- **Branching:** Use feature branches per spec to keep history clean and reviews focused.
- **Reviews:** Link specs, plans, and tasks in PR descriptions to align code reviews with intent.

---

## Troubleshooting

- **Slash commands don’t appear in chat**  
  Ensure you ran `specify init` *inside the project you opened* in your agent. If needed, re‑init with the correct `--ai` flag for your agent, or bypass tool checks with `--ignore-agent-tools` during init.

- **Confirm install/environment**  
  Use:
  ```bash
  specify check
  ```
  to verify required tools (git, agent CLI, etc.). Upgrade the CLI with:
  ```bash
  uv tool install specify-cli --force --from git+https://github.com/github/spec-kit.git
  ```

- **Wrong constitution location**  
  Spec Kit reads from `.specify/memory/constitution.md`. Move or copy your file there if it lives elsewhere.

---

## What SSD buys you

- Less “vibe‑coding,” more repeatable outcomes.
- Fewer mismatches: specs → plans → tasks keep AI on rails.
- Easier pivots: change the spec/plan, regenerate tasks, continue implementing.

---

### One‑liner init (optional, no prior install)
```bash
uvx --from git+https://github.com/github/spec-kit.git specify init <PROJECT_NAME>
```
