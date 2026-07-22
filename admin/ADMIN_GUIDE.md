---
title: Administrator Guide
description: Administrator guide for platform management and moderation on the Town Ruins platform.
tags:
  - admin-guide
  - administrator
  - platform-management
aliases:
  - Admin Guide
  - Administration
---

# Administrator Guide

## Last Verified

Last Verified: 2026-07-20

Branch context: awsfullmig

## Purpose

This guide is the operational manual for administrators. Use it to review accounts, manage listings and reports, verify providers, and handle day-to-day moderation work. Follow the procedures in order when action is required.

## Related Documents

- [Moderator Guide](../moderation/MODERATOR_GUIDE.md)
- [Landlord Guide](../guides/LANDLORD_GUIDE.md)
- [End User Guide](../guides/END_USER_GUIDE.md)
- [Operations Runbook](../operations/OPERATIONS_RUNBOOK.md)

## Prerequisites

Before using the admin tools, confirm:

1. You have administrator access to the admin dashboard.
2. You can see the moderation queue, verification queue, and account review tools.
3. You can access the relevant support or incident channel when an urgent case is identified.

## Admin Dashboard Navigation

Use the following sequence when entering the admin area:

1. Open the admin dashboard from the main application navigation.
2. Select the relevant module:
   - Dashboard overview
   - Verification requests
   - Flagged listings or reports
   - User or provider management
3. Review the queue and sort items by newest, oldest, or severity as needed.
4. Open each case and take the appropriate administrative action.

## Daily Administrator Workflow

### 1. Review the dashboard

1. Open the admin console.
2. Review the overview metrics or queue counts.
3. Note any unusual spikes in verification requests, flags, or reports.
4. Prioritize high-severity items first.

### 2. Review verification requests

1. Open the verification queue.
2. Review each request in order.
3. Approve or reject the request based on the submitted evidence.
4. Leave a note if additional information is required.
5. If a request is incomplete, return it for clarification rather than approving it by mistake.

### 3. Review flagged listings or reports

1. Open the moderation queue.
2. Review the reported listing, account, or message.
3. Confirm whether the issue is spam, inappropriate content, fraud, or policy violation.
4. Apply the correct action:
   - Remove the listing
   - Warn the user
   - Suspend the account
   - Escalate to a higher-level moderator or owner
5. Record the decision and reason clearly.

### 4. Review user and provider accounts

1. Open the account review area.
2. Review tenant, landlord, or provider activity where relevant.
3. Confirm account details are consistent with the submitted identity or business information.
4. Restrict or restore access only when a clear policy basis exists.
5. If a fraud or abuse pattern is observed, escalate the issue promptly.

### 5. Monitor operational issues

1. Review whether any admin action has failed or is pending.
2. Check whether verification, moderation, and listing updates are completing normally.
3. Report any recurring issue in the operations channel so it can be investigated.

## Escalation Procedure

Escalate to the operations team or engineering lead when:

- A moderation issue is severe or may affect multiple users.
- A fraud, abuse, or policy violation appears coordinated or repeated.
- An admin action cannot be completed because the dashboard or backend is failing.
- A payment, verification, or authentication issue affects admin functions.

## Administrative Actions Checklist

Use this checklist for each case:

- [ ] Confirm the case is the correct one.
- [ ] Review the evidence or report.
- [ ] Choose the correct action.
- [ ] Apply the action in the admin system.
- [ ] Record the reason and outcome.
- [ ] Notify the relevant party if required.

## Notes

Administrators should not make changes based only on a single incomplete report. Always verify the evidence available in the admin console before applying a restriction, removal, or approval decision.
