# Tech-21 Interview Handbook: Public Sampler Specification

> **Public Open Lead Magnet & Community Teaser Repository**  
> Repository: [https://github.com/manojkumar-nt/tech-21-interview-handbook](https://github.com/manojkumar-nt/tech-21-interview-handbook)

This specification defines the architectural rules, structure, and synchronization protocols for `tech-21-interview-handbook`.

---

### 0. Autonomous Maintenance & Git Safety Protocols

#### A. Autonomous & Automatic AGENTS.md Updates (Self-Maintaining Specification)
- **Mandatory Self-Update**: Whenever any directory structure, generation script, contribution guideline, or licensing model changes, **you MUST automatically update `AGENTS.md`** (and companion `GEMINI.md`) in that same turn/task.
- **Zero Lag**: Do not ask the user for permission to update `AGENTS.md` or leave documentation out-of-sync.

#### B. Strict Git Remote Push Policy (Zero Autonomous Remote Push)
- **COMMITS MUST NEVER BE PUSHED TO REMOTE AUTOMATICALLY**: Under no circumstances should an AI agent or automated script run `git push`, `git push origin`, or push any branch or tag to remote automatically.
- **Local Commits Only**: Commits must remain local. Pushing to GitHub is strictly reserved for manual user action or explicit user request.

---

### 1. Repository Purpose & Structure

`tech-21-interview-handbook` serves as the public open-source entry point and lead magnet for the Tech-21 Series:

- **Free Sampler Scope**: Exactly **Questions 01 through 03 + Preface** across all **15 engineering editions** (45 free chapters total).
- **Directory Layout**:
  ```text
  tech-21-interview-handbook/
  ├── README.md               # Master catalog, badges, syllabus links & monetization paths
  ├── CONTRIBUTING.md         # Public contribution and errata guidelines
  ├── LICENSE                 # CC BY-NC 4.0 License
  ├── books/
  │   ├── ai-agents/          # README.md + 00-preface.md + 01 to 03 markdown chapters
  │   ├── angular/
  │   ├── architect-technologies/
  │   ├── coding-with-agents/
  │   ├── docker/
  │   ├── helm/
  │   ├── java/
  │   ├── javascript/
  │   ├── kubernetes/
  │   ├── nodejs/
  │   ├── openshift/
  │   ├── python/
  │   ├── react/
  │   ├── system-design/
  │   └── typescript/
  ├── AGENTS.md               # Repository specification
  └── GEMINI.md               # Rules pointer to AGENTS.md
  ```

---

### 2. Synchronization from Parent Monorepo

Content in this repository is automatically generated and synchronized from the parent `tech-21` monorepo:

- **Generator Engine**:
  ```bash
  # Executed from parent tech-21 repository:
  node tools/generate-sampler.js
  # Or:
  npm run generate:sampler
  ```
- **Generation Logic**:
  - Extracts `src/00-preface.md`, `src/01-*.md`, `src/02-*.md`, and `src/03-*.md` from `books/<tech>/`.
  - Re-writes relative asset links to ensure native Mermaid diagrams render cleanly on GitHub.
  - Automatically compiles edition `README.md` files with complete 21-question syllabi, book links, and Gumroad/KDP store links.
- **Git Safety Protocol**:
  - The parent repository's pre-commit hook auto-stages sampler updates locally.
  - **NEVER** push commits to GitHub automatically.

