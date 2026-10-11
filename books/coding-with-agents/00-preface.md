[← Back to Tech-21: Coding with AI Agents Overview](./README.md) | [🏠 Series Catalog](../../README.md)

---

# Preface 

## The Tech-21 Philosophy

AI coding agents—such as Cursor, Claude Code, GitHub Copilot, Windsurf, Cline, and Aider—have fundamentally transformed the software engineering profession. For decades, coding required typing every token manually into an editor. Today, an engineer equipped with an AI coding agent acts as a tech lead and architect commanding a tireless, junior-to-mid-level pair programmer.

However, the vast majority of software developers use these powerful tools inefficiently:
- They type vague, conversational prompts like *"fix this bug"* or *"make this faster"*, and then wonder why the agent hallucinates broken imports or corrupts existing business logic.
- They fall into the trap of **Vibe Coding**: blindly accepting code suggestions without reading the diff, silently piling up technical debt and introducing critical security flaws.
- They watch agents get trapped in infinite 20-step retry loops, burning through API allowances and generating frustration.
- They struggle to get agents to write solid, reliable unit test suites rather than trivial mock assertions.

**This book was written specifically for the working software developer.** You do not need to understand Transformer attention mathematics, rotary position embeddings, or compiler parsing theory to become a world-class AI-assisted software engineer. What you need is an actionable, battle-tested playbook of **daily engineering habits, prompt architectures, context hygiene practices, and verification guardrails**.

**Tech-21: Coding with AI Agents** delivers exactly that: 21 pragmatic questions answering how to turn AI agents into your greatest daily productivity multiplier without compromising code quality, security, or craft.

---

## The 21-Question Curation Framework

This volume organizes the developer's journey into **21 practical questions** across four progressive tiers, followed by two deep-dive field reference appendices:

| Tier | Focus Area | Chapters | Core Developer Competencies |
| :--- | :--- | :--- | :--- |
| **Tier 1** | **Daily Foundations & Getting Started** | Q01 – Q05 | Setting up `AGENTS.md` and `.cursorrules`, writing spec-driven prompts, managing context windows and tab hygiene, driver-navigator pair programming, and choosing between inline assistants and autonomous CLI loops. |
| **Tier 2** | **Core Engineering Workflows** | Q06 – Q10 | Getting agents to write thorough unit/integration tests, diagnosing and fixing complex production bugs, safely refactoring legacy spaghetti code, scaffolding new features/APIs without bloat, and navigating unfamiliar repositories. |
| **Tier 3** | **Advanced Collaboration & Quality Control** | Q11 – Q15 | Reviewing AI-generated diffs and PRs, preventing hallucinated libraries and APIs, steering agents stuck in error loops (the 3-turn rule), safe terminal and Git execution, and generating accurate documentation and OpenAPI specs. |
| **Tier 4** | **Professional Mastery & Team Scale** | Q16 – Q21 | Creating reusable slash commands and custom prompt templates, handling database migrations and schema changes safely, balancing speed with clean architecture, automating dependency upgrades, building personal workflows, and avoiding vibe coding anti-patterns. |
| **Tier 5** | **Reference Appendices** | Q22 – Q23 | The Pragmatic Developer Prompt Templates Cheatsheet, and the Daily AI Coding Checklist & Anti-Pattern Field Guide. |

---

## Strict 5-Section Chapter Schema

Every core chapter follows our signature 5-part anatomy designed for maximum signal and lifelong retention:

1. **The Core Concept & Intuition**: The practical developer bottleneck, why naive prompting fails, and the engineering mental model.
2. **Under the Hood: Practical Mechanics**: The underlying interaction mechanics, horizontal Mermaid architectural diagrams (`graph LR`), and structured comparison matrices.
3. **Clean Code in Action**: Ready-to-use prompt blueprints, configuration templates, and automated verification scripts demonstrating primary patterns and advanced workflows.
4. **Common Pitfalls & Developer Traps**: Crisp 2-column tables analyzing real-world developer failure modes and their exact practical remediations.
5. **The 60-Second Memory Anchor**: A punchy, memorable rule of thumb locking the concept permanently into memory.

---

## How to Use This Book

- **For Frontend, Backend & Fullstack Developers**: Read Tiers 1 and 2 to instantly double your daily feature velocity and eliminate prompt frustration.
- **For Senior Engineers & Tech Leads**: Leverage Tiers 3 and 4 to establish team-wide rules files, code review standards, and safe Git workflows for AI-authored pull requests.
- **For Daily Standups & Coding Sessions**: Keep Appendix A and B open as your desk reference for battle-tested prompt templates and review checklists.

Let's begin with Question 1.

---

**Next**: [Question 01 →](./01-how-should-you-set-up-your-project-for-ai-coding-agents.md)
