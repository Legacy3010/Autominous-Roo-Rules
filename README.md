# Autominous-Roo-Rules
Autonomous Roo rule structure and mode definitions.
# 🧠 Roo Agent – Deterministic AI Mode Engine

Roo is a modular autonomous system designed for deterministic task resolution, memory fidelity, and fault-tolerant execution. It operates through a rich mesh of custom modes, file scaffolding, and recovery logic to ensure every AI action is transparent, logged, and correctable.

## 🌐 Project Overview

This repository contains the foundational rule system that governs Roo's internal cognition loop:

- **Core agent structure** (`FILE 00`)  
  Defines Roo’s internal memory layout: directories, file ownership, and logging protocols.

- **All modes system prompt** (`FILE 01`)  
  Describes the behavior of all active modes, including fallback routing and completion logic.

- **Agentic intent resolution contract** (`FILE 02`)  
  Outlines the lifecycle of every task, including tool invocation, failure tracing, and task classification (`task-type: todo`, `blocked`, etc).

These files work in harmony with Roo’s `customModes.yaml`, which defines each cognitive mode used in the system (e.g., test-mode, emergency-mode, report-mode, agent-mesh-mode, and more).

## 🛠 Architecture Highlights

- ✅ **Append-only memory** with snapshot recovery  
- 🧩 **Mode-to-file mapping** for memory accountability  
- 📋 **Checklist integrity** with task-type classification  
- 🔐 **Failure escalation** via causal reasoning and emergency fallback  
- 🚀 **Parallel task dispatch** using agent-mesh-mode and fast MCP integration

## 🧬 Mode Contract Validator (New Addition)

To ensure each mode operates exactly as defined, Roo includes a universal validator that checks:

- That required memory files are read/written  
- That each action updates logs and checklists properly  
- That mode responsibilities match observed behavior

Failed validations escalate automatically to the appropriate reasoning or recovery mode.

## ⚡ Getting Started

You can clone this repo and connect it to your Roo runtime or VS Code environment:

```bash
git clone https://github.com/your-username/roo-agent-rules
From there, you can:

Explore or modify the rule files inside /rules/

Review the mode definitions via customModes.yaml

Use the structure to build your own deterministic cognition agent

📦 Related Technologies
This system is designed to integrate with:

MCP Servers (Model Context Protocol) for high-speed reasoning and file access

Gemini CLI for fallback inference or external code suggestions

VS Code Copilot Chat Extension for agent-mode compatibility

👤 Author
Created by Lewis — visionary technologist exploring deterministic AI, abstract storytelling, and fault-resilient automation.

🧭 License
To share, fork, or contribute, define your license here (MIT recommended for open collaboration).
