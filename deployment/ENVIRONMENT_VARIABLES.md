# Environment Variables

## Last Verified

Last Verified: 2026-07-20

Branch context: awsfullmig

## Purpose

Use this guide to configure environment variables for the Town Ruins deployment correctly. The values must be set in the right place for the frontend and backend services, and each value should be validated before deployment.

## Related Documents

- [Deployment](DEPLOYMENT.md)
- [Operations Runbook](../operations/OPERATIONS_RUNBOOK.md)
- [Pre-Deployment Checklist](../operations/PRE_DEPLOYMENT_CHECKLIST.md)

## Prerequisites

- Review [real-app-backend-main/.env.example](../../real-app-backend-main/.env.example)
- Review [amplify.yml](../../amplify.yml)
- Review [real-app-backend-main/render.yaml](../../real-app-backend-main/render.yaml)

## Configuration Workflow

### 1. Identify the target platform

Determine whether the value belongs to:

- The frontend application hosted through Amplify
- The backend application hosted through Render
- A shared or platform-level service such as AWS or a payment provider

Set the value in the platform console or deployment interface that actually runs that service. Do not set a frontend variable only in the backend service, or vice versa.

### 2. Set frontend values in Amplify

In the Amplify environment settings, configure the frontend variables below:

- REACT_APP_API_URL — The public URL of the backend API.
- REACT_APP_BACKEND_URL — The public backend base URL used by the frontend.
- REACT_APP_FIREBASE_API_KEY — Only set if the frontend uses Firebase authentication.
- REACT_APP_TOKEN_PAYER_ROLE — Only set when the payment or token behavior is feature-flagged.
- REACT_APP_LISTING_FEE_AMOUNT — Only set when the listing fee amount must differ per environment.
- REACT_APP_TENANT_PREMIUM_AMOUNT — Only set when tenant premium pricing varies by environment.

Step-by-step:

1. Open the Amplify app environment settings.
2. Select the target environment.
3. Add or update each variable with the production-safe value.
4. Save the changes.
5. Trigger a new frontend deployment so the new values are applied.

### 3. Set backend values in Render

In the Render service environment settings, configure the backend variables below:

- DATABASE_URL — The production database connection string.
- JWT_SECRET — A secure secret used for token signing.
- JWT_EXPIRES_IN — Token lifetime setting.
- FRONTEND_URL — The public frontend URL used by callbacks and CORS.
- PAYNOW_RETURN_URL — The callback URL used by the payment provider.
- PAYMENT_PROVIDER — The selected provider name.
- TOKEN_PAYER_ROLE — The role used by the payment flow.
- LISTING_FEE_AMOUNT — Optional listing-fee value.
- TENANT_PREMIUM_AMOUNT — Optional tenant premium value.
- S3_BUCKET — Storage bucket name for uploads.
- S3_REGION — Storage region for uploads.
- S3_PUBLIC_BASE_URL — Public base URL for uploaded assets.
- EMAIL_FROM — Sender address for outgoing mail.
- GMAIL_USER — Mail account username if applicable.
- GMAIL_APP_PASSWORD — Mail account password or app password.

Step-by-step:

1. Open the Render service for the backend.
2. Open the Environment section.
3. Add or update each required variable.
4. Save the environment values.
5. Redeploy the backend service after changing sensitive values.

### 4. Validate values before deployment

Before deployment, check each value carefully:

1. Confirm no placeholder text remains, such as "changeme" or "example".
2. Confirm frontend URL values use the correct public host and do not include trailing mistakes.
3. Confirm secrets are not exposed in logs or in repository files.
4. Confirm that the backend and frontend URLs are aligned with one another.
5. Confirm database and storage values point to the intended environment.

### 5. Validate after configuration changes

After the values are set:

1. Trigger or rerun the deployment.
2. Check that the frontend can reach the backend.
3. Confirm login, upload, and payment flows behave as expected.
4. If a value is wrong, correct it in the platform console and redeploy.

## Variable Summary

### Frontend / Amplify

- REACT_APP_API_URL
- REACT_APP_BACKEND_URL
- REACT_APP_FIREBASE_API_KEY
- REACT_APP_TOKEN_PAYER_ROLE
- REACT_APP_LISTING_FEE_AMOUNT
- REACT_APP_TENANT_PREMIUM_AMOUNT

### Backend / Render

- DATABASE_URL
- JWT_SECRET
- JWT_EXPIRES_IN
- FRONTEND_URL
- PAYNOW_RETURN_URL
- PAYMENT_PROVIDER
- TOKEN_PAYER_ROLE
- LISTING_FEE_AMOUNT
- TENANT_PREMIUM_AMOUNT
- S3_BUCKET / S3_REGION / S3_PUBLIC_BASE_URL
- EMAIL_FROM / GMAIL_USER / GMAIL_APP_PASSWORD

## Common Configuration Issues

- Missing frontend URL causes sign-in or API failures.
- Wrong backend URL causes CORS or callback failures.
- Missing storage variables prevents uploads from working.
- Missing payment values prevents callback or reconciliation flows from working.
- Incorrect secrets can cause authentication failures after deployment.

## Notes

This guide provides the operational steps required to configure and validate environment variables for the current deployment flow. If a value is not used by the live environment, it should not be added just because it appears in an example file.

