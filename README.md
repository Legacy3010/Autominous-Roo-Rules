### Updated `README.md`

**Autominous-Roo-Rules**

Autonomous Roo rule structure and mode definitions.
🧠 **Roo Agent – Deterministic Cognitive System**

[cite\_start]This repository provides a unified ruleset for Roo Code, a VS Code extension that offers a team of AI agents for autonomous coding[cite: 255]. [cite\_start]The rules file, located in `<PROJECT_ROOT>/.roo/rules/rules.md`, governs all default and custom Roo modes[cite: 255]. The accompanying mode definitions in `<PROJECT_ROOT>/modes/customModes.yaml` extend Roo's capabilities with specialized agents. [cite\_start]The agent's memory and state are managed in a separate, project-specific ramdisk directory at `R:/workspaces/<WORKSPACE_NAME>/.ai_coder/`[cite: 267].

**Purpose**
The ruleset and custom modes enable Roo to:

  * [cite\_start]**Manage Context Autonomously:** Tracks past (`context_log.md`), present (`active_context.md`), and future (`future_context.md`) context within the `R:/.../.ai_coder/` directory, allowing seamless agent handoff for continuous project work[cite: 271].
  * [cite\_start]**Isolate Projects:** Each project uses a unique `R:/workspaces/<WORKSPACE_NAME>/.ai_coder/` directory to prevent crossover between projects[cite: 273].
  * [cite\_start]**Act as an Advanced Developer:** Conducts environment scans, security checks, and documentation, driven by a project blueprint[cite: 255, 277].
  * [cite\_start]**Support SLMs:** Optimized for small language models with concise context files and minimal API calls[cite: 255].
  * [cite\_start]**Ensure Security:** Scans for secrets and unsafe code before changes, logging to `R:/workspaces/<WORKSPACE_NAME>/.ai_coder/logs/security_audit.md`[cite: 277].

**Updates**
As of July 31, 2025, the ruleset has been unified and enhanced to include advanced, self-optimizing logic. All rules are now in a single file (`rules.md`) located in `<PROJECT_ROOT>/.roo/rules/`. The system also introduces a comprehensive set of custom modes defined in `<PROJECT_ROOT>/modes/customModes.yaml` to handle specialized tasks like self-optimizing orchestration, continuous security auditing, and automated documentation sync. [cite\_start]The previous fragmented configurations are now archived as templates for historical reference[cite: 255].

**Structure**
The system uses two main directory structures:

1.  **Project Root (`<PROJECT_ROOT>`)**: Contains the core configuration files.
      * [cite\_start]**:** Contains the unified rules file (`rules.md`) for all modes[cite: 255].
      * [cite\_start]**modes/:** Contains the custom mode definitions (`customModes.yaml`)[cite: 255].
2.  [cite\_start]**Roo's Ramdisk Directory (`R:/workspaces/<WORKSPACE_NAME>/.ai_coder/`)**: This is the agent's workspace for memory and state management, as defined in `rules.md`[cite: 267].
      * [cite\_start]**context/:** `project_tree.md`, `current_task.lock`, `context_log.md`, `active_context.md`, `future_context.md`[cite: 267].
      * [cite\_start]**goals/:** `project_blueprint.md` (immutable project goals)[cite: 267].
      * [cite\_start]**logs/:** `execution_trace.log`, `task_history.log`, `issues.md`, `security_audit.md`[cite: 267, 280].
      * [cite\_start]**status/:** `checklist.md`, `test_outcomes.md`, `mode_switches.log`[cite: 268].
      * [cite\_start]**snapshots/:** `state_TIMESTAMP.md` (periodic state snapshots)[cite: 268, 276].
      * [cite\_start]**reports/:** `project_report.md` (final summary)[cite: 268].

**Key Features**

  * [cite\_start]**Context Management:** Maintains past, present, and future context for agent continuity across sessions[cite: 271, 297, 306].
  * [cite\_start]**Self-optimizing Orchestration:** The orchestrator dynamically reprioritizes tasks based on test outcomes and detected bottlenecks[cite: 161, 294].
  * [cite\_start]**Predictive Test Generation:** `test-mode` automatically creates edge-case and regression tests after each code change[cite: 217, 218].
  * [cite\_start]**Continuous Security Auditing:** `security-review-mode` runs automatically after every code or dependency change[cite: 225, 226].
  * [cite\_start]**Automated Documentation Sync:** `documentation-writer` mode is triggered after every feature or API change to keep docs up to date[cite: 230].
  * [cite\_start]**Root Cause Analytics:** After any failure, `causal-reasoning-mode` generates a root-cause report and improvement plan[cite: 243, 244].
  * [cite\_start]**Memory Anchoring and Rollback:** `redundancy-checkpointing-mode` snapshots the state before high-risk operations for instant rollback[cite: 245, 246].
  * [cite\_start]**Prompt Engineering:** `context-composer` injects high-level project goals and recent context into every mode to align all actions[cite: 249, 250].
  * [cite\_start]**Task Tracking:** Uses task-type metadata (`todo`, `done`, `blocked`, `escalated`) in `checklist.md` for autonomous progress[cite: 275].
  * [cite\_start]**Error Recovery:** Logs failures to `issues.md`, snapshots state on critical errors, and triggers `emergency-mode`[cite: 213, 295, 303].
  * [cite\_start]**Documentation:** Updates `docs/plan.md`, `docs/implementation.md`, and `project_report.md` for comprehensive records[cite: 268, 284].

**Setup Instructions**
To initialize a project with these rules, follow Roo Code’s workspace rules setup:

1.  **Install Roo Code:** Install the Roo Code extension from the VS Code Marketplace. [cite\_start]Ensure Python 3 is installed[cite: 255].
2.  **Clone Repository:** `git clone https://github.com/Legacy3010/Autominous-Roo-Rules.git`
    `cd Autominous-Roo-Rules`
3.  **Set Up Project Rules and Modes:**
      * Create the directories in your project root: `mkdir -p <PROJECT_ROOT>/{rules,modes}`.
      * Copy the files from this repository:
          * `cp rules.md <PROJECT_ROOT>/.roo/rules/rules.md`
          * `cp customModes.yaml <PROJECT_ROOT>/modes/customModes.yaml`
4.  **Set Up Roo's Ramdisk Directory:**
      * Create the full directory structure: `mkdir -p R:/workspaces/<WORKSPACE_NAME>/.ai_coder/{context,goals,logs,status,snapshots,reports}`.
5.  **Seed `R:/workspaces/<WORKSPACE_NAME>/.ai_coder/goals/project_blueprint.md`** with your project goals, e.g.:
    ```markdown
    # Project Blueprint: Local AI Model Calculator
    Goal: Build a React web app to recommend AI models based on VRAM, RAM, context length, and task type.
    Success Criteria:
    * Recommend quantized models (e.g., Qwen3-4B-Q4_K_M).
    * Explain settings with metaphors (e.g., Top P as Creativity Slider).
    * Provide LM Studio/Ollama download instructions.
    * Responsive design for mobile browsers.
    ```
6.  [cite\_start]**Initialize Project:** Run `<list_files><PROJECT_ROOT>true</list_files>` in Roo Code to generate `R:/workspaces/<WORKSPACE_NAME>/.ai_coder/context/project_tree.md`[cite: 272].
7.  **Run with LM Studio:** Load Qwen3-4B-Q4\_K\_M in LM Studio. [cite\_start]Set context length to 32768 and server timeout to 600s in `server.ini` to avoid “Client disconnected” errors[cite: 255]:
    ```ini
    [server]
    timeout=600
    ```
8.  [cite\_start]Start Roo in `orchestrator` mode to plan your project[cite: 255].

**Usage Notes**

  * [cite\_start]**Modes:** The rules file applies to all modes, and the custom modes are defined in `customModes.yaml`[cite: 255].
  * [cite\_start]**Security:** Automatically scans for secrets and unsafe code, ensuring secure development[cite: 277].
  * [cite\_start]**LM Studio:** Keep context files concise (\<200 tokens) for Qwen3-4B compatibility[cite: 255].
  * [cite\_start]**Archival:** Previous rulesets are archived and can be used as templates for mode-specific rules in a `R:/workspaces/<WORKSPACE_NAME>/.ai_coder/rules-{modeSlug}/` directory[cite: 255].

**Contributing**
Contributions are welcome\! [cite\_start]Follow the guidelines in `CONTRIBUTING.md`[cite: 255].

📦 **Integration & Usage**
This repo is platform-agnostic. [cite\_start]You may connect it to your own runtime, terminal agent, local AI assistant, or experimental cognition stack[cite: 255].
Suggested directory:

  * [cite\_start]`/.roo/rules/` → Drop `rules.md` here for immediate use[cite: 255].
  * [cite\_start]`/modes/` → Place your mode definitions (`customModes.yaml`) to activate Roo’s mesh[cite: 255].

👤 **Maintainer**
[cite\_start]This system is custom-designed and maintained by Lewis Anderson — a technologist focused on deterministic AI, modular reasoning, and cognitive reliability across autonomous agents[cite: 255].

🧭 **License**
Licensed under the MIT License — free to use, modify, and share. [cite\_start]See `LICENSE` for full terms[cite: 255].
