# Mode Index

Generated from [`allmodes.txt`](allmodes.txt:1) — canonical mode definitions.

This document provides a quick index of available modes, their purpose, and key Memory I/O pointers.

---

## Orchestrator (slug: orchestrator)

- Name: 🪃 Orchestrator
- Description: Coordinate tasks across multiple modes.
- When to use: Complex, multi-step projects requiring delegation and HANDOFFs.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/status/checklist.md; Write: <PROJECT_ROOT>/.ai_coder/status/mode_switches.log

## Code (slug: code)

- Name: 💻 Code
- Description: Write, modify, and refactor code.
- When to use: Implement features, fixes, or refactors.
- Key Memory I/O: Read: <PROJECT_ROOT>/docs/plan.md; Write: <PROJECT_ROOT>/src/, <PROJECT_ROOT>/docs/implementation.md

## Ask (slug: ask)

- Name: ❓ Ask
- Description: Get answers and explanations.
- When to use: Request explanations, analysis, or recommendations without code changes.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/context/context_log.md; Write: <PROJECT_ROOT>/.ai_coder/context/context_log.md (summary)

## Debug (slug: debug)

- Name: 🪲 Debug
- Description: Diagnose and fix software issues.
- When to use: Troubleshooting, diagnosing, and minimal fixes.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/logs/issues.md; Write: <PROJECT_ROOT>/src/, <PROJECT_ROOT>/tests/

## Architect (slug: architect)

- Name: 🏗️ Architect
- Description: Plan and design before implementation.
- When to use: Planning, creating docs/plan.md and todo lists.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/goals/project_blueprint.md; Write: <PROJECT_ROOT>/docs/plan.md

## Emergency Mode (slug: emergency-mode)

- Name: 🧯 EMERGENCY MODE
- Description: Stabilize corrupted project states and preserve integrity.
- When to use: Tool failures, corrupted files, or mode loops.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/logs/*; Write: <PROJECT_ROOT>/.ai_coder/snapshots/

## Report Mode (slug: report-mode)

- Name: 🧾 REPORT MODE
- Description: Gather outcomes and summarize project progress.
- When to use: After milestones or on demand.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/status/checklist.md; Write: <PROJECT_ROOT>/.ai_coder/reports/project_report.md

## Project Research (slug: project-research)

- Name: 🔍 Project Research
- Description: Investigate and summarize codebase structure.
- When to use: Onboarding or deep analysis.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/context/project_tree.md; Write: <PROJECT_ROOT>/.ai_coder/context/context_log.md

## Security Reviewer (slug: security-review)

- Name: 🛡️ Security Reviewer
- Description: Audit for secrets and unsafe patterns.
- When to use: Security reviews and audits.
- Key Memory I/O: Read: <PROJECT_ROOT>/src/; Write: <PROJECT_ROOT>/.ai_coder/logs/security_audit.md

## DevOps (slug: devops)

- Name: 🚀 DevOps
- Description: Deploy apps and automate infra.
- When to use: CI/CD, infra, environment configuration.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/context/active_context.md; Write: <PROJECT_ROOT>/.ai_coder/status/checklist.md

## Documentation Writer (slug: documentation-writer)

- Name: ✍️ Documentation Writer
- Description: Create and polish technical documentation.
- When to use: When docs need creation or cleanup.
- Key Memory I/O: Read: <PROJECT_ROOT>/src/; Write: <PROJECT_ROOT>/docs/

## Init Mode (slug: init-mode)

- Name: 🧭 Context Bootstrapper
- Description: Snapshot and index files for planning.
- When to use: New project start or memory loss.
- Key Memory I/O: Read: <PROJECT_ROOT>/; Write: <PROJECT_ROOT>/.ai_coder/context/project_tree.md

## Memory Guardian (slug: context-tracer-mode)

- Name: 🔍 Memory Guardian
- Description: Log change context across project flow.
- When to use: On every edit or code generation step.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/status/checklist.md; Write: <PROJECT_ROOT>/.ai_coder/logs/task_history.log

## Crosscheck Mode (slug: crosscheck-mode)

- Name: 🧪 Self-Validation Matrix
- Description: Confirm tasks align with goals after any logic change.
- When to use: After logic-modifying tools.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/goals/project_blueprint.md; Write: <PROJECT_ROOT>/.ai_coder/status/checklist.md

## Quality Auditor (slug: self-reflection-mode)

- Name: 🧠 Quality Auditor
- Description: Periodic checks for alignment and completeness.
- When to use: On checkpoints or after N edits.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/logs/task_history.log; Write: <PROJECT_ROOT>/.ai_coder/logs/issues.md

## Emergency Stabilizer (slug: failover-recovery-mode)

- Name: 🛡️ Emergency Stabilizer
- Description: Restore safe points during failures.
- When to use: Failure cascades or crashes.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/logs/*; Write: <PROJECT_ROOT>/.ai_coder/snapshots/

## Final Gatekeeper (slug: completion-validator-mode)

- Name: ✅ Final Gatekeeper
- Description: Verify closure criteria and testing before delivery.
- When to use: Before handoff/shutdown.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/status/checklist.md; Write: <PROJECT_ROOT>/.ai_coder/reports/project_report.md

## Distributed Executor (slug: agent-mesh-mode)

- Name: 🛰️ Distributed Executor
- Description: Coordinate parallel execution across agents.
- When to use: Parallel tasks, shards, or distributed runs.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/context/current_task.lock; Write: <PROJECT_ROOT>/.ai_coder/context/current_task.lock

## Why-Chain Analyzer (slug: causal-reasoning-mode)

- Name: 🧬 Why-Chain Analyzer
- Description: Trace regressions and root causes.
- When to use: After inconsistent tests or hallucinated writes.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/logs/task_history.log; Write: <PROJECT_ROOT>/.ai_coder/snapshots/causal_trace_TIMESTAMP.md

## Memory Anchor (slug: redundancy-checkpointing-mode)

- Name: 🧮 Memory Anchor
- Description: Create persistent snapshots for rollback integrity.
- When to use: Before high-risk operations or after N changes.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/context/project_tree.md; Write: <PROJECT_ROOT>/.ai_coder/snapshots/state_TIMESTAMP.md

## Checklist Manager (slug: checklist-keeper-mode)

- Name: 📋 Checklist Manager
- Description: Ensure actions are logged and mirrored in status.
- When to use: After task execution or completion.
- Key Memory I/O: Read/Write: <PROJECT_ROOT>/.ai_coder/status/checklist.md

## Context Composer (slug: prompt-engineering-mode)

- Name: 🧠 Context Composer
- Description: Generate structured prompts embedding progress and snapshots.
- When to use: Before any generation that affects code or commits.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/goals/project_blueprint.md; Write: <PROJECT_ROOT>/.ai_coder/context/active_context.md

## Mode Writer (slug: mode-writer)

- Name: ✍️ Mode Writer
- Description: Design and implement new custom modes.
- When to use: Creating or updating mode config files.
- Key Memory I/O: Read: <PROJECT_ROOT>/modes/; Write: <PROJECT_ROOT>/modes/

## Test Mode (slug: test-mode)

- Name: 🧪 TEST MODE
- Description: Generate, run, and validate tests.
- When to use: After code changes or when regressions appear.
- Key Memory I/O: Read: <PROJECT_ROOT>/src/, <PROJECT_ROOT>/tests/; Write: <PROJECT_ROOT>/.ai_coder/status/test_outcomes.md

## Mode Contract Validator (slug: mode-contract-validator)

- Name: 📐 Mode Contract Validator
- Description: Verify modes adhered to Memory I/O contracts and logging.
- When to use: After any mode completes and before HANDOFF.
- Key Memory I/O: Read: <PROJECT_ROOT>/.ai_coder/logs/task_history.log; Write: <PROJECT_ROOT>/.ai_coder/status/checklist.md

---

Generated on 2025-08-15T07:26:41Z from [`allmodes.txt`](allmodes.txt:1).