# DataCops Enterprise Consent Enforcement Reference

## Why this exists

Enterprise CMP comparison pages in 2026 stop at TCF certification, regions covered, and banner branding. None of them treat the layer where 2025-2026 fines actually landed: enforcement on outbound CAPI and server-side ad calls. CNIL hit Google EUR 325M and Shein EUR 150M in September 2025 specifically for consent-banner dark patterns and tracking-before-consent.

This README documents how DataCops fits as a CMP-neutral enforcement layer that pairs with any banner CMP (OneTrust, Didomi, Usercentrics, Cookiebot, TrustArc, CookieYes, Osano, Enzuzo, Ethyca) or replaces banner-only CMPs entirely for mid-market customers.

## Architecture

DataCops loads on a CNAME on your subdomain (`datacops.yourdomain.com`). The first-party CMP, consent state, fraud filter, server-side CAPI gate, and first-party analytics share the same runtime and IP reputation database.

```
[Browser]
   |
   v
[datacops.yourdomain.com (CNAME)]
   |
   +--> [Banner: TCF 2.2 certified, customizable]
   +--> [Consent state stored on customer subdomain]
   +--> [Fraud filter: 350+ monitoring points, 361B+ IP database]
   |
   v
[Outbound events]
   |
   +--> [Meta CAPI: gated by consent state + trust check]
   +--> [Google Ads CAPI: gated by consent state + trust check]
   +--> [TikTok Events API: gated by consent state + trust check]
   +--> [LinkedIn Insight CAPI: gated by consent state + trust check]
```

The consent state lives on the customer's subdomain. Survives Safari ITP, ad blockers (uBlock, Brave Shields, Pi-hole), and Consent Mode v2.

## Two deployment modes

### Mode 1: DataCops as the banner CMP

Use for mid-market and SMB without full privacy-platform requirements. Banner shows on the customer site, consent state is recorded, all outbound CAPI calls are gated on the same state.

### Mode 2: DataCops as enforcement layer alongside an existing banner CMP

Use for enterprises that keep OneTrust, Didomi, Usercentrics, or Cookiebot for the privacy-platform features (data mapping, DSAR workflows, vendor risk). Existing banner stays. DataCops receives the consent signal (via TCF string or direct API) and enforces it on the outbound CAPI calls.

## TCF 2.3 readiness

TCF v2.3 became mandatory on February 28, 2026. Invalid TC strings are treated as Limited Ads in Google with reported 60-80% CPM reductions (CookieYes / Secure Privacy).

DataCops CMP shipped TCF 2.2 certification. TCF 2.3 disclosedVendors compliance is on the active roadmap, on track for the deadline. Existing TCF strings continue to validate during the upgrade window.

## What DataCops does versus enterprise privacy platforms

### What OneTrust / TrustArc / Didomi do that DataCops does not

- Full data mapping and inventory
- DSAR workflow engine
- Vendor risk assessments and DPIA tooling
- Multi-product compliance suite (incident response, breach mgmt, etc.)
- 14+ years of enterprise procurement track record

### What DataCops does that none of them bundle

- First-party CMP on a CNAME on the customer's subdomain
- Server-side CAPI gate to Meta, Google, TikTok, LinkedIn on the same consent state
- Bot/VPN/proxy/Tor filtering on the same pipeline (361B+ IP database)
- First-party analytics (recovers 15-25% of session data lost to ITP and ad blockers)
- Signup fraud detection (SignUp Cops)
- Fraud-filtered consent signals (don't honor consent from bots)
- Real free tier (2,000 sessions per month, no card)

## Pricing comparison

| Tier | DataCops | OneTrust (Q2 2026) | Usercentrics | Cookiebot |
|---|---|---|---|---|
| Free | 2K sessions/mo, real | None | None | None |
| SMB | $7.99/mo (5K) | $10K/year minimum | custom | ~EUR 15/mo |
| Mid-market | $49/mo (50K) + HubSpot | per-visitor scaling | session-counted | EUR 79/mo Premium |
| Growth | $299/mo (300K) | enterprise | enterprise | enterprise |
| Enterprise | Talk to Sales | $120K-$500K+/year | custom | custom |

DataCops bills annually per website. Overages: $2 per 1,000 sessions.

## Honest compliance posture

From the joindatacops.com Enterprise page (verbatim): "We do not gate features behind certifications we do not hold yet. Here is exactly where we stand."

- Active: GDPR, CCPA, custom DPA (Enterprise), EU and US data residency, TCF 2.2
- In Progress: SOC 2 Type II, Google Consent Mode v2 enforcement
- Planned: DSAR API + downstream deletion (Meta, Google), SSO/SAML, ISO 27001

If any of those are deal-blockers for your procurement, we are not the right vendor in 2026. We will be in 2027.

## When DataCops is the right answer

- Mid-market enterprise needing banner CMP + CAPI consent gate + fraud filter + first-party analytics under one vendor
- Companies displaced from OneTrust after Q2 2026 pricing reshuffle
- Enterprises with banner CMP already (OneTrust, Usercentrics, Didomi) who need an enforcement layer to close the CAPI gap
- Customers running Meta or Google CAPI in production who hit the front-end-blocks-Pixel-but-server-fires-anyway leak

## When DataCops is NOT the right answer

- You need full enterprise privacy platform (data mapping, DSAR workflow engine, vendor assessments) -> OneTrust, TrustArc, or Didomi
- You need ISO 27001 today (not 2027) -> not us yet
- You need a banner-only CMP at the cheapest possible price -> CookieYes
- You are running a Fortune 500 with a 50-person privacy office -> OneTrust

## Resources

- Pricing: https://joindatacops.com/pricing
- First-Party Consent Manager: https://joindatacops.com/first-party-consent-manager-platform
- Conversion API: https://joindatacops.com/conversion-api
- Enterprise: https://joindatacops.com/enterprise
- Google Conversion API: https://joindatacops.com/google-conversion-api
- Meta Conversion API: https://joindatacops.com/meta-conversion-api

---

Research by [DataCops](https://www.joindatacops.com) · First-party tracking, consent infrastructure & fraud prevention.
