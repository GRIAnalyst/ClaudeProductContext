# 2. MI Activities & Roles Reference — 1 April 2026
**Source:** MI activities roles - 19 Jan 2026.xlsx
**Total Activities:** 113 across 4 modules
**Note:** Activities labeled "Buzzz" in the source Excel have been migrated into My Incentives. All 113 activities are MI activities.

---

## Role Definitions

| Role | Type | Description |
|------|------|-------------|
| **CS Admin with Proxy** | CSM (internal) | GRG Customer Success admin with proxy access — highest CSM-level access |
| **CS Admin (Standard)** | CSM (internal) | Standard GRG Customer Success admin |
| **Junior Admin** | CSM (internal) | Junior-level GRG admin — restricted access to sensitive configurations |
| **Administrator (Standard)** | Client | Client-facing admin role — limited system configuration access |
| **Product Admin** | System | Full product configuration access — can edit all settings |
| **Finance Admin** | System | Finance-specific access — TDS, PAN L2, Payout L2, budget curator |
| **Documents Approver** | System | KYC document approval access — PAN L1, Payout L1, profile viewing |

**Access counts (activities granted):** CS Admin Proxy: 85 | CS Admin Standard: 83 | Junior Admin: 76 | Client Administrator: 61

---

## Platform Activities (79)
*Source module: "Buzzz" — migrated into My Incentives*

### Company & Settings Configuration

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0001 | View Company Settings | See settings link | 1 | 1 | 1 | 1 | yes | yes | yes |
| A0007 | Go Inside View Settings | Go inside company settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0008 | Edit Company Profile | Change configs in company profile | 0 | 0 | 0 | 0 | yes | yes | no |
| A0012 | Configure Access Control | Define access control for client company | 0 | 0 | 0 | 0 | yes | no | no |
| A0043 | Configure Security Policy | Configure Password Management | 1 | 0 | 0 | 0 | yes | no | no |
| A0054 | Configure SSO Settings | Access SSO settings for company | 0 | 0 | 0 | 0 | yes | no | no |

### Budget Management

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0002 | View Budget Management | View Budget Management | 1 | 1 | 1 | 1 | yes | yes | no |
| A0003 | Add Edit Budget | Add/edit/delete budget creation entries | 1 | 1 | 0 | 0 | no | yes | no |
| A0004 | Allocate Edit Delete Points to Budget Owners | Allocate budget, edit/delete allocated points for budget owners | 1 | 1 | 1 | 1 | yes | no | no |
| A0027 | Configure Budget Categories | Configure budget categories | 1 | 1 | 1 | 1 | yes | no | no |
| A0085 | Point Curator at Bucket Level | Be mapped as points curator (bucket) | 1 | 1 | 1 | 1 | no | yes | no |

### User Management & Profiles

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0010 | View/Edit/Activate/Deactivate Users | View/Edit/Activate/Deactivate Users (limited to primary profile) | 1 | 1 | 1 | 1 | yes | no | no |
| A0011 | View Edit My Profile | View and edit own profile and change password | 1 | 1 | 1 | 1 | yes | yes | yes |
| A0024 | Bulk Upload Users | Create users without verifying emails/mobile | 1 | 1 | 1 | 0 | yes | no | no |
| A0023 | Add Dummy User | Add dummy user (product admin) | 0 | 0 | 1 | 0 | yes | no | no |
| A0071 | View/Download Primary Profiles | View and download Primary Profile of any user from user management | 1 | 1 | 1 | 1 | yes | yes | yes |
| A0088 | Edit Email ID in User Profile | Edit email ID in any user profile | 1 | 1 | 0 | 0 | yes | no | no |
| A0089 | Edit Bank and PAN Details | Edit Bank and PAN details of other users | 0 | 0 | 1 | 1 | yes | no | no |

### KYC & Document Management

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0072 | View/Download PAN Profiles | View and download PAN Profile from user management | 1 | 1 | 1 | 1 | yes | yes | yes |
| A0073 | View/Download Bank Account Profiles | View and download Bank Account Profile from user management | 1 | 1 | 1 | 1 | yes | yes | yes |
| A0074 | Manage/Approve PAN Profiles | Manage/Approve PAN Profiles (Edit, bulk upload, L1 approve) | 0 | 0 | 0 | 0 | no | no | no |
| A0075 | Manage/Approve Bank Account Profiles | Manage/Approve Bank Account Profiles (Edit, bulk upload, L1 approve) | 0 | 0 | 0 | 0 | no | no | no |
| A0076 | Manage TDS | Manage TDS including upload of TDS certificates | 0 | 0 | 0 | 0 | no | yes | no |
| A0077 | PAN Details Level 1 Approval | Approve/Reject PAN L1 one by one or bulk | 0 | 0 | 1 | Removed | yes | no | yes |
| A0078 | PAN Details Level 2 Approval | Approve/Reject PAN L2 one by one or bulk | 0 | 0 | 0 | 0 | no | yes | no |
| A0079 | Payout Details Level 1 Approval | Approve/Reject payout L1 one by one or bulk | 0 | 0 | 1 | Removed | yes | no | yes |
| A0080 | Payout Details Level 2 Approval | Approve/Reject payout L2 one by one or bulk | 0 | 0 | 0 | 0 | no | yes | no |

### Hierarchy Management

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0081 | View Hierarchy | View Hierarchy section and different levels | 1 | 1 | 1 | 1 | yes | no | no |
| A0082 | Manage Hierarchy | Edit Hierarchy section and levels | 1 | 1 | 1 | Removed | yes | no | no |
| A0083 | Mapping Hierarchy to User Profile | Map hierarchy to any user profile | 1 | 1 | 1 | 1 | yes | no | no |
| A0022 | View & Edit Organisation Structure | Configure organisation structure of the company | 1 | 1 | 1 | 1 | yes | no | no |

### Engagement Features

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0005 | Award Points | Award points on Recognitions, Bdays and Anniversaries | 1 | 1 | 1 | 1 | yes | no | no |
| A0009 | Manage Behaviours | View/Create/Edit/Activate/Deactivate behaviours | 1 | 1 | 1 | 1 | yes | no | no |
| A0013 | Create Delete Posts | Create and delete own posts | 1 | 1 | 1 | 1 | no | no | no |
| A0014 | Monitor Posts | Monitor all posts as admin | 1 | 1 | 1 | 1 | yes | no | no |
| A0015 | Create/Edit/Delete News | Create, edit and delete news | 1 | 1 | 1 | 1 | no | no | no |
| A0019 | Add/Edit Photo & Video Gallery | Add or edit photo album or video | 1 | 1 | 1 | 1 | yes | no | no |
| A0020 | Knowledge Center Articles | Create/Edit/Delete articles in Knowledge Center | 1 | 1 | 1 | 1 | no | no | no |
| A0025 | Configure Mood-O-Meter | Configure Mood-O-Meter | 1 | 1 | 1 | 1 | yes | no | no |
| A0026 | Theme & Splash Customization | Theme customization for client company | 1 | 1 | 1 | 1 | yes | no | no |
| A0028 | Configure Badges | Configure Badges | 1 | 1 | 1 | 1 | yes | no | no |
| A0029 | Manage All Nomination Events | Add/Edit/View all nomination events | 1 | 1 | 1 | 1 | yes | no | no |
| A0030 | Manage Own Nomination Events | Add/Edit/View only own events | 1 | 1 | 1 | 1 | yes | no | no |
| A0041 | Configure Certificates | Configure Certificates | 1 | 1 | 1 | 1 | yes | no | no |
| A0070 | View Home Page | View home page (if access control ON) | 1 | 1 | 1 | 1 | yes | no | no |

### Hub

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0067 | Hub — Add/Edit Documents | Add/Edit documents in Hub | 1 | 1 | 1 | 1 | yes | no | no |
| A0068 | Hub — Configure Settings | Configure Hub related settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0069 | Hub — View Settings | View Hub related settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0084 | View Hub Section | View Hub section | 1 | 1 | 1 | 1 | yes | no | no |

### Rewards & Wallet

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0006 | Access to Wallet | Check wallet details | 1 | 1 | 1 | 1 | no | no | no |
| A0016 | View Rewards | View rewards | 1 | 1 | 1 | 1 | yes | yes | no |
| A0017 | View My Orders | View own orders | 1 | 1 | 1 | 1 | yes | no | no |
| A0046 | View Rewards Settings | View Rewards Settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0047 | Edit Rewards Settings | Edit Rewards Settings (Product Admin only) | 0 | 0 | 0 | 0 | yes | no | no |
| A0086 | Manage Forced Redemptions | Initiate forced redemption | 1 | 1 | 1 | 1 | yes | no | no |
| A0087 | View & Debit User Wallet | View and debit other user's wallet points | 1 | 1 | 1 | 1 | yes | no | no |

### Dashboards & Approvals

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0018 | View Engagement Dashboard | View engagement dashboard by department | 1 | 1 | 1 | 1 | yes | yes | no |
| A0042 | View My Approvals | View my approvals | 1 | 1 | 1 | 1 | yes | no | no |
| A0051 | View Campaigns Points Dashboard | View Campaigns points dashboard in MI | 1 | 1 | 1 | 1 | yes | yes | no |
| A0052 | View Visibility Settings for Dashboard | View visibility settings for dashboard | 1 | 1 | 0 | 0 | yes | no | no |
| A0053 | View User Assignment for Dashboard | View User Assignment setting for dashboard | 1 | 1 | 1 | 1 | yes | no | no |

### Communications & Settings

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0021 | Configure Emails | Configure emails for client company | 1 | 1 | 1 | 0 | yes | no | no |
| A0044 | View Storage Settings | View Storage settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0045 | Edit Storage Settings | Edit Storage settings (Product Admin) | 0 | 0 | 0 | 0 | yes | no | no |
| A0048 | View Support Settings | View Support Settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0049 | Edit Support Settings | Edit Support Settings (Product Admin) | 0 | 0 | 0 | 0 | yes | no | no |
| A0050 | Access to Help | View Help section | 1 | 1 | 1 | 1 | yes | yes | yes |

### LinkedIn Integration

| Activity ID | Activity Name | CS Proxy | CS Std | Jr Admin | Client Admin |
|-------------|--------------|----------|--------|----------|-------------|
| A0064 | Share on Personal Wall | 0 | 0 | 0 | 1 |
| A0065 | Share on Company LinkedIn Page | 0 | 0 | 0 | 0 |
| A0066 | Manage LinkedIn Settings | 0 | 0 | 0 | 1 |

### SuperCheques (Legacy)

| Activity ID | Activity Name | CS Proxy | CS Std | Jr Admin | Client Admin |
|-------------|--------------|----------|--------|----------|-------------|
| A0055-A0063 | SuperCheques management (9 activities) | 0 | 0 | 0 | 0 |

---

## Programs Module Activities (9)

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0032 | View Program Config (Settings) | View Program configurations from settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0033 | Edit Program Config (Settings) | Edit Program configurations from settings | 1 | 1 | 1 | Removed | yes | no | no |
| A0034 | View Programs Section | View Programs Tab | 1 | 1 | 1 | 1 | yes | no | no |
| A0035 | View Program Config (Company) | View Program configurations at company level | 1 | 1 | 1 | 1 | yes | no | no |
| A0036 | Edit Program Config (Company) | Edit Program configurations at company level | 1 | 1 | 1 | Removed | yes | no | no |
| A0037 | Manage Own Programs | Add/edit/activate/deactivate own programs, manage points/approvals | 1 | 1 | 1 | 1 | yes | no | no |
| A0038 | Manage All Programs | Add/edit/activate/deactivate any program (client admin level) | 1 | 1 | 1 | 1 | yes | no | no |
| A0039 | View Email & Notification Settings | View email & notification settings under overall settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0040 | Manage Emails & Notifications | Manage & customise emails/notifications for company | 1 | 1 | 1 | 1 | yes | no | no |

---

## My Incentives Module Activities (3)

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| A0090 | View Reportee Rules & Requests | View reportee creation rules, view all reportee addition requests, edit profile settings | 1 | 1 | 1 | 1 | yes | no | no |
| A0092 | RM Edit Non-Primary Profiles | Allow Reporting Manager to view and edit all profiles other than primary | 1 | 1 | 1 | 0 | no | no | no |
| M0091 | Add/Edit Reportee Creation Rules | Add/edit/activate/deactivate reportee creation rules | 0 | 0 | 0 | 0 | yes | no | no |

---

## MyIncentives Module Activities (22)

### Data Sources & Campaigns

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin | Fin Admin | Doc Approver |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|-----------|-------------|
| M0093 | Data Sources Tab Visible | Add, edit and manage custom data tables for Data Sources | 1 | 1 | 0 | 0 | yes | no | no |
| M0098 | View Referrals (Type F) | View all referrals by hierarchy in Type F campaign | 1 | 1 | 1 | 0 | yes | no | no |
| M0099 | Auto-Participant Type F | Active user directly becomes participant in Type F | 1 | 1 | 1 | 1 | yes | yes | no |
| M0104 | View All Referrals (No Hierarchy) | View all referrals irrespective of hierarchy in Type F | 0 | 0 | 0 | 0 | N/A | N/A | N/A |
| M0105 | Include SKUs/Codes Type G | Include SKUs and codes in Type G campaign | 1 | 1 | 0 | 0 | yes | no | no |

### Tier Management

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|
| M0106 | View Tier Management | View Tier management under settings | 1 | 1 | 1 | 1 | yes |
| M0107 | Edit Tier Management | Edit Tier management under settings | 1 | 1 | 0 | 0 | yes |

### Engagement & Communication

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|
| M0094 | Redeem Rewards | Redeem rewards using Redeem button | 1 | 1 | 1 | 1 | no |
| M0095 | Create Global Engagement Post | Create global post for engagement items | 1 | 1 | 1 | 1 | no |
| M0096 | Subscribe/Unsubscribe Comms (Self) | Subscribe/unsubscribe own communications | 1 | 1 | 0 | 0 | no |
| M0097 | Subscribe/Unsubscribe Comms (Others) | Subscribe/unsubscribe communications for other users | 1 | 1 | 1 | 0 | yes |
| M0102 | Manage All Quizzes | Add/Edit/View all quizzes & questions library | 1 | 1 | 1 | 1 | yes |
| M0103 | Manage Own Quizzes | Add/Edit/View only own quizzes | 1 | 1 | 1 | 0 | yes |

### Dashboards & Reports

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|
| M0108 | View Zoho Custom Dashboard | View Zoho custom dashboard in MI | 1 | 1 | 1 | 0 | yes |
| M0109 | View Engagement Dashboard (MI) | View engagement dashboard in MI (master activity) | 1 | 1 | 1 | 0 | yes |
| M0112 | Reference File Upload (Points) | Make reference file upload with every points upload in Type A, B and D campaigns | 1 | 1 | 1 | Removed | yes |
| M0113 | View Points File Uploads & Audits | View 'Points File Uploads and Audits' section under analytics dashboard | 1 | 1 | 1 | Removed | yes |

### User & Reportee Management

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|
| M0100 | View Orders Management | View-only rights for orders management under settings | 1 | 1 | 0 | 0 | yes |
| M0101 | Initiate Order Cancellation | Cancel orders for given client company | 1 | 1 | 0 | 0 | yes |
| M0110 | RM Edit Mobile & Shop Name | Edit mobile number (with OTP) and Shop name from reportee primary profile | 1 | 1 | 0 | 0 | no |
| M0111 | RM View-Only All Profiles | Reporting Manager can ONLY view all profiles of reportees | 1 | 1 | 0 | 0 | no |

### Proxy Access

| Activity ID | Activity Name | Description | CS Proxy | CS Std | Jr Admin | Client Admin | Prod Admin |
|-------------|--------------|-------------|----------|--------|----------|-------------|------------|
| M0114 | Assign Proxy Access | Allows CMS admins to give internal GRG user proxy access to client companies | 1 | 0 | 0 | 0 | — |

---

## Key Access Patterns

### Activities ONLY Product Admin can perform (not available to any CSM or Client Admin):
- A0008: Edit Company Profile
- A0012: Configure Access Control
- A0047: Edit Rewards Settings
- A0049: Edit Support Settings
- A0054: Configure SSO Settings
- A0045: Edit Storage Settings
- M0091: Add/edit reportee creation rules

### Activities ONLY Finance Admin can perform:
- A0003: Add/Edit Budget (shared with CS Proxy/Std)
- A0076: Manage TDS
- A0078: PAN Details Level 2 Approval
- A0080: Payout Details Level 2 Approval
- A0085: Point Curator at Bucket Level

### Activities available to Documents Approver:
- A0077: PAN Details Level 1 Approval
- A0079: Payout Details Level 1 Approval
- A0071-A0073: View/Download all profile types
- A0001: View Company Settings
- A0011: View/Edit own profile
- A0050: Access to Help

### Activities removed from Client Administrator:
- A0033, A0036: Edit Program Configurations
- A0077: PAN Details L1 Approval
- A0079: Payout Details L1 Approval
- A0082: Manage Hierarchy
- M0112: Reference file upload for points
- M0113: View Points File Uploads & Audits

---

## Cross-References to User Manual

| Activity Area | Activity IDs | User Manual Section |
|--------------|-------------|-------------------|
| Company Setup & Config | A0001, A0007, A0008, A0012, A0022 | Section 1 — Company Setup |
| License & Whitelisting | A0043, A0054 | Section 1a — License Management |
| User Management | A0010, A0024, A0071, A0088, A0089 | Section 2 — User Onboarding |
| Reportee Management | A0090, A0092, M0091, M0110, M0111 | Section 2d — Reportee Addition |
| Budget Management | A0002, A0003, A0004, A0027, A0085 | Section 3a — Budget Setup |
| Campaign Management | A0037, A0038, M0105 | Sections 4a-4g — Campaign Setup |
| Data Sources | M0093 | Section 5 — Data Sources |
| KYC — PAN | A0072, A0074, A0077, A0078 | Section 6b — PAN KYC |
| KYC — Bank | A0073, A0075, A0079, A0080 | Section 6c — Bank KYC |
| Rewards & Redemption | A0006, A0016, A0017, A0046, A0047, M0094 | Section 6 — Rewards |
| TDS | A0076 | Section 6f — TDS Management |
| Forced Redemption | A0086 | Section 3e / 6 — Force Redemption |
| Engagement — Recognition | A0005, A0009, A0013, A0014 | Section 7b — Recognition |
| Engagement — Certificates | A0041 | Section 7d — Certificates |
| Engagement — Quizzes | M0102, M0103 | Section 7e — Quizzes |
| Engagement — Hub | A0067, A0068, A0069, A0084 | Section 7g — Hub |
| Engagement — News/Knowledge | A0015, A0020 | Section 7f — Gallery, News & KC |
| Theme & Splash | A0026 | Section 7k — Splash Screen |
| Communications | A0021, A0039, A0040, M0096, M0097 | Section 7h — Communication Templates |
| Hierarchy | A0081, A0082, A0083 | Section 1c — Business Hierarchy |
| Tier Management | M0106, M0107 | Section 4g — Tier Management |
| Dashboards | A0018, A0051, A0052, A0053, M0108, M0109 | Section 9 — Reporting & Analytics |
| Points File Upload & Audit | M0112, M0113 | Section 5c — Points File Upload |
| Approvals | A0042 | Section 4d — My Approvals Hub |
| Proxy User | M0114 | Section 2c — Proxy User |
| Orders | M0100, M0101 | Section 6 — Rewards |
| Wallet | A0006, A0087 | Section 8 — End-User Rewards |
