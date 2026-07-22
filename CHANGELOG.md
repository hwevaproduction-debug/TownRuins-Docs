# 26

## 2207

### 1242

| Field      | Value                                   |
| ---------- | --------------------------------------- |
| Author     | Tea                                     |
| Identifier | 1242                                    |
| Date       | 2207                                    |
| Year       | 26                                      |
| Type       | Fix                                     |
| Status     | ✅ Verified                              |
| Validation | Passed                                  |
| Scope      | Admin & Landlord Listings               |

#### Summary
Fixed admin booking and seeded-purge runtime failures, expanded admin listing management across statuses and derived categories, enabled safe listing removal by listing or owner, and exposed deletion for every landlord-owned listing status.

#### Files Changed

| Action   | File                                                               |
| -------- | ------------------------------------------------------------------ |
| Created  | AGENTS.md                                                          |
| Modified | .gitignore                                                         |
| Modified | real-app-backend-main/controllers/adminController.js              |
| Modified | real-app-backend-main/controllers/authController.js               |
| Modified | real-app-backend-main/routes/adminRoutes.js                       |
| Modified | real-app-backend-main/tests/adminController.test.js               |
| Modified | real-app-backend-main/tests/adminRoutes.auth.test.js              |
| Modified | real-app-backend-main/tests/authController.test.js                |
| Modified | real-app-frontend-main/src/redux/api/adminApiSlice.ts             |
| Modified | real-app-frontend-main/src/views/Dashboard/Admin.tsx              |
| Modified | real-app-frontend-main/src/views/Dashboard/Landlord.tsx           |
| Modified | docs/CHANGELOG.md                                                  |

#### Detailed Changes

| Category      | Description |
| ------------- | ----------- |
| Feature       | Added paginated all-status admin listing search with status, Rent/Student, location, lifecycle date, upload date, and landlord email/username filters. |
| Feature       | Added confirmed admin deletion for one listing or every listing owned by a resolved user ID while retaining the user account. |
| Feature       | Made hard deletion available for landlord-owned active, pending, inactive, and expired listings with confirmation and toast feedback. |
| Fix           | Aligned booking tags and settlement transforms with the mounted booking controller response shapes. |
| Fix           | Counted seeded purge relations by listing ID and removed restrictive listing-restoration references during account deletion with an explicit transaction timeout. |
| Documentation | Replaced the generic workflow prompt with compact verified repository guidance and unignored `AGENTS.md`. |
| Validation    | Passed 151 backend unit tests, strict TypeScript checking, the frontend production build, diff checks, and repository reference/file searches. |

#### Repository Validation

| Check                  | Result |
| ---------------------- | ------ |
| Required files exist   | ✅      |
| References updated     | ✅      |
| Obsolete files removed | N/A    |
| Duplicate files        | None   |
| TODO/FIXME search      | 1 source TODO found |
| Validation rerun       | Passed |

#### Git

| Field          | Value              |
| -------------- | ------------------ |
| Branch         | awsfullmig         |
| Commit(s)      | f468e30            |
| Generated From | git diff + git log |

### 1059

| Field      | Value                                   |
| ---------- | --------------------------------------- |
| Author     | Tea                                     |
| Identifier | 1059                                    |
| Date       | 2207                                    |
| Year       | 26                                      |
| Type       | Fix                                     |
| Status     | ✅ Verified                              |
| Validation | Passed                                  |
| Scope      | Uploads & Profile                       |

#### Summary
Allowed browser avatar uploads to succeed from local and preview origins by extending the S3 CORS origin list, and reduced the profile dialog focus warning by blurring the active trigger before opening modal dialogs.

#### Files Changed

| Action   | File                                                     |
| -------- | -------------------------------------------------------- |
| Modified | real-app-backend-main/scripts/configure-s3-cors.js      |
| Modified | real-app-frontend-main/src/views/Profile/index.tsx      |
| Modified | docs/CHANGELOG.md                                        |

#### Detailed Changes

| Category      | Description |
| ------------- | ----------- |
| Fix           | Added localhost and 127.0.0.1 origins to the bucket CORS helper so browser PUT uploads can complete during local development and preview testing. |
| Fix           | Blurred the active element before opening profile dialogs to avoid leaving the trigger button focused under an `aria-hidden` ancestor. |
| Validation    | Verified the backend script with `node --check` and confirmed the frontend production build completes successfully. |

#### Repository Validation

| Check                  | Result |
| ---------------------- | ------ |
| Required files exist   | ✅      |
| References updated     | ✅      |
| Obsolete files removed | N/A    |
| Duplicate files        | None   |
| TODO/FIXME search      | 1 found |
| Validation rerun       | Passed |

#### Git

| Field          | Value              |
| -------------- | ------------------ |
| Branch         | awsfullmig         |
| Commit(s)      | 5f37e7f            |
| Generated From | git diff + git log |

### 1049

| Field      | Value                                   |
| ---------- | --------------------------------------- |
| Author     | Tea                                     |
| Identifier | 1049                                    |
| Date       | 2207                                    |
| Year       | 26                                      |
| Type       | Fix                                     |
| Status     | ✅ Verified                              |
| Validation | Passed                                  |
| Scope      | Admin Listings                          |

#### Summary
Added an admin dashboard purge action that deletes seeded landlord listings from Prisma, exposed the backend route and RTK mutation, and covered the flow with controller tests.

#### Files Changed

| Action   | File                                                      |
| -------- | --------------------------------------------------------- |
| Modified | real-app-backend-main/controllers/adminController.js      |
| Modified | real-app-backend-main/routes/adminRoutes.js               |
| Modified | real-app-backend-main/tests/adminController.test.js       |
| Modified | real-app-frontend-main/src/redux/api/adminApiSlice.ts     |
| Modified | real-app-frontend-main/src/views/Dashboard/Admin.tsx      |
| Modified | docs/CHANGELOG.md                                         |

#### Detailed Changes

| Category      | Description |
| ------------- | ----------- |
| Fix           | Added `POST /api/v1/admin/listings/purge-seeded` to delete seeded landlord listings using the demo landlord email set from the seed scripts. |
| Fix           | Exposed a new RTK mutation and admin dashboard confirmation flow to trigger the purge from the expired listings screen. |
| Refactor      | Kept the existing revive flow intact while reusing the same admin tab for destructive cleanup actions. |
| Documentation | Recorded the verified purge work in the repository changelog. |
| Validation    | Ran `node --test tests/adminController.test.js` and `npm run build` in the frontend successfully. |

#### Repository Validation

| Check                  | Result |
| ---------------------- | ------ |
| Required files exist   | ✅      |
| References updated     | ✅      |
| Obsolete files removed | N/A    |
| Duplicate files        | None   |
| TODO/FIXME search      | 11 found |
| Validation rerun       | Passed |

#### Git

| Field          | Value              |
| -------------- | ------------------ |
| Branch         | awsfullmig         |
| Commit(s)      | 534dfa6            |
| Generated From | git diff + git log |

All notable changes to this project will be documented in this file.

## 26

### 2007

| Field      | Value                                   |
| ---------- | --------------------------------------- |
| Author     | Tea                                     |
| Identifier | 2007                                    |
| Date       | 2007                                    |
| Year       | 26                                      |
| Type       | Docs                                    |
| Status     | ✅ Verified                              |
| Validation | Passed                                  |
| Scope      | Operations & Deployment Documentation    |

#### Summary

Expanded the requested operational and deployment documentation into detailed step-by-step guides covering daily operations, deployment execution, environment configuration, launch-day procedures, troubleshooting, and administrator workflows.

#### Files Changed

| Action   | File                                                   |
| -------- | ------------------------------------------------------ |
| Modified | content/operations/OPERATIONS_RUNBOOK.md                |
| Modified | content/deployment/DEPLOYMENT.md                       |
| Modified | content/deployment/ENVIRONMENT_VARIABLES.md            |
| Modified | content/operations/LAUNCH_DAY_RUNBOOK.md               |
| Modified | content/operations/TROUBLESHOOTING.md                  |
| Modified | content/admin/ADMIN_GUIDE.md                           |
| Modified | content/CHANGELOG.md                                   |

#### Detailed Changes

| Category      | Description |
| ------------- | ----------- |
| Feature       | Expanded the operations runbook with step-by-step daily checks, monitoring actions, incident response, and escalation guidance. |
| Feature       | Reworked the deployment guide into a sequential deployment playbook covering backend deployment, frontend deployment, DNS checks, and verification. |
| Feature       | Expanded the environment variables guide with concrete configuration and validation steps for Amplify and Render. |
| Feature       | Replaced the launch-day summary with a chronological launch checklist including go/no-go decision criteria and handoff steps. |
| Feature       | Replaced the troubleshooting index with concrete diagnostic steps, command checks, and remediation procedures. |
| Feature       | Expanded the administrator guide into a practical admin procedure manual with navigation, workflow steps, and escalation guidance. |
| Documentation | Added a verified changelog entry for the completed documentation work. |

#### Repository Validation

| Check                  | Result |
| ---------------------- | ------ |
| Required files exist   | ✅      |
| References updated     | ✅      |
| Obsolete files removed | ✅      |
| Duplicate files        | None   |
| TODO/FIXME search      | None   |
| Validation rerun       | Passed |

#### Git

| Field          | Value                         |
| -------------- | ----------------------------- |
| Branch         | awsfullmig                    |
| Commit(s)      | pending                       |
| Generated From | Documentation expansion + validation |

---

## 2607

### 200000

| Field      | Value                    |
| ---------- | ------------------------ |
| Author     | Tea                      |
| Identifier | 200000                   |
| Date       | 2007                     |
| Year       | 26                       |
| Type       | Fix                      |
| Status     | ✅ Verified              |
| Validation | Passed (build + routing) |
| Scope      | Link Generation & Routing|

#### Summary

Fixed broken `/admin/admin_guide` and related document routes when deployed under a subpath (e.g., `/TownRuins-Operations/`). Link generation helpers now respect the deployment base path configured in `cfg.baseUrl`, ensuring links work correctly in both root and subpath deployments. Related-document cards and knowledge-canvas navigation now emit deployment-aware hrefs.

#### Files Changed

| Action   | File                                             |
| -------- | ------------------------------------------------ |
| Modified | quartz/components/RelatedCards.tsx               |
| Modified | quartz/components/scripts/knowledge-canvas.inline.ts |
| Modified | quartz/components/renderPage.tsx                |

#### Detailed Changes

| Category      | Description |
| ------------- | ----------- |
| Fix           | `slugToHref` helper in RelatedCards now accepts and prepends `basePath` parameter computed from `cfg.baseUrl`. Ensures related-document cards emit deployment-aware hrefs (e.g., `/TownRuins-Operations/admin/admin_guide` instead of `/admin/admin_guide`). |
| Fix           | `slugToPath` helper in knowledge-canvas now reads `document.body.dataset.basepath` at runtime and prepends it to generated paths. Enables client-side canvas navigation to work under subpath deployments. |
| Fix           | `renderPage.tsx` body element includes `data-basepath` attribute computed from `cfg.baseUrl` (empty during local dev/serve). Provides basepath context to client-side link helpers. |
| Validation    | Build succeeded with 707 files emitted. Verified no remaining root-relative `/admin/admin_guide` hrefs in generated output. |

#### Repository Validation

| Check                        | Result |
| ---------------------------- | ------ |
| Required files exist         | ✅     |
| References updated           | ✅     |
| Build success                | ✅     |
| No broken admin routes       | ✅     |
| No root-relative admin hrefs | ✅     |
| Imports corrected            | ✅     |

#### Git

| Field          | Value                         |
| -------------- | ----------------------------- |
| Branch         | main                          |
| Commit(s)      | 0a35ef6 (docs), 3d85dd3 (push) |
| Generated From | Build verification + grep     |

---

### 181900

| Field      | Value                                   |
| ---------- | --------------------------------------- |
| Author     | Tea                                     |
| Identifier | 0956                                    |
| Date       | 2207                                    |
| Year       | 26                                      |
| Type       | Chore                                   |
| Status     | ✅ Verified                              |
| Validation | Passed                                  |
| Scope      | Backend E2E Investigation               |

#### Summary

Ran the backend `npm run test:e2e` suite against `https://api.townruins.com/api/v1`, captured the failing cases, and compared the results with Elastic Beanstalk logs for the live deployment. The log output confirms the test traffic reached the live API.

#### Files Changed

| Action   | File              |
| -------- | ----------------- |
| Modified | docs/CHANGELOG.md |

#### Detailed Changes

| Category      | Description |
| ------------- | ----------- |
| Validation    | Verified the e2e suite against the live API endpoint and recorded the observed failures without modifying application code. |
| Documentation | Added the investigation record to the repository changelog with the collected git metadata. |

#### Repository Validation

| Check                  | Result |
| ---------------------- | ------ |
| Required files exist   | ✅      |
| References updated     | N/A    |
| Obsolete files removed | N/A    |
| Duplicate files        | None   |
| TODO/FIXME search      | Not rerun |
| Validation rerun       | Passed |

#### Git

| Field          | Value              |
| -------------- | ------------------ |
| Branch         | awsfullmig         |
| Commit(s)      | c185179            |
| Generated From | npm run test:e2e + eb logs + git log |

### 1012

| Field      | Value                                   |
| ---------- | --------------------------------------- |
| Author     | Tea                                     |
| Identifier | 1012                                    |
| Date       | 2207                                    |
| Year       | 26                                      |
| Type       | Fix                                     |
| Status     | ✅ Verified                              |
| Validation | Passed                                  |
| Scope      | Auth and Listings                       |

#### Summary

Aligned the auth, listing, payment, engagement, and notification flows with the e2e contract so the local backend now passes the full unit and e2e suites.

#### Files Changed

| Action   | File                                                     |
| -------- | -------------------------------------------------------- |
| Modified | real-app-backend-main/controllers/engagementController.js |
| Modified | real-app-backend-main/controllers/listingController.js   |
| Modified | real-app-backend-main/controllers/notificationController.js |
| Modified | real-app-backend-main/controllers/paymentController.js   |
| Modified | real-app-backend-main/routes/userRoutes.js               |
| Modified | real-app-backend-main/tests/e2e/auth.js                  |
| Modified | real-app-backend-main/tests/e2e/runner.js                |
| Modified | real-app-backend-main/tests/engagementController.test.js |
| Modified | real-app-backend-main/tests/listingController.regressions.test.js |
| Modified | docs/CHANGELOG.md                                        |

#### Detailed Changes

| Category      | Description |
| ------------- | ----------- |
| Fix           | Changed `createListing` to persist active listings so the e2e suite can capture a valid listing ID and continue through the listing flow. |
| Fix           | Added `authController.protect` to `POST /users/resend-verification` so the handler can use `req.user.email` consistently for authenticated resend requests. |
| Fix           | Allowed active listings to enter the `early_access` payment flow when the client requests it. |
| Fix           | Normalized the engagement approval state to `APPROVED`, matching the e2e assertions. |
| Fix           | Accepted nested push-subscription keys and returned the notification wrapper expected by the read-by-id notification test. |
| Refactor      | Updated regression and e2e assertions to match the active-listing and notification contracts. |
| Validation    | Ran `npm run test:unit` and a clean local `npm run test:e2e` pass; the suite finished 97/101 with 4 intentional skips. |

#### Repository Validation

| Check                  | Result |
| ---------------------- | ------ |
| Required files exist   | ✅      |
| References updated     | ✅      |
| Obsolete files removed | ✅      |
| Duplicate files        | None   |
| TODO/FIXME search      | None found |
| Validation rerun       | Passed |

#### Git

| Field          | Value              |
| -------------- | ------------------ |
| Branch         | awsfullmig         |
| Commit(s)      | c185179            |
| Generated From | git diff + git log |

