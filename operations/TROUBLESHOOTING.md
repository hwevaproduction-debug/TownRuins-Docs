---
title: Troubleshooting
description: Symptom-oriented troubleshooting entry points for Town Ruins ops — collated from existing runbooks and admin guides (no invented procedures).
tags:
  - operations
  - troubleshooting
  - incident-response
aliases:
  - Ops Troubleshooting
  - Diagnostics
---

# TROUBLESHOOTING.md — Symptom Entry Points

> **Policy:** This page is a **portal index** into verified docs already in this content tree. It does not invent product SLAs, hostnames, or unshipped admin UI.

## First response

| Symptom class | Start here |
| --- | --- |
| Deploy or health check failed | [POST_DEPLOYMENT_CHECKLIST](POST_DEPLOYMENT_CHECKLIST) → [DEPLOYMENT](DEPLOYMENT) § Health Verification |
| Need fast critical-path check | [SMOKE_TEST_PLAN](SMOKE_TEST_PLAN) |
| Day-to-day ops / monitoring scope | [OPERATIONS_RUNBOOK](OPERATIONS_RUNBOOK) |
| Admin / payment / outage playbooks | [Admin Guide — Incident Response](../guides/admin_guide#incident-response) |
| Rollback decision | [ROLLBACK](ROLLBACK) |
| Env / config suspicion | [ENVIRONMENT_VARIABLES](ENVIRONMENT_VARIABLES) |

## Platform outage (from Admin Guide)

Summarized from [guides/ADMIN_GUIDE](../guides/admin_guide#incident-response) — use the full section for detail:

1. Check backend health: `GET /api/v1` should return `{ status: "ok" }`.
2. Check database connectivity (Prisma connection errors in logs).
3. Check background jobs are running (expiry scanner, reconciliation).
4. Check payment provider status pages.
5. Notify users via email if outage exceeds 30 minutes (per that guide).

## Payment / reconciliation issues

See [guides/ADMIN_GUIDE](../guides/admin_guide) payment and incident sections, and confirm provider configuration via [ENVIRONMENT_VARIABLES](ENVIRONMENT_VARIABLES).

## Deploy-time failures

| Area | Document |
| --- | --- |
| EB / Amplify deploy steps | [DEPLOYMENT](DEPLOYMENT) |
| Pre-flight gates | [PRE_DEPLOYMENT_CHECKLIST](PRE_DEPLOYMENT_CHECKLIST) |
| After deploy verification | [POST_DEPLOYMENT_CHECKLIST](POST_DEPLOYMENT_CHECKLIST) |
| Version revert | [ROLLBACK](ROLLBACK) |

## Owner-facing product issues

For non-infrastructure owner staff issues (login, moderation, bookings), use the Owner Pack:

- [Owner Pack — Troubleshooting](../owner-pack/09-troubleshooting)
- [Owner Pack — FAQ](../owner-pack/08-faq)
- Support contact documented in [Owner Pack — Support & Warranty](../owner-pack/14-support-and-warranty)

## Known limit

A full standalone multi-hundred-line symptoms matrix from an external monorepo path is **not** duplicated here. When a concrete failure mode is verified in production, add a dated row to this page or to [OPERATIONS_RUNBOOK](OPERATIONS_RUNBOOK) rather than inventing untested steps.

## Related

- [DOCUMENTATION_INDEX](DOCUMENTATION_INDEX)
- [LAUNCH_DAY_RUNBOOK](LAUNCH_DAY_RUNBOOK)
- [ADMIN_RUNBOOK](admin_runbook)
