# FAQ

| Field | Value |
| --- | --- |
| **Title** | Town Ruins Owner Pack — FAQ |
| **Audience** | Platform owners (Hweva Tech Holdings) |
| **Version** | 1.0 |
| **Product** | [https://app.townruins.com](https://app.townruins.com) |
| **Support** | [sandbox@townruins.com](mailto:sandbox@townruins.com) |
| **Related** | [09 Troubleshooting](09-Troubleshooting.md) · [03 User Manual](03-User-Manual.md) · [04 Administrator Guide](04-Administrator-Guide.md) · [14 Support and Warranty](14-Support-and-Warranty.md) |

---

## Purpose

Short answers to questions owner staff hear most often — from yourselves or from tenants, landlords, and providers you support.

- Prefer **self-service product paths** first.
- Escalate product defects to [sandbox@townruins.com](mailto:sandbox@townruins.com).
- Response times and warranty scope follow the **full-time contract** (see [14 Support and Warranty](14-Support-and-Warranty.md)).

For step-by-step procedures, use the manuals. For symptom checklists, use [09 Troubleshooting](09-Troubleshooting.md).

---

## Accounts and login

### How do I reset my password (user or admin)?

1. On the login screen at [https://app.townruins.com](https://app.townruins.com), open **Forgot password**.
2. Enter the email for that account.
3. Open the reset link from the email (check spam / promotions).
4. Set a new password and sign in.

The same self-service flow works for **public users** and **admin** accounts when email delivery is working. If staff admin reset fails and self-service is broken for that account, contact [sandbox@townruins.com](mailto:sandbox@townruins.com) under the full-time contract.

You do **not** need the developer for every forgotten password.

---

### Why can someone not log in?

Common causes, in order:

| Likely cause | What to check / tell them |
| --- | --- |
| Wrong email or password | Re-type carefully; check Caps Lock |
| Email not verified (public roles) | Complete verification email; use **resend** if needed; check spam |
| Wrong account type | Admin work requires **admin** credentials issued for ownership — not a personal tenant signup |
| Google vs password mix-up | Sign in with the same method they used at registration |
| Widespread failure | If many people fail at once, treat as product/mail issue → [sandbox@townruins.com](mailto:sandbox@townruins.com) |

Admin accounts are **not** created via public sign-up. See [Admin account creation](#how-are-admin-accounts-created) below.

---

### How are admin accounts created?

Admin accounts are created only through a **controlled seed / provision process** during setup or when ownership requests new staff access.

| Do | Do not |
| --- | --- |
| Request provisioning via [sandbox@townruins.com](mailto:sandbox@townruins.com) / developer under contract | Tell staff to “register as admin” on the public site |
| Confirm the person is authorised by Hweva Tech Holdings | Share one admin password among the team |
| Use person-specific accounts (audit logs need real names) | Expect public sign-up to produce an admin role |

There is **no** public “Create admin account” button in version 1.0.

---

## Landlords, verification, and listings

### How do I verify a landlord?

Landlords may submit **ID image + selfie** for identity verification.

1. Watch for **pending review** (admin notification and/or admin surface).
2. Review documents for legitimacy and match.
3. **Approve** or **Reject**.

| Status | Meaning |
| --- | --- |
| Unverified | Nothing submitted |
| Pending review | Waiting on owner staff |
| Approved / verified | Identity accepted |
| Rejected | Not accepted; landlord may need to resubmit |

**v1.0 honesty:** The landlord verification **admin review UI may be partial**. Document submission exists; you still own the business decision. If tooling blocks you entirely, contact support under contract. See [04 Administrator Guide](04-Administrator-Guide.md).

---

### How do I verify a provider?

Providers (short-stay hosts) are verified from the admin **Providers** section:

1. Sign in as admin → open **Providers**.
2. Find the host (search / filter by verification status when available).
3. **Approve** (verify) or **Reject**.

Approved providers can move toward full operation; related accommodations follow the moderation path. If a **super_admin** account cannot complete provider verify or commission update, use a designated **admin** account or ask support under contract.

---

### Can deleted listings be recovered?

| Action | Recoverable? |
| --- | --- |
| Landlord **deletes** a listing | Treat as **permanent removal** by the listing owner — do not promise recovery from the admin panel |
| Listing is **expired** or **inactive** | Often recoverable: landlord can **restore with TR Tokens** (1 TR × days, up to 30); admin may **bulk revive** inactive stock when policy allows |

If a user says “deleted,” confirm whether they mean delete vs expired/inactive. Only promise revive for statuses the admin tools actually restore.

---

### Why can’t a tenant contact a landlord?

Contact details stay protected until an **engagement** is approved.

| Step | What happens |
| --- | --- |
| Tenant sends a contact request (engagement) | No contact details revealed yet; **no 5 TR charge** on send |
| Landlord **approves** | Contact details unlock; **5 TR** is charged to the **tenant** |
| Landlord **declines** or ignores | Tenant cannot see contact details |

Common “cannot contact” causes:

- Engagement still **pending** or was **declined**
- Tenant has **insufficient TR balance** when approval would charge 5 TR
- User expects in-app chat — **in-platform messaging is not in v1.0**
- User is looking at a listing detail page before approval (by design)

Explain the rule clearly: **send is free; charge is on landlord approval**.

---

## Bookings, money, and tokens

### How do bookings work (money path)?

Temporary stays (hotels, lodges, BnBs) are separate from long-term rental listings.

| Domain | How money works |
| --- | --- |
| **Temporary stay bookings** | **Real money** — charges, refunds, cancellations, and settlement (exception to token-only platform features) |
| **Long-term rental contact unlock** | **TR Tokens** (5 TR on engagement approval) |
| **Listing restore** | **TR Tokens** (1 TR × days) |

Stay flow (plain language):

1. Guest finds a room and books (**instant** or **request/confirm**, depending on provider settings).
2. Guest pays via the real payment path for stays.
3. Provider confirms/declines when in request mode.
4. Stay progresses (confirmed → stay → completed).
5. Owner staff **settle** completed stays in admin with a clear settlement reference when finance requires it.

Disputes are resolved by **owner staff** in the admin disputes section. See [03 User Manual](03-User-Manual.md) and [04 Administrator Guide](04-Administrator-Guide.md).

---

### How do TR Tokens work?

TR Tokens are Town Ruins’ **in-app currency** for premium platform behaviour — not a substitute for stay room payments.

| Event | Amount | Who |
| --- | --- | --- |
| Welcome bonus (first email verification or new Google user) | **100 TR** | Credit to new user |
| Engagement approved | **5 TR** | Debit from **tenant** |
| Listing restored | **1 TR × days** (up to 30) | Debit from **landlord** |
| Token package purchase | Package sizes in product UI (e.g. 50 / 100 / 300 TR) | User — see known limit below |
| Admin promo grant | Variable | Support/technical path — **no dedicated admin grant UI** in v1.0 |

**Known limit:** Token **purchase** may be **demo-mode** in v1.0 (no real card charge until live payment is fully wired). Stay bookings remain the real-money domain. Be honest with users; do not promise live token card charges if the product path is still demo.

---

### Can I export reports?

| What you have in v1.0 | What to do |
| --- | --- |
| Admin queues and lists (bookings, reports, disputes, audit logs) | Use on-screen views for day-to-day operations |
| Export / download where the product offers it | Use those controls when present |
| Full custom reporting suite or guaranteed CSV for every queue | **Not** promised as a complete BI package in this pack |

**Honest guidance:** Export when the tools allow. If a needed extract is missing, record the gap and request a technical extract via [sandbox@townruins.com](mailto:sandbox@townruins.com) under the full-time contract. Do not invent a reporting suite that is not on the admin surface. See [04 Administrator Guide](04-Administrator-Guide.md) § Analytics, reports, and exports.

---

## Support and ownership

### Who do I contact for support?

| Situation | Contact |
| --- | --- |
| Product defect, delivery/warranty question, staff admin provisioning | [sandbox@townruins.com](mailto:sandbox@townruins.com) |
| Routine “user forgot password / listing expired / engagement declined” | Owner staff — use this pack first |
| Response time / warranty scope | **Per full-time contract** — this pack does not invent fixed SLA hours or days |

Developer counter-sign for delivery and acceptance: **Alvin Phiri**. Owner organisation: **Hweva Tech Holdings**.

Details: [14 Support and Warranty](14-Support-and-Warranty.md).

---

### Where is the live product and admin panel?

| What | Where |
| --- | --- |
| Production | [https://app.townruins.com](https://app.townruins.com) |
| Admin panel | **Same app** — sign in with **admin** credentials (no separate admin host) |

---

### What is not in version 1.0 that people often assume exists?

| Often assumed | v1.0 reality |
| --- | --- |
| Browse-all-users CRM list in admin | **No full users list UI** |
| Admin button to grant TR Tokens | **No dedicated grant UI** (technical/support path) |
| In-app chat without revealing contact details | **Not in v1.0** |
| Multiple active listings per landlord | **One active listing** limit |
| Live paid “featured listing” / visibility boosts | **Not** live acceptance features (flagged / not in v1.0) |
| Polished full landlord ID review UI | **Partial** — decision still owner-owned |

Full delivered list and known limits: [06 Feature Catalogue](06-Feature-Catalogue.md) and [13 Release Notes](13-Release-Notes.md).

---

## Quick index

| Question | Section |
| --- | --- |
| Reset password | [Accounts and login](#how-do-i-reset-my-password-user-or-admin) |
| Cannot log in | [Why can someone not log in?](#why-can-someone-not-log-in) |
| Verify landlord / provider | [Landlords, verification, and listings](#how-do-i-verify-a-landlord) |
| Deleted listings | [Can deleted listings be recovered?](#can-deleted-listings-be-recovered) |
| Tenant contact blocked | [Why can’t a tenant contact a landlord?](#why-cant-a-tenant-contact-a-landlord) |
| Bookings and money | [How do bookings work?](#how-do-bookings-work-money-path) |
| TR Tokens | [How do TR Tokens work?](#how-do-tr-tokens-work) |
| Export reports | [Can I export reports?](#can-i-export-reports) |
| Create admin | [How are admin accounts created?](#how-are-admin-accounts-created) |
| Support email | [Who do I contact for support?](#who-do-i-contact-for-support) |
