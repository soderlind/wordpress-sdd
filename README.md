# WordPress Spec-Driven Development 

Building WordPress products? I just open-sourced a **Spec-Driven Development constitution** for WP. It defines non-negotiables so teams ship faster—and safer: [constitution.md](https://github.com/soderlind/wordpress-sdd/blob/main/constitution.md)

What’s inside:
1. 🔒 Security (nonces, caps, escaping)
2. 🧱 Block-first architecture
3. ✅ WPCS + ESLint/Prettier
4. 🧪 PHPUnit/Jest/Playwright
5. ♿️ A11y, 🌍 i18n
6. 🚀 CI, SemVer, releases

Works with [GitHub **Spec Kit**](https://github.com/github/spec-kit): /speckit.specify → plan → tasks → implement—all bound by the constitution so specs can’t drift.

Use it, fork it, file issues. Make it your team’s source of truth for plugins, themes & headless builds: [constitution.md](https://github.com/soderlind/wordpress-sdd/blob/main/constitution.md)

## Spec-Driven Development (SDD)

-	From “vibe-coding” to structured development: Many AI code tools quickly produce code based on vague descriptions, but the result is often unreliable. Spec-driven development replaces this with a structured process where specifications are the central source of truth.
-	[**Spec Kit**](https://github.com/github/spec-kit) — a new open-source tool: GitHub has launched Spec Kit, which helps developers use AI tools like GitHub Copilot, Claude Code, and the Gemini CLI in a specification-driven workflow. The tool supports four phases: Specify, Plan, Tasks, and Implement.
-	Specifications as living artifacts: Instead of static documents, specifications become dynamic and evolve alongside the project. They describe user experiences and desired outcomes, and serve as the basis for technical plans and tasks.
-	Benefits of clear structure: By giving the AI agent clear specifications, technical plans, and tasks, errors and misunderstandings are reduced. This yields more precise code and makes it easier to iterate and change direction along the way.
-	Use cases and the future: Spec-driven development is particularly well-suited to new projects, feature expansions in existing systems, and modernization of legacy code. GitHub views specifications as the new source of truth in AI-driven development.
-	Use the [**SSD Quick Start**](https://github.com/soderlind/wordpress-sdd/blob/main/ssd-quick-start.md) to bootstrap Spec Kit, add [constitution.md](https://github.com/soderlind/wordpress-sdd/blob/main/constitution.md), and run the Specify → Plan → Tasks → Implement workflow.

### Learn 
- [Spec-Driven Development With GitHub Spec Kit](https://developer.microsoft.com/blog/spec-driven-development-spec-kit)
- [Complete Spec-Driven Development Methodology](https://github.com/github/spec-kit/blob/main/spec-driven.md)


## Copyright and License

The [constitution.md](https://github.com/soderlind/wordpress-sdd/blob/main/constitution.md) is copyright 2025 Per Soderlind

The [constitution.md](https://github.com/soderlind/wordpress-sdd/blob/main/constitution.md) is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 2 of the License, or (at your option) any later version.

The [constitution.md](https://github.com/soderlind/wordpress-sdd/blob/main/constitution.md) is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with the Extension. If not, see http://www.gnu.org/licenses/.
