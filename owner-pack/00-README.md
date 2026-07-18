---
title: Owner Pack
description: Index and reading map for the Town Ruins owner operating pack for Hweva Tech Holdings platform owners.
tags:
  - owner
  - owner-pack
  - readme
  - hweva
aliases:
  - Owner Pack README
  - Town Ruins Owner Pack
---

# Town Ruins Owner Pack

| Field | Value |
| --- | --- |
| **Title** | Town Ruins Owner Pack — README |
| **Audience** | Platform owners (Hweva Tech Holdings) |
| **Version** | 1.0 |
| **Product** | [https://app.townruins.com](https://app.townruins.com) |
| **Support** | [sandbox@townruins.com](mailto:sandbox@townruins.com) |

---

## Who this pack is for

This pack is for **platform owners and operators** at **Hweva Tech Holdings** — the people who own Town Ruins day to day, accept delivery, and run the platform after go-live.

It is **not** a thin client overview for an external customer. You are the owner. These documents assume you (or your staff) will:

- Log in at [https://app.townruins.com](https://app.townruins.com) with admin credentials
- Use the **admin panel** as the main operating surface
- Own decisions about accounts, listings, bookings, tokens, and moderation
- Know where support starts and stops (see Support and Warranty)

Technical engineering guides live elsewhere in this portal (for example `guides/` and `operations/`). This pack is the **official non-technical operating set**.

---

## How to use this pack

| If you need to… | Start here |
| --- | --- |
| Orient yourself after delivery | [01 Welcome](01-welcome) → [02 Quick Start](02-quick-start) |
| Run daily work | [11 Daily Operations](11-daily-operations) → [05 Business Processes](05-business-processes) |
| Use the admin panel | [07 Admin Panel Guide](07-admin-panel-guide) → [04 Administrator Guide](04-administrator-guide) |
| Support end users | [03 User Manual](03-user-manual) → [08 FAQ](08-faq) → [09 Troubleshooting](09-troubleshooting) |
| Understand roles and data | [10 Roles and Permissions](10-roles-and-permissions) → [12 Data Ownership](12-data-ownership) |
| See what shipped / known limits | [06 Feature Catalogue](06-feature-catalogue) → [13 Release Notes](13-release-notes) |
| Support contact and warranty | [14 Support and Warranty](14-support-and-warranty) |
| Formal acceptance of version 1.0 | [15 Project Acceptance](15-project-acceptance) |

**Suggested first pass for a new owner staff member**

1. Read this README (conventions and index).
2. Read Welcome and Quick Start.
3. Skim Daily Operations and the Admin Panel Guide.
4. Keep FAQ, Troubleshooting, and Support/Warranty handy for real work.

---

## Document index

| # | Document | Path | Status |
| --- | --- | --- | --- |
| 00 | This README | [00-readme](00-readme) | Complete |
| 01 | Welcome | [01-welcome](01-welcome) | Complete |
| 02 | Quick Start | [02-quick-start](02-quick-start) | Complete |
| 03 | User Manual | [03-user-manual](03-user-manual) | Complete |
| 04 | Administrator Guide | [04-administrator-guide](04-administrator-guide) | Complete |
| 05 | Business Processes | [05-business-processes](05-business-processes) | Complete |
| 06 | Feature Catalogue | [06-feature-catalogue](06-feature-catalogue) | Complete |
| 07 | Admin Panel Guide | [07-admin-panel-guide](07-admin-panel-guide) | Complete |
| 08 | FAQ | [08-faq](08-faq) | Complete |
| 09 | Troubleshooting | [09-troubleshooting](09-troubleshooting) | Complete |
| 10 | Roles and Permissions | [10-roles-and-permissions](10-roles-and-permissions) | Complete |
| 11 | Daily Operations | [11-daily-operations](11-daily-operations) | Complete |
| 12 | Data Ownership | [12-data-ownership](12-data-ownership) | Complete |
| 13 | Release Notes | [13-release-notes](13-release-notes) | Complete |
| 14 | Support and Warranty | [14-support-and-warranty](14-support-and-warranty) | Complete |
| 15 | Project Acceptance | [15-project-acceptance](15-project-acceptance) | Complete |

Folder layout (target):

```text
owner-pack/
├── 00-readme                 ← you are here
├── 01-welcome
├── 02-quick-start
├── 03-user-manual
├── 04-administrator-guide
├── 05-business-processes
├── 06-feature-catalogue
├── 07-admin-panel-guide
├── 08-faq
├── 09-troubleshooting
├── 10-roles-and-permissions
├── 11-daily-operations
├── 12-data-ownership
├── 13-release-notes
├── 14-support-and-warranty
└── 15-project-acceptance
```

All documents in this index are **Complete** for version **1.0**. Links above are the canonical paths for navigation.

---

## Conventions

### Owner voice

- Write for **owners and operators**, not “the client” or an external handover audience.
- Prefer plain language. Avoid engineering jargon unless a short plain-language gloss is needed.
- Admin panel first: when there are multiple surfaces, document the owner/admin path fully; cover tenant/landlord paths only as far as owners need to support users.
- Use “you” for the owner staff member reading the pack.

### Version and product

| Field | Settled value |
| --- | --- |
| Pack / acceptance version | **1.0** |
| Production URL | https://app.townruins.com |
| Admin access | Same app — sign in with admin credentials (no separate admin-only host) |
| Support email | sandbox@townruins.com |
| Owner organisation | Hweva Tech Holdings |
| Developer counter-sign | Alvin Phiri |
| Warranty / support terms | Per full-time contract (do not invent fixed SLA numbers in these docs) |

### Truth bar

- Describe **what ships in version 1.0** as implemented.
- Do **not** use “Planned” as an escape hatch inside manuals for features that are not delivered.
- Real gaps, limits, or deferred items belong only in **Release Notes** and **known limitations** (and, where needed, Support/Warranty).
- If something is unknown and not settled by product or contract, say so clearly rather than inventing detail.

### Screenshot placeholder format

Screenshots will be captured in a later pass. Until then, every place a screenshot should appear uses this labeled placeholder so authors and reviewers share one format:

```markdown
> **Screenshot:** `[SCREENSHOT: short-label]`
>
> - **Where:** Admin panel → example path
> - **Shows:** What the reader should see (one sentence)
> - **Capture later:** Yes — full text is complete without the image
```

**Rules**

- Use a short, stable `short-label` (kebab-case), e.g. `admin-users-list`, `listing-moderation-queue`.
- Keep the surrounding text complete: a reader must be able to follow the procedure without the image.
- Do not block document completion on live captures.
- When an image is added later, replace the block with a normal markdown image and keep the same label in the alt text if useful:

```markdown
![Admin users list](./images/admin-users-list.png)
```

### Shared document header

Every owner-pack document (including this README) opens with the same header pattern so version and audience stay consistent:

```markdown
# <Document title>

| Field | Value |
| --- | --- |
| **Title** | <same as H1 or short formal title> |
| **Audience** | Platform owners (Hweva Tech Holdings) |
| **Version** | 1.0 |
| **Product** | [https://app.townruins.com](https://app.townruins.com) |
| **Support** | [sandbox@townruins.com](mailto:sandbox@townruins.com) |

---
```

Optional fields (use when helpful):

| Field | When to use |
| --- | --- |
| **Related** | Links to sibling pack docs |
| **Last reviewed** | After a content pass against the live product |

---

## Relationship to other docs

| Location | Role |
| --- | --- |
| **`content/owner-pack/`** (this folder in the Operations Portal) | Canonical **non-technical** owner operating pack |
| `content/guides/` | Technical / engineering-oriented user and admin guides |
| `content/operations/` | Deployment, runbooks, environment — for technical operators |
| `content/client-handover/` | **Separate non-owner hub** — client/handover readers; not the owner pack. Still live for that audience. |

---

## When you need more

This pack is the owner operating set. When work steps outside day-to-day ownership, use these portal areas:

| Area | Go here | Use when | Honesty |
| --- | --- | --- | --- |
| **Operations** | [Operations](../operations) | Deployment, runbooks, rollback, operational procedures | Full ops depth in-portal |
| **Product** | [Product](../product/) | Feature roadmap and product folder navigation | Some “vision” pages may describe off-product strategy copy — treat as **index**, not sole product truth |
| **Legal** | [Legal](../legal/) | Where legal materials are indexed | **Index only** in this portal; canonical legal bodies often live in monorepo / live app — not full contracts here |
| **Workflows** | [Workflows](../workflows/) | Use cases, user journeys, and system interaction flows | In-portal workflows docs |

---

## Support

For product and delivery support questions covered by the engagement:

- Email: [sandbox@townruins.com](mailto:sandbox@townruins.com)
- Warranty and boundaries: [14 Support and Warranty](14-support-and-warranty)
- Contract terms govern response expectations; this pack does not invent SLA numbers.
