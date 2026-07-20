---
title: Deployment
description: Deployment guide for the Town Ruins platform, covering architecture, build process, environment variables, Prisma migrations, DNS, and health checks.
tags:
  - deployment
  - devops
  - infrastructure
  - amplify
  - elastic-beanstalk
aliases:
  - Deploy
  - Infrastructure
---

# Deployment

## Last Verified

Last Verified: 2026-07-20

Branch context: awsfullmig

## Purpose

Use this guide to perform a safe deployment of the Town Ruins frontend and backend. Follow each step in order. Do not skip the verification steps, because a frontend build, a backend deploy, and the URL/configuration handoff all need to be validated together.

## Related Documents

- [Environment Variables](ENVIRONMENT_VARIABLES.md)
- [Operations Runbook](../operations/OPERATIONS_RUNBOOK.md)
- [Pre-Deployment Checklist](../operations/PRE_DEPLOYMENT_CHECKLIST.md)
- [Post-Deployment Checklist](../operations/POST_DEPLOYMENT_CHECKLIST.md)

## Prerequisites

Before beginning, confirm the following:

1. The target branch and commit hash are known.
2. The frontend and backend repositories are accessible.
3. The production environment variables are reviewed and approved.
4. The deployment window is open and a rollback plan is ready.

## Deployment Sequence

### 1. Prepare the release

1. Review the pre-deployment checklist and resolve every blocking item.
2. Confirm the frontend build configuration in [amplify.yml](../../amplify.yml).
3. Confirm the backend service configuration in [real-app-backend-main/render.yaml](../../real-app-backend-main/render.yaml).
4. Verify that the correct environment variables are already configured for the target environment.
5. Record the release version and the person approving the deployment.

### 2. Deploy the backend first

1. Open the backend deployment service for the target environment.
2. Confirm the service is healthy before deploying.
3. Trigger the backend deployment from the approved commit or branch.
4. Wait for the deployment to finish and confirm the service reaches a healthy state.
5. Verify the backend health endpoint responds successfully.

Example verification commands:

```bash
curl -sS https://<backend-url>/api/health
curl -sS https://<backend-url>/api/v1
```

Expected result:
- The endpoint returns a successful response.
- No startup, migration, or dependency errors are visible in the logs.

### 3. Deploy the frontend second

1. Open the Amplify console or deployment pipeline for the frontend.
2. Confirm the branch or commit selected for deployment is correct.
3. Start the frontend deployment.
4. Wait for the build to complete and verify the deploy status changes to successful.
5. Confirm the deployed frontend URL is reachable.

Example verification commands:

```bash
curl -I https://<frontend-url>
```

### 4. Validate the frontend-to-backend connection

1. Open the deployed frontend in a browser.
2. Attempt a sign-in flow.
3. Confirm the frontend can reach the backend without CORS or URL mismatch issues.
4. Verify that any API URL values in the frontend configuration match the deployed backend URL.

If the frontend cannot reach the backend, fix the URL or environment configuration before continuing.

### 5. Apply or verify DNS and domain routing

1. Confirm the production domain points to the correct frontend host.
2. Confirm the backend is reachable through the intended public URL, if applicable.
3. Review any custom domain, CNAME, or alias records before declaring deployment complete.
4. If DNS changes were required, wait for the changes to propagate before final verification.

### 6. Run post-deployment verification

1. Verify the application loads without rendering errors.
2. Run a login test.
3. Run a listing creation or booking test.
4. Check file uploads and any notification path.
5. Review admin and moderation actions.
6. Mark the deployment successful only after all critical checks pass.

## Rollback Procedure

If the deployment introduces an outage or severe regression:

1. Stop further deployments.
2. Revert to the previous known-good release.
3. Redeploy the backend first, then the frontend.
4. Re-run health and smoke checks after rollback.
5. Document the failure and the recovery action in the operations record.

## Verification Checklist

Use this checklist after each deployment:

- [ ] Backend health endpoint responds successfully.
- [ ] Frontend returns a successful HTTP response.
- [ ] Login and core flows work.
- [ ] Uploads and notifications function.
- [ ] Admin moderation actions remain available.
- [ ] DNS and domain routing are correct.

## Notes

This guide intentionally focuses on the operational deployment sequence. If a value or host is not visible in the repository, treat it as an environment-specific detail that must be verified in the live platform console before the release is marked complete.

