# Release Notes

| Field | Value |
| --- | --- |
| **Title** | Town Ruins Owner Pack — Release Notes |
| **Audience** | Platform owners (Hweva Tech Holdings) |
| **Version** | 1.0 |
| **Product** | [https://app.townruins.com](https://app.townruins.com) |
| **Support** | [sandbox@townruins.com](mailto:sandbox@townruins.com) |
| **Related** | [06 Feature Catalogue](06-Feature-Catalogue.md) · [01 Welcome](01-Welcome.md) · [15 Project Acceptance](15-Project-Acceptance.md) |

---

## Version 1.0

| Field | Value |
| --- | --- |
| **Product version** | **1.0** |
| **Production URL** | [https://app.townruins.com](https://app.townruins.com) |
| **Admin access** | Same app — sign in with admin credentials |
| **Owner organisation** | Hweva Tech Holdings |
| **Pack version** | 1.0 (this owner operating pack) |

These notes describe **what shipped** for acceptance of Town Ruins **1.0**. They match the truth bar used across this pack: delivered capabilities only; real gaps called out as known limitations — not sold as future promises.

The full capability list is in [06 Feature Catalogue](06-Feature-Catalogue.md). This document is the release summary for owners.

---

## Delivered features (summary)

### Accounts and access

- Email/password registration for tenants and landlords; separate provider sign-up path
- Email verification required before normal public login; resend verification
- Login, Google sign-in (where configured), password reset
- Profile maintenance (username, email, avatar, password) and display preferences
- Admin accounts via **controlled seed / provision process** (not public sign-up)
- Admin dashboard on the **same** production app

### Long-term rental marketplace

- Browse, search, and filter listings; listing detail with protected contact until engagement approval
- Landlord listing wizard, drafts with autosave, images, activation lifecycle, statuses
- One active listing per landlord
- Engagements: tenant contact request → landlord approve/decline; **5 TR** charged to tenant on **approval** only
- Contact details revealed after approval
- Tenant premium membership (early access) and saved searches with email alerts (as product configures)
- Listing restore with TR Tokens (**1 TR × days**, up to 30)
- User reporting of listings and related targets

### Temporary stays

- Provider accommodations, rooms, availability
- Stay search and booking (instant vs request/confirm)
- **Real-money** payment path for stay bookings (charges, refunds, cancellations, settlement-related flows)
- Guest booking management; provider confirm/decline lifecycle
- Admin: view bookings, settle completed stays, disputes
- Provider verification, commission, suspend/reinstate
- Accommodation moderation (approve, reject, suspend, reinstate)
- Guest reviews with admin publish/unpublish

### TR Tokens and wallet

- Wallet balance and transaction history
- Welcome bonus (**100 TR**) on first email verification / new Google user path
- Engagement and restore debits as above
- Token package UI (purchase path may be demo — see known limitations)
- Low-balance warning behaviour where implemented

### Admin operations and trust

- Listing moderation (inactive stock, bulk revive, deactivate)
- Landlord identity verification review (**UI may be partial** — see known limitations)
- Reports, disputes, reviews, legal document version management
- Audit logs of admin actions
- Public legal pages maintained by owner staff

### Notifications

- In-app notifications
- Email notifications (production mail configuration dependent)
- Push (where configured); SMS only if enabled

### Owner pack (documentation delivery)

- Full non-technical owner pack **00–15** under `docs/owner-pack/` for day-to-day ownership and acceptance

---

## Improvements included in 1.0 delivery

Version **1.0** is the **first accepted production baseline** documented by this pack. Items below are product qualities of that baseline, not a separate later patch list:

| Area | Improvement / quality in 1.0 |
| --- | --- |
| Operating surface | Single production host for public users and admin operators |
| Privacy design | Contact unlock only after engagement approval |
| Dual commercial model | Clear split: TR for platform premium actions; real money for stay bookings |
| Trust tools | Reports, disputes, legal CMS, audit logs for owner accountability |
| Onboarding | Welcome tokens and wallet introduction for new public users |

---

## Known limitations

These are **honest v1.0 limits**. They are **not** acceptance defects if they match commercial expectation; they must not be described as delivered full features.

| Item | Reality in 1.0 |
| --- | --- |
| Full admin **browse all users** list | **Not in v1.0** as a dashboard CRM-style directory |
| Admin **token-grant UI** | **Not in v1.0** — promo grants use technical / support path |
| **TR Token purchase** real payment | **Known limit** — package purchase may be **demo-mode** until live payment is fully wired |
| Landlord ID verification **admin review UI** | **Partial** — submission exists; polished full UI may be incomplete |
| In-platform messaging (chat without revealing contact) | **Not in v1.0** |
| Map-based search | **Not in v1.0** |
| Multiple active listings per landlord | **Not in v1.0** (one active listing limit) |
| Account type switching (e.g. tenant → landlord) in product | **Not in v1.0** |
| Featured listing placement / premium visibility boosts | **Not** live paid acceptance features (off / planned outside this release) |
| Phone verification as fully enabled default path | **Not enabled by default** (flag / config dependent) |
| Full custom reporting / guaranteed export suite | Exports only **where tools allow**; no BI suite promised |
| Super admin vs admin provider actions | A few provider verify/commission actions may require a designated **admin** account |

Operational honesty for these items is also stated in [03 User Manual](03-User-Manual.md), [04 Administrator Guide](04-Administrator-Guide.md), [06 Feature Catalogue](06-Feature-Catalogue.md), and [07 Admin Panel Guide](07-Admin-Panel-Guide.md).

---

## Optional future enhancements (not delivered)

The following are **not** part of version **1.0** acceptance. They are listed only so owners do not confuse roadmap ideas with shipped product. Delivery of any item requires a separate agreement — this pack does not commit dates or scope.

- Full users directory and richer admin user management UI  
- Dedicated admin TR grant UI  
- Live card payment for token packages (if still demo at acceptance)  
- Polished landlord verification review UI completion  
- In-platform messaging  
- Map search  
- Multiple active listings per landlord  
- Featured listings / visibility boosts as live paid products  

Do **not** treat this list as a delivery schedule.

---

## Acceptance pointer

To accept Town Ruins **1.0** against delivered product + this pack, use:

- Capability evidence: [06 Feature Catalogue](06-Feature-Catalogue.md)  
- Formal sign-off: [15 Project Acceptance](15-Project-Acceptance.md)  
- Support boundaries: [14 Support and Warranty](14-Support-and-Warranty.md)  

**Product:** [https://app.townruins.com](https://app.townruins.com) · **Support:** [sandbox@townruins.com](mailto:sandbox@townruins.com) · **Developer counter-sign:** Alvin Phiri · **Owner:** Hweva Tech Holdings
