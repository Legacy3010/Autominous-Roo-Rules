# Autominous Roo Rules

A curated set of Roo modes, rulebooks, and workflows for autonomous, file-centric software delivery in VS Code.

## What this repository contains

- Process rulebooks that standardize ACTION/HANDOFF logging, memory I/O, and pipeline enforcement.
- Exported Roo modes (architect, code, debug, orchestrator, ask) in YAML for portability.
- Reference implementations and usage notes for integrating Roo with Git and CI.
- Project documentation stubs under docs/ that describe plan and implementation history.

## Why this exists

This repo captures a working baseline for operating Roo as an autonomous developer:
- Deterministic process: 2.5 Process Pipeline with context persistence.
- Append-only logs: checklist, task history, and context logs.
- Safe defaults: ignore ephemeral state (.ai_coder, .roo, .local_backup).
- Git-first operations: branch-based integration and PR flow.

## Repository structure

- Rules.MD — master process and memory contract used by modes.
- RullesRAMdisk.MD — RAM-disk optimized variant of the rules.
- CustomModesRAMdisk.MD — notes for RAM-disk workflows.
- Roo-Code-Full — reference content for the Code mode.
- allmodes.txt — quick index of available modes and exports.
- architect-export.yaml, ask-export.yaml, code-export.yaml, debug-export.yaml, orchestrator-export.yaml — exported Roo modes.
- orchestrator-exportog.yaml — legacy orchestrator export for comparison.
- docs/plan.md — project goals and plan.
- docs/implementation.md — running implementation log.
- .gitignore — excludes .ai_coder/, .roo/, .local_backup/, caches, and local artifacts.

## Quick start

- Clone the repo and open in VS Code.
- Review Rules.MD to understand the workflow and memory guarantees.
- Import the YAML mode exports into your Roo environment.
- Work on a feature in a branch, keeping context logs under .ai_coder/ locally (untracked).
- Raise a PR from your integration branch to main.

## Conventions adopted here

- ACTION/HANDOFF blocks are used to pass state between modes.
- Append-only logs for checklist and context; never rewrite history.
- Documentation lives in docs/ and is updated alongside changes.
- Ephemeral directories are ignored by Git to keep the repo clean.

## Notes on ignored paths

The following are intentionally untracked:
- /.ai_coder/ — local memory, logs, snapshots.
- /.roo/ — local rules cache or runtime artifacts.
- /.local_backup/ — one-off safety backups.

## Contributing

- Open an issue describing the change.
- Submit a PR from a feature branch with a concise summary and references to updated docs.
- Ensure new or changed modes align with Rules.MD contracts.

## Status

Active and evolving; integration branch was merged into main to enforce ignore rules and repository hygiene.
