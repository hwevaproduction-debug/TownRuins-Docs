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

Technical engineering guides live elsewhere under `docs/` (for example `guides/` and `operations/`). This pack is the **official non-technical operating set**.

---

## How to use this pack

| If you need to… | Start here |
| --- | --- |
| Orient yourself after delivery | [01 Welcome](01-Welcome.md) → [02 Quick Start](02-Quick-Start.md) |
| Run daily work | [11 Daily Operations](11-Daily-Operations.md) → [05 Business Processes](05-Business-Processes.md) |
| Use the admin panel | [07 Admin Panel Guide](07-Admin-Panel-Guide.md) → [04 Administrator Guide](04-Administrator-Guide.md) |
| Support end users | [03 User Manual](03-User-Manual.md) → [08 FAQ](08-FAQ.md) → [09 Troubleshooting](09-Troubleshooting.md) |
| Understand roles and data | [10 Roles and Permissions](10-Roles-and-Permissions.md) → [12 Data Ownership](12-Data-Ownership.md) |
| See what shipped / known limits | [06 Feature Catalogue](06-Feature-Catalogue.md) → [13 Release Notes](13-Release-Notes.md) |
| Support contact and warranty | [14 Support and Warranty](14-Support-and-Warranty.md) |
| Formal acceptance of version 1.0 | [15 Project Acceptance](15-Project-Acceptance.md) |

**Suggested first pass for a new owner staff member**

1. Read this README (conventions and index).
2. Read Welcome and Quick Start.
3. Skim Daily Operations and the Admin Panel Guide.
4. Keep FAQ, Troubleshooting, and Support/Warranty handy for real work.

---

## Document index

| # | Document | Path | Status |
| --- | --- | --- | --- |
| 00 | This README | [00-README.md](00-README.md) | Complete |
| 01 | Welcome | [01-Welcome.md](01-Welcome.md) | Complete |
| 02 | Quick Start | [02-Quick-Start.md](02-Quick-Start.md) | Complete |
| 03 | User Manual | [03-User-Manual.md](03-User-Manual.md) | Complete |
| 04 | Administrator Guide | [04-Administrator-Guide.md](04-Administrator-Guide.md) | Complete |
| 05 | Business Processes | [05-Business-Processes.md](05-Business-Processes.md) | Complete |
| 06 | Feature Catalogue | [06-Feature-Catalogue.md](06-Feature-Catalogue.md) | Complete |
| 07 | Admin Panel Guide | [07-Admin-Panel-Guide.md](07-Admin-Panel-Guide.md) | Complete |
| 08 | FAQ | [08-FAQ.md](08-FAQ.md) | Complete |
| 09 | Troubleshooting | [09-Troubleshooting.md](09-Troubleshooting.md) | Complete |
| 10 | Roles and Permissions | [10-Roles-and-Permissions.md](10-Roles-and-Permissions.md) | Complete |
| 11 | Daily Operations | [11-Daily-Operations.md](11-Daily-Operations.md) | Complete |
| 12 | Data Ownership | [12-Data-Ownership.md](12-Data-Ownership.md) | Complete |
| 13 | Release Notes | [13-Release-Notes.md](13-Release-Notes.md) | Complete |
| 14 | Support and Warranty | [14-Support-and-Warranty.md](14-Support-and-Warranty.md) | Complete |
| 15 | Project Acceptance | [15-Project-Acceptance.md](15-Project-Acceptance.md) | Complete |

Folder layout (target):

```text
owner-pack/
├── 00-README.md                 ← you are here
├── 01-Welcome.md
├── 02-Quick-Start.md
├── 03-User-Manual.md
├── 04-Administrator-Guide.md
├── 05-Business-Processes.md
├── 06-Feature-Catalogue.md
├── 07-Admin-Panel-Guide.md
├── 08-FAQ.md
├── 09-Troubleshooting.md
├── 10-Roles-and-Permissions.md
├── 11-Daily-Operations.md
├── 12-Data-Ownership.md
├── 13-Release-Notes.md
├── 14-Support-and-Warranty.md
└── 15-Project-Acceptance.md
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
| **`docs/owner-pack/`** (this folder) | Canonical **non-technical** owner operating pack |
| `docs/guides/` | Technical / engineering-oriented user and admin guides |
| `docs/operations/` | Deployment, runbooks, environment — for technical operators |
| `docs/client-handover/` | **Retired** — pointer only; do not use as the live pack |

---

## Support

For product and delivery support questions covered by the engagement:

- Email: [sandbox@townruins.com](mailto:sandbox@townruins.com)
- Warranty and boundaries: [14 Support and Warranty](14-Support-and-Warranty.md)
- Contract terms govern response expectations; this pack does not invent SLA numbers.
