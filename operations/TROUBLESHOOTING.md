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

# Troubleshooting

## Last Verified

Last Verified: 2026-07-20

Branch context: awsfullmig

## Purpose

Use this document when a service issue is already occurring. It provides step-by-step diagnostic actions and remediation steps that can be followed without needing to jump between multiple documents.

## First Response Procedure

### 1. Confirm the symptom

1. Identify the affected area: frontend, backend, login, uploads, booking, moderation, or payments.
2. Record the time the issue started and whether it affects one user or many users.
3. Check whether the problem began during or after a deployment.
4. Note whether the issue is intermittent or continuous.

### 2. Run basic health checks

Run the following checks in order:

```bash
curl -I https://<frontend-url>
curl -sS https://<backend-url>/api/health
```

Interpretation:
- If the frontend fails but the backend responds, the issue is likely frontend or configuration-related.
- If both fail, inspect backend deployment status and logs.
- If the backend responds but user flows fail, inspect application-specific configuration or database connection issues.

### 3. Review backend logs

1. Open the backend runtime logs for the most recent deployment window.
2. Look for startup failures, migration errors, authentication failures, and database connection errors.
3. Note the first error message and the timestamp.
4. If the logs show missing environment values, check the deployment environment settings immediately.

### 4. Review frontend behavior

1. Open the deployed site and verify whether it renders fully or throws a runtime error.
2. Try a basic login flow.
3. If the page loads but API calls fail, verify the frontend API URL and backend URL configuration.
4. If the frontend is blank or crashing, check the latest deployment logs and the environment variables for the frontend build.

## Common Failure Scenarios

### Frontend is unavailable

1. Check whether the frontend build finished successfully.
2. Confirm the frontend URL is correct and active.
3. Verify the environment variables for the frontend are present.
4. If the deploy was recent, compare it to the previous known-good version.
5. If the issue persists, rollback to the previous release.

### Backend is unhealthy

1. Confirm the backend deployment is healthy and not still in progress.
2. Check runtime logs for migration, dependency, or secret issues.
3. Confirm the database connection string and required secrets are present.
4. If the service is unhealthy after a deployment, rollback the release.

### Login or authentication failures

1. Confirm the frontend and backend URLs are aligned.
2. Review the authentication secrets and token configuration.
3. Check whether the deployment introduced a bad secret or invalid environment value.
4. Re-validate the environment settings and redeploy if a misconfiguration is found.

### Upload failures

1. Confirm the storage bucket, region, and public URL values are set.
2. Verify the storage service is reachable and the bucket exists.
3. Check whether uploads fail due to missing credentials or invalid bucket configuration.
4. Correct the values in the platform settings and redeploy when necessary.

### Payment or callback failures

1. Confirm the provider name and callback URL values are configured.
2. Verify the return URL is correct and reachable.
3. Check provider logs or status pages if available.
4. If the issue is external, inform the appropriate owner and continue monitoring.

## Remediation Flow

1. If the issue is caused by a bad deployment, stop further changes and revert to the last known-good release.
2. If the issue is caused by a bad environment value, correct the environment setting and redeploy.
3. If the issue is caused by an external provider, notify the responsible owner and continue monitoring.
4. If the issue cannot be resolved quickly, escalate to the engineering lead.

## Escalation Criteria

Escalate if:

- Multiple user-facing flows are failing at once.
- The problem affects payments, authentication, or data integrity.
- The issue remains unresolved after the basic checks and remediation steps.
- The incident appears to be caused by a release or broken configuration that cannot be safely corrected in place.

## Related Documents

- [Operations Runbook](OPERATIONS_RUNBOOK.md)
- [Launch Day Runbook](LAUNCH_DAY_RUNBOOK.md)
- [Deployment](../deployment/DEPLOYMENT.md)
- [Environment Variables](../deployment/ENVIRONMENT_VARIABLES.md)
