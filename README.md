# Autominous-Roo-Rules
Autonomous Roo rule structure and mode definitions.
# 🧠 Roo Agent – Deterministic Cognitive System

Autominous Roo Rules
This repository provides a unified ruleset for Roo Code, a VS Code extension that offers a team of AI agents for autonomous coding. The rules file, located in <PROJECT_ROOT>/.roo/rules/rules, governs all default Roo modes (architect, code, test, debug, report, orchestrator, emergency), ensuring consistent context management, memory fidelity, and advanced developer behavior across projects.
Purpose
The rules file enables Roo to:

Manage Context Autonomously: Tracks past (context_log.md), present (active_context.md), and future (future_context.md) context, allowing seamless agent handoff for continuous project work.
Isolate Projects: Uses a project-specific <PROJECT_ROOT>/.roo/ directory to prevent crossover between projects.
Act as an Advanced Developer: Conducts environment scans, security checks, and documentation, driven by a project blueprint (e.g., for the Local AI Model Calculator).
Support SLMs: Optimized for small language models like Qwen3-4B in LM Studio with concise context files (<200 tokens) and minimal API calls.
Ensure Security: Scans for secrets and unsafe code before changes, logging to <PROJECT_ROOT>/.roo/logs/security_audit.md.

Updates
As of July 29, 2025, the ruleset has been unified into a single plain text file (rules) located in <PROJECT_ROOT>/.roo/rules/rules, replacing previous fragmented configurations. This aligns with Roo Code’s preferred directory-based approach for workspace rules (.roo/rules/). Older files have been archived in the archive/ directory to serve as templates for custom modes or historical reference; they are no longer active but can be adapted for mode-specific rules (e.g., .roo/rules-code/).
Structure
The ruleset creates a <PROJECT_ROOT>/.roo/ directory with:

rules/: Contains the unified rules file for all modes.
context/: project_tree.md, current_task.lock, context_log.md, active_context.md, future_context.md
goals/: project_blueprint.md (immutable project goals)
logs/: execution_trace.log, task_history.log, issues.md, security_audit.md
status/: checklist.md, test_outcomes.md, mode_switches.log
snapshots/: state_TIMESTAMP.md (periodic state snapshots)
reports/: project_report.md (final summary)

Key Features

Context Management: Maintains past, present, and future context for agent continuity across sessions.
Security Checks: Scans for secrets and unsafe code before changes, logging to security_audit.md.
Environment Scan: Generates project_tree.md on startup to map project structure using <list_files>.
Task Tracking: Uses task-type metadata (todo, done, blocked, escalated) in checklist.md for autonomous progress.
Error Recovery: Logs failures to issues.md, snapshots state on critical errors, and triggers emergency mode.
Documentation: Updates docs/plan.md, docs/implementation.md, and project_report.md for comprehensive records.

Setup Instructions
To initialize a project with these rules, follow Roo Code’s workspace rules setup:

Install Roo Code:
Install the Roo Code extension from the VS Code Marketplace.
Ensure Python 3 is installed.


Clone Repository:git clone https://github.com/Legacy3010/Autominous-Roo-Rules.git
cd Autominous-Roo-Rules


Set Up Workspace Rules:
Create the directory <PROJECT_ROOT>/.roo/rules/ in your project:mkdir -p <PROJECT_ROOT>/.roo/rules


Copy the rules file from this repository to <PROJECT_ROOT>/.roo/rules/rules:cp rules <PROJECT_ROOT>/.roo/rules/rules


Seed <PROJECT_ROOT>/.roo/goals/project_blueprint.md with your project goals, e.g.:# Project Blueprint: Local AI Model Calculator
Goal: Build a React web app to recommend AI models based on VRAM, RAM, context length, and task type.
Success Criteria:
- Recommend quantized models (e.g., Qwen3-4B-Q4_K_M).
- Explain settings with metaphors (e.g., Top P as Creativity Slider).
- Provide LM Studio/Ollama download instructions.
- Responsive design for mobile browsers.


Initialize Project:
Run <list_files><path><PROJECT_ROOT></path><recursive>true</recursive></list_files> in Roo Code to generate <PROJECT_ROOT>/.roo/context/project_tree.md.


Run with LM Studio:
Load Qwen3-4B-Q4_K_M in LM Studio.
Set context length to 32768 and server timeout to 600s in server.ini to avoid “Client disconnected” errors:[server]
timeout=600

Start Roo in architect mode to plan your project.

Usage Notes

Modes: The rules file applies to all default modes (architect, code, test, debug, report, orchestrator, emergency). For custom modes, use archived files in archive/ as templates in <PROJECT_ROOT>/.roo/rules-{modeSlug}/.
Security: Automatically scans for secrets and unsafe code, ensuring secure development.
LM Studio: Keep context files concise (<200 tokens) for Qwen3-4B compatibility.
Archival: Previous rulesets in archive/ can be used as templates for mode-specific rules (e.g., .roo/rules-code/) or historical reference.

Example: Local AI Model Calculator
To develop a mobile-friendly React web app for AI model recommendations:

Create <PROJECT_ROOT>/calculator/.roo/rules/rules with the rules file.
Add <PROJECT_ROOT>/calculator/.roo/goals/project_blueprint.md (see setup instructions).
Start Roo in architect mode to generate docs/plan.md.
Monitor <PROJECT_ROOT>/.roo/status/checklist.md and <PROJECT_ROOT>/.roo/logs/security_audit.md for progress and security findings.

Contributing
Contributions are welcome! Follow the guidelines in CONTRIBUTING.md:

## 📦 Integration & Usage

This repo is platform-agnostic. You may connect it to your own runtime, terminal agent, local AI assistant, or experimental cognition stack.

Suggested directory:  
`/rules/` → Drop all three files here for immediate use  
`/modes/` → Place your mode definitions (YAML or JSON) to activate Roo’s mesh

## 👤 Maintainer

This system is custom-designed and maintained by Lewis Anderson — a technologist focused on deterministic AI, modular reasoning, and cognitive reliability across autonomous agents.

## 🧭 License

Licensed under the MIT License — free to use, modify, and share.
See [`LICENSE`](LICENSE) for full terms.
