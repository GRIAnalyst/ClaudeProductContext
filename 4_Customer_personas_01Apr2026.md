# 4. My Incentives — Customer Personas & Client Profiles — 1 April 2026

> **Companion document to [1_User_manual_01Apr2026.md](1_User_manual_01Apr2026.md)**. All section references (e.g., "Section 4d", "Section 10") point to the User Manual for detailed setup steps, screen descriptions, and dependency maps.

---

## Platform Summary (as of Feb 2026)

| Metric | Value |
|--------|-------|
| Total licenses | ~62,948 |
| Total active users | ~60,697 |
| Monthly logins (Dec/Jan) | ~26,565 |
| Overall login rate | ~44% |
| Total end users (retailers/applicators) | ~58,118 |
| End user logins (Dec/Jan) | ~23,689 |
| Total L1 managers | ~4,227 |
| L1 manager logins | ~2,537 (60%) |
| Total L2 managers | ~570 |
| L2 manager logins | ~333 (58%) |

---

## Client Portfolio Overview

| # | Code Name | Client | Licenses | Active Users | Login Rate | Campaign Types | Audience | Reward Type |
|---|-----------|--------|----------|-------------|-----------|---------------|----------|-------------|
| 1 | FMCG | Adani Retailers | 20,422 | 20,422 | 8.8% | Type D, Type A | Retailers, DSMs, ASEs | Cash (98% force redemption) |
| 2 | FMCG 2 | Adani Wholesalers | 6,521 | 6,521 | 5.1% | Type D, Type A | Retailers, DSMs, ASEs | Cash (98% force redemption) |
| 3 | Luxury Stores Part 1 | Tanishq | 12,892 | 12,891 | 89.8% | Type A/B | RSO, SM, ABM | Cash (96% manual, 4% FR) |
| 4 | Luxury Stores Part 2 | Caratlane | 2,297 | 2,297 | 94.8% | Type A | End users | Cash (95-98% manual, 2-5% FR) |
| 5 | Retail Store Part 1 | Titan, Fastrack, Helios | 6,330 | 6,330 | 72.9% | Type A/B/D | ABM, CRO, SM | Cash (85% manual, 15% FR) |
| 6 | EyeRetail | Titan Eye Plus | 3,424 | 3,424 | 72.2% | Type D, Type A | RSO, SM, ASM | Cash |
| 7 | Auto Parts Part 1 | Gulf Oil Unnati | 9,458 | 7,227 | 34.6% | Type A in Type D | Retailers | Digital/Gulf Oil vouchers (manual) |
| 8 | Auto Parts Fancy 1 | Garware | 281 | 281 | 33.5% | Type G | Applicators | Not started yet |
| 9 | Auto Parts Part 2 | Gulf Oil DSS | 620 | 605 | 89.3% | Type A in Type D | Retailers | Cash/bank transfer (manual) |
| 10 | Auto Parts Part 3 | Gulf Oil GRS | 703 | 699 | 65.7% | Type A in Type D | Retailers | Gulf Oil vouchers (manual) |

---

## Customer Persona Archetypes

Based on cross-client analysis of the data, four distinct customer archetypes emerge. Each archetype has different usage patterns, feature needs, and platform interaction models.

### Archetype 1: FMCG Distributor Network

**Clients:** Adani Retailers, Adani Wholesalers

**Profile:**
- Very large user base (20K-27K combined licenses)
- Extremely low login rate (5-9%) — the vast majority of users are passive
- Audience is retailers, distributors, DSMs (District Sales Managers), and ASEs (Area Sales Executives)
- Incentives calculated automatically via Data Sources (Type D) with some direct awarding (Type A) for visibility payouts
- Cash rewards with ~98% force redemption — users don't come to the app to redeem; the system pushes payouts to them

**User Behavior:**
- Only 4-5K unique visitors/month log in out of 20K+ licenses
- Only ~20-25% of users ever log in at all, and those who do log in about once a month
- One-time KYC/bank/UPI submission spikes for new users, then activity drops
- A small number of DSMs/ASEs log in more frequently to check dashboards
- L1 managers show 18-22% login rates; L2 managers show ~47-66% login rates — management is more engaged than the field

**Features Used:**
- Target meter ([User Manual Section 4d — Optional KPIs](1_User_manual_01Apr2026.md#optional--kpis-individual---my-performance))
- Widgets dashboard ([User Manual Section 10 — Screen: Campaign Settings Type D](1_User_manual_01Apr2026.md#screen-campaign-settings-type-d))
- Splash screens ([User Manual Section 7h](1_User_manual_01Apr2026.md#7h-splash-screen-pop-ups))

**Key Analytics Questions:**
- Are users returning after first login, or is it one-and-done?
- Do DSMs/ASEs actually check their reportee dashboards?
- Which widgets are clicked vs. just displayed?
- Are nudges effective — do they lead to target meter views?
- Which ASE/DSM teams have the lowest KYC completion (blocking payouts)?
- How many retailers achieved targets but didn't receive payout due to incomplete KYC?

**Critical Risk Signals:**
- Retailers with zero logins after onboarding
- Retailers with logins but no target meter views
- ASE/DSM with no reportees added or low KYC completion rates
- Retailers receiving nudges but taking no action

**Product Dependency Chain** (ref: [User Manual Section 11](1_User_manual_01Apr2026.md#11-product-dependency-map--what-needs-to-be-set-up-first)):
```
Company Setup → Business Hierarchy → User Mapping →
Budget (Sponsor → Bucket → PO) → Type D Campaign →
Data Sources Pipeline (Custom table → Derived table → Final "F" table) →
Campaign Settings (table mapping, KPIs, nudges) →
Force Redemption Setup → KYC Verification (PAN → Bank L1/L2)
```

---

### Archetype 2: Luxury & Branded Retail Stores

**Clients:** Tanishq, Caratlane, Titan/Fastrack/Helios, Titan Eye Plus

**Profile:**
- Medium user bases (2.3K-12.9K licenses)
- High login rates (72-95%) — engaged user base that actively uses the platform
- Audience is internal retail staff: RSOs (Retail Sales Officers), Store Managers (SM), Area Business Managers (ABM), CROs (Chief Retail Officers)
- Mix of campaign types: Type A (direct awarding), Type B (approval-based distribution), Type D (automated calculations)
- Cash rewards with high manual redemption (85-96%) — users actively come to redeem

**User Behavior (Tanishq — flagship example):**
- ~400 store managers + 50-80 area managers log in frequently (5-20x/month)
- Remaining ~12K users log in once or twice a month
- Heavy usage concentrated among ~3-4% of licenses (the management layer)
- Monthly visits range 30K-55K with significant weekly spikes (up to 20K in peak weeks around Diwali)
- L1 manager login rate is 88%; L2 manager login rate is 80% — management is deeply embedded in the platform

**User Behavior (Titan/Fastrack/Helios):**
- ~600 store managers + 80-100 area managers log in very frequently
- Remaining ~5,200 frontline users log in once a month, likely around payday/redemption
- Weekly visits spike dramatically around month-end (3K normal → 7.5K peak)

**User Behavior (Caratlane — simplest model):**
- 94.8% login rate — nearly universal adoption
- Flat structure: all 2,297 users are end users, zero managers
- Type A only (direct awarding) — no approval workflows
- Almost all users log in and redeem manually

**Features Used:**
- Equal distribution ([User Manual Section 4b — Step v](1_User_manual_01Apr2026.md#step-v--allocate-points))
- Reportee addition ([User Manual Section 2b](1_User_manual_01Apr2026.md#2b-reportee-addition-and-approval-workflow))
- Certificates — ABM certificate allocation ([User Manual Section 7d](1_User_manual_01Apr2026.md#7d-certificates))
- Communication — email, WhatsApp, notification, SMS (for KYC, password setting)
- Target meter and target distribution ([User Manual Section 4d — Optional Target Distribution](1_User_manual_01Apr2026.md#optional--target-distribution))
- Widgets dashboard, splash screens
- Quizzes ([User Manual Section 7e](1_User_manual_01Apr2026.md#7e-quizzes))

**Key Analytics Questions:**
- Login & Activation: Are ABMs, CROs, SMs logging in after activation? Do logins spike near certificate allocation or payout periods? Are there stores where no user logs in at all?
- Feature Usage: Which widgets are clicked by each role? Are certificates viewed by ABMs before allocation? Do ABMs revisit certificate screens? Are CROs/SMs viewing dashboards but not taking actions?
- Targets: Does equal distribution reduce confusion or repeated target checks? Does target visibility correlate with higher redemption?
- Redemption: What % is forced vs. manual? How long does manual redemption take? Do timelines differ by store or role?

**Critical Risk Signals:**
- Stores with zero logins after go-live
- Users who log in but never view targets
- ABMs who don't allocate certificates
- Stores with targets achieved but no redemption initiated
- Roles that are consistently inactive

**Product Dependency Chain:**
```
Company Setup → Business Hierarchy → User Mapping →
Budget → Type A/B Campaign →
  Type B path: Approval Matrix → Distribution Controls → Point Allocation →
    Manager distributes → Approver approves
  Type A path: Direct point upload
→ Certificate Setup (template → allocation to ABMs) →
KYC Verification → Manual Redemption
```

---

### Archetype 3: Auto Parts / Lubricants Distributor Network

**Clients:** Gulf Oil Unnati, Gulf Oil DSS, Gulf Oil GRS

**Profile:**
- Range from small (600-700) to medium-large (9,500 licenses)
- Login rates vary dramatically: 34.6% (Unnati — large base), 65.7% (GRS), 89.3% (DSS — small, concentrated)
- Audience is exclusively retailers — flat structure with zero L1 or L2 managers (except Unnati which has none in the system)
- All use "Type A in Type D" — incentives calculated via Data Sources, then awarded as direct points
- Reward types vary: digital vouchers/Gulf Oil vouchers (Unnati, GRS) vs. cash/bank transfer (DSS)

**User Behavior (Gulf Oil Unnati — largest):**
- New program → 4,500 KYC submissions created a one-time spike
- Payouts in Sep-Oct-Nov caused burst usage during those periods
- Otherwise login frequency settles to 1-2x per month
- Only 2,500 of 9,454 end users logged in (26.4%)

**User Behavior (Gulf Oil DSS — highest engagement):**
- 540 of 617 end users log in (87.5%) — nearly universal for the base
- 300-400 weekly visits, 2K-3K monthly visits
- Quarterly Type D campaigns (2 per quarter)
- Small, concentrated user base drives high per-user engagement

**User Behavior (Gulf Oil GRS):**
- 459 of 699 users log in (65.7%)
- Quarterly Type D campaigns (1 per quarter) with occasional festive campaigns
- Engagement dashboard not visible — limited platform instrumentation

**Features Used:**
- Target meter ([User Manual Section 4d](1_User_manual_01Apr2026.md#optional--kpis-individual---my-performance))
- Widgets dashboard ([User Manual Section 10](1_User_manual_01Apr2026.md#screen-campaign-settings-type-d))
- Splash screens (Unnati) ([User Manual Section 7h](1_User_manual_01Apr2026.md#7h-splash-screen-pop-ups))
- Nudges (DSS, GRS) ([User Manual Section 4d — Optional Nudges](1_User_manual_01Apr2026.md#optional---adding-dynamic-kpi-based-nudges))

**Key Analytics Questions:**
- How many days after onboarding does the first login happen?
- Are there retailers who logged in once and never returned?
- Do login patterns drop after the first payout cycle, or do they increase to redeem?
- Which widgets are actually clicked vs. just shown?
- Are nudges effective — do they lead to target meter views? Are they more effective near month-end?
- How many retailers log in and directly go to redeem?
- Does the expiry date of points increase logins?
- At which step does KYC most commonly fail?

**Critical Risk Signals:**
- Retailers with zero logins after onboarding
- Retailers who log in but never view targets
- Retailers receiving nudges but taking no action
- Retailers eligible but never redeeming

**Product Dependency Chain:**
```
Company Setup → Product Hierarchy (for voucher SKUs if applicable) →
Budget → Type D Campaign →
Data Sources Pipeline (quarterly data cleaning → upload → derived table → "F" table) →
Campaign Settings (table mapping, target meter KPIs, nudges) →
KYC Verification → Manual Redemption (vouchers or cash)
```

---

### Archetype 4: Scan-and-Earn Field Network

**Clients:** Garware

**Profile:**
- Small user base (281 licenses)
- Low login rate (33.5%)
- Audience is applicators (field workers who apply products)
- Type G (Scan and Earn) — QR code scanning for points
- Redemption not started yet — program is early stage
- Fundamentally different interaction model: all users actively scan on the platform rather than passively receiving calculated incentives

**User Behavior:**
- Monthly visits growing: 150 (Jun) → 350 (Nov) — 2.3x growth over 6 months
- Weekly visits: 45-90 range
- 154 end users, 109 L1 managers, 17 L2 managers — unusually high manager-to-end-user ratio
- Only 61 end users and 29 L1 managers logging in — significant activation gap
- Widgets-based dashboard pending approval — limited feature deployment so far

**Features Used:**
- QR scanning ([User Manual Section 4f — Type G](1_User_manual_01Apr2026.md#4f-type-g--scan-code-and-earn))
- Widgets-based dashboard (pending) ([User Manual Section 10 — Screen: Campaign Settings Type G](1_User_manual_01Apr2026.md#screen-campaign-settings-type-g))

**Key Analytics Questions:**
- Do applicators log in after onboarding? How many drop off after the first login?
- Do users understand where to scan from in the app?
- How many users view the dashboard but never scan?
- Are scans loading correctly on low-network devices?
- What % of scans are successful vs. failed? Are failed scans causing permanent drop-offs?
- How many scans does an average user perform per week?
- Do users stop scanning after first success?
- Are there regions with consistently low scan activity?

**Critical Risk Signals:**
- Users who logged in but never scanned
- Users who scanned once and never returned
- Users inactive for 30+ days
- Failed scans causing permanent drop-offs
- Regions with consistently low scan activity

**Product Dependency Chain** (ref: [User Manual Section 11 — Type G Dependencies](1_User_manual_01Apr2026.md#campaign-prerequisites-by-type)):
```
Company Setup → Product Hierarchy (SKUs for scannable products) →
Budget → Type G Campaign →
SKU Codes Upload (scan codes with expiry dates) →
Scan Validation Matrix (points per SKU, optionally per role/tier) →
Optional: Final Scan Table (for milestone-based earning) →
Incentive Formula Configuration →
KYC Verification → Redemption Setup (pending)
```

---

## User Role Personas (Cross-Client)

These personas describe the actual humans using the platform, independent of which client they belong to. Each persona maps to specific screens and workflows in the User Manual.

### Persona 1: The Field Retailer / Salesperson

**Who they are:** The largest user group (~58K users, ~41% login rate). Retailers, distributors, store sales officers, applicators. They are the reason the platform exists — incentivizing their sales behavior is the core value prop.

**How they use the platform:**
- Log in 1-2x/month, usually around payday or when nudged
- Check target meter to see progress against KPIs
- View earned/redeemed/balance points on home dashboard
- Submit claims (Type C) or scan QR codes (Type G) if applicable
- Redeem points for cash or vouchers
- Complete KYC once (PAN, bank/UPI) — this is often the biggest friction point

**Key screens they interact with** (ref: [User Manual Section 10](1_User_manual_01Apr2026.md#10-screen-inventory)):
- Participant Mobile App — Home (points dashboard, campaign banners)
- Participant Mobile App — Campaign View (Type D for target meters, Type C for claims, Type G for scanning)
- Participant Mobile App — Rewards (catalogue, redemption)
- Participant Mobile App — Profile & KYC (PAN, bank, UPI submission)

**Setup required to serve this persona** (ref: [User Manual Section 11](1_User_manual_01Apr2026.md#11-product-dependency-map--what-needs-to-be-set-up-first)):
- User onboarded with correct role/scope/hierarchy ([Section 2a](1_User_manual_01Apr2026.md#2a-adding-users-individual-or-bulk))
- Added as campaign participant ([Section 3d](1_User_manual_01Apr2026.md#3d-add-participants-to-the-campaign))
- KYC verification flow configured ([Section 6a-6e](1_User_manual_01Apr2026.md#6a-reward-settings-configuration))
- Rewards catalogue mapped and activated ([Section 6a — Reward Catalogue Settings](1_User_manual_01Apr2026.md#reward-catalogue-settings))

**Pain points:**
- KYC completion is the single biggest blocker to getting paid
- Low engagement unless nudges/communications actively pull them in
- Many don't return after first login if the value isn't immediately clear
- Force redemption (98% at Adani) vs. manual redemption (85-96% at Titan) reflects how "passive" vs. "active" the user base is

---

### Persona 2: The Store / Area Manager

**Who they are:** ~4,800 users across L1 and L2 manager roles. Store Managers (SM), Area Business Managers (ABM), Area Sales Executives (ASE), District Sales Managers (DSM), CROs. They are the middle management layer.

**How they use the platform:**
- Log in 5-20x/month (power users of the platform)
- View team performance dashboards — by KPI or by user
- Distribute targets to team members (Type D)
- Distribute and approve points (Type B)
- Approve invoice claims from salespeople (Type C)
- Allocate certificates to team members
- Add new reportees (salespeople/retailers) to the platform
- Submit KYC on behalf of reportees
- View leaderboards filtered by their scope/region

**Key screens they interact with** (ref: [User Manual Section 10](1_User_manual_01Apr2026.md#10-screen-inventory)):
- Manager Mobile App — Team Performance (by KPI, by user, leaderboard)
- Manager Mobile App — My Reportees (add users, manage KYC)
- Campaign Settings screens (for Type B approval, Type C claim approval, Type D target distribution)

**Setup required to serve this persona:**
- Mapped in business hierarchy at the correct level ([Section 1c](1_User_manual_01Apr2026.md#1c-setting-up-and-updating-the-business-hierarchy))
- Set as reporting manager for their team members
- Added to approval matrix (Type B or Type C) ([Section 4b — Step iv](1_User_manual_01Apr2026.md#step-iv--upload-the-approval-matrix), [Section 4c — Step iv](1_User_manual_01Apr2026.md#step-iv--upload-the-claim-approval-matrix))
- Added as "Report Owner" on relevant campaigns for leaderboard access
- Certificates allocated to them for distribution ([Section 7d](1_User_manual_01Apr2026.md#7d-certificates))

**Pain points:**
- Approval matrix errors (inactive users, wrong hierarchy level) block workflows
- If not properly mapped in hierarchy, they can't see their team's data
- Need to understand the difference between "reporting hierarchy" and "business hierarchy"
- Bulk operations (approval, KYC verification) are tedious one-by-one via UI

---

### Persona 3: The Client Stakeholder

**Who they are:** 1-3 people per client. The client-side program owner — usually from HR, Sales Operations, or Channel Sales at the brand. They do NOT operate the platform directly; all configuration and admin actions are performed by the GRG India Product Admin (account manager) on their behalf.

**How they interact with the program:**
- Provide business requirements, campaign rules, and incentive structures to the GRG account manager
- Share raw data (sales files, user lists, hierarchy changes) for the GRG team to clean and upload
- Review campaign performance via dashboards or reports shared by the GRG team
- Approve budgets and PO allocations (sign-off, not platform execution)
- Request changes to user lifecycle (onboarding, role changes, deactivation) — GRG team executes
- Coordinate with GRG on data pipeline timing, campaign launch schedules, and payout cycles

**What they see (view-only or limited access):**
- Analytical Dashboard (if configured via Homepage Builder for their role)
- Campaign performance summaries and downloadable reports
- May have a Client Administrator role in the system with restricted activity set (see [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — several activities have been removed from Client Administrator)

**What the GRG Product Admin does on their behalf** (ref: [User Manual Sections 1-7](1_User_manual_01Apr2026.md#1-company-setup-step-by-step)):
- All configuration in Sections 1 (Company Setup) through 7 (Engagement Features)
- Campaign creation, budget setup, hierarchy management, approval matrix uploads
- Data pipeline: cleaning client-provided Excel → upload to Data Sources → derived tables → campaign linking
- Ongoing: monthly/quarterly data uploads for Type D campaigns, user management, budget top-ups

**Pain points:**
- Dependency on GRG team for all platform changes — turnaround time can be a bottleneck
- Lack of direct visibility into data pipeline status (is my data uploaded? when will calculations run?)
- Understanding the dependency chain (what needs to exist before what) to provide inputs in the right order
- PO approval workflow confusion — the Point Curator approves, not the Campaign Owner

---

### Persona 4: The GRG India Internal Team (Product Admin / Account Manager)

**Who they are:** The My Incentives operations team at GRG India. The Product Admin is the account manager who handles all platform configuration, data operations, and ongoing management for assigned clients. They are the hands-on operators of the platform — the client stakeholder provides requirements, and the Product Admin executes.

**How they use the platform:**
- All system-level configuration (license management, domain whitelisting, program setup, access control, SSO)
- Campaign creation, configuration, and lifecycle management for all campaign types
- Budget setup: create sponsors, buckets, POs; allocate points to budget owners
- Data pipeline management (cleaning client-provided data, uploading, derived table creation, campaign linking)
- Business hierarchy and product hierarchy setup and maintenance
- Approval matrix uploads and validation template configuration
- User lifecycle management (onboarding, bulk upload, role/scope assignment, activation/deactivation)
- KYC verification workflows (PAN, bank, UPI approval)
- TDS certificate management
- Rewards catalogue configuration (Tolshop coordination)
- Engagement feature setup (certificates, quizzes, hub, splash screens, communications)
- Helpdesk/Zoho integration management

**System roles:**
- Product Admin — full configuration access across all modules ([User Manual — System Roles](1_User_manual_01Apr2026.md#system-roles))
- Finance Admin — TDS, PAN L2, Payout L2, budget curator
- System Report Owner — report generation
- Point Curator — campaign budget/PO approval

**Key operational workflows:**
- Monthly Type D data cycle: receive client Excel → clean data → upload to Data Sources → create derived tables → verify → link to campaign → trigger calculations ([Section 5b](1_User_manual_01Apr2026.md#5b-data-workflow-cleaning-upload-verification-and-table-creation))
- KYC approval cycle: L1 document verification → L2 penny drop verification → manual review of mismatches ([Sections 6b-6e](1_User_manual_01Apr2026.md#6b-kyc--pan-card-approval-workflow))
- Quarterly TDS certificate upload ([Section 6f](1_User_manual_01Apr2026.md#6f-tds-management))
- Campaign launch cycle: budget setup → campaign creation → participant upload → approval matrix → go-live
- User onboarding cycle: bulk upload users → assign roles/scopes → map to hierarchy → trigger activation emails

---

## Client Engagement Patterns

### Login Rate Tiers

**Tier 1 — High Engagement (>70% login rate):**
Tanishq (89.8%), Caratlane (94.8%), Titan/Fastrack/Helios (72.9%), Titan Eye Plus (72.2%), Gulf Oil DSS (89.3%)

Common traits: internal sales teams (not external retailers), relatively smaller user bases, cash rewards with manual redemption driving active usage, strong management layer using the platform daily.

**Tier 2 — Medium Engagement (30-70% login rate):**
Gulf Oil GRS (65.7%), Gulf Oil Unnati (34.6%), Garware (33.5%)

Common traits: external retailer/applicator networks, quarterly or periodic campaign cycles (not continuous), voucher-based rewards (less urgency to log in than cash).

**Tier 3 — Low Engagement (<10% login rate):**
Adani Retailers (8.8%), Adani Wholesalers (5.1%)

Common traits: very large external distributor networks, force redemption removes the need to actively engage, users are passive recipients of incentive payouts.

### Feature Usage by Client Segment

| Feature | FMCG (Adani) | Luxury Retail (Tanishq/Titan) | Auto Parts (Gulf) | Scan (Garware) |
|---------|-------------|-------------------------------|-------------------|----------------|
| Target Meter | Yes | Yes | Yes | No |
| Widgets Dashboard | Yes | Yes | Yes | Pending |
| Splash Screens | Yes | Yes | Yes (Unnati) | No |
| Equal Distribution | No | Yes | No | No |
| Certificates | No | Yes (ABM allocation) | No | No |
| Quizzes | No | Yes (Titan Eye) | No | No |
| Nudges | No | Yes (notifications/SMS) | Yes (DSS, GRS) | No |
| Target Distribution | No | Yes (Titan Eye) | No | No |
| QR Scanning | No | No | No | Yes |
| Reportee Addition | No | Yes | No | No |
| Force Redemption | Yes (98%) | Partial (4-15%) | No | No |
| Communications | Basic | Full (email/WhatsApp/SMS/notification) | Basic | Basic |

Cross-reference: Each feature maps to a specific setup workflow in the User Manual. See [Section 11 — Engagement Feature Dependencies](1_User_manual_01Apr2026.md#engagement-feature-dependencies) for what needs to be configured before each feature works.

---

## Campaign Type Usage by Client

| Campaign Type | User Manual Section | Clients Using It | Key Differentiator |
|--------------|--------------------|-----------------|--------------------|
| Type A — Direct Awarding | [Section 4a](1_User_manual_01Apr2026.md#4a-type-a--direct-awarding-of-points) | Caratlane, Adani (visibility payouts), Titan group, Gulf (within Type D) | Simplest setup; bulk point upload |
| Type B — Approval-Based | [Section 4b](1_User_manual_01Apr2026.md#4b-type-b--approval-based-point-distribution) | Tanishq, Titan/Fastrack/Helios | Requires approval matrix; store-level distribution |
| Type D — Automated Calculation | [Section 4d](1_User_manual_01Apr2026.md#4d-type-d--automated-sales-based-incentive-calculation) | Adani, Titan group, Titan Eye, Gulf Oil (all 3) | Most complex; requires full Data Sources pipeline |
| Type G — Scan and Earn | [Section 4f](1_User_manual_01Apr2026.md#4f-type-g--scan-code-and-earn) | Garware | Requires product hierarchy + scan codes; real-time point earning |

---

## Redemption Behavior Patterns

| Client | Primary Mode | FR vs Manual | Redemption Rate | Key Questions |
|--------|-------------|-------------|----------------|---------------|
| Adani Retailers | Cash | 98% FR, 2% manual | High (forced) | Are users even aware they're getting paid? |
| Adani Wholesalers | Cash | 98% FR, 2% manual | High (forced) | Same as above |
| Tanishq | Cash | 4% FR, 96% manual | >95% | How long does manual redemption take? |
| Caratlane | Cash | 2-5% FR, 95-98% manual | >95% | Simplest flow — direct cash |
| Titan/Fastrack/Helios | Cash | 15% FR, 85% manual | >95% | Do timelines differ by store or role? |
| Titan Eye Plus | Cash | Unknown split | Unknown | Similar to Titan group expected |
| Gulf Oil Unnati | Digital/Gulf vouchers | 100% manual | Unknown | Which vouchers face most delays? |
| Gulf Oil DSS | Cash/bank transfer | 100% manual | Unknown | Does expiry date drive logins? |
| Gulf Oil GRS | Gulf Oil vouchers | 100% manual | Unknown | Are there repeat redemptions? |
| Garware | Not started | N/A | N/A | Program too early |

KYC dependency: All cash redemption requires completed KYC verification ([User Manual Section 6b-6e](1_User_manual_01Apr2026.md#6b-kyc--pan-card-approval-workflow)). The KYC completion rate directly determines payout success.

---

## Product Analytics Event Model (Phase 1)

The platform tracks user behavior across four event categories, each mapping to specific product features described in the User Manual:

### Category 1: Login & Activation
**Maps to:** [User Manual Section 8 — Login Flow](1_User_manual_01Apr2026.md#login-flow), [Section 2 — User Onboarding](1_User_manual_01Apr2026.md#2-user-onboarding)

Key events: user_activated, login_success, first_login_completed, repeat_login, monthly_active_login, manager_login, post_payout_login, first_login_delay, login_dropoff, payout_window_login

**What it answers:** Are users returning after onboarding? How quickly do they activate? Which roles have the lowest engagement?

### Category 2: Feature & Usage (Dashboard / Widgets)
**Maps to:** [User Manual Section 8 — Home Page](1_User_manual_01Apr2026.md#home-page), [Section 10 — Participant Mobile App Home](1_User_manual_01Apr2026.md#screen-participant-mobile-app--home)

Key events: dashboard_viewed, widget_viewed, widget_clicked, campaign_viewed, campaign_opened, dashboard_scrolled, feature_time_spent, reportee_section_viewed, splash_shown, splash_interacted, early_exit, no_action_session

**What it answers:** Which widgets drive engagement? Are users scrolling or bouncing? Do splash screens lead to action?

### Category 3: Target & Engagement (Target Meter + Nudges)
**Maps to:** [User Manual Section 4d — KPIs](1_User_manual_01Apr2026.md#optional--kpis-individual---my-performance), [Section 4d — Nudges](1_User_manual_01Apr2026.md#optional---adding-dynamic-kpi-based-nudges)

Key events: target_meter_viewed, target_check_timing, target_month_end_view, nudge_received, nudge_clicked, nudge_ignored, nudge_repeat, target_view_post_nudge, target_view_delay

**What it answers:** Do nudges drive target meter views? Are targets checked early or only at month-end? Does target visibility correlate with higher redemption?

### Category 4: Redemption Behavior
**Maps to:** [User Manual Section 6 — Rewards & Redemption](1_User_manual_01Apr2026.md#6-budget-management-rewards--redemption), [Section 8 — Rewards Section](1_User_manual_01Apr2026.md#rewards-section)

Key events: redemption_eligible, redemption_initiated, redemption_completed, redemption_failed, payout_initiated, payout_completed, payout_failed, payout_retry, kyc_started, kyc_completed, kyc_failed, expiry_driven_login

**What it answers:** Where in the redemption funnel are users dropping off? Is KYC the bottleneck? Does point expiry drive urgency?

### Category 5: Zero / Low Usage (Critical Alerts)
**Maps to:** All sections — this is a cross-cutting risk layer

Key signals per archetype:
- FMCG: retailers with zero logins, ASE/DSM with no reportees added, retailers blocked from payout due to KYC
- Luxury Retail: stores with zero logins after go-live, ABMs not allocating certificates, stores with targets achieved but no redemption
- Auto Parts: retailers who log in but never view targets, retailers eligible but never redeem
- Scan: users who scanned once and never returned, regions with consistently low scan activity
