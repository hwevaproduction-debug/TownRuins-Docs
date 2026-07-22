---
title: Operations Runbook
description: Day-to-day operational procedures, monitoring, and incident response for the Town Ruins platform.
tags:
  - operations
  - runbook
  - monitoring
  - incident-response
aliases:
  - Ops Runbook
  - Runbook
---

# Operations Runbook

## Last Verified

Last Verified: 2026-07-20

Branch context: awsfullmig

## Purpose

This runbook is the operating playbook for the Town Ruins platform. Use it for daily monitoring, release verification, incident triage, and role-based handoff. Follow the steps in order when the service is being checked or when a problem is suspected.

## Related Documents

- [Deployment](../deployment/DEPLOYMENT.md)
- [Environment Variables](../deployment/ENVIRONMENT_VARIABLES.md)
- [Launch Day Runbook](LAUNCH_DAY_RUNBOOK.md)
- [Troubleshooting](TROUBLESHOOTING.md)

## Prerequisites

- Confirm you have access to the production frontend and backend dashboards.
- Confirm the current deployment version, branch, and release owner.
- Confirm the incident communication channel is available before beginning operational checks.

## Step-by-Step Daily Operating Flow

### 1. Start of shift

1. Open the deployment dashboard and note the current frontend and backend versions.
2. Record the current date, time, and the person responsible for the shift.
3. Confirm whether any release, migration, or rollback action is in progress.
4. If a deployment is active, pause routine checks until the deploy completes.

### 2. Verify service health

Run these checks from a shell or terminal that can reach the production URLs:

```bash
curl -I https://<frontend-url>
curl -sS https://<backend-url>/api/health
```

Expected outcome:
- The frontend responds with an HTTP success code.
- The backend health endpoint returns a healthy status or JSON payload.

If either command fails, move immediately to the incident response section below.

### 3. Verify core user journeys

Perform the following checks in the live environment, one by one:

1. Sign in with a test account or admin account.
2. Complete the email or phone verification flow, if applicable.
3. Create or edit a listing.
4. Submit a booking request or reservation flow.
5. Upload an image or document.
6. Confirm a moderation or admin action can be completed.

Record each result as:
- Passed
- Failed
- Not tested

### 4. Review operational queues

1. Review pending verification requests.
2. Review flagged listings or moderation reports.
3. Check whether booking, upload, or notification activity is abnormal.
4. Confirm that admin actions are visible and that the dashboard is not stuck in a loading state.

### 5. Review background jobs and integrations

1. Confirm that upload processing is still completing.
2. Confirm notifications are not accumulating in a failed queue.
3. Review any provider or payment callback failures if they occurred during the shift.
4. If a background job is failing, capture the timestamp, affected flow, and relevant error text.

### 6. End-of-shift handoff

Before handing off:

1. Summarize what was checked and what passed.
2. Note any warnings, degraded behavior, or unresolved alerts.
3. Record the next action required for the next shift.
4. If an incident remains open, leave the incident summary with the next responder.

## Incident Response Procedure

### 1. Triage the issue

1. Confirm the symptom clearly: frontend outage, backend failure, login failure, upload failure, payment issue, or moderation failure.
2. Identify the affected surface area:
   - Frontend only
   - Backend API only
   - Database connectivity
   - Integrations such as file storage, email, or payments
3. Check whether the issue started after a deployment or a configuration change.
4. Capture the first observation, timestamp, and any user impact.

### 2. Immediate actions

If the frontend is failing:
1. Verify the Amplify deployment status.
2. Confirm the frontend environment variables are present and valid.
3. Check whether the API URL points to the correct backend endpoint.

If the backend is failing:
1. Confirm the Render service is running and not in a failed deployment state.
2. Check the runtime logs for startup, migration, or connection errors.
3. Review the backend environment variables for missing or malformed values.

If the database is failing:
1. Confirm the database connection string is present and valid.
2. Check whether a migration is pending or failed.
3. Stop any new deployment work until the database issue is resolved.

If the issue affects payments or notifications:
1. Confirm the provider credentials and callback URLs are present.
2. Check the service status page for the third-party provider if available.
3. Notify the appropriate owner if the issue is external to the platform.

### 3. Contain and recover

1. If the issue is clearly introduced by a bad release, pause further changes and prepare for rollback.
2. If the issue is caused by a configuration error, correct the values and redeploy only after confirming the change.
3. If the problem is transient, retry the health check after a short interval before attempting a rollback.
4. Record the recovery decision and the reason for it.

### 4. Communication and evidence

1. Post the incident summary in the internal operations channel.
2. Include the affected service, the current symptom, the time it started, and the current status.
3. Attach any relevant screenshots, log snippets, or command output.
4. Keep the incident record updated until the service is fully stable.

## Monitoring Checklist

Use this checklist during each shift:

- [ ] Frontend responds to an HTTP request.
- [ ] Backend health endpoint responds successfully.
- [ ] Sign-in and verification flows work.
- [ ] Listing creation and booking flows work.
- [ ] Uploads and notification flows work.
- [ ] Admin moderation tools are available.
- [ ] No new deployment or rollback is pending.

## Escalation Criteria

Escalate to the engineering lead or release owner if:

- The service is unavailable or partially unavailable.
- Two or more critical flows fail at once.
- A suspected security, data, or payment issue is detected.
- The issue cannot be resolved within the current shift.

## Related Operational Documents

- [Deployment](../deployment/DEPLOYMENT.md)
- [Environment Variables](../deployment/ENVIRONMENT_VARIABLES.md)
- [Launch Day Runbook](LAUNCH_DAY_RUNBOOK.md)
- [Troubleshooting](TROUBLESHOOTING.md)

