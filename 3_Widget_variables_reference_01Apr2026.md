# 3. Widget Variables — Master Reference — 1 April 2026
**Source:** Widgets variables_MASTER_2025.xlsx
**Last Updated:** 1 April 2026

---

## Widget Types Overview

| ID | Widget Type | Description | Sprint |
|----|------------|-------------|--------|
| A | Status Card | Single status card for account details or verification status | Sep 2025 |
| B | Metric Card | Single variable card for KPI, sales, points, or earnings | Sep 2025 |
| C | Progress Bar | Single progress bar for individual or team goal tracking | Sep 2025 |
| D | Campaign Card | Multi-variable card with 4-6 campaign variables | Sep 2025 |
| E | Text Card | Text card for greetings, dividers, or extra details | Sep 2025 |
| F | Quick Actions | Card with multiple shortcuts to key pages | Sep 2025 |
| G | Icon Card | Profile info card with icons | April 2026 |

---

## Widget A: Status Card

**Config steps:** Select variable → Show icon (Yes/No)

**Pre-fixed Variables:**

| # | Variable | Options |
|----|----------|---------|
| 1 | UPI verified | Yes / No |
| 2 | Bank verified | Yes / No |
| 3 | PAN verified | Yes / No |

---

## Widget B: Metric Card

**Config steps:**
1. Widget title (free text, e.g., "Earned" / "Balance")
2. Widget unit (free text, 6 char limit, e.g., "INR" / "Points")
3. Unit as prefix / suffix (radio)
4. Select metric source: Global / Campaign / Data Sources (radio)

### If Global — Variable Dropdown:

| Variable | Sprint |
|----------|--------|
| Earned points | Sep 2025 |
| Redeemed points | Sep 2025 |
| Expired points | Sep 2025 |
| Balance points | Sep 2025 |
| Earned points from active campaigns | ND 2025 |
| Redeemed points from active campaigns | ND 2025 |
| Balance points from active campaigns | ND 2025 |

### If Campaign:
5. Select campaign name (dropdown — active campaigns)
6. Select metric: Earned / Redeemed / Expired / Balance points

### If Data Sources:
5. Select Data Sources table (dropdown)
6. Select unique identifier (data sources table) → Unique ID
7. Select unique identifier (user table) → Employee ID
8. Select column (dropdown)

---

## Widget C: Progress Bar

**Config steps:**
1. Name widget (free text)
2. Select category: Global or Data Sources (radio)

### If Global — Numerator Variables:

| Variable | Sprint |
|----------|--------|
| Payout verified reportees | Sep 2025 |
| PAN verified reportees | Sep 2025 |
| Active reportees | Sep 2025 |
| Reportees earning points | Sep 2025 |
| Direct reportees | Sep 2025 |
| Total reportees | Sep 2025 |
| Payout verified x indirect reportees | ND 2025 |
| PAN verified x indirect reportees | ND 2025 |

### Denominator Variables:

| Variable | Sprint |
|----------|--------|
| Active reportees | Sep 2025 |
| Direct reportees | Sep 2025 |
| Total reportees | Sep 2025 |

### Percentage Variables:

| Variable | Sprint |
|----------|--------|
| Payout verified / Active reportees | Sep 2025 |
| Bank verified / Active reportees | Sep 2025 |
| UPI verified / Active reportees | Sep 2025 |
| Users earning points / Active reportees | Sep 2025 |
| Payout verified / Total reportees | Sep 2025 |
| Bank verified / Total reportees | Sep 2025 |
| UPI verified / Total reportees | Sep 2025 |
| Users earning points / Total reportees | Sep 2025 |

### If Data Sources:
3. Select Data Sources table
4. Select unique identifier (data sources table)
5. Select unique identifier (user table)
6. Select numerator column
7. Select denominator column
8. Select percentage column

---

## Widget D: Multi-Variable Campaign Card

**Config steps:**
1. Widget title (free text)
2. Select number of metrics: 4 or 6 (radio)
3. Select metric source: Data Sources / Campaign variable (radio)

### If Campaign:
4. Select campaign (dropdown — active campaigns)
5. Select variables (multi-select dropdown, 4 or 6)
   - Each variable auto-populates name → user can edit description
   - Unit: free text (6 char limit)
   - Unit position: Prefix / Suffix

### If Data Sources:
4. Select Data Sources table
5. Select unique identifier (data sources table)
6. Select unique identifier (user table)
7. Select 4 or 6 columns as variables

**Example layouts:**
- Campaign: Earned / Redeemed / Expired / Balance
- Data Sources: Total Sales / Total Target / Achievement % / Incentives Earned

---

## Widget E: Text Card

**Config steps:**
1. Enter width of text box
2. Enter text (multi-line, 100 char limit, rich text: bold, italic, underline, bullets)
3. Placement alignment: Left / Center / Right

**Available Variables (auto-populate from user profile):**

| Variable | Example |
|----------|---------|
| First + Last name | Kishor Ramesh |
| Email ID | kishor@anandstore.com |
| Registered Entity name | Anand Kirana Store |
| Department | Delhi |
| Scope | Retailer |
| Tier | Bronze |

---

## Widget F: Quick Actions / Shortcuts

**Config steps:**
1. Widget title (name)
2. Select shortcut type (dropdown: Global variable based shortcut)
3. Select icon (predefined icon set)
4. Label shortcut (pre-filled editable, 15 char limit)
5. Arrange layout (drag & drop ordering, fixed grid with center alignment)

**Available shortcuts:** Rewards (Redeem points), My Profile, Submit Bank, Submit PAN, Submit UPI, My Wallet, Hub/Documents, Support, etc.

System passes user_id and campaign_id (if campaign-based).

---

## Widget G: Icon Card (April 2026)

| # | Variable | Icon Type |
|----|----------|-----------|
| 4 | First + Last name | 1 icon |
| 5 | Email ID | 1 icon |
| 6 | Registered Entity name | 1 icon |
| 7 | Department | 1 icon |
| 8 | Designation | — |
| 9 | Scope | 1 icon |
| 10 | Tier | Tier from tier selection |

---

## Click Destinations & Redirection

### KPI → Widget Type → Click Destination

| KPI | Widget Type | Source | Click Destination | Purpose |
|-----|------------|--------|-------------------|---------|
| Total Points (e.g., 2,750) | Metric Card | Global | Modal: points_breakdown OR /points/history | Breakdown: earned vs redeemed vs pending; transactions list |
| Total Points Redeemed | Metric Card | Global | Modal: redemption_breakdown | Redeem history, nearest redemption offers |
| Expired Points | Metric Card | Global | Modal: expired_points_detail | List of expired points & reasons |
| Balance Points | Metric Card | Global | Modal: balance_points_detail | Current balance split by campaign |
| Bank/PAN/UPI Verified | Status Card | Global | /profile/verification OR Modal: verification_status | Verification steps, docs required, CTA to upload |
| Active Campaigns – % Total Sales | Progress Widget | Campaign/DS | Modal: campaign_progress OR /campaign/:id | Time-series, milestones, filters |
| Active Campaigns – Unique Products Sold | Progress Widget | Campaign/DS | Modal: product_mix OR /campaign/:id?products | Product-level contributions, SKU list |
| Count Retailers Earning Points | Metric Card | Campaign/DS | Modal: retailer_list (paginated) | Retailer table, points per retailer, filters |
| Achievement >95% Count | Metric/Slab Card | Campaign/DS | Modal: achievement_slabs | Slab distribution by % ranges |
| Quick Actions | Shortcut Grid | Global | Navigation to respective pages | Trigger quick flows |
| Announcements / Text | Text Widget | Global | Modal or /announcement | Full announcement content |
| Campaign Summary | Campaign Widget | Campaign | /campaign/:id | Full campaign KPIs, leaderboards, rules |

### System Re-direction Pages

**Rewards:**

| Short Form | Re-direction Page |
|-----------|------------------|
| Points | Total earned points detail page |
| Redeemed | Redeemed points detail page |
| Expired | Expired points detail page |
| Balance | Balance points detail page |
| Redeem | Rewards catalogue |
| Wallet | My wallet - my transactions |

**My Profile & KYC:**

| Short Form | Re-direction Page |
|-----------|------------------|
| Get help | Support |
| Profile | My profile |
| Tier | Tier page |
| Submit Bank | Bank submission page |
| Submit Pan | PAN submission page |
| Submit UPI | UPI submission page |

**Campaign & Homepage:**

| Short Form | Re-direction Page |
|-----------|------------------|
| Campaign | View campaign (requires campaign_id) |
| Documents | View hub |

**My Reportees:**

| Short Form | Re-direction Page |
|-----------|------------------|
| My team | My reportees |

### My Reportees Widget → Filter Pre-configuration

When redirecting from the My Reportees summary widget on the homepage to the actual reportees page, the redirect can be configured to auto-apply one or more filters:

| Filter | Options |
|--------|---------|
| Status | Active / Draft / Inactive |
| Direction | Direct / Indirect |
| Payout Completed | Yes / No |
| PAN Completed | Yes / No |

---

## Admin Configuration for Clickable Widgets

| Setting | Description | Type |
|---------|-------------|------|
| Widget Name | Display name on dashboard | Text field |
| Widget Type | Metric / Progress / Campaign / Text / Shortcut / Status | Dropdown |
| KPI Source | Data API or table from backend | Dropdown/Search |
| KPI Variables | Parameters needed for API | Key-Value |
| Visibility – Role | Roles that can view widget | Multi-select |
| Visibility – Campaign Type | Campaign types where widget appears | Multi-select |
| Mandatory Widget | Lock widget from user removal | Toggle |
| Click Behaviour Type | Entire Card or Component (future) | Radio button |
| Destination Type | Modal / Side Panel / Page | Dropdown |
| Destination Mapping | Predefined destination ID or page route | Dropdown/Search |
| Auto Variable Mapping | Pulls default params from session (user, campaign, org) | Toggle |
| Manual Variable Override | Admin-defined static values | Key-Value |
| Preview Click | Test destination in CMS | Button |
