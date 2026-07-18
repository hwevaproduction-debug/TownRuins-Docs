---
title: Launch Day Runbook
description: Chronological launch sequence for Town Ruins using existing pre-deploy, smoke, post-deploy, and rollback docs.
tags:
  - operations
  - launch-day
  - runbook
aliases:
  - Launch Day
  - Go-Live Runbook
---

# LAUNCH_DAY_RUNBOOK.md — Chronological Launch Sequence

> **Source of truth:** sequences existing checklists and runbooks. No invented SLAs or unshipped console steps.

## Roles (logical)

| Role | Responsibility on launch day |
| --- | --- |
| DevOps / Infra | Pre-deploy gates, deploy, env confirmation |
| QA | Smoke tests and post-deploy verification |
| Engineering lead | Go / no-go and rollback decision |
| Owner staff (optional) | Product smoke via admin app after green deploy |

## Sequence

### 1. Pre-flight (before deploy)

Work through [PRE_DEPLOYMENT_CHECKLIST](PRE_DEPLOYMENT_CHECKLIST) end-to-end. Blocking items must be resolved before go-live.

Confirm environment variables against [ENVIRONMENT_VARIABLES](ENVIRONMENT_VARIABLES) and the architecture in [DEPLOYMENT](DEPLOYMENT).

### 2. Deploy

Follow [DEPLOYMENT](DEPLOYMENT) for frontend (Amplify) and backend (Elastic Beanstalk) order, migrations, and health endpoints.

### 3. Post-deploy verification

Complete [POST_DEPLOYMENT_CHECKLIST](POST_DEPLOYMENT_CHECKLIST).

### 4. Smoke (15–30 minutes)

Run [SMOKE_TEST_PLAN](SMOKE_TEST_PLAN). Failures → stop and consult [TROUBLESHOOTING](TROUBLESHOOTING); escalate to [ROLLBACK](ROLLBACK) if the release is worse than previous.

### 5. Steady-state handoff

- Day-to-day monitoring: [OPERATIONS_RUNBOOK](OPERATIONS_RUNBOOK)
- Admin operating surface for owners: [Owner Pack — Quick Start](../owner-pack/02-quick-start) and [Daily Operations](../owner-pack/11-daily-operations)

## Rollback decision points

| Signal | Action |
| --- | --- |
| Health endpoints fail after deploy | [TROUBLESHOOTING](TROUBLESHOOTING) then [ROLLBACK](ROLLBACK) |
| Smoke critical path fails widely | [ROLLBACK](ROLLBACK); do not mark launch successful |
| Partial non-blocking issues | Document in ops notes; fix-forward if prior version was worse |

## Related index

Full registry: [DOCUMENTATION_INDEX](DOCUMENTATION_INDEX).
