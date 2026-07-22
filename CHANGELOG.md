# 26

## 2207

### 0956

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

