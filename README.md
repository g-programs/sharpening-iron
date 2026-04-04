# ⚔️ Sharpening Iron: The Skeptic-in-Chief Extension

**Sharpening Iron** is a universal "Devil's Advocate" for software engineering. It integrates directly with the Gemini CLI to provide a rigorous, project-agnostic logic audit for every implementation plan, architectural decision, and complex bug fix.

Its primary mission is to identify "Single Points of Failure" and "Happy Path" biases **before** a single line of code is written or modified.

## 🌟 Key Features

- **The "Skeptic-in-Chief" Persona**: Actively questions every plan to find logic gaps, systemic vulnerabilities, and hidden side effects.
- **Project-Agnostic Audit**: Works across any codebase, language, or framework.
- **Strategic Intervention**: Automatically prompts for activation during "Strategy" and "Execution" phases.
- **The "Iron List"**: Generates a mandatory list of 3-5 critical "What If" scenarios that must be addressed for a plan to be "Skeptic-Approved."

## 🛠️ How It Works

Sharpening Iron systematically refines your development workflow by auditing four critical areas:

1.  **Happy Path Bias**: Identifies assumptions of perfect conditions (e.g., ignoring network timeouts, state inconsistencies, or malformed data).
2.  **Boundary & Edge Cases**: Stresses the logic at its limits (e.g., concurrency race conditions, scale issues, and security leaks).
3.  **Integration Gaps**: Analyzes downstream side effects and implicit assumptions about dependencies.
4.  **Root Cause Verification**: Ensures the solution addresses the core issue rather than just the symptoms.

## 🚀 Installation

Install directly via the Gemini CLI:

```bash
gemini extensions install https://github.com/g-programs/sharpening-iron.git
```

## 📋 Usage

Once installed, the extension monitors your workflow. When you move into a **Strategy** or **Execution** phase for a task, the agent will prompt to activate the **Sharpening Iron** skill.

### Example Interaction

> **User**: "I'm going to implement a new caching layer for the user profiles."
>
> **Agent**: "I've detected a new architectural plan. Should I activate **Sharpening Iron** to audit the strategy?"
>
> **User**: "Yes."
>
> **Agent (Sharpening Iron)**: "Activating Skeptic-in-Chief... I've identified 3 critical gaps in your profile caching plan:
> 1. **Race Condition**: What happens if two updates occur simultaneously?
> 2. **Cache Invalidation**: How do we handle stale data if the DB update fails after the cache is cleared?
> 3. **Memory Pressure**: What is the eviction policy if the cache hits its limit under 100x load?"

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
*Developed by the Focus Fire Team*
