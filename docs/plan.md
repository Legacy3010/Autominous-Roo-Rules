# Integration Plan: Autominous-Roo-Rules at Workspace Root

Objective
Replace nested clone [Autominous-Roo-Rules](Autominous-Roo-Rules) with repository contents at workspace root without leaving duplicates.

Current state
- Nested folder present: [Autominous-Roo-Rules](Autominous-Roo-Rules)
- Root contains existing files: [modes](modes), [docs](docs), [.roo/rules/rules.md](.roo/rules/rules.md)

Action plan
1) Remove the nested folder
Windows
```powershell
rmdir /S /Q Autominous-Roo-Rules
```
2) Initialize Git in workspace root (if not already a repo)
```bash
git rev-parse --is-inside-work-tree || git init
```
3) Add remote and fetch
```bash
git remote remove origin 2>NUL || echo no-remote
git remote add origin https://github.com/Legacy3010/Autominous-Roo-Rules.git
git fetch origin --prune
```
4) Create integration branch and bring in remote files
Option A: Merge (preserves existing files, may create conflicts)
```bash
git checkout -B integration
git pull --allow-unrelated-histories origin main
```
Option B: Overlay remote files (prefer remote on conflicts)
```bash
git checkout -B integration
git pull -X theirs --allow-unrelated-histories origin main
```
5) Verify structure at root
Ensure files present:
- [README.md](README.md)
- [modes/customModes.yaml](modes/customModes.yaml)
- [modes/*.yaml](modes)
- [roo/rules/Rules.md](roo/rules/Rules.md)
- [LICENSE/MIT-License](LICENSE/MIT-License)

6) Clean duplicates and finalize
- Remove obsolete copies if any remain.
- Commit baseline:
```bash
git add -A
git commit -m "Integrate Autominous-Roo-Rules at workspace root"
```

Acceptance criteria
- [Autominous-Roo-Rules](Autominous-Roo-Rules) folder is removed.
- Repo files exist at root paths listed above.
- Git remote points to 'origin' of the repository.
- Workspace opens without duplicated mode/rules files.
- Plan recorded in [docs/plan.md](docs/plan.md).

Rollback
If the integration is unsatisfactory:
```bash
git reset --hard
git checkout -
git branch -D integration
```

Notes and assumptions
- Default branch is 'main'. If different, replace 'main' accordingly.
- No destructive deletion beyond the nested folder.

Handoff to Code Mode
- Execute steps 1–6 above.
- Update [.ai_coder/context/project_tree.md](.ai_coder/context/project_tree.md) and [.ai_coder/status/checklist.md](.ai_coder/status/checklist.md).