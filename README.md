Updated README.md
Autominous-Roo-Rules

Autonomous Roo rule structure and mode definitions.
🧠 Roo Agent – Deterministic Cognitive System

This repository provides a unified ruleset for Roo Code, a VS Code extension that offers a team of AI agents for autonomous coding. The rules file, 

rules/rules.md, is located in the root of the project. This file governs all default and custom Roo modes, ensuring consistent context management, memory fidelity, and advanced developer behavior across projects. The accompanying mode definitions in 

<PROJECT_ROOT>/modes/customModes.yaml extend Roo's capabilities with specialized agents. The agent's memory and state are managed in a separate, project-specific ramdisk directory at 

R:/workspaces/<WORKSPACE_NAME>/.ai_coder/.

Purpose
The ruleset and custom modes enable Roo to:


Manage Context Autonomously: Tracks past (context_log.md), present (active_context.md), and future (future_context.md) context within the R:/.../.ai_coder/ directory, allowing seamless agent handoff for continuous project work.


Isolate Projects: Each project uses a unique R:/workspaces/<WORKSPACE_NAME>/.ai_coder/ directory; no global or cross-project directories are allowed.


Act as an Advanced Developer: Conducts environment scans, security checks, and documentation, driven by a project blueprint.


Support SLMs: Optimized for small language models with concise context files and minimal API calls.


Ensure Security: Scans for secrets and unsafe code before changes, logging to R:/workspaces/<WORKSPACE_NAME>/.ai_coder/logs/security_audit.md.

Updates
As of July 31, 2025, the ruleset has been unified and enhanced to include advanced, self-optimizing logic. All rules are now in a single file (rules.md). The system also introduces a comprehensive set of custom modes defined in customModes.yaml to handle specialized tasks like self-optimizing orchestration, continuous security auditing, and automated documentation sync. The previous fragmented configurations are now archived as templates for historical reference.

Structure
The system uses two main directory structures:

Project Root (<PROJECT_ROOT>): Contains the core configuration files.


rules/: Contains the unified rules file (rules.md) for all modes.


modes/: Contains the custom mode definitions (customModes.yaml).


Roo's Ramdisk Directory (R:/workspaces/<WORKSPACE_NAME>/.ai_coder/): This is the agent's workspace for memory and state management, as defined in rules.md.


context/: project_tree.md, current_task.lock, context_log.md, active_context.md, future_context.md.


goals/: project_blueprint.md (immutable project goals).


logs/: execution_trace.log, task_history.log, issues.md, security_audit.md.


status/: checklist.md, test_outcomes.md, mode_switches.log.


snapshots/: state_TIMESTAMP.md (periodic state snapshots).


reports/: project_report.md (final summary).

Key Features


Context Management: Maintains past, present, and future context for agent continuity across sessions.


Self-optimizing Orchestration: The orchestrator dynamically reprioritizes tasks based on test outcomes and detected bottlenecks.


Predictive Test Generation: test-mode automatically creates edge-case and regression tests after each code change.


Continuous Security Auditing: security-review-mode runs automatically after every code or dependency change.


Automated Documentation Sync: documentation-writer mode is triggered after every feature or API change to keep docs up to date.


Root Cause Analytics: After any failure, causal-reasoning-mode generates a root-cause report and improvement plan.


Memory Anchoring and Rollback: redundancy-checkpointing-mode snapshots the state before high-risk operations for instant rollback.


Prompt Engineering: context-composer injects high-level project goals and recent context into every mode to align all actions.


Task Tracking: Uses task-type metadata (todo, done, blocked, escalated) in checklist.md for autonomous progress.


Error Recovery: Logs failures to issues.md, snapshots state on critical errors, and triggers emergency-mode.


Documentation: Updates docs/plan.md, docs/implementation.md, and project_report.md for comprehensive records.

Setup Instructions
To initialize a project with these rules, follow Roo Code’s workspace rules setup:

Install Roo Code: Install the Roo Code extension from the VS Code Marketplace. Ensure Python 3 is installed.

Clone Repository: git clone https://github.com/Legacy3010/Autominous-Roo-Rules.git
cd Autominous-Roo-Rules

Set Up Project Rules and Modes:

Create the directories in your project root: mkdir -p <PROJECT_ROOT>/{rules,modes}.

Copy the files from this repository:

cp rules.md <PROJECT_ROOT>/rules/rules.md

cp customModes.yaml <PROJECT_ROOT>/modes/customModes.yaml

Set Up Roo's Ramdisk Directory:

Create the full directory structure: mkdir -p R:/workspaces/<WORKSPACE_NAME>/.ai_coder/{context,goals,logs,status,snapshots,reports}.

Seed R:/workspaces/<WORKSPACE_NAME>/.ai_coder/goals/project_blueprint.md with your project goals, e.g.:

Markdown

# Project Blueprint: Local AI Model Calculator
Goal: Build a React web app to recommend AI models based on VRAM, RAM, context length, and task type.
Success Criteria:
* Recommend quantized models (e.g., Qwen3-4B-Q4_K_M).
* Explain settings with metaphors (e.g., Top P as Creativity Slider).
* Provide LM Studio/Ollama download instructions.
* Responsive design for mobile browsers.

Initialize Project: Run <list_files><PROJECT_ROOT>true</list_files> in Roo Code to generate R:/workspaces/<WORKSPACE_NAME>/.ai_coder/context/project_tree.md.

Run with LM Studio: Load Qwen3-4B-Q4_K_M in LM Studio. Set context length to 32768 and server timeout to 600s in 

server.ini to avoid “Client disconnected” errors.

Ini, TOML

[server]
timeout=600
Start Roo in orchestrator mode to plan your project.

Usage Notes


Modes: The rules file applies to all default modes, and the custom modes are defined in customModes.yaml.


Security: Automatically scans for secrets and unsafe code, ensuring secure development.


LM Studio: Keep context files concise (<200 tokens) for Qwen3-4B compatibility.

Archival: Previous rulesets are archived and can be used as templates for mode-specific rules in a R:/workspaces/<WORKSPACE_NAME>/.ai_coder/rules-{modeSlug}/ directory.

Contributing
Contributions are welcome! Follow the guidelines in CONTRIBUTING.md.

📦 Integration & Usage
This repo is platform-agnostic. You may connect it to your own runtime, terminal agent, local AI assistant, or experimental cognition stack.
Suggested directory:

/rules/ → Drop rules.md here for immediate use.

/modes/ → Place your mode definitions (customModes.yaml) to activate Roo’s mesh.

👤 Maintainer
This system is custom-designed and maintained by Lewis Anderson — a technologist focused on deterministic AI, modular reasoning, and cognitive reliability across autonomous agents.

🧭 License
Licensed under the MIT License — free to use, modify, and share. See LICENSE for full terms.
