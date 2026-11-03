# Tech-21 Interview Handbook: Public Sampler Specification

This repository follows the **Tech-21 Interview Handbook Public Sampler Specification**.

> **Note**: To prevent content duplication, all rules, structure details, and synchronization procedures are maintained in:
>
> 📖 **[AGENTS.md](./AGENTS.md)**

Please refer directly to `AGENTS.md` for all guidelines.

---

### Core Operational Rules for AI Agents

1. **Autonomous & Automatic AGENTS.md Updates**:
   - Whenever any sampler extraction logic, directory layout, or synchronization procedure changes, **you MUST automatically update `AGENTS.md`** immediately in that same task without waiting for user prompting.
2. **Strict Git Remote Push Policy (Zero Autonomous Remote Push)**:
   - **COMMITS MUST NEVER BE PUSHED TO REMOTE AUTOMATICALLY**.
   - All commits remain strictly local. Never run `git push`, `git push origin`, or push commands/flags autonomously. Pushing to remote is exclusively a user-directed action.

