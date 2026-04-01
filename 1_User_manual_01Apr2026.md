# 1. My Incentives — Product Reference — 1 April 2026

## Platform Overview

My Incentives is an end-to-end incentive management SaaS platform for channel partners, retailers, salespeople, and influencers. It automates incentive calculations, manages rewards and redemptions, and drives engagement through gamification — replacing manual Excel-based tracking with a configurable, real-time system.

**Core value prop:** Automate incentive design, calculation, payout, and engagement across distributed sales teams and channel partners — with full visibility, compliance (KYC/TDS), and budget controls.

**Access:** Web admin panel (clients.myincentives.in) + mobile app (iOS/Android) for end users.

---

## User Architecture

> **Full role-activity mapping:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) for the complete matrix of 113 activities across 7 admin roles (CS Admin with Proxy, CS Admin Standard, Junior Admin, Client Administrator, Product Admin, Finance Admin, Documents Approver). Each section below includes role-specific callouts for key activities.

### User Types
- **Client Users:** Licensed/paid users (retailers, salespeople, channel partners, influencers) who participate in campaigns, earn and redeem points
- **System Users:** Internal/unlicensed users for administration

### System Roles
- **Product Admin:** Full program setup and configuration — can set up client programs and all product configurations (85+ activities)
- **Finance Admin:** Admin user with finance rights to approve campaign budgets, TDS, PAN L2, Payout L2 (limited activity set)
- **System Report Owner:** User exclusively with rights to generate reports
- **Point Curator:** Approves campaign budget/PO mappings (mapped per Sponsor)
- **Documents Approver:** KYC document approval access — PAN L1, Payout L1, profile viewing (7 activities)

### Client Roles
Customizable per client. Typical hierarchy: National Head → Regional Head → City Manager → Store Manager → Salesperson. Client roles are assigned based on the functions the user is expected to carry out. Note: Client Administrator role has had several activities **removed** in recent updates — see [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) for the full list of removed activities.

### Domain Whitelisting
User registration restricted to whitelisted email domains per client (e.g., only @gulf.co.in and @grgindia.in). If a user tries to register with a non-whitelisted domain (e.g., @yahoo.com), the system will reject the registration.

---

## 1. Company Setup (Step-by-Step)

> **Activities & Roles:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — Company & Settings Configuration.
> Key activities: A0001 (View Settings), A0007 (Go Inside Settings), A0008 (Edit Company Profile — Product Admin only), A0012 (Configure Access Control — Product Admin only), A0022 (Org Structure), A0043 (Security Policy — CS Proxy + Product Admin), A0054 (SSO — Product Admin only).
> Client Administrators can view settings and org structure but cannot edit company profile, access control, or SSO.

### 1a. License Management & Whitelisting

New users can be added based on available licenses. To add new licenses, contact GRG admin with the required details.

**Initial Login:**
1. Go to clients.myincentives.in
2. Log in using your admin user ID and password (or email OTP)

**Product Licensing and Payment Terms:**
Navigate to Settings > Company > Company Profile to view:
- Allotted Licenses (total purchased), Used Licenses, Available Licenses
- License Expiry Date

**Other Configurations (Settings > Company > Company Profile):**
- **Financial Year:** Apr to Mar (or as configured)
- **Transactions Logic:** "Points with earlier expiry date will be used first" (default) or "FIFO i.e. points received first will be used first"
- **Enable Hierarchy:** Yes/No — controls whether business hierarchy features are active
- **Enable comments in all approvals:** Yes/No — when enabled, all approval workflows include a comments field
- **Proxy Approval Mechanism:** Yes/No — controls whether proxy user access requires target user approval (see Section 2c)
- **Allow Redemption by Proxy User?** Yes/No — controls whether proxy users can perform redemption actions
- **Allow user to edit mobile number and email ID:** Yes/No — controls whether end users can self-edit their contact details

**Configuring Domain Whitelisting:**
1. Navigate to Company settings
2. Add the allowed email domains (e.g., grgindia.in, gulf.co.in)
3. Only users with email addresses from whitelisted domains can register

### 1b. Setting Up Users, Roles, Departments, Designations, and Scopes

**Adding Roles:**
1. Navigate to the user management section
2. For System Users: assign Product Admin, System Report Owner, or Finance Admin roles
3. For Client Users: assign customized client roles based on the program's needs

**Adding Departments and Designations:**
- Departments and designations are pre-defined in the system by GRG admin based on client requirements
- Product Admin (GRG account manager) typically performs this; Client Administrator role can also access if needed
- Navigate to Company > Organization Structure to add departments and designations

**Adding Scopes:**

Scopes allow the platform to restrict or customize visibility across engagement features such as posts, recognitions, and galleries. Each user can be tagged with one or more Scopes (e.g., Region = Mumbai, Department = Sales, Role = Manager).

1. Navigate to Company > Organization Structure
2. Add new scopes in the scope management section

**Assigning Scopes to Users:**

Method 1 — Manual Scope Assignment:
1. Go to User Management > Edit User
2. Use the multi-select dropdown to assign scopes like Region, Department, or Role

Method 2 — Bulk Upload via CSV:
1. Prepare a file with a Scopes column containing comma-separated values
2. Upload in User Management > Upload Users
3. The system validates scope entries and logs all changes in the Audit Log

If no scope is selected by a user, the system automatically applies a default (either first alphabetical or as defined by business rules). This default persists for subsequent sessions.

The 'scope POC' receives an email if there are any SSO-related errors for users in that scope or within the business hierarchy.

### 1c. Setting Up and Updating the Business Hierarchy

> **Activities & Roles:** A0081 (View Hierarchy — all admin roles), A0082 (Manage Hierarchy — removed from Client Admin), A0083 (Map Hierarchy to User — all admin roles). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

**Purpose:** The business hierarchy exists in addition to the reporting structure within user management. It provides:
1. Cascading data visibility — managers at a given business hierarchy level can see data for all nodes below them, even if they are not the direct reporting manager
2. Approval routing — users mapped to a business hierarchy node can approve requests (Type B distribution approvals, Type C claim approvals, Type F referral approvals) even if they are not the reporting manager

**One-Time Setup:**
1. Navigate to Company > Hierarchy > Actions within "Business hierarchy" > Configure
2. Set the number of levels (e.g., Country, Region, City, Store) — this can only be set once
3. Name each level
4. Add values (data entries) within each level — values represent geographic zones, business units, or organizational elements, NOT users

**Common configuration error:** The values of the business hierarchy are NOT users. They refer to geographical zones, business units, or other structural elements. Once the hierarchy structure is set up, users are separately mapped to values based on their position/seniority.

**Mapping Users to the Business Hierarchy:**
1. Navigate to User Management > Hierarchy Mapping
2. This displays all users in the company

Method 1 — Individual Mapping:
1. Click Actions > Edit in the row of the relevant user
2. Select the relevant level (e.g., Level 3 for a City Manager)
3. Map to specific values (e.g., Mumbai) and select all stores under that city, or a relevant sub-section

Method 2 — Bulk Upload:
1. Click "Upload Mapping" (top right) > "Download Standard Template"
2. The template's 'reference' tab shows all existing hierarchy paths
3. Map each user to ALL relevant paths they need visibility into

Example hierarchy paths:

| Level 1 | Level 2 | Level 3 | Hierarchy Path |
|---------|---------|---------|----------------|
| India | West | Mumbai | india>west>mumbai |
| India | West | Pune | india>west>pune |
| India | South | Bangalore | india>south>bangalore |

Example user mapping (National Sales Manager mapped to all paths):

| User ID | Email | Hierarchy Level | Hierarchy Path |
|---------|-------|-----------------|----------------|
| A01 | NationalSalesManager@grgindia.in | 1 | india>west>mumbai |
| A01 | NationalSalesManager@grgindia.in | 1 | india>west>pune |
| A01 | NationalSalesManager@grgindia.in | 1 | india>south>bangalore |
| A04 | WestZonalManager@grgindia.in | 2 | india>west>mumbai |
| A04 | WestZonalManager@grgindia.in | 2 | india>west>pune |
| A08 | MumbaiCityManager@grgindia.in | 3 | india>west>mumbai |

4. Add a new version ID in the file
5. Upload the file and click "Submit"
6. Click Actions > "Mark for Process" — the file will update within 15 minutes

### 1d. Setting Up and Updating the Product Hierarchy

**Purpose:** The product hierarchy is a separate hierarchy for SKUs/products. It is used in claim-based (Type C), referral (Type F), and scan-and-earn (Type G) campaigns to define which products are incentivized and at what rates. Only SKUs added in the product hierarchy can earn incentives.

**One-Time Setup:**
1. Navigate to Company > Hierarchy > Actions within "Product hierarchy" > Configure
2. Select the number of nodes within the hierarchy
3. Name each level — the last level defaults to "SKU" (can be renamed to product code, product category, etc.)
4. For the last level (SKU), select which properties are mandatory:
   - Compulsory properties: SKU code and description (cannot be changed)
   - Optional properties: size, volume, weight, SKU cost, SKU price

**Ongoing Maintenance:**
- Add new data values at any level — select both the label and the parent value
- Add new SKUs or mark discontinued SKUs as inactive
- Bulk upload SKUs using a template (format depends on properties selected in setup)

### 1e. Email Support & Zoho Helpdesk Integration

Configurable integration with Zoho for support ticket management. Contact GRG admin for setup.

**Multi-Company Ticket Routing (U210117):**
For users belonging to multiple companies, the Zoho integration supports department-based ticket segregation and auto-phone mapping:

- Each client is mapped to a dedicated Zoho Desk Department with a client-specific support email (e.g., clientname_support@domain.com)
- Tickets are auto-tagged to the corresponding department
- Account-Contact mapping: Zoho Account = Company, Zoho Contact = User. System handles users belonging to multiple accounts by linking tickets to the Account matching the Department
- Auto Phone Mapping: system fetches the logged-in user's mobile number and sends it to Zoho Desk as part of ticket creation (visible as custom field in Zoho Desk)

**Terminology mapping:** Zoho Account = Company Name, Zoho Contact = User of that company, Zoho Department = Client-level grouping for support tickets.

---

## 2. User Onboarding

> **Activities & Roles:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — User Management & Profiles.
> Key activities: A0010 (View/Edit/Activate/Deactivate Users — all admin roles), A0024 (Bulk Upload — not Client Admin), A0071 (View/Download Primary Profiles — all roles incl. Finance & Doc Approver), A0088 (Edit Email — CS Proxy/Std + Product Admin only), A0089 (Edit Bank/PAN — Junior Admin, Client Admin + Product Admin).

### 2a. Adding Users (Individual or Bulk)

**Individual User Addition:**
1. Go to User Management in the left-hand menu
2. Click "Add User" to open the profile page
3. Company name displays by default based on client setup
4. Select user type from the dropdown
5. Fill in required fields:
   - Employee ID (optional)
   - First Name and Last Name (mandatory)
   - Email ID and Mobile number (one mandatory based on communication preference)
   - Date of Joining and Date of Birth (optional — useful for engagement features like birthday/anniversary wishes)
6. Assign role, department, and scope
7. Click "Save" to just add the user, or "Save and Send Email" to add and trigger the default welcome communication

**Bulk User Addition:**
- Upload users via CSV through User Management > Upload Users

### 2b. GSTIN as Profile Field (U210088)

GSTIN (GST Identification Number) can be configured as a profile field for users, supporting Indian GST compliance. This is a configurable field — admin can enable/disable GSTIN collection per client.

**End-User Flow (when GSTIN is enabled):**
When a user submits PAN Profile (IN) details, the form changes as follows:

1. "PAN Card Profile Type" is the only field visible initially on the page ("Upload PAN Card Copy" is hidden upfront)
2. If the user selects Business PAN profile (or only Business PAN is available due to admin configuration), the next field asks: "Does your annual turnover exceed Rs. 40 lakhs in the case of goods supplied OR Rs. 20 lakhs for the supply of services?" with Yes/No radio buttons (no default selection)
3. **If No:** The usual PAN card-related fields appear and the existing PAN verification journey continues as normal
4. **If Yes:** The following field appears:
   - **Enter GSTIN number:** Alphanumeric only, 15 characters max, mandatory, must be unique within the same company
   - Help text below the field: "Your PAN number and PAN names will be extracted and verified from this entered number. Therefore, please enter GST number of your own organization to avoid rejections."
   - Action button: **Verify** — system extracts PAN number and name from the GSTIN and proceeds with verification

### 2c. Proxy User Functionality (U210091)

> **Activities & Roles:** M0114 (Assign Proxy Access — CS Admin with Proxy ONLY). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — Proxy Access.

**Goal:** Enable secure, time-bound impersonation access for GRG India's internal users to view client configurations in an impersonation mode, ensuring data masking, client consent, and strict session control. This facilitates faster troubleshooting and setup verification without needing client credentials or creating users in client companies, reducing support turnaround time and building client trust through transparency and consent-based access.

**Admin Configuration:**
The Proxy Approval mechanism is configured at: Settings > Company > Company Profile > Other Configurations.

Two key settings:
- **Proxy Approval Mechanism:** Yes/No — determines whether the target user must give permission before proxy access, or whether proxy access is direct (no approval needed)
- **Allow Redemption by Proxy User?** Yes/No — controls whether a proxy can perform redemption actions on behalf of the user

**Proxy User Login Flow (GRG Internal User):**
1. Log into the system — if assigned proxy activities in CMS, an option **"Login as Proxy"** appears in the left-hand navigation menu (under profile icon), along with the delegation period
2. Click "Login as Proxy" — a search interface opens showing all client users created in MI (client users only, not system users)
3. Search and select the target user to impersonate
4. If Proxy Approval Mechanism = Yes: the target user receives a request and must approve before proxy access is granted. If = No (Direct): proxy access is granted immediately
5. System enters proxy mode — a prominent banner displays at the top: **"Proxy mode active. Click 'Stop' to exit. Stop sharing."**
6. The proxy user can now view the client's configurations, campaign setup, and other relevant data in impersonation mode
7. Click "Stop" to end the proxy session

**Session Audit Trail:**
After the session ends, a detailed session summary is logged and viewable via "View Details":

| Field | Example Value |
|-------|--------------|
| User ID | U02809469 |
| Employee ID | RTS711281 |
| Email ID | 9842227917@myincentives.in |
| Mobile | +91 9842227917 |
| Name | MS MAC AUTO CORPORATION LTD |
| Approval Type | Direct |
| Requested Date | 2026-04-01 10:22:53 |
| Proxy Status | Completed |
| Approval Date | 2026-04-01 10:22:53 |
| Session Start Time | 2026-04-01 10:22:53 |
| Session End Time | 2026-04-01 10:23:12 |
| Session Duration | 00:19 |

All proxy activity is time-stamped and logged for compliance and transparency.

### 2d. Reportee Addition and Approval Workflow

> **Activities & Roles:** A0090 (View Reportee Rules & Requests — all admin roles), M0091 (Add/Edit Reportee Creation Rules — Product Admin only), A0092 (RM Edit Non-Primary Profiles — not Client Admin), M0110 (RM Edit Mobile & Shop Name — CS roles only), M0111 (RM View-Only All Profiles — CS roles only). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Sales Managers can add reportees:
1. Navigate to Profile > My Reportees
2. Click the add button (bottom right of screen)
3. Fill in contact details, location, and access permissions (role/designation/scope)

**Separate Add/Delete Approval Configuration (U210111):**
The system supports granular control with separate approval configurations for reportee addition vs. deletion. Configure at: Settings > User Management > Reportee Settings > +Criteria.

**Two modes per action (add and delete configured independently):**
- **Without approval:** SM adds/deletes directly — action takes effect immediately
- **With approval:** SM submits, request routes to 1st / 2nd / 3rd level reporting manager for approval. Request appears in the manager's My Approvals queue (see My Approvals hub — Section 4d). SM is notified of approval/rejection.

**SM Experience — Adding a Reportee:**
1. Navigate to My Reportees > click Add (+)
2. Fill in mandatory user profile fields: First Name, Last Name, Email ID or Mobile (based on communication preference), Role, Department, Scope, Designation
3. Optionally fill: Employee ID, Date of Joining, Date of Birth
4. Submit — if approval is configured, request enters approval workflow. If no approval, reportee is added immediately.

**SM Experience — Deleting a Reportee:**
1. Navigate to My Reportees > select reportee > Actions > Delete
2. Submit — if approval is configured, request enters approval workflow. If no approval, reportee is deactivated immediately.

The UI for add and delete is the same approval flow — the only difference is that "add" requires filling out the user profile form, while "delete" is a single action on an existing reportee.

**Designation Update by Store Manager with ABM Approval (U210120):**
Store Managers can request designation changes for their direct reportees, requiring ABM approval before the change takes effect:

1. SM navigates to My Reportees > selects direct reportee > View and Edit dropdown > selects new designation from master list > submits request
2. Request status = Pending Approval (visible in "reportee requests," locked for editing). ABM notified via email and push notification
3. ABM opens Designation Approval Queue > reviews employee and designation details > approves or declines (with optional remarks for decline)
4. On approval: designation updated immediately. On decline: no change applied. SM notified of decision either way

Key controls: SMs can only raise requests for direct reportees. Certain fields are frozen (Company, Employee ID, Date of Joining). Editing overwrites any previous pending request. No additional license consumed.

### 2e. API or SFTP Based User Onboarding

Data can be ingested via API or SFTP integration. Contact GRG admin for setup.

---

## 3. Campaigns — Common Steps Across All Campaign Types

> **Activities & Roles:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — Budget Management + Programs Module.
> Budget: A0002 (View Budget — all admin + Finance), A0003 (Add/Edit Budget — CS Proxy/Std + Finance Admin), A0004 (Allocate Points to Budget Owners — all admin + Product Admin), A0027 (Configure Budget Categories — all admin + Product Admin), A0085 (Point Curator at Bucket Level — all admin + Finance Admin).
> Campaigns: A0037 (Manage Own Programs — all admin + Product Admin), A0038 (Manage All Programs — all admin + Product Admin).

### 3a. Budget Setup: Create Sponsor, Bucket, and Purchase Order (PO)

Budget setup (sponsors, program budgets, purchase orders) is typically performed by the Product Admin (GRG account manager) on behalf of the client. This must be done BEFORE creating campaigns.

**Step 1 — Create a Sponsor:**
1. Navigate to Budget Management > Sponsors
2. Click "+ Sponsor"
3. Add Sponsor name, description, and select an icon
4. A sponsor is the entity that funds the budget (e.g., Microsoft funding campaigns within Dell, Garmin funding campaigns within Helios). Sponsors enable funding-entity-wise reconciliation in reporting.

**Step 2 — Create a Bucket:**
1. Navigate to Budget Management > Buckets
2. Click "+ Bucket"
3. Fill in:
   - Bucket type: Campaign
   - Sponsor name: select the relevant sponsor
   - Bucket description
   - Point curator: the user who will approve PO-to-campaign mappings
   - Bucket expiry date

**Step 3 — Create a Purchase Order (PO):**
1. After saving the bucket, click Actions > Manage Points
2. Click "+PO" and fill in:
   - PO description
   - Unique PO ID
   - Upload PO attachment file
   - Budget amount in points — the total points earned within the mapped campaign cannot exceed this amount

### 3b. Creating a New Campaign (Common Form)

1. Navigate to All Campaigns in the left-hand menu
2. Click "Add Campaign"
3. Select the campaign type from the dropdown (configured by GRG admin during program setup)
4. Fill in the campaign form:

**Basic Details & UI Configuration:**
- Campaign name, description, and banner (visible on app homepage to all participants)
- Banner should match the client's theme color
- Description should NOT repeat the campaign name — instead include:
  - Instructions on how to use the campaign (e.g., "Scan QR code or type in code manually to earn points")
  - Details on SKUs/product categories/goals needed to earn points

**Stakeholders:**
- Campaign Owner: can see all admin parts of the campaign (must be a role with campaign ownership access — typically the Product Admin / GRG account manager)
- Co-owner: can also see all admin parts
- Points Manager
- Reports Owner

**Duration:**
- Start date and end date
- Campaign homepage visibility end date: after this date, participants can no longer see the campaign in their "Active campaigns" section
- Points expiry date: after this date, any unearned/unredeemed points move to "expired" — typically used for financial year liability management or to encourage faster redemption

**Budget:**
- Tentative budget for point payouts — this is a subset of the total program budget, managed via PO mapping

**Participant Wallet Type:**
- Common Wallet: shared rewards catalogue across campaigns
- Campaign-specific Wallet: unique catalogue where only points from this campaign can be redeemed (useful for bonus campaigns with specific merchandise/vouchers)

**Leaderboard Configuration:**
- Choose to show/hide leaderboard
- Set number of ranks displayed on the main campaign page
- Configure whether participants can "view all ranks" (if No, only the specified number of ranks is visible)
- Note: Type D campaigns have a separate scope-based leaderboard configuration in Campaign Settings

### 3c. Point Curator Approval of Campaign PO Mapping

After campaign creation, the campaign status is "Pending for Approval."

1. The Point Curator (mapped via the Sponsor selected during campaign creation) navigates to My Account > My Approvals
2. Selects "View Details" within Actions
3. Maps the PO to the campaign
4. Approves — campaign status changes to "Active"

**Common configuration error:** The Campaign Owner does NOT approve the campaign. Approval is routed based on the Sponsor selected during creation. Each Sponsor is mapped to a Point Curator (usually the Finance Admin for live clients).

### 3d. Add Participants to the Campaign

Participants are added after the campaign is active. Users must be registered in the platform before they can be added as participants.

### 3e. Optional — Force Redemption Setup

> **Activities & Roles:** A0086 (Manage Forced Redemptions — all admin roles + Product Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Force redemption auto-triggers payouts for users who don't redeem before points expiry. Configurable under Rewards settings — enables direct redemption to registered bank/UPI/PayTM accounts.

---

## 4. Campaign-Specific Setup

> **Activities & Roles:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — Programs Module + Data Sources & Campaigns.
> M0105 (Include SKUs/Codes Type G — CS Proxy/Std + Product Admin), M0098 (View Referrals Type F — CS roles + Product Admin), M0099 (Auto-Participant Type F — all admin roles + Finance), M0112 (Reference File Upload for Points — removed from Client Admin), A0042 (View My Approvals — all admin roles).
> Points file uploads and audits: M0112, M0113 (both removed from Client Administrator).

### 4a. Type A — Direct Awarding of Points

Simplest campaign type. Admin uploads a file with user-to-point mappings, and points are directly credited.

**Setup Steps:**
1. Create the campaign using the common form (Section 3b)
2. Get PO approved (Section 3c)
3. Add participants
4. Upload the bulk file mapping users to points

### 4b. Type B — Approval-Based Point Distribution

Points are allocated to hierarchy nodes (e.g., stores), then distributed by awarders (e.g., store managers) to individual participants. Multi-level approval workflow.

**Step i — Create the Campaign:**
1. Navigate to Campaign Management > Create New Campaign
2. Select "Type B: Approval-based awarding of points"
3. Select the level of point awarding — this refers to the hierarchy level (e.g., Level 4 or 5) of users who will distribute points to participants. Higher levels (e.g., Level 2 or 3) act as approvers.
4. The selected level must be greater than 1 (campaigns cannot be created for Level 1 users)
5. Campaign type and awarding level CANNOT be changed once saved (even as draft)
6. Complete the common campaign form (Section 3b) and get PO approved (Section 3c)

**Step ii — Set Distribution and Approval Controls:**
Navigate to All Campaigns > Actions > Campaign Settings (available only to Campaign Owner).

Configure:
- Requester Time Limit (days): how long the awarder has to submit points for approval (Default: 1, Range: 1-20). Users can still award after this period, but reminders are affected.
- Approver Time Limit (days): maximum days for an approver to approve/reject (Default: 1, Range: 1-20)
- Equal Distribution Date: on this date, unawarded points are automatically distributed equally among users within that node (e.g., 1,000 points across 5 store people = 200 each)
- Email Alert for Approval Matrix Changes (optional): email ID that receives alerts if approval matrix users become inactive or hierarchy changes invalidate the matrix (daily system check sends an Excel with invalid entries)

**Step iii — Set Distribution Controls:**
Four types (only one active at a time, default is "No control"):

1. No Control: awarders/approvers distribute in any proportion without limits
2. Fixed Value: no participant can be awarded more than the specified maximum points
3. % Fixed Percentage of Allocated Budget: points to any individual cannot exceed this percentage of the store's total allocated points (e.g., 15.2% of 10,000 = 1,520 max)
4. Multiplier of Average Participant Earning: max = (total allocated / number of participants) x multiplier (e.g., 10,000 / 5 users x 2 = 4,000 max)

**Step iv — Upload the Approval Matrix:**
1. Download the standard approval matrix template (auto-generated based on awarding level)
2. For each hierarchy level, set "Part of Campaign" to Yes if users at that level will award or approve points
3. Awarder email is mandatory if "Part of Campaign" is Yes
4. Approver 1 is required to enable further approval levels (Approver 2/3 cannot exist without Approver 1)
5. Only active users in the hierarchy can be selected
6. Upload the template

Matrix statuses: Not Defined, Defined, Upload in Progress, or Defined with Errors. Points allocation is blocked until status is "Defined." Error rows are shown in a downloadable error Excel.

The matrix can be edited during an active campaign after resolving any validation errors.

**Step v — Allocate Points:**
Navigate to Points Management > Allocation from the campaign Actions button.

Two tabs visible: Allocation and Awarding (visible to Campaign Owner and Points Manager).

Method 1 — Upload Allocation:
1. Download the standard template
2. Enter points to allocate at each level
3. Upload — system sends emails/notifications to tagged Awarders
4. Allocation cannot drop below the level's current balance points

Method 2 — Edit Allocation via UI:
- Edit allocated points directly from the grid
- Every edit triggers a notification to the relevant Awarder

**End-User Flow (Store Manager distributing points):**
1. Log in and navigate to the relevant campaign
2. Go to Points Distribution section
3. Choose Equal Distribution (auto) or Custom Distribution (manual)
4. For Custom: enter total points and points per participant
5. If excess distribution warnings are enabled (U210102): the system validates each participant's allocation in real time against configured user-level caps. If a value exceeds the cap, the input field highlights in red with an inline message showing the allowed vs. attempted allocation (e.g., "Allowed: 1,000 / Attempted: 1,520"). For hard limits, the Submit button is disabled until all values are within range. For soft limits, a warning is shown but submission is allowed.
6. Submit for approval (or directly award if permitted)
7. Approver receives notification and can approve or reject
8. SM is notified once the approver takes action (approval or rejection)

**Bulk Distribution:** When distributing via Excel upload, the system performs pre-submission validation. If any rows exceed caps, a downloadable error report is generated showing which participants would exceed limits. SM corrects the file and re-uploads.

**System Controls:**
- Participant limit per store: if exceeded (including past + pending awards), the system blocks the action
- Multiple awards: system adds all approved + pending points before allowing a new award
- Mid-campaign limit changes: past awards stay as-is, new awards follow updated limits
- Multiplier-based control uses live values at time of awarding

**Excess Distribution Warnings (U210102):**
The system highlights when distribution would exceed permissible user-level caps, preventing accidental over-allocation:

- Admin can enable limit validation, set per-user caps, define time-based limits, and toggle soft/hard limits
- UI shows red highlighting for inputs exceeding caps, with inline messages showing allowed vs. attempted allocations
- Hard limit breaches disable the submit button entirely; soft limits show warnings but allow submission
- Bulk upload mode performs pre-submission validation and generates downloadable error reports
- Distribution modes supported: UI dashboard, bulk Excel upload, API
- Real-time validation during individual allocation; pre-submission validation in bulk mode

### 4c. Type C — Invoice Claim-Based Campaign

Salespeople submit invoice claims (photo + details) to earn points. Claims go through multi-level approval.

**Prerequisites:**
- Product hierarchy must be set up with the relevant SKUs (Section 1d)
- Business hierarchy must be configured with users mapped (Section 1c)

**Step i — Create the Campaign:**
1. Navigate to Campaign Management > Create New Campaign
2. Select "Type C: Claim approval based campaign"
3. Select level of point awarding — the level of users who will submit claims (typically Level 3 or lower salespeople who directly interact with customers)
4. Select claim form type:
   - SKU-wise claim: points earned based on specific SKUs within the invoice
   - Total invoice value claim: points earned based on total invoice amount
5. Complete the common campaign form (Section 3b) and get PO approved (Section 3c)

**Step ii — Create the Claim Form:**
1. After saving as draft, a new "Claim Form" section appears
2. Click "Edit Form" to add fields from the menu (similar to Google Forms or MS Forms)
3. You can copy fields from an existing form using "Copy Form"

For Total Invoice Value Claims — mandatory fields: invoice number, total invoice value, invoice copy attachment. All other fields are optional.

For SKU-Based Claims — mandatory fields: invoice number, SKU, quantity, invoice copy attachment. All other fields are optional.

**Step iii — Earning Logic and SKU Selection:**
Navigate to All Campaigns > Actions > Campaign Settings.

For Total Invoice Value Claims:
- Input earning logic using slabs (e.g., invoice 5K-10K = X points, 10K-20K = Y points)
- Earning can be absolute incentive number or percentage of total invoice value
- Overlapping slabs trigger an error; uncovered invoice values earn 0 incentives
- Points awarded after manager approval

For SKU-Based Claims:
1. Download the standard template (contains all SKUs from product hierarchy)
2. Select which SKUs are incentivized ("Part of the Campaign" = Yes/No)
3. Fill in points per unit of SKU sold (no decimal points allowed)
4. Upload

**Step iv — Upload the Claim Approval Matrix:**
1. Select approval workflow type:
   - Type 1: any rejection stops the chain (claim rejected immediately)
   - Type 2: claim passes through all levels regardless; only the final approver's decision is binding
2. Download the standard template (pre-populated with existing hierarchy paths)
3. Fill in approver emails for each hierarchy path (minimum 1 approver, maximum 3)
4. Approver 2/3 cannot exist without Approver 1
5. Approvers must be tagged in a hierarchy level above the lowest point-awarding level
6. Upload

Example claim approval matrix:

| Level 1 | Level 2 | Level 3 | Part of Campaign | Approver 1 | Approver 2 | Approver 3 |
|---------|---------|---------|-----------------|-----------|-----------|-----------|
| India | West | Mumbai | Yes | MumbaiCityManager@grgindia.in | WestFinanceHead@grgindia.in | SalesOperationsHead@grgindia.in |
| India | West | Pune | Yes | PuneCityManager@grgindia.in | WestFinanceHead@grgindia.in | SalesOperationsHead@grgindia.in |
| India | South | Bengaluru | Yes | BangaloreCityManager@grgindia.in | SouthFinanceHead@grgindia.in | SalesOperationsHead@grgindia.in |

**Step v — Admin & Campaign Owner Capabilities:**

Viewing Claims:
- Navigate to Claim Management in the campaign
- View grid of all submitted claims with status filters

| Action | Availability |
|--------|-------------|
| + Claim | Not available unless user is a participant |
| View Details | Always available |
| Delegate Approver (pending claims) | Button next to approver name, triggers email |

Reports (Admin View): claim counts (submitted/approved/rejected/pending), detailed approval history, claim drill-down with filters.

Approval History: tracks approval level, approver name, comments, approval status, and date of action.

**End-User Flow (Salesperson submitting claims):**
1. Go to the relevant campaign > click "+ Claim"
2. For SKU-based: enter SKU code/name from the invoice, fill all form fields, upload invoice copy
3. For Total Invoice Value: enter invoice value/breakup, fill form fields, upload invoice copy
4. Claim enters approval workflow — status tracked as Pending/Approved/Rejected
5. On approval, points are credited to participant's wallet with notification

**Manager Approval Flow:**
1. Go to My Approvals > Select Claim > View Details
2. View claim details and open invoice in a new tab
3. Add comments
4. Click Approve or Reject
5. Comments from all approval stages merge into a single thread
6. Only the final approver changes status to Approved; until then, claim remains Pending

### 4d. Type D — Automated Sales-Based Incentive Calculation

> **Activities & Roles:** A0042 (View My Approvals — all admin roles). Type D hierarchy approval uses the My Approvals hub. See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

The most powerful campaign type. Connects to Data Sources to automatically calculate incentives from uploaded or integrated sales data.

**Prerequisites:**
- Data Sources must be set up with sales/target data (Section 5)
- Business hierarchy configured (Section 1c)
- Users mapped to hierarchy (Section 1c)

**Step i — Create the Campaign:**
1. Create using the common form (Section 3b)
2. Get PO approved (Section 3c)
3. Add participants — ensure hierarchy is mapped for users prior to adding them

**Step ii — Configure Final Incentive Table (Campaign Settings):**
Navigate to All Campaigns > Actions > Campaign Settings.

The purpose is to map/link campaign participants with their sales and incentive data using a common identifier.

1. User Unique Identifier Selection:
   - Select the column from the user table that matches the data sources table
   - Options: Employee ID, User ID, Email, or Phone Number

2. Data Table Selection:
   - Select the final table from Data Sources (prefixed with "F", e.g., "F April 2025 Store Managers Incentive")
   - Map the unique identifier column from the data sources table to match the user identifier

3. Output Columns Selection:
   - "Select Table 1 columns": user table columns visible to participants and managers (typically just the identifier)
   - "Select Table 2 columns": sales and incentive columns visible to participants and managers (e.g., sales volume, target, % achievement, incentive per unit, total payout)

**Common configuration error:** "Map unique identifier from table 1" refers to the email/Employee ID/User ID/phone number column, NOT the final incentive column. This maps users to their data rows, similar to a VLOOKUP or LEFT JOIN in Excel/SQL.

**Step iii — Set Incentive Calculation Rule:**
1. Go to All Campaigns > Actions > Incentives Calculation
2. In the "Incentives Rules" section, under Action, select the column containing the final calculated incentive
3. The selected columns will appear in the "Incentives Payout" section

**Optional — Target Distribution:**
Allows distribution of targets from hierarchy levels down to individual team members.

Prerequisites: business hierarchy set up + distributor mapped as reporting manager

Setup:
1. Create and approve the campaign
2. Add participants (ensure hierarchy mapped first)
3. Go to Campaign Settings > Targets tab > enable Target Distribution
4. Set distribution controls (Fixed Value, Fixed Percentage, or Multiplier)
5. Set distribution time limit and reminder schedule
6. Optional: set equal distribution date for auto-distribution of undistributed targets
7. Select hierarchy level for distribution
8. Upload the target distribution matrix (download template, assign distributor and target per hierarchy node)
9. Process the matrix — distributors can now view and distribute targets

End-user target distribution flow:
1. Store Manager logs in > Campaign Management > Campaign Dashboard
2. Click Actions > Target Distribution
3. Click View Details for the relevant store
4. Click "+Distribute" to assign targets to users
5. Choose Equal Distribution (default) or Custom Distribution
6. Click "Distribute" to submit
7. Note: targets once distributed cannot be changed; if not distributed by deadline, system auto-distributes equally

**Optional — KPIs (Individual - My Performance):**
1. Select KPI visualization type: Target Meter, Score Card, or Progress Bar
2. Click "+KPI" and configure:
   - KPI name (visible to all users — ensure correct formatting)
   - Number of decimal places (0 in most scenarios)
   - Unit for KPI (shown in brackets near KPI name)
   - Show achievement in % (typically yes)
   - Show rank against KPI (typically no if leaderboard exists)
3. Select target and achievement columns from the Data Sources final table
4. KPI order matters: first added (bottom of table) = shown first to users (top/left)

**Common configuration error:** "KPI Achievement" refers to total sales done, NOT the % Achievement column. Select "Clothing Sales" NOT "% Achievement."

**Optional — KPIs (Hierarchy-based - Team Performance):**
Enable achievement view for team members based on reporting hierarchy. Display formats: Progress Bar, Card, or Target Meter.

**Optional — Leaderboard:**
1. Select leaderboard type:
   - Performance metric based: select any column from the data sources table as KPI
   - Points based: based on final earned incentives
   - Don't show (default)
2. If performance metric based:
   - Select metric (e.g., "% Achievement")
   - Enter unit
   - Set number of ranks to display
   - Select display columns for the leaderboard table
   - Allow viewing all ranks (Yes for internal teams, No for external channel sales)
3. To give hierarchy managers access, add them as "Report Owner" in the campaign form (individual users or by role)

**Optional — Dynamic KPI-Based Nudges:**
1. Click "+Nudge" on the campaign dashboard
2. Enter nudge name
3. Select recipients: individual selection, filter by scope/role/department, or select all
4. Set event conditions using variables from the Final table with IF-THEN logic and AND/OR operators
5. Configure communication content:
   - Email: editable subject line, rich text body, schema variables from Final Incentives Table
   - Push notification: rich text with schema variables
6. Set scheduler: time (HH format), repeat frequency (one-time, daily, weekly, monthly, custom)

**Optional — Sales Transaction View:**
Gives sales agents visibility into eligible transactions contributing to their incentives.
1. Select transaction table and unique user identifier
2. Map identifier from transaction table to user table
3. Select output columns for the table view
4. Select columns for mobile grid view (limit to 3-4 columns)

**End-User Flow (Salesperson viewing Type D campaign):**
1. Log in and scroll to active campaigns on homepage
2. Click into the relevant campaign
3. View real-time performance dashboard: sales, targets, % achievement, projected and earned incentives across all KPIs
4. View transaction-wise sales summary
5. View leaderboard to compare with peers

**Manager View (Type D):**
1. Log in and click into the relevant campaign
2. View team performance:
   - By KPI: select KPI, view overall performance across all mapped retailers/salespeople
   - By User: select user, view all KPIs with targets and achievements in bar form
3. View leaderboard section below target meters:
   - Full list of retailers with beat codes, total earned incentives, KYC status
   - Customizable columns, search by beat code
   - Managers only see KPIs for retailers mapped to them

**Flexible Widget-Based Campaign View (U210116):**
Type D campaign detail pages can be configured as flexible, widget-based views (similar to homepage builder), allowing role-specific customization:

Admin Configuration:
1. Add dashboard (similar to widget builder)
2. Select role/department/designation/scope
3. Toggle "part of campaign" switch
4. Choose dashboard type: Only regular Type D dashboard, or Regular + widget-based dashboard

Dashboard options within regular view: Point dashlets (earned, balance, expired, redeemed), KPIs (progress bars, target meters, score cards), scope-based leaderboard, sales transactions table, basic campaign information.

End-user experience: Widget-based dashboard displayed first, then regular dashboard below. Campaign details accessible via "view details." Sales Managers (non-participants) can view reports within "view details," track team KPI progress, and access scope-based leaderboard.

**Hierarchy Approval for Type D Distribution (U210118):**
Type D campaigns support hierarchical approval workflows for incentive distribution. This is particularly relevant for large client deployments (e.g., Titan with 1,157 stores across 55 ABMs).

**Admin/CSM Workflow:**
1. CSM receives and validates the earning file
2. Data cleaning and validation
3. System routes approval through the business hierarchy — multi-level approvals based on role

**ABM/Approver Flow:**
1. Navigate to My Account > My Approvals (or via the notification received)
2. The My Approvals page shows all pending requests with tabs: Pending for Approval, Approved, Rejected
3. The approvals table shows: Request ID, Requested By, Request Type (e.g., "Campaign – Type D"), Request Date, Pending Since, Status, and Action button
4. Click Action > View Details on the relevant Type D approval request
5. The approval detail page shows "Basic Details of Approval": Campaign Name, Approval Type (Manual/Automatic), Requested By, Approver Email, Status (Pending/Approved/Rejected)
6. Below the basic details, the "Final Incentive Distribution to Users" table shows all participants with columns: User Name, Designation, User Status, Incentives Payout (calculated amount), Cap Value (if row-level cap enabled — see U210126), and Payout (editable)
7. Note at top: "Users having Negative Calculated points, Zero points and those having error in calculation will not be awarded points. Points will only be awarded to users who has a positive payout after approval."
8. The approver can edit individual Payout values using the edit icon (pencil) per row
9. Balance Points shown at top right indicates remaining budget
10. Approve or reject the entire distribution

**Note:** The My Approvals page is a unified hub for all approval types — Type B campaign distributions, Type C claim approvals, Type D incentive approvals, Type F referrals, reportee additions, and designation changes all appear here with their respective Request Types. Approvers can use Bulk Approval for batch processing.

**Point Restrictions for Type D Approval (U210126):**
When Type D distribution with approval is enabled, per-row edit caps prevent approvers from inflating individual payouts beyond configured ceilings.

**Admin Configuration:**
1. In the "final calculation" page, enable "row-level edit cap" via radio button
2. Select a column as the ceiling value — dropdown shows all numeric columns from the final incentive table
3. Cap can be a fixed column (e.g., per-person cap) or calculated (e.g., store budget ÷ participants)
4. Cap column is separate from the payout column
5. Admin cannot change cap column after values are frozen — configuration saved as draft, applied on "freeze"

**Approver Experience (What the ABM/Manager sees):**
When reviewing the "Final Incentive Distribution to Users" table, the approver sees three key columns side by side: Incentives Payout (the system-calculated amount, shown in red/orange), Cap Value (the maximum allowed per row), and Payout (the editable final amount).

- To edit a payout, click the pencil icon on the relevant row
- If the approver enters a value exceeding the cap, the Payout value turns red and an inline error appears below the row: "Edited value [X] exceeds the maximum allowable payout [Y] for this row."
- The approver must correct the value to proceed — the system will not allow approval with any row exceeding its cap
- If the approver reduces a payout below the calculated amount, the freed-up delta becomes available for reallocation to other participants within the same distribution
- Bottom of table shows: Total Target Distribution and Remaining Balance After Distribution
- Full audit trail logs every edit with the original value, edited value, and cap at time of edit

### 4e. Type F — Refer and Earn

Referral-based campaign where users earn points for successful referrals.

**End-User Flow:**
1. Navigate to the "Refer a Friend" section within the campaign
2. Submit referral details via the referral form
3. Referee receives a referral code
4. After the sale, a dealer adds the referee to the platform
5. Referee claims points by submitting the referral code and uploading invoice as proof
6. Referral claim goes through approval workflow
7. On approval, both referrer and referee receive points (amounts can be same or different)

### 4f. Type G — Scan Code and Earn

Users scan QR codes or enter codes manually to earn points. Codes are pre-generated per SKU with expiry dates.

**Prerequisites:**
- Product hierarchy set up with relevant SKUs (Section 1d)
- Business hierarchy configured (Section 1c)

**Step i — Check or Update the Product Hierarchy:**
Ensure the product hierarchy contains all needed SKUs. Refer to Section 1d for setup instructions.

**Step ii — Upload SKU Codes (Campaign Settings):**
1. Navigate to All Campaigns > Action > Campaign Settings
2. Download the standard SKU and Codes template
3. Fill in: SKU codes, corresponding scan codes, and validity date (YYYY-MM-DD format)
4. Upload the template

Common configuration errors:
- SKUs must already exist in the product hierarchy
- Use SKU name (not description) in the upload
- Expiry date must be in YYYY-MM-DD format
- Possible failures: SKU not in product hierarchy, duplicate scan code, code exists in another campaign, past validity date

After upload:
- Use "Search Code" to look up individual codes
- For used codes: view scan history (user details, scan time)
- For unused codes: edit details or delete

**Step iii — Point Validation (Scan Validation Matrix):**
The scan validation matrix drives how different user groups earn points for different SKUs.

1. Download the template
2. Fill in points logic:
   - If points vary only by SKU: update SKU and scan points columns only
   - If points vary by user attributes (scope, tier, department, role): update all relevant columns

Example:

| # | SKU | Role | Tier | Scan Points |
|---|-----|------|------|-------------|
| 1 | PPF | Standard User | Beginner | 100 |
| 2 | PPF | Standard User | Expert | 200 |
| 3 | SKU 3 | Standard User | Beginner | 300 |
| 7 | PPF | Manager | Gold | 800 |
| 8 | PPF | Manager | Platinum | 1000 |

Common configuration errors: ensure role/tier/department/designation exists in the company and is updated for users.

**Configure Multiple Scan Settings (Optional):**
1. Enable or disable multiple scans
2. If enabled, select which attributes allow multiple scans — each unique combination of selected attributes can scan the same code only once

Example: if attributes "role" and "SKU" are selected for multiple scans:
- PPF can be scanned twice: once by a Standard User and once by a Manager
- SKU 3 can be scanned once by a Standard User only (no Manager rows defined)

**Step iv — Final Scan Table (Optional):**
Only needed if users don't earn points on each individual scan (e.g., points earned only after 5+ successful scans).

If points are earned per scan, skip this step (Base Scan Table is used by default).

For milestone-based earning:
1. Choose to create a custom Final Scan Table (FST) instead of using the Base Scan Table (BST)
2. Map the unique identifier, data sources table, and identifier column
3. The analyst team typically configures derived tables for scan counting

**Step v — Incentive Calculation:**
1. Incentives per scan:
   - Select the formula for base points earned when scanning
   - Use any variable from the Final Scan Table in conditions and output
   - If points = scan validation matrix values: leave Condition blank, select "scan points" in Action

2. Bonus per scan:
   - Configure bonus points for milestone achievers or power users
   - If no bonus: leave Condition blank, type 0 in Action

3. Final payout amount: shows total payout based on scans to date, with downloadable details

**End-User Flow (Scanning):**
1. Log in to the My Incentives app
2. On home screen, two options: "Enter Code" and "Scan QR Code/Barcode"
3. To scan: click Scan > mobile camera opens > scan the QR code
4. Responses:
   - Success: QR scanned successfully, points credited to wallet
   - Error: invalid code
   - Sorry: technical error, try again later or contact helpdesk
5. View all transactions in the transaction section

### 4g. Tier Management — Performance-Based Tiers

> **Activities & Roles:** M0106 (View Tier Management — all admin + Product Admin), M0107 (Edit Tier Management — CS Proxy/Std + Product Admin only; not Junior Admin or Client Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Dynamic, performance-based tier system that drives differentiated incentives, visibility, and engagement.

**Step i — Create Tier Segments:**
Tier segments group tiers for specific user populations (e.g., separate tier ladders for salespeople, retailers, and influencers).

1. Navigate to Tier Management > Tier Segments
2. Click "+ Segment"
3. Fill in:
   - Segment Name (unique, max 100 characters)
   - Select Scope(s) (multi-select)
   - Select Role(s) (multi-select)
4. Note: each scope and role can only be used in ONE segment

**Step ii — Add Tiers to Segments:**
1. Click "+ Tier"
2. Configure:
   - Tier Name (unique, max 20 characters)
   - Tier Logo (upload)
   - Background color
   - Tier Description (max 3,000 characters)
3. System auto-assigns Tier Order (first tier added = lowest; subsequent tiers take consecutive order numbers)
4. Tiers display sorted by order (lowest on top)

**Step iii — Define KPIs:**
1. Navigate to Tier Management > Tier KPIs
2. Click "Add KPI"
3. Configure:
   - KPI Name (unique, max 100 characters)
   - Select the relevant table from Data Sources
   - Choose column for unique user identification
   - Select Achievement Column (must be numeric)
4. The data sources table MUST have one row per user

**Common configuration error:** If the KPI depends on a scan-and-earn campaign, the auto-generated Base Scan Table CANNOT be used (it has multiple rows per user for each scan). Create a derived table that counts total successful scans per user.

**Step iv — Create the Tier Movement Matrix:**
1. Go to Tier Management > Tier Movement Matrix
2. Download the template
3. Fill in:
   - Tier segment
   - Optional: User Scope, User Role
   - Tier information and order
   - Tier upgrade conditions: KPI thresholds with AND or OR logic
4. Upload — the matrix must be uploaded completely each time (not incremental; older version is fully replaced)

Example:

| Segment ID | Scope | User Role | Tier Code | Tier | Order | KPI-T001 (Last year sales) | Logic |
|-----------|-------|-----------|-----------|------|-------|---------------------------|-------|
| S0001 | Default | Standard User | T001 | Silver | 1 | 0 | KPI-T001 |
| S0001 | Default | Standard User | T002 | Gold | 2 | 3,000 | KPI-T001 |
| S0001 | Default | Standard User | T003 | Royale | 3 | 6,000 | KPI-T001 |

**Common configuration error:** Ensure scope and user role are updated to include all users for whom tiers should apply. Also, at least one participant must be added to the scan-and-earn campaign for tiers to start being assigned (triggers backend user data sync).

**Step v — Set Up the Tier Movement Scheduler:**
1. In Tier Movement Matrix section, locate Scheduler settings
2. Choose evaluation frequency: daily, weekly, or monthly
3. System runs evaluation at 5:00 AM on the scheduled day
4. Tier movements are recorded with date and audit history at user level

**Step vi — Configure Nudges:**
1. In Tier Movement Matrix section, find Nudge Configuration
2. Select dates for sending upgrade nudges
3. Optional: set exclusion period for recently upgraded users

**Reporting:**
- All user reports in Analytical Dashboard include user tier
- All User Information Report: includes tier change audit trail (date, tier assigned, upgrade/downgrade)
- Date-wise Tier Upgrade Report: all users and their tier change activity on a selected date, including user profile parameters, previous/new tier, status, and KPI values

---

## 5. Data Sources

> **Activities & Roles:** M0093 (Data Sources Tab Visible — CS Proxy/Std + Product Admin only; not Junior Admin or Client Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

### 5a. Overview

Data Sources is the backend data engine for Type D campaigns and tier management. Think of it as an in-app database with spreadsheet-like tables.

**Table Types:**
- **Custom:** Raw data uploaded via CSV
- **Integrated:** Raw data uploaded via API integration
- **Derived:** Created by combining, summarizing, or aggregating existing tables
- **Campaign:** Final table linked to a campaign for incentive calculation

**Column Types:**
- **Simple:** Data uploaded manually
- **Calculated:** System-computed values using formulas (like Excel calculated columns)

**Data Types Supported:** Single line text, multi-line text, number, date, email, dropdown, checkbox, attachment

**Key Design Principles:**
- Each row should map to one user (no duplicates on the unique identifier)
- Common identifiers for joining: Employee ID, User ID, Email, Phone
- Tables prefixed with "F" are final/campaign-linked tables
- Derived tables can reference other tables for lookups and aggregations

**CSV Upload to Integrated Tables (U210106):**
Product Admins (GRG account managers) can upload CSV files directly into Integrated Tables for month-end sales data adjustments, eliminating manual backend updates.

Step-by-step:
1. Navigate to Data Sources in the left-hand menu
2. Locate the relevant Integrated Table (table type = "Integrated")
3. Click Actions > Upload CSV
4. Select the CSV file containing adjustment data (corrections, new records, or deletions)
5. System runs validation: mandatory fields present, correct data types/formats, duplicate detection based on unique keys, Campaign ID/Date Range validation
6. Review the difference calculation summary: new records (to be inserted), changed records (to be updated), deleted records (to be removed)
7. Confirm upload — system processes the changes
8. Verify by spot-checking updated rows in the table view

Benefits: eliminates manual backend updates, reduces backend dependency, faster incentive calculations, self-service data corrections for Product Admins.

**Bulk Field Creation via CSV (U210112):**
Instead of creating fields one-by-one, admins can bulk-create simple field definitions through CSV file upload. Download the CSV template, define field names and types, upload for validation and creation. System validates field names and types and reports any errors.

**Identifier-Based Joins for Scan and Target Tables (U210119):**
Flexible table joins in Data Sources allow users to explicitly select join columns (e.g., Email ↔ User ID), removing dependency on lookup tables or schema matching:
- Problem solved: separate target/scan tables generated for each campaign cannot be merged when User ID isn't configured as a lookup field
- Solution: users select join columns explicitly, enabling a VLOOKUP-like functionality across tables
- Supports multi-column identifier mapping and manual join logic
- Enables single consolidated view combining monthly distributed targets, historical targets (multi-month), and aggregated metrics
- Existing join behavior remains unchanged for backward compatibility

**Spot Checks After Upload:**
- Number of rows should match total users with sales in the relevant period/region
- No duplicate entries for the same user identifier

### 5b. Data Workflow: Cleaning, Upload, Verification, and Table Creation

The data workflow follows a consistent pattern regardless of the client. Here is the generalized process:

**Step 1 — Data Cleaning (in Excel before upload):**
1. Add a unique primary key column (e.g., "TM June 1", "dss 2025 Q1 1")
2. Format numbers correctly — change percentage columns to Number (Decimal - 2 places)
3. Replace any #N/A or error values with 0
4. Add a period identifier column (e.g., monthId = "2025june", quarterYr = "Q12025")
5. Clean column headers: unmerge cells, add complete information, delete blank/irrelevant columns
6. Remove special characters (especially %) from text values — characters not accepted: anything outside [A-Za-z0-9,-:.\_@\s'&/;()#*$\_[]+
7. For ongoing programs: identify and add missing entries from previous periods using COUNTIFS

**Step 2 — Upload Data:**
1. Navigate to the relevant table in Data Sources
2. Click View Table > Import > Upload
3. Click "Map Columns" and map columns properly
4. Click Save > Import
5. Wait for the cron job to process
6. If errors occur: download the Error File, fix data per error messages, re-upload

Common upload errors:
- Text fields with special characters (remove %)
- Email fields with invalid format or blank values (delete the row and re-upload)

**Step 3 — Data Verification:**

Method 1 — UI Spot Checks:
1. Go to the table in Data Sources
2. Click Actions > View
3. Use the search feature to perform 2-3 spot checks

Method 2 — Export Verification:
1. Click Actions > View > Export > initiate new download
2. Wait for file generation
3. Open file, add totals for data columns (sales, targets, incentives)
4. Compare totals with the original data file

**Step 4 — Create Derived Tables (for period filtering):**
1. Go to Data Sources > Create Table
2. Select "Derived" table type
3. Select the master table as the base table
4. Click "Select All Columns"
5. Enable "Apply Conditions"
6. Add filter: Column = period identifier, Operator = Equal, Value = the target period

**Step 5 — Create Custom Tables:**
1. Go to Data Sources > Create New Table
2. Enter a meaningful name
3. Select "Custom" table type
4. Add a unique primary key column name
5. Save
6. Click Actions > View > Columns tab > "+Columns"
7. Select "Simple" for manual data columns or "Calculated" for formula-based columns
8. Define column structure with appropriate data types

### 5c. Points File Upload and Auditing (U210085)

> **Activities & Roles:** M0112 (Reference File Upload with Points — removed from Client Admin), M0113 (View Points File Uploads & Audits — removed from Client Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Bulk upload of points files with comprehensive auditing capabilities. Allows administrators to upload, validate, and audit points data in batch operations. Includes audit trail generation, data validation workflows, and error handling/reporting.

### 5d. L1 Data Cleanliness — Data Validation Dropdowns (U210107)

Standardized dropdown lists for comment fields at L1 data entry level improve data consistency and reporting quality:

- Problem: free-text comments at L1 entry result in high variation, spelling errors, and difficulty in reporting/filtering
- Solution: predefined, frequently-used comment options (top 10-15 reasons) presented as a searchable dropdown with auto-suggest
- User flow: Settings > User Management > PAN/Bank/UPI Profiles > select comment field > choose from dropdown OR enter free-text "Others"
- Admin can configure dropdown options; system tracks frequency of option selection
- Applies across all KYC verification workflows (PAN, Bank, UPI profiles)

---

## 6. Budget Management, Rewards & Redemption

> **Activities & Roles:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — Rewards & Wallet + KYC & Document Management.
> Rewards: A0016 (View Rewards — all admin + Finance), A0046/A0047 (View/Edit Rewards Settings — Edit is Product Admin only), A0086 (Forced Redemption — all admin + Product Admin), A0087 (View & Debit Wallet — all admin + Product Admin), M0094 (Redeem Rewards — all admin roles).
> KYC: A0077 (PAN L1 Approval — Junior Admin, Product Admin, Doc Approver; removed from Client Admin), A0078 (PAN L2 — Finance Admin only), A0079 (Payout L1 — Junior Admin, Product Admin, Doc Approver; removed from Client Admin), A0080 (Payout L2 — Finance Admin only), A0076 (TDS — Finance Admin only).

### 6a. Reward Settings Configuration

Navigate to Settings > Rewards.

**Basic Settings:**
1. Enter the Catalog ID (shared by Rewards team)
2. Set "Show reward worth in base currency" (usually No — rewards shown in points)
3. Set Required Order OTP mode (Mobile & Email OTP, or no OTP confirmation)
4. Select Country for currency type and applicable TDS laws

**Cash Payout Settings:**
1. Enable cash transfer in the catalogue
2. Set processing charges visibility
3. Select allowed cash transfer modes: Bank, UPI, PayTM
4. Configure KYC verification levels for each mode:

| Profile | L1 — Document Verification | L2 — Finance Verification | L2 Mechanism | Manual L2 Name Mismatch |
|---------|---------------------------|--------------------------|-------------|------------------------|
| Bank Account (India) | Yes/No (default No) | Yes/No (default No) | Manual/Automated (default Manual) | Yes |
| UPI (India) | Yes/No (default No) | Yes/No (default No) | Manual/Automated (default Manual) | Yes |
| PayTM (India) | Yes/No (default No) | Yes/No (default No) | Automated (cannot change) | No |
| PAN Profile (India) | Yes/No (default No) | Yes/No (default No) | Manual/Automated (default Automated) | Yes |

**Reward Catalogue Settings:**
1. Go to Rewards Settings > Rewards Catalogue > "+ Catalogue"
2. Enter catalogue and scope (which users can see the rewards)
3. Click "Map Products" — select and activate products for the catalogue
4. Optional: enable Force Redemption for direct cash transfer to registered accounts

### Point System
1 point = 1 rupee (configurable). Points earned across campaigns can be redeemed through multiple channels.

### Redemption Options
- **Cash:** Direct bank transfer (requires completed KYC). Modes: Bank account, UPI, PayTM.
- **Gift Cards:** 300+ digital and physical vouchers across retail, lifestyle, jewelry, travel, food, electronics, beauty, wellness, gaming
- **Merchandise:** Physical goods via fulfillment partners (100+ brands, up to 100K shipments/month at peak)
- **Non-monetary:** Staff parties, celebrations, health checkups, insurance, education scholarships, promotional vouchers

### Payout Frequency
Usually monthly, supports weekly/daily cycles. Force redemption auto-triggers for users who don't redeem before expiry.

**Grouped Payouts for Multiple Campaigns (U210109):**
Points for the same user across multiple campaigns are consolidated into a single order, reducing clutter and simplifying reconciliation:
- Admin sees campaign-wise breakdown for accounting; users see a consolidated order
- Rule: only applies for common wallet campaigns; different payment modes = different orders

**15-Minute Force Redemption Frequency (U210109):**
Instead of monthly FR batches, the system now supports round-the-clock forced redemption via a two-tier cron system:
- Cron 1: runs every 15 minutes when points are distributed, flags eligible users for FR
- Cron 2: backup cron runs every 4 hours for missed accounts
- Result: near-real-time payout processing instead of monthly batch spikes

### 6b. KYC — PAN Card Approval Workflow

> **Activities & Roles:** A0072 (View/Download PAN Profiles — all roles incl. Finance & Doc Approver), A0074 (Manage/Approve PAN — currently no roles assigned), A0077 (PAN L1 Approval — Junior Admin, Product Admin, Doc Approver; removed from Client Admin), A0078 (PAN L2 Approval — Finance Admin only). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

**PAN OCR Configurability (U210108):**
PAN OCR (Optical Character Recognition) functionality is configurable at the individual client level. Admin can enable/disable OCR per client via the configuration management interface. When enabled, the end user's camera opens automatically to scan the PAN card — OCR attempts to extract details first, and falls back to manual entry if OCR fails or the image is unclear. When disabled, users upload a PAN card copy manually as before.

**Titan Audit Enhancement (U210084):**
Enhanced audit processes for L1 and L2 verification workflows include dedicated verification page designs for both Bank and PAN profiles, with milestone tracking for implementation progress. UI mockups define the verification page layouts.

**L1 Auto Verification (via NSDL API):**
- PAN details sent to NSDL website via API for instant verification
- Checks: PAN validity, PAN card name match (personal PAN against profile name; firm PAN against entity name), PAN number exact match, optional DOB match, and Aadhaar-PAN linkage status
- If rejected, user can resubmit correct details

**L1 Manual Verification:**
1. KYC approver logs in > User Management > PAN Profiles
2. View dashboard of all submitted PAN cards
3. Click "Action" to view each profile with PAN card copy
4. Verify each parameter and approve/reject individually
5. When adding remarks/comments, use the standardized dropdown (U210107) to select from predefined reasons (top 10-15 common reasons, searchable with auto-suggest). Select "Others" for free-text entry if none of the standard options apply. This dropdown applies across all KYC profile types (PAN, Bank, UPI).
6. Bottom panel shows summary (total claims, approved/rejected, balance)

**L2 Finance Verification (via NSDL):**
After L1 approval, PAN moves to "Pending Verification" status.

Bulk approval steps:
1. Download PAN profiles for verification
2. Check details against NSDL portal
3. Upload data to NSDL for verification
4. Click Bulk Approval L2, download template
5. Map NSDL response against user PANs
6. Upload for approval

L2 verification checks: PAN name exact match with NSDL AND 90% match with MI profile name, PAN number exact match, optional DOB match, Aadhaar-PAN link status (Y = linked, NA = firm PAN, R = rejected).

If PAN is rejected due to Aadhaar not being linked, it is resent for verification once Aadhaar-PAN linking is completed.

### 6c. KYC — Bank Account Approval Workflow

> **Activities & Roles:** A0073 (View/Download Bank Profiles — all roles incl. Finance & Doc Approver), A0075 (Manage/Approve Bank — currently no roles assigned), A0079 (Payout L1 Approval — Junior Admin, Product Admin, Doc Approver; removed from Client Admin), A0080 (Payout L2 Approval — Finance Admin only). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

**L1 Verification:**
1. KYC approver logs in > User Management > Bank Profiles
2. View dashboard, approve/reject individually or bulk upload
3. Verify: account holder name matches profile name, account type matches document, bank name matches, IFSC code matches
4. Enter remarks and approve/reject

**L1 Bulk Approval:** Upload bank profile details with status in available template, then mark for process. Note: individual UI verification is advisable.

**L2 Verification (Penny Drop):**
Post L1 approval, status moves to "Pending Verification Auto." System transfers Rs.2 via API to verify the account is active and validate the account holder's name.

- If name matches 80%+: auto-approved
- If name does not match 80%: moves to "Pending Verification (Manual)" for finance approver review
- Finance approver checks name match (allows spelling mismatches, first/last name interchange, partial middle name)
- Bulk upload option available for L2 verification

### 6d. KYC — UPI Approval Workflow

**UPI ID Entry via Scanning or Upload (U210089):**
Users can enter UPI IDs through multiple methods: direct QR code scanning (camera-based), manual text entry, or file upload for bulk UPI entry. The system validates UPI ID format before submission.

**L1 Verification:**
1. Go to User Management > UPI Profiles
2. Verify: UPI ID prefix matches profile name/shop name/mobile number, UPI name matches profile name
3. Approve/reject individually or bulk upload

**L2 Verification (Penny Drop):**
- Rs.2 transferred to UPI account via API
- Validates UPI account status and matches beneficiary name
- 80%+ match = auto-approved; below 80% = manual verification
- Finance approver checks bank name matches UPI ID bank, beneficiary name matches 80%+

### 6e. KYC — PayTM Approval Workflow

**L1 Verification:**
- Verify: PayTM account name matches profile name, PayTM mobile matches registered mobile (100% match)

**L2 Verification (Penny Drop):**
- Rs.2 transferred via API
- Checks: name 80%+ match, PayTM account validity, minimum KYC completed, mobile number linked (100% match)

### 6f. TDS Management

> **Activities & Roles:** A0076 (Manage TDS — Finance Admin only). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Navigate to Rewards > TDS Management.

Steps:
1. Finance team downloads bulk TDS report from portal for the quarter
2. Uploads required details in template
3. Uploads file and processes
4. TDS certificates become visible to users in the TDS Certificates section

**End-User KYC Flow:**
1. Go to My Profile from My Account
2. **PAN Profile:**
   - If GSTIN is not enabled: When PAN OCR is enabled for the client (U210108), the camera opens automatically to scan the PAN card — system attempts OCR extraction first and falls back to manual entry if scanning fails. When OCR is not enabled, upload PAN card copy manually. Either way, submitted for verification > status changes to "Verified" on success
   - If GSTIN is enabled (U210088): See Section 2b for the conditional GSTIN flow (PAN Card Profile Type → Business PAN → turnover question → GSTIN entry with auto-extraction)
3. **Bank Account:** Enter account number, name (self only), IFSC, select bank > submit > status changes to "Verified" on success
4. **UPI (U210089):** Three input methods available:
   - **Type manually:** Enter UPI ID directly (e.g., name@upi)
   - **Scan QR code:** Use camera to scan a UPI QR code — system extracts the UPI ID automatically
   - **Upload:** Upload an image of the UPI QR code — system extracts the UPI ID from the image
   - After entry, UPI ID is validated and submitted for verification > status changes to "Verified" on success
5. After all required verifications are complete, user is eligible to redeem points for cash

---

## 7. Engagement Features

> **Activities & Roles:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — Engagement Features + Hub + Communications.
> Buzzz: A0005 (Award Points), A0009 (Manage Behaviours), A0013 (Create/Delete Posts), A0014 (Monitor Posts) — all admin roles.
> Certificates: A0041 (Configure Certificates — all admin + Product Admin).
> Quizzes: M0102 (Manage All Quizzes — all admin + Product Admin), M0103 (Manage Own Quizzes — CS roles + Product Admin).
> Hub: A0067 (Add/Edit Docs), A0068 (Configure Hub Settings), A0084 (View Hub) — all admin + Product Admin.
> Communications: A0021 (Configure Emails — not Client Admin), A0039/A0040 (Email & Notification Settings — all admin + Product Admin), M0096 (Subscribe Self — CS Proxy/Std), M0097 (Subscribe Others — CS roles + Product Admin, not Client Admin).

All engagement modules can be toggled on/off per program via Settings > Company > Access Control. Content can be published globally or scoped to specific user groups.

### 7a. Configuration and Scope Controls

**Enabling Engagement Features:**
1. Navigate to Settings > Company > Access Control
2. Toggle ON the modules needed: Buzzz, E-Certificates, Gallery, Hub, Quizzes, News
3. Activated features appear in the left navigation panel

**Using Scope in Engagement Features:**
When composing posts:
- Global audience: visible to all users
- Scoped audience: visible only to users with selected scope tags
- Use the radio button toggle between Global and Scoped
- Last selected scope persists across sessions

**Communication Preferences:**
- Users can subscribe/unsubscribe per module and scope
- Changes propagate in real time across email, SMS, and in-app notifications

### 7b. Buzzz (Recognition)

> **Activities & Roles:** A0005 (Award Points — all admin roles), A0009 (Manage Behaviours — all admin + Product Admin), A0013 (Create/Delete Posts — all admin roles, not Product Admin), A0014 (Monitor Posts — all admin + Product Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Peer-to-peer and manager-to-team recognition posts linked to predefined behaviors.

**Admin Setup:**
1. Navigate to Settings > Engagement > Buzzzes > Buzzz Settings
2. Enable Video and/or Audio Buzzz options
3. Navigate to Settings > Engagement > Buzzzes > Behavior to add/edit/remove behaviors

Default behaviors include: Being Accountable, Being Innovative, Being Creative, Being Hard Working, Being Customer Centric, Being Problem Solver, Taking Initiative, Being a Team Player, Being Passionate, Going Extra Mile, Being Professional.

**Features:**
- Point-based or non-point-based recognition
- Text, audio, and video recognition
- Scope-based filtering and leaderboards
- Likes and comments on posts

### 7c. Birthdays & Anniversaries

Automated notifications and Buzzz wall posts for birthdays and work anniversaries.

Navigate to Engagement > Birthdays or Anniversaries to view published entries with date filters and search.

Requires Date of Birth and Date of Joining in user profiles.

### 7d. Certificates

> **Activities & Roles:** A0041 (Configure Certificates — all admin + Product Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Formal achievement certificates with or without reward points.

**Creating a Certificate Template:**
1. Navigate to Settings > Engagement > Certificates
2. Click "Add a new certificate"
3. Enter certificate name and type (with/without points)
4. Add description for the awarding event
5. Select from pre-designed templates
6. Customize with company logo and signature upload
7. Preview and click "Add"

**Allocating Certificates:**
1. Go to Certificate Allocation section
2. Select users and map certificates from the list
3. Users can then view and award mapped certificates to beneficiaries

**Store Code Search for Certificates (U210103):**
ABMs managing multiple stores can search users by Store Code (department identifier) in addition to name during certificate allocation. Store Code is a mandatory filter in the certificate distribution page — search operates as an AND condition: select Store Code first, then search by email/name. This improves accuracy in user identification and reduces certificate misallocation for multi-store ABMs.

Recipients can download as PDF and share directly to LinkedIn.

### 7e. Quizzes

> **Activities & Roles:** M0102 (Manage All Quizzes — all admin + Product Admin), M0103 (Manage Own Quizzes — CS roles + Product Admin, not Client Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Scheduled knowledge quizzes for training and engagement.

**Creating a Quiz:**
1. Navigate to Engagement > Quiz > "+ Add Quiz"

Step 1 — Quiz Details:
- Quiz name, description, department(s), participants (individual or Select All), number of questions

Step 2 — Schedule:
- Select time, repeat frequency (dropdown), start and end dates
- Schedule notification timing

Step 3 — Add Questions:
- Download template
- Add questions and possible answers with Yes/No for correct answers
- Upload (number of questions must not exceed the pre-set count)

Step 4 — Reward Points:
- With or without points
- If with points: add total reward points per quiz
- Ensure sufficient budget (contact GRG program manager if needed)

Step 5 — Winner Count:
- Set how many winners per quiz
- Preview all sections, then publish

Winners auto-selected by correct answers + fastest completion time. Results displayed on user wall.

### 7f. Gallery, News & Knowledge Center

> **Activities & Roles:** A0019 (Add/Edit Photo & Video Gallery — all admin + Product Admin), A0015 (Create/Edit/Delete News — all admin roles, not Product Admin), A0020 (Knowledge Center Articles — all admin roles, not Product Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

**Gallery:**
1. Navigate to Engagement > Gallery
2. Click "+Album" to create, name it, and upload photos
3. Albums support scope-based visibility and trending dashboards
4. Edit album names, add/delete photos

**News & Articles:**
1. Navigate to Engagement > News & Articles
2. Click "+Add Article"
3. Add headline and body (rich text), assign scopes, optionally enable likes/comments
4. Published articles appear on user walls per scope

**Knowledge Center:**
1. Navigate to Engagement > Knowledge Center
2. Click "+Add Article"
3. Add title, content, scope(s), and optional attachments (PDFs, links, visuals)

### 7g. Hub

> **Activities & Roles:** A0067 (Add/Edit Documents), A0068 (Configure Hub Settings), A0069 (View Hub Settings), A0084 (View Hub Section) — all admin + Product Admin. See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Document repository for training materials, product catalogues, and communications. Supports PDF, MP4, DOCX, MOV.

**Setup:**
1. Activate Hub in the engagement section (Settings > Company > Access Control)
2. Go to Hub section, select allowed document formats, save
3. Click "Add" to create sections
4. Name the section and set its position (start, above, or below existing sections)
5. Create subsections within sections
6. Open subsection > "Add File" to upload documents
7. Verify section name, subsection, add document name, and upload

### 7h. Communication Templates & Management (U210114)

> **Activities & Roles:** A0021 (Configure Emails — CS roles + Product Admin, not Client Admin), A0039 (View Email & Notification Settings — all admin + Product Admin), A0040 (Manage Emails & Notifications — all admin + Product Admin), M0096 (Subscribe/Unsubscribe Self — CS Proxy/Std only), M0097 (Subscribe/Unsubscribe Others — CS roles + Product Admin, not Client Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

**Admin Navigation:** Settings > Communications (left sidebar). Sub-sections: Customization and All Communications.

**All Communications View (Settings > Communications > All Communications):**
The master communications table shows all configured communications across four channel tabs: Emails, Notifications, SMSs, and WhatsApp. Each row displays: Sr No, Communication Code (e.g., Com1, Com2), Communication Event (e.g., Account Activation Reminder, Account Visit Reminder, Buzzz Someone Reminder, Redeem Points Reminder), Can Be Unsubscribed (Yes/No), Subject line, Status (Active/Inactive), and Actions dropdown.

**Email Configuration Options (radio buttons):**
- Default Configuration
- Deactivate all the emails
- Deactivate all the emails that CAN BE UNSUBSCRIBED and activate the rest
- Activate all the emails
- Custom Configuration

A "Download Emails" button is available to export the full email list.

**Communication Master Reference:** The platform includes 217+ pre-configured communication templates across 31 modules (Rewards Management: 54, Campaigns: 42, User Management: 23, Nominations: 19, Recognition: 12, Points Management: 11, Quiz: 8, and others). Channels: Email (214), Notifications (212), SMS (207), WhatsApp (2 via Interakt). Each communication has a unique code (Com1–Com217+) and email code (E001–E217+). Full master list available in `MyIncentives Communications Master 2023.xlsx` in the Claude context folder. Key template variables include: #product_name#, #first_name#, #last_name#, #signature#, #site_url#, #totalwalletbalance#, and 100+ others documented in the "Keys used in Emails n Notifications" sheet.

**Default Communication List:**
A global set of pre-defined default communication templates (Email, SMS, Notifications, WhatsApp) is auto-applied to all new clients. Templates are marked with "Default (Global)" label and can be overridden with custom client-specific templates. This accelerates client onboarding by providing a ready-made communication foundation.

**Status Display Update:**
SMS, Notifications, and WhatsApp communication types no longer use checkboxes — status is displayed as text (active/inactive) and editable via the Actions dropdown.

**Download Options:**
Download button available across all four communication tabs (Email, SMS, Notifications, WhatsApp). Export in CSV or XLSX format with all displayed fields.

**Audit History:**
Unified audit trail tracks all template updates across all communication types, improving compliance and transparency.

### 7i. WhatsApp Status Reports (U210096)

Admin-facing tracking of WhatsApp message delivery. The feature provides visibility into WhatsApp send status across all outbound messages:

- **Status tracking:** Queued, Sent, Delivered, Read, and Failed statuses are available in the UI for each WhatsApp message
- **Admin view:** Allows tracking of WhatsApp sends across campaigns, nudges, and notifications
- **Note:** This feature tracks WhatsApp delivery status — the specific WhatsApp templates and content being sent depend on the client's communication configuration (see Section 7h for communication template management)

### 7j. WhatsApp Two-Way Integration (U210123)

**Phase 1 (Current):** Foundation for inbound WhatsApp message capability:
- Integrates Interakt inbound webhooks with MI
- Receives and logs inbound WhatsApp messages
- Handles message payloads, metadata, retries, and edge cases
- No workflow execution or business actions yet in this phase

**Phase 2 (Planned) — Conversational Workflow Engine:** Will design a deterministic workflow/state engine mapping inbound messages to system states and allowed actions. Evaluating approaches: custom engine, open-source tools, AI-assisted intent resolution.

**Phase 3 (Planned) — Business Flows & Use-Case Enablement:** Will enable actual WhatsApp-driven user journeys with client-specific flows, templates, and measurable business outcomes.

### 7k. Splash Screen Pop-Ups

> **Activities & Roles:** A0026 (Theme & Splash Customization — all admin + Product Admin). See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md).

Full-screen pop-ups shown immediately after login for program announcements, reward schemes, KYC drives.

**Setup Steps:**
1. Navigate to Settings > Company > Theme > Splash Screen
2. Click Edit > select Yes to enable > Save
3. Click "+ Splash Screen"
4. Fill mandatory details:
   - Splash Name (max 30 characters, no special characters)
   - Splash Description (max 270 characters, no special characters)
   - Splash Image (max 5MB, min 400x400, min 72 DPI, PNG/JPG/JPEG)
5. Personalize by scope, role, department, designation
6. Configure redirection: Edit > Yes > select target campaign/page
7. Set visibility schedule and target audience (scope, role, department, designation)
8. Manage order with Move Up/Move Down in Actions
9. Edit anytime including dates; reuse by updating visibility period; delete if not needed

---

## 8. End-User Experience (Mobile App)

> **Activities & Roles:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — Rewards & Wallet + User & Reportee Management.
> Wallet: A0006 (Access to Wallet — all admin roles), A0087 (View & Debit User Wallet — all admin + Product Admin).
> Orders: M0100 (View Orders Management — CS Proxy/Std + Product Admin), M0101 (Initiate Order Cancellation — CS Proxy/Std + Product Admin).
> RM Reportee Management: M0110 (RM Edit Mobile & Shop Name — CS roles only), M0111 (RM View-Only All Profiles — CS roles only).

### Login Flow
1. Download My Incentives from Play Store/App Store
2. Log in with registered email or mobile number
3. First-time users: click "New User" > verify registered mobile/email > request OTP > submit OTP
4. Returning users: log in with password or "Login with OTP" (enter captcha to generate OTP)

**Default India Code +91 (U210104):**
Since all platform users are India-based, the country code defaults to +91 on the login screen. Users enter only their 10-digit mobile number. System gracefully handles pasted inputs with +91 prefix or leading 0 by auto-trimming to the standard +91XXXXXXXXXX format. Cross-platform tested (web, iOS, Android).

**Unauthorized Access Control (U210095):**
Security controls to prevent unauthorized access to the My Incentives platform across all environments:

- **Email domain enforcement:** On UAT and Staging, all user accounts must use @grgindia.in email addresses only — all other domains are blocked. For Live clients, GRG system users must also use @grgindia.in emails.
- **Deactivation of unused companies & users:** All unused companies and their associated users on Staging, UAT, and Live are deactivated.
- **Domain normalization:** Existing users on Staging/UAT with non-@grgindia.in domains (e.g., abcd@gmail.com) are updated to @grgindia.in format (e.g., abcd@grgindia.in), eliminating access for ex-employees or unauthorized users.
- **Mobile number policy:** Mobile numbers removed for all existing users on Staging/UAT. CMS-level configuration enforces email-only user creation, with mobile number input blocked. Mobile numbers can be enabled for specific companies only (for build testing). On Live, mobile numbers are removed for all GRG India system users.
- **CMS governance:** These controls are configured in the CMS (Content Management System), which manages all companies, roles, activity-to-role mappings, license expiry, and license counts per company.

### Home Page
The homepage is widget-based and configurable per role/scope/designation by the admin (U210092/U210100). Typical elements include:

- Points dashboard: earned, redeemed, expired, and balance points cards (may show active-campaign-only data if configured with active-only variables — U210113)
- Click any card for detailed transaction history
- 1 point = 1 rupee
- Graph showing incentive achievement over time
- **Active Campaigns widget (U210125):** Automatically displays all active campaigns the user is part of. Shows 2-4 campaign sub-cards, each with key metrics (e.g., points earned, target progress). Click any sub-card to navigate directly to that campaign's detail page. If 5+ campaigns: first 4 shown + "View All Campaigns" button redirecting to My Campaigns. If no active campaigns: "User is not currently a part of any active campaigns."
- Clickable widgets (U210100): some dashboard elements may be interactive — clicking navigates to detail pages (e.g., clicking a points widget opens transaction history)

Note: Different roles may see different homepage layouts based on admin configuration. The widgets, metrics, and visible campaigns are all tailored per role/scope/designation.

### Campaign Views
- **Type D (Auto-calc):** If widget-based view is enabled (U210116), the campaign page shows a configurable widget dashboard first (point dashlets, KPIs, leaderboard, sales transactions), followed by the regular dashboard below. Click "View Details" for full campaign details. If widget-based view is not enabled, shows the standard real-time performance dashboard with sales, targets, % achievement, projected and earned incentives across all configured KPIs, transaction-wise sales summary, and leaderboard.
- **Type D (Sales Manager view):** Non-participant managers can view reports within "View Details," track team KPI progress, and access scope-based leaderboard for their mapped retailers/salespeople.
- **Type C (Claims):** Submit claims with photo upload, track claim status (pending/approved/rejected), view history
- **Type G (Scan):** Camera-based QR scanner or manual code entry, instant point confirmation, scan history
- **Type B (Approval-based):** View distributed points, approval status. If excess distribution warnings are active (U210102), the SM sees real-time cap validation during point distribution (see Section 4b for full flow).
- **Type F (Referral):** Submit referral details, track referral status

### Tiers
- View current tier status on login (similar to airline/hotel apps)
- View points required for next tier
- Tier upgrades based on achievement thresholds (real-time upgrades, periodic downgrades)
- Different point earnings based on tier status

### Rewards Section
Browse catalogue, filter by category, redeem points for cash/gift cards/merchandise. View transaction history, pending payouts, and point balance. Note: payouts from multiple campaigns are now consolidated into a single order per user (U210109), so users see fewer, larger transactions instead of scattered small ones. Force redemption payouts are processed every 15 minutes (instead of monthly batches), so users receive payouts much faster after points are distributed.

### Profile & KYC
Update personal details, submit KYC documents (PAN, bank, UPI — see End-User KYC Flow in Section 6f for detailed steps including GSTIN entry, PAN OCR scanning, and UPI QR scanning), track verification status. If GSTIN is enabled for the client, the PAN submission flow includes a conditional GSTIN entry path (see Section 2b).

### Notifications & Nudges
- Bell icon (top right) for all app notifications
- Also receivable as phone push notifications (must enable in phone settings)
- **WhatsApp (U210096):** Status reports and notifications can also be delivered via WhatsApp. Users may receive automated reports on point balances, campaign performance, or payout confirmations directly in WhatsApp.
- Types: Updates (onboarding counts, point credits), Reminders (campaign deadlines, target gaps), Insights (peer comparisons, earning opportunities)

### Engagement
Access Buzzz wall, certificates, quizzes, gallery, news, knowledge center, and hub. Scope selector filters content.

### Help & Support
Email support via ticketing system. When submitting a support ticket, the user's phone number is auto-filled from their profile (U210117), and for users in multiple companies, tickets are automatically routed to the correct company's support department. Dedicated call center support available at additional cost with multiple language options.

---

## 9. Reporting & Analytics

> **Activities & Roles:** See [2_Activities_roles_reference_01Apr2026.md](2_Activities_roles_reference_01Apr2026.md) — Dashboards & Reports.
> A0018 (Engagement Dashboard — all admin + Finance), A0051 (Campaigns Points Dashboard — all admin + Finance), A0052 (Dashboard Visibility Settings — CS Proxy/Std + Product Admin), A0053 (User Assignment for Dashboard — all admin + Product Admin), M0108 (Zoho Custom Dashboard — CS roles + Product Admin, not Client Admin), M0109 (Engagement Dashboard MI — CS roles + Product Admin, not Client Admin), M0113 (Points File Uploads & Audits — removed from Client Admin).

### Standard Reports Available
- Campaign-level: Points allocated, awarded, pending, redeemed, expired
- Claim reports: Submitted, approved, rejected, pending — with drill-down and approval history
- User reports: All user info with tier audit trail, KYC status, point balances
- Tier reports: Date-wise tier movements with user profile data and KPI values
- Scan reports: Scan history, success/failure, points earned per scan
- Redemption reports: Payout status, mode breakdown, TDS deductions
- Engagement analytics: Scope-wise engagement metrics, trending content

**Reporting Enhancements (U210105):**
New columns added across key reports to improve reconciliation, fulfillment tracking, and participant-level analysis. Report access depends on whether the relevant activity is assigned to the user's role (see 2_Activities_roles_reference_01Apr2026.md).

| # | Report Name | New Columns Added | Purpose | Navigation Path |
|---|------------|-------------------|---------|----------------|
| 1 | Force Redemption Report | Order Status, UTR ID | Link financial records with campaign context and transaction-level identifiers for reconciliation and tracking | Force Redemption Report |
| 2 | Redemption Report | Order Delivered Date, FR/Non-FR order type | Visibility of campaign association and fulfillment timeline within redemption tracking | Redemption Report |
| 3 | Participants Data | User ID | Support participant-level data mapping and analysis of user activation timelines | L1: Monthwise Data View > L2: May-Campaigns Data View > L3: [Program] Participants Data View |
| 4 | Primary Profile Report / Attrition Report | First Activation Date | Track the first time a user was activated (previously only last activation date was available) | Primary Profile, Attrition Report |

### Dashboards
Real-time analytical dashboards with filters by campaign, hierarchy level, time period. Manager and admin views with cascading visibility per business hierarchy mapping.

**Customizable Widgets — Phase I (U210092):**
Administrators can customize dashboard widgets with drag-and-drop configuration, variable mapping for metrics, and widget-specific configuration options. A master variable list (maintained in Excel) governs available metrics for each widget type.

**Customizable Clickable Widgets — Phase II (U210100):**
Phase 2 extends widgets with interactive/clickable elements:
- Clickable widget components that navigate to detail pages
- Interactive dashboard elements with advanced configuration
- Widget nesting capabilities
- Multiple design iterations incorporating testing feedback (including Khushy's testing feedback)

**Active-Only Variables for Metric Card Widget (U210113):**
New variables that show only active campaign data, excluding expired campaigns:
- `active_camp_points_earned`: Points earned from active campaigns only
- `active_camp_points_balance`: Balance from active campaigns only
- `active_camp_points_redeemed`: Redeemed points from active campaigns only
- Variables visible in metric card widget creation; expired campaign data never included
- Empty/zero/fallback states handled gracefully

**Active Campaigns Widget (U210125):**
A new homepage widget type that automatically displays all active campaigns relevant to the logged-in user, eliminating manual admin configuration overhead:

- Master card titled "Active Campaigns" contains 2-4 campaign sub-cards
- Each sub-card shows 2 default variables (or custom admin-configured variables) and is clickable to navigate to campaign detail page
- Edge cases: 0 campaigns → "User is not currently a part of any active campaigns"; 1-4 campaigns → display all; 5+ campaigns → show 4 + "View All Campaigns" button redirecting to My Campaigns page
- Admin configures visibility by role/scope/designation and can set visible variables per campaign type
- Auto-updates as campaigns are created or expired — configured once, no ongoing maintenance

**Homepage Builder — Dashboard Configuration:**
The Homepage Builder (Settings > Dashboard > Homepage Builder) controls which dashboard type each user segment sees. When adding a new dashboard:
1. Navigate to Dashboard > Homepage Builder > Add new dashboard
2. Enter Dashboard Name (max 100 characters)
3. Select Role (required) — note: Standard user role cannot be selected for Analytical Dashboard
4. Select Scope (required)
5. Select Department (required)
6. Select Designation (required)
7. Select dashboard type (radio buttons):
   - **Standard Dashboard** — default point widgets and banner-based homepage
   - **Widget-Based Dashboard** — fully configurable widget homepage (U210092/U210100)
   - **5X Dashboard** — powered by the BI reporting layer
   - **Analytical Dashboard** — desktop-only data dashboard (U210122)
8. Save

Each combination of Role + Scope + Department + Designation gets exactly one dashboard type. Sub-sections under Dashboard in the left sidebar: Engagement, Campaign, Homepage Builder.

**Analytical Dashboard Enhancement (U210122):**
Desktop-only (explicitly not mobile build) analytical dashboard with four core sections:

**Section 1 — Point Summary** (formerly "Campaign Performance Overview" / "Points Graph"):
- Month-by-month points summary (April → March) controlled by Financial Year dropdown (default = current FY, toggle to previous FY)
- Cluster bar chart (not stacked); single color with shades (5 distinct colors was too jarring)
- Shows 6 most recent months with horizontal scroll capability
- Improved dashlet design: aligned on same line, commas in large numbers (dashlets + axes)
- X-axis = month (not campaign); no red for rejected numbers
- Edge case handling: graceful display when only 1-2 months completed in a given FY

**Section 2 — User Summary** (formerly "Users Count"):
- **2a. User Count:** Total users, active users, licenses, licenses available. New metric: users earning points in last 3 months (engagement proxy). Summary table with stats side by side and percentages with denominators shown.
- **2b. Payout Status:** Bank + UPI consolidated using OR logic ("Payout verified" = Bank verified OR UPI verified). Other states: rejected, pending verification, document mismatch, submitted, not submitted.
- **2c. PAN Status:** All statuses must sum to 100% of total users. Statuses vary by client configuration:
  - Clients with Aadhaar linkage + ₹10K threshold: PAN+Aadhaar KYC, Only PAN, Not submitted, Pending verification, Not Applicable (<₹10K)
  - Clients without Aadhaar or threshold: PAN KYC complete, Not submitted, Pending verification
  - TDS consent users (no PAN but gave consent; redemption allowed at 20% TDS vs 15% for PAN verified)
  - Radio toggle in Homepage Builder to switch PAN/Payout widgets on/off (not all clients use both, e.g. Titan)
- **2d. Login Trend (Visitor Trend):** Monthly unique visitors only (daily/weekly filter removed by design). Filters: Role, Scope.

**Section 3 — Campaign Detail** (formerly "Data View"):
- Table loads directly (no multi-level dropdown navigation)
- Includes all campaigns in selected FY (not only active); Financial Year toggle top right
- Columns include: campaign ID/name/status, participant count, activation/expiry dates, allocated/unused/distributed/not redeemed/redeemed/expired wallet/expired campaign, plus two new columns:
  - Campaign Type with display labels: Direct Awarding (A), Distribution and Approval (B), Invoice Upload (C), Calculation and Approval (D), Refer and Earn (F), Scan and Earn (G)
  - % Participants Earning Points
- Owner and Sponsor columns hidden. Pagination ~10 rows/page. Commas for readability. Total Allocated Points column visually distinguished. Status entries color-coded. Fixed column widths (no horizontal scroll).

**Campaign Summary Cards:** Summary card view above the detail table with visual hierarchy (key metrics vs. supporting metrics differentiated by card size). White and grey colour scheme for dashlets.

**General Design Direction:** More whitespace throughout; reduced visual density; percentages on same line without repeated "of total users" text.

**Advanced Filters in My Reportees Section (U210101):**
Enhanced filtering in the "My Reportees" management section for managers. Navigate to My Account > My Reportees > Primary Profiles to access the "Advanced filters" panel.

**Available filter dropdowns:**
- **Select Status:** Active / Draft / Inactive
- **Select Reportee Type:** Direct / Indirect
- **Select Payout Verified:** Yes / No (whether the reportee's payout method is verified)
- **Select PAN Verified:** Yes / No (whether PAN is verified)
- **Select Active in Last 30 Days:** Yes / No (recent activity filter)

Filters are applied per session — there are no saved filter presets; each time the manager opens the page, filters reset to default (all). The table shows columns: User ID, Employee ID, Email ID, Name, Activation date, User Role, Reportee Type (Direct/Indirect), Pan Status, Payout Status, Status, and Actions.

**Linkage with Homepage Widget:** When a My Reportees summary widget is configured on the homepage (U210092/U210100), the redirect from the widget to the reportees page can be pre-configured to auto-apply one or more of these filters (e.g., Active + Direct + Payout Completed + PAN Completed), so the manager lands on a pre-filtered view directly from the dashboard.

---

## 10. Screen Inventory

### Screen: Admin Dashboard — All Campaigns
- **Purpose:** Admin overview of all active/completed/pending campaigns
- **Key elements:** Campaign cards with status (Active, Pending for Approval, Draft, Completed), type, date range, budget, participant count
- **Actions available:** Create new, Edit, Pause, Clone, View Analytics, Campaign Settings, Incentives Calculation, Points Management
- **Users:** Product Admin, Finance Admin, Campaign Owner
- **Navigation path:** Left menu > All Campaigns
- **Current limitations:** Campaign type and awarding level cannot be changed once saved

### Screen: Budget Management — Sponsors, Buckets, POs
- **Purpose:** Manage funding sources, budget containers, and purchase orders
- **Key elements:** Sponsor list with icons, Bucket list with curator and expiry, PO list with ID/amount/attachment
- **Actions available:** Create sponsor, Create bucket, Manage Points, Add PO, Approve PO
- **Users:** Product Admin (create), Point Curator (approve)
- **Navigation path:** Left menu > Budget Management > Sponsors/Buckets

### Screen: Data Sources — Table Management
- **Purpose:** Manage the data engine powering Type D campaigns and tier management
- **Key elements:** Table list with type tags (Custom/Integrated/Derived/Campaign), column headers, row counts, import/export status
- **Actions available:** Create Table, View, Import (Upload/Map Columns), Export, Create Derived Table
- **Users:** Product Admin, Campaign Owner, Analysts
- **Navigation path:** Left menu > Data Sources

### Screen: Campaign Settings (Type D)
- **Purpose:** Configure final incentive table mapping, KPIs, leaderboards, nudges, and transaction views for automated campaigns
- **Key elements:** Final Incentive Table config (identifier mapping, output columns), KPI list (target meters/scorecards/progress bars), Leaderboard config, Nudge list, Transaction Table config
- **Actions available:** Map tables, Add/Edit KPIs, Configure leaderboard, Add nudges, Set transaction view
- **Users:** Campaign Owner
- **Navigation path:** All Campaigns > Actions > Campaign Settings

### Screen: Campaign Settings (Type B)
- **Purpose:** Configure point distribution controls, approval matrix, and allocation for approval-based campaigns
- **Key elements:** Distribution controls (No control/Fixed/Percentage/Multiplier), Time limits, Equal distribution date, Approval matrix status, Allocation grid
- **Actions available:** Edit controls, Upload approval matrix, Upload/Edit allocation, View awarding status
- **Users:** Campaign Owner, Points Manager
- **Navigation path:** All Campaigns > Actions > Campaign Settings / Points Management

### Screen: Campaign Settings (Type C)
- **Purpose:** Configure claim forms, earning logic, SKU selection, and approval matrix for invoice claim campaigns
- **Key elements:** Claim form builder (Google Forms-style), Earning logic slabs, SKU selection template, Approval matrix, Approval workflow type selector
- **Actions available:** Edit form, Upload SKU template, Upload claim approval matrix, View/Delegate claims
- **Users:** Campaign Owner
- **Navigation path:** All Campaigns > Actions > Campaign Settings / Claim Management

### Screen: Campaign Settings (Type G)
- **Purpose:** Configure scan codes, point validation, final scan table, and incentive formulas for scan-and-earn campaigns
- **Key elements:** SKU codes list with search, Scan validation matrix, Multiple scan settings, Base/Final scan table selector, Incentive formula builder (condition + action), Payout summary
- **Actions available:** Upload codes, Search codes, Upload validation matrix, Configure scan table, Set incentive formula
- **Users:** Campaign Owner, Analysts
- **Navigation path:** All Campaigns > Actions > Campaign Settings

### Screen: Tier Management
- **Purpose:** Configure dynamic performance-based tier system
- **Key elements:** Segments list (with scope/role tags), Tiers within segments (name/logo/color/order), KPI list (table/column mappings), Movement matrix status, Scheduler settings, Nudge configuration
- **Actions available:** Create segment, Add tiers, Add KPIs, Upload movement matrix, Configure scheduler, Set nudges
- **Users:** Product Admin
- **Navigation path:** Left menu > Tier Management

### Screen: User Management
- **Purpose:** Manage all platform users, their profiles, hierarchy mappings, and KYC status
- **Key elements:** User list with status/role/department/scope, Hierarchy Mapping grid, PAN/Bank/UPI/PayTM profile dashboards with approval status
- **Actions available:** Add user, Edit user, Upload users (bulk CSV), Hierarchy Mapping, PAN/Bank/UPI profile approval (individual + bulk), Download profiles
- **Users:** Product Admin, Finance Admin, KYC Approver
- **Navigation path:** Left menu > User Management

### Screen: Rewards Settings
- **Purpose:** Configure reward catalogue, cash payout options, KYC requirements, and TDS settings
- **Key elements:** Catalogue mapping with scope, Cash payout mode toggles (Bank/UPI/PayTM), KYC L1/L2 configuration matrix, TDS country settings, Force redemption toggle
- **Actions available:** Add catalogue, Map products, Activate products per scope, Configure KYC levels, Upload TDS certificates
- **Users:** Product Admin, Finance Admin, Rewards Team
- **Navigation path:** Left menu > Settings > Rewards

### Screen: Engagement Settings
- **Purpose:** Enable and configure all engagement modules
- **Key elements:** Feature toggles (Buzzz, Certificates, Gallery, Hub, Quizzes, News), Buzzz behavior list, Certificate templates, Quiz builder, Splash screen manager
- **Actions available:** Toggle features, Add behaviors, Create certificates, Build quizzes, Configure splash screens
- **Users:** Product Admin
- **Navigation path:** Left menu > Settings > Company > Access Control / Engagement

### Screen: Participant Mobile App — Home
- **Purpose:** Salesperson/retailer sees their active campaigns, points balance, and recent activity
- **Key elements:** Points dashboard (earned/redeemed/expired/balance), Active campaign banners with progress, Quick actions (Scan QR, Enter Code)
- **Navigation:** Home, Campaigns, Rewards, Profile, Engagement
- **Users:** Channel partners, retailers, salespeople, influencers

### Screen: Participant Mobile App — Campaign View (Type D)
- **Purpose:** View real-time performance against KPIs and incentive calculations
- **Key elements:** KPI visualizations (target meters/progress bars/scorecards) with target vs. achievement, Leaderboard section, Transaction-wise sales summary table, Projected and earned incentive amounts
- **Actions available:** View KPIs, View leaderboard, View transactions, View all ranks
- **Users:** Campaign participants

### Screen: Participant Mobile App — Campaign View (Type C)
- **Purpose:** Submit and track invoice claims
- **Key elements:** Claim form (configurable fields), Invoice upload, Claim history with status (Pending/Approved/Rejected), Approval comments thread
- **Actions available:** + Claim (submit new), View claim details, Track status
- **Users:** Campaign participants (claim submitters)

### Screen: Participant Mobile App — Campaign View (Type G)
- **Purpose:** Scan QR codes and earn instant points
- **Key elements:** QR scanner (camera-based), Manual code entry field, Scan result (Success/Error/Sorry), Scan history, Points balance update
- **Actions available:** Scan QR, Enter code manually, View transaction history
- **Users:** Campaign participants

### Screen: Participant Mobile App — Rewards
- **Purpose:** Browse and redeem earned points
- **Key elements:** Rewards catalogue (cash/gift cards/merchandise), Category filters, Point balance, Transaction history, Pending payouts
- **Actions available:** Browse catalogue, Redeem points, View history, Download TDS certificates
- **Users:** All participants with verified KYC (for cash)

### Screen: Participant Mobile App — Profile & KYC
- **Purpose:** Manage personal details and KYC document submission
- **Key elements:** Primary profile fields, PAN profile (with status), Bank account profile (with status), UPI profile (with status), PayTM profile (with status)
- **Actions available:** Update profile, Submit PAN, Submit bank details, Submit UPI, Track verification status
- **Users:** All participants

### Screen: Manager Mobile App — Team Performance
- **Purpose:** View aggregated team performance and manage approvals
- **Key elements:** Team performance view (By KPI / By User), KPI target meters for each team member, Leaderboard with customizable columns, Search bar (by beat code), Approval queue (claims/distributions)
- **Actions available:** View by KPI, View by user, View all (leaderboard), Approve/Reject claims, Approve/Reject distributions, Search retailers
- **Users:** Sales Managers, Regional Managers, City Managers

### Screen: Manager Mobile App — My Reportees
- **Purpose:** Manage team members and their KYC status
- **Key elements:** Reportee list with status, KYC submission status per user (PAN/Bank/UPI), Add new user form, Advanced filters (U210101), Designation update request flow (U210120)
- **Actions available:** Add retailer/salesperson, View/edit reportee details, Submit KYC on behalf of reportees, Request designation change (with ABM approval), Add/delete reportees with separate approval configs (U210111), Filter reportees with multi-criteria advanced filters
- **Users:** Sales Managers

### Screen: Customizable Widget Dashboard (U210092/U210100)
- **Purpose:** Admin-configurable homepage with drag-and-drop widgets showing key metrics
- **Key elements:** Metric card widgets (with active-only variables — U210113), clickable widgets navigating to detail pages, active campaigns widget (U210125), variable mapping from master list
- **Actions available:** Add/remove/reorder widgets, configure widget variables, set role/scope/designation visibility, nest widgets
- **Users:** Product Admin (configuration), all users (viewing)
- **Navigation path:** Admin: Settings > Homepage Configuration; Users: Home page

### Screen: Analytical Dashboard (U210122)
- **Purpose:** Desktop-only consolidated analytics with 4 sections: Point Summary, User Summary (User Count + Payout + PAN + Login Trend), Campaign Detail, Campaign Summary Cards
- **Key elements:** Point Summary (month-by-month cluster bar chart with FY toggle, 6-month scroll), User Summary (total/active/licensed users + payout status + PAN status + monthly unique visitors), Campaign Detail table (all campaigns in FY with type labels, % earning points), Campaign Summary Cards
- **Actions available:** Toggle financial year, scroll months, download reports, filter by Role/Scope (Login Trend), view campaign detail with pagination
- **Users:** Access controlled via Homepage Builder — configured per Role + Scope + Department + Designation. Standard user role excluded from Analytical Dashboard.
- **Navigation path:** Dashboard > Homepage Builder (admin config); end users see it as their homepage if assigned

### Screen: Designation Approval Queue (U210120)
- **Purpose:** ABMs review and approve/decline designation change requests from Store Managers
- **Key elements:** Queue of pending designation requests with employee details, current and proposed designation, SM who initiated, remarks field
- **Actions available:** Approve, Decline (with optional remarks), view request history
- **Users:** Area Business Managers (ABMs)

### Screen: Type D Hierarchy Approval (U210118/U210126)
- **Purpose:** Multi-level approval workflow for automated incentive distribution with edit guardrails
- **Key elements:** Earning file with per-row data, approval chain status, edit cap indicators (U210126), campaign-wise breakdown
- **Actions available:** Approve/reject/edit individual rows (within cap limits), view audit trail, process approval chain
- **Users:** ABMs, Managers, Approvers in hierarchy chain

### Screen: Communication Management (U210114)
- **Purpose:** Manage communication templates across all channels with default templates and audit history
- **Key elements:** Tabs for Email/SMS/Notifications/WhatsApp, default (global) templates with override capability, status display (active/inactive), audit history log
- **Actions available:** Create/edit templates, download template lists (CSV/XLSX), toggle status via Actions dropdown, view audit trail
- **Users:** Product Admin, Client Admin

---

## 11. Product Dependency Map — What Needs to Be Set Up First

Understanding the linkages between different parts of My Incentives is critical for successful implementation. Here is the dependency chain showing what must be configured before each feature can work.

### Foundation Layer (Must Be Set Up First for Everything)

```
Company Setup
├── License Management & Whitelisting (1a)
├── User Types & Roles (1b)
├── Departments & Designations (1b)
├── Scopes (1b)
└── Business Hierarchy (1c)
    └── User-to-Hierarchy Mapping
```

**Without this:** No users can register, no campaigns can function, no approval workflows work, no data visibility cascading.

### Campaign Prerequisites by Type

**All Campaign Types require:**
1. Company Setup (Section 1) — complete
2. Budget Setup: Sponsor > Bucket > PO (Section 3a) — must exist before campaign creation
3. Users onboarded (Section 2) — participants must be registered
4. PO Approved by Point Curator (Section 3c) — campaign stays "Pending" without this

**Type A (Direct Awarding) additionally requires:**
- Nothing beyond the common prerequisites

**Type B (Approval-Based) additionally requires:**
- Business hierarchy with users mapped to hierarchy nodes
- Approval matrix uploaded and status = "Defined" (blocks point allocation until defined)
- Awarders and approvers must be active users in the hierarchy
- Optional: Excess distribution warnings configured with user-level caps (U210102)

**Type C (Invoice Claims) additionally requires:**
- Product hierarchy set up with SKUs (Section 1d) — required before SKU selection
- Business hierarchy with users mapped — required for claim approval routing
- Claim form configured
- Earning logic defined (slabs or per-SKU points)
- Claim approval matrix uploaded — maps which user at each node approves claims

**Type D (Automated Calculation) additionally requires:**
- Data Sources tables created and populated (Section 5) — the entire data pipeline must exist
- Final incentive table (prefixed "F") created in Data Sources
- Campaign Settings configured: table mapping, output columns, incentive calculation rule
- Users must be both campaign participants AND have matching entries in Data Sources (unmatched users are excluded)
- Business hierarchy mapped for users BEFORE adding them as participants
- Optional: Flexible widget-based campaign view configured per role (U210116)
- Optional: Hierarchy approval workflow for distribution (U210118) — requires business hierarchy + approval chain
- Optional: Row-level edit caps configured for approver guardrails (U210126) — requires cap column in final incentive table

**Type F (Refer and Earn) additionally requires:**
- Product hierarchy (if product-specific referrals)
- Referral approval workflow configured

**Type G (Scan and Earn) additionally requires:**
- Product hierarchy with SKUs (Section 1d) — SKUs must exist before code upload
- SKU codes uploaded with validity dates (must use SKU name, not description)
- Scan validation matrix uploaded — defines points per SKU per user type
- Optional: Final Scan Table for milestone-based earning (requires Data Sources derived table)

### Tier Management Dependencies

```
Tier Management requires:
├── At least one Scan & Earn campaign with participants added
│   (triggers backend user data sync in MongoDB)
├── Data Sources table with 1 row per user
│   ├── Cannot use auto-generated Base Scan Table (multiple rows per user)
│   └── Must create a derived table (e.g., count of total scans per user)
├── Tier Segments defined with scopes and roles
├── KPIs mapped to Data Sources columns
└── Tier Movement Matrix uploaded
    └── Scope and role in matrix must match actual user attributes
```

### KYC & Rewards Dependencies

```
Cash Redemption requires:
├── Rewards Settings configured (catalogue, cash modes, KYC levels)
├── PAN verification (if TDS applicable)
│   ├── L1: Document verification (manual or NSDL API)
│   └── L2: Finance verification (NSDL portal check)
├── Bank/UPI/PayTM verification
│   ├── L1: Document verification
│   └── L2: Penny drop (Rs.2 API transfer)
└── TDS certificates uploaded (quarterly, by Finance team)

Gift Card / Merchandise Redemption requires:
├── Rewards catalogue mapped (Catalogue ID from Tolshop)
├── Products activated per scope
└── Sufficient point balance
```

### Engagement Feature Dependencies

```
All Engagement Features require:
├── Feature toggled ON in Settings > Company > Access Control
└── Scopes defined (for targeted content)

Buzzz requires:
├── Behaviors configured (default or custom)
└── Optional: Video/Audio enabled in Buzzz Settings

Certificates require:
├── Templates created with logo/signature
└── Certificates allocated to managers/users

Quizzes require:
├── Questions uploaded via template
├── Schedule configured
└── Budget allocated (if points-based)

Birthdays/Anniversaries require:
└── Date of Birth / Date of Joining in user profiles

Hub requires:
├── Document formats selected
└── Sections and subsections created

Splash Screens require:
├── Splash Screen enabled in Theme settings
└── Images meeting minimum specs (400x400, 72 DPI)
```

### Data Flow Dependencies (Type D Campaigns)

```
Raw Sales Data (Excel from client)
    ↓ Data Cleaning (add primary key, format numbers, add period ID)
    ↓ Upload to Custom/Integrated table in Data Sources
    ↓ Verification (UI spot checks or export comparison)
    ↓ Create Derived table (filter by period)
    ↓ Create Final table (prefix "F") with incentive calculations
    ↓ Map Final table to Campaign (Campaign Settings)
    ↓ Map unique user identifier (Email/Employee ID/User ID/Phone)
    ↓ Select output columns visible to participants and managers
    ↓ Set incentive calculation rule (select final incentive column)
    ↓ Optional: Configure KPIs, Leaderboard, Nudges, Transaction View
    ↓ Participants see real-time performance in mobile app
```

---

## 12. Integration Capabilities

- **Data ingestion:** CSV upload (including to Integrated Tables — U210106), API, SFTP
- **KYC verification:** NSDL API (PAN), penny drop (bank accounts), UPI VPA validation, PAN OCR scanning (U210108), UPI QR code scanning (U210089)
- **Notifications:** Email, SMS, push notifications, in-app
- **WhatsApp:** Status reports delivery (U210096), two-way integration via Interakt webhooks (U210123 — Phase 1 live, Phases 2-3 planned)
- **Communication management:** Default global templates, client-level overrides, audit history across all channels (U210114)
- **Helpdesk:** Zoho integration with multi-company ticket routing, department-based segregation, auto phone mapping (U210117)
- **SSO:** Supported with error alerts to scope POC
- **Rewards fulfillment:** Tolshop execution panel for catalogue management
- **Dashboards:** Zoho or 5X based hierarchical dashboards (optional), customizable widgets (U210092/U210100), analytical dashboard enhancements (U210122)

---

## 13. Key Terminology Quick Reference

| Term | Meaning |
|------|---------|
| Sponsor | Funding entity for campaign budgets |
| Bucket | Budget container linked to a sponsor |
| PO | Purchase Order — defines budget ceiling for a campaign |
| Point Curator | User who approves PO-to-campaign budget mapping |
| Scope | Tag for controlling content visibility (region, department, etc.) |
| Business Hierarchy | Org structure for data visibility and approval routing |
| Product Hierarchy | SKU/product tree for campaign incentive mapping |
| Data Sources | In-app database with custom, integrated, derived, and campaign tables |
| BST | Base Scan Table — auto-generated scan log for Type G campaigns |
| FST | Final Scan Table — custom table for milestone-based scan earning |
| Tier Segment | Group of tiers for a specific user population |
| Tier Movement Matrix | Rules defining KPI thresholds for tier upgrades |
| Force Redemption | Auto-payout of unredeemed points before expiry |
| Buzzz | Peer recognition module |
| Common Wallet | Shared rewards catalogue across campaigns |
| Campaign-specific Wallet | Unique catalogue for a single campaign |
| L1 Verification | First-stage KYC: document check |
| L2 Verification | Second-stage KYC: financial verification (penny drop) |
| Penny Drop | Rs.1-2 test transfer to verify active bank/UPI/PayTM account |
| Derived Table | Data Sources table created by joining/aggregating other tables |
| Campaign Table | Final Data Sources table linked to a campaign (prefixed "F") |
| Approval Matrix | Template mapping awarders and approvers per hierarchy path |
| Scan Validation Matrix | Template defining points per SKU per user attribute |
| Cron | Scheduled system job that processes uploaded files (runs periodically) |
| Hierarchy Path | Full path notation e.g., india>west>mumbai |
| Scope POC | Point of contact who receives SSO error alerts for their scope |
| GSTIN | GST Identification Number — configurable user profile field (U210088) |
| Proxy User | User acting on behalf of another within defined permissions (U210091) |
| PAN OCR | Optical Character Recognition for PAN card scanning, configurable per client (U210108) |
| Row-Level Edit Cap | Per-row ceiling on Type D approver edits to prevent payout inflation (U210126) |
| Active Campaign Widget | Homepage widget auto-displaying active campaigns per user (U210125) |
| Interakt | WhatsApp Business API provider used for MI's WhatsApp integration (U210096/U210123) |
| FR Frequency | Force Redemption execution frequency — now supports 15-minute cycles (U210109) |
| Identifier-Based Join | Flexible table join using explicitly selected columns (U210119) |
