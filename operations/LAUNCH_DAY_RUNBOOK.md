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

# Launch Day Runbook

## Last Verified

Last Verified: 2026-07-20

Branch context: awsfullmig

## Purpose

Use this document as the launch-day execution checklist. It is written as a chronological operating procedure, not a summary. Complete each step in order and stop immediately if a go/no-go condition is not met.

## Launch Roles

- Release lead: owns the deployment and go/no-go decision.
- Operations lead: runs the deployment and confirms health.
- QA: performs smoke validation and records issues.
- Admin or owner representative: confirms business-ready functionality after deployment.

## Launch-Day Checklist

### 1. Pre-launch confirmation (60–30 minutes before deployment)

1. Review the pre-deployment checklist and confirm every blocking item is resolved.
2. Confirm the deployment target, version, and commit hash.
3. Confirm the environment variables are present and correct.
4. Confirm DNS, domain routing, and public URLs are ready.
5. Check that monitoring channels and incident contacts are available.
6. Confirm a rollback path exists before deployment begins.

Go / no-go rule:
- Proceed only if the target environment is healthy, the release is approved, and there are no unresolved blockers.
- If a blocker remains, do not deploy.

### 2. Backend deployment

1. Open the backend deployment service.
2. Confirm the backend service is available and healthy before deployment.
3. Start the deployment from the approved version.
4. Wait for completion and verify the service health endpoint responds successfully.
5. Review logs for startup, migration, or runtime failures.

If the backend deployment fails or the health endpoint is not healthy, stop the launch and begin the rollback or remediation path.

### 3. Frontend deployment

1. Open the frontend deployment service.
2. Start the frontend deployment from the approved branch or commit.
3. Wait for the build and deploy steps to finish.
4. Confirm the deployed frontend URL is reachable.
5. Confirm the deployed frontend can reach the backend without errors.

If the frontend deployment fails, stop the launch and escalate immediately.

### 4. Post-deployment verification

1. Open the live site and confirm it loads fully.
2. Test sign-in and account access.
3. Test a listing creation path.
4. Test a booking or reservation path.
5. Test file upload and notification handling.
6. Confirm admin moderation tools remain available.

### 5. Launch decision

Make the launch decision only after the checks above are completed.

Proceed if:
- The frontend and backend are both healthy.
- Critical user journeys pass.
- No blocking errors remain in logs or monitoring.

Do not proceed if:
- The health endpoint fails.
- Sign-in or booking fails widely.
- The frontend cannot reach the backend.
- A security, payment, or data issue appears.

### 6. Handoff and steady-state

1. Inform the operations team that the launch is complete and stable.
2. Hand over the release version, deployment time, and any known caveats.
3. Leave the monitoring checklist active for the first operating shift.
4. Schedule a follow-up review if any non-blocking issues were observed.

## Rollback Criteria

Rollback immediately if:

- The backend health endpoint remains unhealthy after deployment.
- The frontend is unavailable or returns major rendering errors.
- Critical flows such as login, booking, or moderation fail for multiple users.
- Security, payments, or database integrity issues are discovered.

Rollback steps:

1. Stop further deployment activity.
2. Revert to the prior known-good release.
3. Redeploy the backend and then the frontend.
4. Re-run health and smoke checks.
5. Record the failure and rollback reason.

## Launch-Day Notes

- Keep the launch record updated in real time.
- Do not declare success based on deployment completion alone.
- Business readiness is only confirmed after operational validation is complete.
