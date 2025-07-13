# Autominous-Roo-Rules
Autonomous Roo rule structure and mode definitions.
# 🧠 Roo Agent – Deterministic Cognitive System

This set of Roo Rules are a custom-built autonomous cognition engine designed for reliable execution, structured memory, and modular reasoning. It operates through a sophisticated mesh of modes, each responsible for distinct phases of logic, validation, and recovery — with zero reliance on generative guesswork or external products.

This repository contains Roo's foundational rule system:

- **FILE 00 – Core Agent Structure**  
  Defines the complete memory architecture for Roo, including logs, goals, snapshots, and failure recovery paths.

- **FILE 01 – All Modes System Prompt**  
  Specifies Roo’s behavioral mesh, outlining the responsibilities, fallback chains, and completion logic for each mode.

- **FILE 02 – Agentic Intent Resolution Contract**  
  Enforces task lifecycle integrity from planning to logging to snapshot validation, ensuring every action is traceable and accountable.

These rules work in tandem with a mode definition file (e.g., `customModes.yaml`), which contains over 20 custom roles like `test-mode`, `emergency-mode`, `causal-reasoning-mode`, `checklist-keeper-mode`, and `agent-mesh-mode`.

## 🔧 System Highlights

- ✅ Deterministic memory scaffolding using append-only logs and structured task types (`todo`, `blocked`, `done`, `escalated`)
- 📋 Mode-aware task tracking with automatic recovery on failure
- 🔁 Tool enforcement policies with fallback escalation and causal tracing
- 🛠 Fast file and context access through integrated MCP servers
- 🧠 Optional support from Gemini CLI for external reasoning assistance

## 💡 Memory & Recovery Features

- Snapshots are taken every few tool steps via `redundancy-checkpointing-mode`
- All failures trace through `tool_failures.md` and escalate via `failover-recovery-mode`
- Every task is validated against a permanent mission goal stored in `permanent_mission.md`
- Roo uses reasoning blocks (`<thinking>`) before every tool call — no silent execution

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
