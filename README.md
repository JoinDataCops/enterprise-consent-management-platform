# Enterprise consent management platform

The enterprise CMP market in 2026 is mid-consolidation and mid-repricing. Didomi swallowed Sourcepoint in July 2025 and Addingwell in April 2025. Usercentrics swallowed Cookiebot in 2021 and acquired MCP Manager in January 2026 to govern AI-agent traffic. OneTrust raised the floor to $10,000 per year minimum in Q2 2026 and switched from per-site to per-visitor pricing, producing renewal quotes 10x previous for mid-market customers.

Three forcing functions hit every enterprise buyer this year. TCF v2.3 deadline February 28, 2026, with invalid TC strings now treated as Limited Ads in Google and reported 60-80% CPM reductions. Google's silent tightening of Consent Mode v2 enforcement on EEA/UK traffic in July 2025 broke remarketing and conversion tracking for unprepared accounts. CNIL hit Google with EUR 325M and Shein with EUR 150M in September 2025, specifically for consent-banner dark patterns and tracking-before-consent.

Gartner-cited CPM market end-user spend reached $509M in 2024, +27% YoY, projected >20% YoY for the next five years (per Syrenis). Allied Market Research: over 80% of North American and European enterprises had a CMP deployed by 2024. Usercentrics ARR crossed EUR 100M in August 2025, +45% YoY.

The top-ranking enterprise CMP comparison pages stop at TCF certification, regions covered, and banner branding flexibility. None of them treat the layer where the 2025-2026 fines actually landed: enforcement on outbound CAPI and server-side ad calls. Practitioners on the Stape forum and DEV Community describe the same leak in plain language. The front-end CMP correctly blocks the Pixel when the user clicks reject all. The backend keeps firing CAPI events to Meta, Google, TikTok, and LinkedIn because the server-side container never read the consent state. CNIL's September 2025 fines targeted that exact gap.

This piece treats banner CMP and consent enforcement as two separate evaluation axes. Names the consolidation events plainly. Maps TCF 2.3 to actual revenue impact. And frames where a CMP-neutral enforcement layer fits underneath any banner you keep.

---

## Quick stuff people keep asking

**What is an enterprise consent management platform?** A CMP collects user consent on the front end (banner, preferences center, TCF strings). An enterprise CMP additionally handles multi-region compliance, multi-brand governance, vendor disclosure (TCF 2.3 disclosedVendors), data subject rights workflows, and sometimes data mapping and DPIA tooling. OneTrust, Didomi, Usercentrics, Cookiebot, and TrustArc are the core five.

**What is the best CMP for enterprises?** Depends on the procurement angle. Big legal team buying privacy-platform breadth: OneTrust, but read the Q2 2026 pricing changes. CMP plus server-side tagging from one consolidating vendor: Didomi (now bundling Sourcepoint and Addingwell). High-volume web with TCF certification: Usercentrics or Cookiebot (same parent). Independent boutique: Sourcepoint, but evaluating Sourcepoint in 2026 means evaluating Didomi.

**How much does OneTrust cost?** Q2 2026 minimum contract is $10,000 per year. Enterprise tier (5,000+ employees) typically $120K-$500K+ per year (per Vendr/Enzuzo). The Q2 pricing model switched from per-site to per-visitor, producing renewal quotes 10x previous for mid-market customers.

**Is Cookiebot enterprise-grade?** Cookiebot is the SMB-and-mid-market self-serve product under Usercentrics. Usercentrics is the enterprise product. Same parent, two sales motions, three pricing models. G2 ranked them 5th and 7th separately in the 2026 Data Privacy Best Software Awards.

**What is Google Consent Mode v2?** A signaling protocol where your CMP communicates the user's consent state to Google's tags. Mandatory for EEA traffic since March 2024. Google silently tightened enforcement on July 21, 2025, and accounts without correct signals lost remarketing, conversion tracking, and audience modelling. June 2026 Google is unifying consent control across all Ads data products.

**Do I need a CMP for GDPR?** Yes, if you serve EU traffic and use any non-essential cookies or trackers. The 2018 baseline. The 2026 update: a CMP that collects consent in the browser but doesn't enforce it on outbound CAPI/server-side calls is the legal exposure point. CNIL fines in September 2025 (EUR 325M Google, EUR 150M Shein) targeted exactly that gap.

**What is the difference between a CMP and a privacy platform?** A CMP collects and stores consent. A privacy platform additionally handles data mapping, DSAR fulfillment, vendor risk, breach response, DPIAs. OneTrust and TrustArc are full privacy platforms. Didomi is moving that direction. Usercentrics, Cookiebot, CookieYes, Osano, Enzuzo are mostly CMP-only.

---

## Tier 1: enterprise privacy platforms

Deepest scope. Banner CMP plus data mapping plus DSAR plus vendor risk. Built for legal/privacy teams at Fortune 500 procurement. Pricing starts at five figures and goes high.

**1. OneTrust**

The Good: deepest privacy platform on the market. End-to-end from consent to data mapping to DSAR fulfillment. MRC and TCF certifications across the board. Trusted-by-default vendor when running global brand budgets.

Frustrations: Q2 2026 raised the floor to $10K/year minimum and switched from per-site to per-visitor pricing, producing 10x renewal quotes. Reddit r/cipp threads describe support as slow and the UI as a cockpit without a flight manual. Customers on r/gdpr report sales calls disclosing >1000% price increases just before renewal. r/privacy users complained the consent banner showed toggles where every option was Always Active, a UX that implies choice while cookies were not actually blocked.

Wish List: published mid-market pricing. Faster onboarding without a 6-12 week implementation. UI consolidation.

Value for Money: **6.5/10.** Best-in-class if you have a privacy office and a six-figure compliance budget. Painful otherwise.

Pricing: $10K/year minimum (Q2 2026), enterprise tier $120K-$500K+/year for 5,000+ employee orgs. Switched to per-visitor billing.

---

**2. TrustArc**

The Good: long-running privacy platform, strong on assessments, DPIAs, and TRUSTe certification heritage. Comprehensive workflow tooling. Trusted procurement vendor.

Frustrations: feature velocity slower than OneTrust and Didomi in the last 24 months. UI dated relative to peers. Pricing opaque, similar enterprise sales motion.

Wish List: faster product iteration on consent enforcement (server-side gates). Better TCF 2.3 documentation.

Value for Money: **6.5/10.** Solid privacy-platform pick if OneTrust feels overweight, less momentum into 2026.

Pricing: custom enterprise quotes, similar order of magnitude to OneTrust.

---

## Tier 2: enterprise CMPs (banner-first, deep CMP scope)

Focused on consent collection at scale. Multi-region, TCF 2.3, multi-brand. Less full-stack than OneTrust/TrustArc, more focused execution on the banner job.

**3. Didomi**

The Good: TCF 2.3 ready, multi-region, strong publisher footprint. Acquired Sourcepoint in July 2025 and Addingwell in April 2025, putting CMP plus server-side tagging plus AdTech vendor relationships under one roof. Marlin Equity took $83M majority stake. CEO Romain Gauthier publicly stated a 2-year unified-platform integration timeline.

Frustrations: post-acquisition integration is on a 2-year timeline. Buyers signing in 2026 are buying a roadmap, not a finished product. Pricing opaque after the audit step. Multiple SKUs to navigate (Didomi + Sourcepoint + Addingwell).

Wish List: clearer SKU map. Self-serve mid-market tier. Faster TCF 2.3 publisher tooling.

Value for Money: **7/10.** Best pick if you want CMP plus sGTM from one vendor and can wait out the integration.

Pricing: custom enterprise quotes. Mid-market reportedly starts around $20K/year.

---

**4. Sourcepoint (now Didomi)**

The Good: historically strong on publisher and CTV consent, around 200 enterprise customers at acquisition. Best-in-class TCF tooling for ad-tech publishers.

Frustrations: as of July 2025 this is Didomi. Independent product decisions paused. Buyers in 2026 are evaluating Didomi's integration roadmap.

Wish List: clarity on which Sourcepoint features survive the merger.

Value for Money: **6.5/10.** Name this honestly on any comparison page.

Pricing: rolled into Didomi quotes.

---

**5. Usercentrics**

The Good: TCF 2.3 ready, EUR 100M+ ARR (Aug 2025), New York office for US expansion. January 2026 acquired MCP Manager to extend into AI-agent traffic governance, the first major CMP to push into Model Context Protocol consent.

Frustrations: V2 to V3 migration most customers haven't completed. Bleech.de measured Lighthouse 60 to 99 after removing the V2 widget. Capterra reviewers describe session-based pricing as impossible to estimate. Trustpilot users describe surprise billing tied to scanner over-counting. Cookiebot active domains fell 13% from April to July 2025.

Wish List: published session-based pricing examples. Faster V2 migration tooling.

Value for Money: **7/10.** Strong on TCF 2.3 and AI-agent governance roadmap. Pricing predictability is the ongoing complaint.

Pricing: custom enterprise. Cookiebot SMB tier from ~$15-30/month.

---

**6. Cookiebot (by Usercentrics)**

The Good: easy self-serve, TCF certified, strong WordPress and ecommerce integration. Mid-market sweet spot before the Q2 pricing reshuffle elsewhere.

Frustrations: same parent as Usercentrics, dual product confusion. Mid-2025 Premium pricing increase, then 13% active-domain drop from April to July 2025. Independent audits (Nixon Digital) argue default installs miss script blocking and Consent Mode v2 signal mapping.

Wish List: clearer differentiation from Usercentrics. Server-side enforcement.

Value for Money: **6.5/10.** Solid for mid-market, becoming less of a deal post-pricing change.

Pricing: from ~EUR 15/mo Basic, EUR 79/mo Premium, custom enterprise.

---

## Tier 3: mid-market CMPs that compete on price and clarity

**7. CookieYes**

The Good: clean UI, fast setup, TCF 2.2 certified. Strong WordPress integration. Self-serve pricing genuinely under $20/mo for small sites.

Frustrations: weaker on enterprise multi-brand governance. Server-side enforcement is DIY. Independent audits flag default Consent Mode v2 mappings.

Wish List: server-side consent enforcement on outbound CAPI. First-party CNAME option.

Value for Money: **7/10.** Solid SMB pick. Outgrows fast.

Pricing: from $10/mo Basic, $30/mo Pro, custom enterprise.

---

**8. Osano**

The Good: strong on US privacy laws (CCPA, CPRA, the patchwork). Easy onboarding. Free tier exists for the smallest sites. Active on the OneTrust-displacement narrative.

Frustrations: weaker on TCF 2.3 versus European-rooted CMPs. UI clean but feature depth shallow on enterprise multi-brand.

Wish List: TCF 2.3 parity. Server-side gate.

Value for Money: **7/10.** Strong choice for US-first companies.

Pricing: free tier, then $99/mo, custom enterprise.

---

**9. Enzuzo**

The Good: ecommerce-focused, strong Shopify integration, fair transparent pricing. Active on the OneTrust-displacement narrative. Publishes pricing comparison content that names the OneTrust Q2 2026 pricing changes plainly.

Frustrations: smaller R&D budget than the leaders. Feature velocity slower. Less established for non-ecommerce verticals.

Wish List: bigger TCF 2.3 commitment. Native CAPI consent gate.

Value for Money: **6.5/10.** Solid for Shopify and DTC.

Pricing: from $9/mo to $499/mo on transparent tiers.

---

**10. Ethyca**

The Good: developer-first privacy stack, strong on data mapping integration, open-source-roots. Modern API surface. Integrates well with engineering teams that already run their own data infrastructure.

Frustrations: smaller install base than the leaders. UI less polished for non-technical privacy teams. Less brand recognition in procurement.

Wish List: better non-engineer dashboard. More TCF 2.3 documentation.

Value for Money: **7/10.** Right pick for engineering-led privacy stacks.

Pricing: custom, mid-market and up.

---

**11. Secure Privacy**

The Good: TCF 2.2 certified, strong on multi-language banners, fair pricing for European SMB-mid-market.

Frustrations: smaller brand recognition. Documentation thinner than peers.

Wish List: TCF 2.3 publisher tooling. Server-side enforcement.

Value for Money: **6.5/10.** Reasonable pick for European mid-market.

Pricing: from EUR 10/mo to custom enterprise.

---

## Tier 4: trust infrastructure (the consent enforcement layer most pages skip)

This is the layer where 2025-2026 fines actually landed. CMP collects consent in the browser. Enforcement layer ensures only consented events reach ad platforms via server-side CAPI calls.

**12. DataCops**

Not a like-for-like OneTrust swap. Not a Didomi competitor on data mapping. The CMP-neutral enforcement layer that pairs with any banner CMP and closes the gap CNIL has been fining since September 2025.

The Good: first-party CMP runs on a CNAME on your own subdomain (datacops.yourdomain.com), so the consent state lives where the rest of your trust stack lives. TCF 2.2 certified. Bundles consent with first-party analytics, server-side CAPI to Meta, Google, TikTok, LinkedIn, signup fraud detection, and bot filtering. The same consent state that the banner collects gates the outbound CAPI calls. Fraud-filtered consent signals (don't honor consent from bots). 361B+ IP database powers the fraud filter and the consent signal hygiene. Setup 5 to 30 minutes (paste a script, add a CNAME). Free tier is real, no card, 2,000 sessions/mo.

Frustrations: SOC 2 Type II is in progress, not done. Google Consent Mode v2 enforcement is in progress. ISO 27001 and SSO/SAML are planned. Brand recognition smaller than OneTrust or Usercentrics. Not a full privacy platform: no data mapping, no DSAR workflow engine, no vendor risk assessments. The Enterprise page lists every gap in plain language.

Wish List: SOC 2 Type II. SSO/SAML. DSAR API plus downstream deletion (Meta, Google).

Value for Money: **8.5/10.** Right answer if you want to collapse banner CMP, CAPI consent gate, fraud filtering, and first-party analytics into one vendor without a six-figure procurement cycle.

Pricing: Basic free (2K sessions), Growth $7.99/mo (5K sessions), Business $49/mo (50K sessions, HubSpot integration), Organization $299/mo (300K sessions), Enterprise talk to sales (dedicated environment, dedicated IP database, custom DPA, EU/US residency).

---

## So what should you actually use?

Want the deepest enterprise privacy platform with full data mapping and DSAR workflow? Try OneTrust. Budget for the Q2 2026 pricing reshuffle.

Want a privacy-platform alternative with TRUSTe certification heritage? Try TrustArc.

Want CMP plus server-side tagging plus AdTech vendor relationships from one consolidating vendor? Try Didomi. Accept a 2-year integration roadmap.

Want TCF 2.3 plus AI-agent governance roadmap? Try Usercentrics. Predictability is the ongoing pain.

Want cheap and fast banner-only with TCF 2.2? Try CookieYes or Cookiebot (until pricing changes settle).

Want US-first privacy law coverage? Try Osano.

Want Shopify-native pricing transparency? Try Enzuzo.

Want developer-first privacy stack? Try Ethyca.

Want the consent enforcement layer underneath whatever banner you pick, plus CAPI gating, plus fraud filtering, plus first-party analytics, all on one CNAME at SMB pricing? Try DataCops underneath.

---

## The mistake I see people make

Treating CMP selection as the entire compliance job. The banner is half the job. Enforcement is the other half. CNIL fined Google EUR 325M and Shein EUR 150M in September 2025 specifically because the banner UI implied choice while tracking continued. The leak is server-side. CAPI calls keep firing because the back-end pipeline never read the consent state. A CMP that does not enforce consent on outbound server events is increasingly the legal exposure point in 2026, not the banner.

The practitioner reality on Stape forums and DEV Community: front-end CMP correctly blocks the Pixel. Backend keeps firing CAPI events to Meta, Google, TikTok, LinkedIn because the server-side container never read the consent state. The single most common 2025-2026 misconfiguration in enterprise stacks. TCF 2.3 (Feb 28, 2026 deadline) makes it worse: invalid TC strings get treated as Limited Ads, with reported 60-80% CPM cuts.

The fix is not a different banner. It is an enforcement layer that gates the same pipeline that fires the server events on the consent the banner collects.

---

## Now your turn

If you run an enterprise CMP today, do you know whether your CAPI events are gated on the consent state your banner collects, or do they fire regardless?

---

Research by [DataCops](https://www.joindatacops.com) — first-party tracking, consent infrastructure, fraud prevention, and server-side CAPI for Meta, Google, TikTok, and LinkedIn.
