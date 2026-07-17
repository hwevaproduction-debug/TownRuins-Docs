---
title: Contributing to shared docs
description: How to edit and publish the TownRuins-Docs submodule used by Creapy and the ops portal.
tags:
  - contributing
  - submodule
  - workflow
---

# Contributing to shared docs

This repository (`TownRuins-Docs`) is the **single source of truth** for product documentation.

| Parent repo | Mount path |
| --- | --- |
| [Creapy](https://github.com/hwevaproduction-debug/Creapy) | `docs/` |
| [TownRuins-Operations](https://github.com/hwevaproduction-debug/TownRuins-Operations) | `content/` |

Do **not** edit product docs as independent copies. Always work through a mount or a direct clone of this repo.

## Edit → publish order

1. **Edit** files in either:
   - `Creapy/docs/…`, or
   - `TownRuins-Operations/content/…`, or
   - a local clone of `TownRuins-Docs`.
2. **Commit and push inside the docs repo** (the submodule), not only in the parent:

```powershell
cd path\to\docs-or-content   # submodule root
git status
git add -A
git commit -m "docs: describe change"
git push origin main
```

3. **Bump both parent gitlinks** so clones stay aligned:

```powershell
# Creapy
cd path\to\Creapy
git add docs
# if you also keep content/ as a submodule of the same repo:
# git add content
git commit -m "chore(docs): bump TownRuins-Docs submodule"
git push

# TownRuins-Operations
cd path\to\TownRuins-Operations
git add content
git commit -m "chore(content): bump TownRuins-Docs submodule"
git push
```

Until both parents point at the same SHA, some clones can lag. Prefer bumping both in the same sitting.

## Conventions

- Prefer YAML frontmatter (`title`, `tags`, optional `aliases`) on pages the portal surfaces.
- Keep portal hub pages (`index.md`, role landings such as `administrator.md`) in this tree so Quartz can keep reading `content/` with no config changes.
- Do **not** commit local noise: `*.coffee` scratch files, `*.code-workspace`, IDE caches.
- Quartz framework docs live under `TownRuins-Operations/docs/` (engine docs). They are **out of scope** for this repo.

## Verify alignment

```powershell
git -C path\to\Creapy\docs rev-parse HEAD
git -C path\to\TownRuins-Operations\content rev-parse HEAD
# both should print the same SHA as origin/main of TownRuins-Docs
```
