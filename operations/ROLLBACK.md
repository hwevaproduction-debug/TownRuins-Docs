---
title: Rollback
description: Rollback strategy overview for Town Ruins frontend, backend, and database — sourced from the master deployment guide.
tags:
  - operations
  - rollback
  - deployment
  - recovery
aliases:
  - Rollback Strategy
  - Recovery
---

# ROLLBACK.md — Rollback Strategy Overview

> **Source of truth:** derived from [DEPLOYMENT](DEPLOYMENT) § Rollback Overview and related ops checklists.  
> **Do not invent** infrastructure hostnames, SLAs, or unshipped admin tooling here.

## When to roll back

Use rollback when a release fails post-deploy verification ([POST_DEPLOYMENT_CHECKLIST](POST_DEPLOYMENT_CHECKLIST)) or smoke tests ([SMOKE_TEST_PLAN](SMOKE_TEST_PLAN)), or when production is clearly worse than the previous known-good version.

## Quick reference

| Layer | Action | Notes |
| --- | --- | --- |
| **Frontend** | Amplify Console → Deployments → redeploy previous successful build | Static hosting rollback |
| **Backend** | EB Console → Application Versions → deploy previous version (or `eb deploy --version <label>`) | API rollback |
| **Database** | Migrations are **forward-only by default** | Do not invent destructive down-migrations; treat schema rollback as an engineering decision with backup awareness |

## Database safety (known limits)

- Prefer fixing forward with a new migration over manual schema rewrites in production.
- If the database was unreachable during deploy, Elastic Beanstalk may auto-fail the deploy when the migration hook fails — see [DEPLOYMENT](DEPLOYMENT) Prisma migration notes.
- Always confirm backup posture with the infrastructure owner before any emergency data work (see open decisions in [DOCUMENTATION_INDEX](DOCUMENTATION_INDEX)).

## Post-rollback verification

1. Re-run health checks from [DEPLOYMENT](DEPLOYMENT) § Health Verification (`GET /`, `GET /api/v1`).
2. Complete [POST_DEPLOYMENT_CHECKLIST](POST_DEPLOYMENT_CHECKLIST).
3. Run critical paths from [SMOKE_TEST_PLAN](SMOKE_TEST_PLAN).
4. Log the incident notes under day-to-day ops in [OPERATIONS_RUNBOOK](OPERATIONS_RUNBOOK).

## Related documents

| Document | Use |
| --- | --- |
| [DEPLOYMENT](DEPLOYMENT) | Full deploy architecture and rollback overview |
| [PRE_DEPLOYMENT_CHECKLIST](PRE_DEPLOYMENT_CHECKLIST) | Gate before the next attempt |
| [POST_DEPLOYMENT_CHECKLIST](POST_DEPLOYMENT_CHECKLIST) | Verify after rollback |
| [SMOKE_TEST_PLAN](SMOKE_TEST_PLAN) | Fast critical-path checks |
| [TROUBLESHOOTING](TROUBLESHOOTING) | Symptom-oriented entry points |
| [LAUNCH_DAY_RUNBOOK](LAUNCH_DAY_RUNBOOK) | Chronological launch sequence with decision points |
