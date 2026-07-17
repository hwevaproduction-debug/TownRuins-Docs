# Support and Warranty

| Field | Value |
| --- | --- |
| **Title** | Town Ruins Owner Pack — Support and Warranty |
| **Audience** | Platform owners (Hweva Tech Holdings) |
| **Version** | 1.0 |
| **Product** | [https://app.townruins.com](https://app.townruins.com) |
| **Support** | [sandbox@townruins.com](mailto:sandbox@townruins.com) |
| **Related** | [01 Welcome](01-Welcome.md) · [12 Data Ownership](12-Data-Ownership.md) · [15 Project Acceptance](15-Project-Acceptance.md) · [09 Troubleshooting](09-Troubleshooting.md) |

---

## Purpose

This document states **how support works** for Town Ruins version **1.0** after ownership transfer to **Hweva Tech Holdings**.

It does **not** replace the **full-time contract**. Where this pack and the contract differ on legal terms, the **contract governs**.

---

## Support contact

| Channel | Detail |
| --- | --- |
| **Email** | [sandbox@townruins.com](mailto:sandbox@townruins.com) |
| **Product** | [https://app.townruins.com](https://app.townruins.com) |
| **Developer counter-sign (delivery)** | **Alvin Phiri** |
| **Owner organisation** | **Hweva Tech Holdings** |

Use the support email for product defects, delivery/warranty questions, staff admin provisioning, and technical assistance that is **in scope of the engagement**.

---

## Coverage and response times

### Contract-first rule

| Topic | Source of truth |
| --- | --- |
| What is covered under warranty / support | **Full-time contract** |
| Response and resolution times | **Full-time contract** |
| Hours of coverage, severity definitions, escalation paths | **Full-time contract** |

This owner pack **does not invent** fixed SLA numbers (for example “reply within X hours” or “fix within Y days”). If you need a numeric commitment, read the contract or ask the developer to confirm the contracted terms in writing.

### What “support” means in plain language

| In scope (typical) | Out of first-line owner pack support |
| --- | --- |
| Defects in delivered v1.0 product behaviour | Routine “user forgot password” coaching (owner does this) |
| Breakage of core flows (login, mail, uploads, stay payments) when platform-wide | Business decisions (approve/reject a host, settle a disputed stay on commercial merits) |
| Agreed technical recovery and warranty work under the contract | New features or redesigns outside contracted scope |
| Controlled admin account provisioning when requested by ownership | Third-party outages outside developer control (see exclusions) |

---

## What is covered vs exclusions

### Typically covered (subject to contract)

- Defects that prevent delivered version **1.0** capabilities from working as documented in this pack and the live product  
- Configuration or integration failures that are the developer’s responsibility under the engagement (for example platform-wide mail or storage misconfiguration when that work sits with the developer)  
- Guidance and fixes for **known technical gaps** where owner UI is incomplete but a support/technical path was agreed (e.g. promo token grant, data extract) — **per contract**, not as unlimited free custom work  
- Security and critical product incidents as defined in the contract  

### Typically excluded or owner-owned

| Exclusion / owner domain | Why |
| --- | --- |
| **Third-party outages** | Payment processors, email providers, DNS, cloud regions, browser vendors, etc. outside developer control — owner and developer coordinate, but warranty is not a guarantee of third-party uptime |
| **New feature requests** outside contracted scope | Roadmap items (chat, map search, multi-listing, full users CRM, etc.) need separate agreement — see [13 Release Notes](13-Release-Notes.md) known limits |
| **Owner operations decisions** | Verification outcomes, moderation, dispute resolution on commercial/policy grounds, legal document wording, who may be staff admin |
| **User content and user error** | Wrong passwords, spam folders, landlord listing quality, guest/provider disputes that are policy not product bugs |
| **Known product limits documented for v1.0** | Missing full users list UI, demo token purchase path, partial landlord verification UI — these are documented limits, not silent defects, unless the contract says otherwise |
| **Misuse or unauthorised access** | Shared admin passwords, compromised accounts due to owner credential handling |

When in doubt: **owner runs the business; developer fixes the product within contract bounds.**

---

## Owner day-to-day responsibility vs developer warranty

```mermaid
flowchart LR
  subgraph owner [Hweva Tech Holdings]
    Ops[Day-to-day ops]
    Support1[First-line user support]
    Policy[Policy and commercial decisions]
  end
  subgraph product [Town Ruins 1.0]
    App[app.townruins.com]
    Admin[Admin panel]
  end
  subgraph dev [Developer engagement]
    Warranty[Warranty and defect fix per contract]
    Contact[sandbox@townruins.com]
  end
  owner --> App
  owner --> Admin
  Support1 -->|product broken| Contact
  Contact --> Warranty
```

| Responsibility | Owner (Hweva Tech Holdings) | Developer (engagement / Alvin Phiri counter-sign) |
| --- | --- | --- |
| Operate admin panel daily | **Yes** | No — not first-line operator |
| Verify landlords/providers; moderate content | **Yes** | Only if tooling is broken |
| Settle stays; resolve disputes on policy | **Yes** | Only for payment/platform defects |
| Reset every user password | **Owner coaches self-service** | Only when reset system is broken |
| Provision new admin staff accounts | Request via support/process | Performs controlled provision under engagement |
| Fix product bugs in delivered 1.0 | Report clearly | **Yes — per full-time contract** |
| Invent SLA hours in this pack | **No** | Contract states terms |
| Accept version 1.0 formally | Sign [15 Project Acceptance](15-Project-Acceptance.md) | Counter-sign as developer |

Full responsibility matrix by data domain: [12 Data Ownership](12-Data-Ownership.md).

---

## How to raise a support request

1. Confirm it is not a routine ops issue ([08 FAQ](08-FAQ.md), [09 Troubleshooting](09-Troubleshooting.md)).  
2. Email [sandbox@townruins.com](mailto:sandbox@townruins.com).  
3. Include:
   - What failed (symptom in plain language)  
   - Scope: one user vs many / whole platform  
   - When it started  
   - Relevant identifiers (emails, listing/booking references) if safe to share  
   - What you already tried  
4. Expect handling **according to the full-time contract** — not according to invented pack SLAs.

---

## Warranty after acceptance

Formal acceptance of Town Ruins **1.0** (product + owner pack) is recorded in [15 Project Acceptance](15-Project-Acceptance.md).

After acceptance:

- **Ownership and day-to-day operation** rest with **Hweva Tech Holdings**.  
- **Warranty and support obligations** continue only as stated in the **full-time contract**.  
- This pack remains the non-technical operating reference; it does not extend warranty beyond the contract.

---

## Summary

| Item | Settled fact |
| --- | --- |
| Support email | [sandbox@townruins.com](mailto:sandbox@townruins.com) |
| Coverage and response times | **Per full-time contract** (no invented numbers here) |
| Owner | Hweva Tech Holdings — day-to-day operations |
| Developer counter-sign | Alvin Phiri |
| Product | https://app.townruins.com version **1.0** |
