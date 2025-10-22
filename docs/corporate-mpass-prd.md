# Product Requirements Document (PRD)

## Document Information

| Field | Value |
|-------|-------|
| **Document Title** | Moneta for Enterprise (Corporate mPass) - Product Requirements Document |
| **Author** | Diem Nguyen |
| **Creation Date** | 10/15/2025 |
| **Last Updated** | 10/20/2025 |
| **Version** | 1.3.0 |
| **Status** | In Review |

> **Note:** This is a living document that will evolve as we learn more through development iterations.

## 1. Product Vision and Goals

### 1.1 Problem Statement

The Moneta Network has successfully addressed the "Digital Services Paradox" in the B2C space by providing Publishers with zero-cost user acquisition and Membership Organizations (MOs) with new revenue streams.

However, a significant and valuable market remains untapped: enterprise clients. These businesses face their own paradox: a critical need for diverse, premium digital services (AI, B2C SaaS, Media) but no centralized, flexible, or secure framework to procure, manage, and pay for them at scale. This leads to uncontrolled "shadow IT" spending on personal credit cards, lack of visibility, and significant administrative overhead for expense reporting.

### 1.2 Product Vision

To become the global standard for how enterprises procure, manage, and pay for digital services, transforming MOs into the indispensable "Trusted Digital Partners" for their business clients. We will achieve this by extending the Moneta Network to empower Corporate Administrators with a simple, secure, and powerful platform to centrally manage employee access to a world of premium digital tools, unlocking new value for the entire ecosystem.

### 1.3 Business Objectives

- **Expand Total Addressable Market (TAM):** Unlock the lucrative B2B segment, driving significant new transaction volume and network fee revenue.
- **Increase MO Stickiness:** Provide MOs with a powerful B2B offering to attract and retain high-value enterprise clients, deepening their customer relationships beyond core services.
- **Boost Publisher Revenue:** Create a zero-cost, high-volume acquisition channel for Publishers to enter the enterprise market, increasing their revenue and predictability.
- **Simplify Corporate Operations:** Radically simplify digital service procurement and management for enterprise clients, reducing their administrative burden and providing clear financial controls.

### 1.4 Target Users

- **Corporate Administrator (Admin):** An IT, Finance, or Operations Manager who needs to control costs, manage access, and simplify billing for all digital services their employees use.
- **Corporate Employee (mPass User):** Any employee who needs seamless, on-demand access to premium digital tools for their job without using personal payment methods or filing expense reports.
- **MO Admin:** An enterprise account manager at an MO who needs a system to onboard, manage risk for, and support their corporate clients.

## 2. Product Backlog Overview

### 2.1 MVP Definition

The Minimum Viable Product (MVP) for "Moneta for Enterprise" will enable a core end-to-end flow using a post-paid funding model: a Corporate Administrator can submit an application for a Corporate mPass, be approved by an MO, onboard employees, set a single company-wide policy for access and spending, receive a consolidated bill, and settle with the MO at the end of the month.

**MVP Includes:**

- **Corporate Onboarding:** A corporate application process that requires manual review and approval by an MO Admin.
- **Post-Paid Funding Model with Credit Limits:** The MO assigns a master spending limit (credit limit) to the Corporate mPass during approval, enabling post-paid billing.
- **Core User Management:** The ability for an Admin to invite individual employees, invite users in bulk via file upload, and manage their activation status.
- **Basic User Groups:** The ability for an Admin to organize employees into User Groups (departments).
- **Hierarchical Policy Controls:** The ability for an Admin to set spending limits and service access policies at the company, group, and individual levels.
- **Transaction Tracking & Billing:** Real-time transaction logs for both Admins and Employees, and a consolidated monthly statement for the Admin with end-of-month settlement to the MO.
- **Direct Dispute & Compensation:** The ability for both Employees and Admins to dispute transactions, which are then automatically compensated, with full visibility for the Admin.

**Post-MVP (Future Enhancements):**

- **Autonomous Corporate Verification:** The MVP onboarding process requires manual MO Admin approval. Automated verification workflows are post-MVP.
- **Advanced Role-Based Access Control (RBAC):** The MVP supports only "Administrator" and "Employee" roles. Additional roles (e.g., Finance Viewer, Department Manager) are post-MVP.
- **Pre-Paid (Top-Up) Funding Model:** Alternative funding models beyond post-paid credit are post-MVP.
- **Advanced Reporting & Analytics:** The MVP provides transaction logs and basic billing statements. A full analytics dashboard with data visualization, trends, and forecasting is post-MVP.

### 2.2 Epic Summary

| Epic | Description | Priority |
|------|-------------|----------|
| **Corporate mPass Onboarding & Management** | Covers the application, approval, and initial setup for a corporate entity. | Must |
| **User Provisioning** | Covers the complete lifecycle management of individual employee mPass users. | Must |
| **User Group Management** | Covers the creation of user groups (departments) and the assignment of users to them. | Should |
| **Policy Management** | Covers the creation of policies that control both service access and financial spending limits. | Must |
| **Corporate Billing & Reporting** | Covers the end-of-cycle billing and administrative reporting. | Must |
| **Corporate Dispute Management** | Defines the administrator-mediated dispute process. | Must |

### 2.3 User Stories

> **Note:** This section includes the list of user stories. The complete acceptance criteria for each user story will be written in a separate story definition document.


#### 2.3.1 Epic 1: Corporate mPass Onboarding & Management

| ID | User Story | Priority |
|----|------------|----------|
| **US-1.1** | As a **Corporate Administrator**, I want to submit an application for a Corporate mPass through my MO so that **I can enable my company to consume digital services via mPass**. | H |
| **US-1.2** | As an **MO Admin**, I want to receive and review new Corporate mPass applications in a dedicated portal queue so that **I can verify the business and assess its creditworthiness**. | H |
| **US-1.3** | As an **MO Admin**, I want to **Approve** or **Deny** a new application so that **I can manage our financial risk and officially onboard the client**. | H |
| **US-1.4** | As an **MO Admin**, I want to assign a master spending limit (credit limit) to a Corporate mPass during approval so that **we can manage our collection risk for corporate clients**. | H |
| **US-1.5** | As a **Corporate Administrator**, I want to receive an email notification after my application has been reviewed so that **I know my application status and can proceed with next steps**. | H |
| **US-1.6** | As a **Corporate Administrator**, I want to log in to my central Admin Portal *once my application is approved* so that **I can start managing my account**. | H |
| **US-1.7** | As a **Corporate Administrator**, I want to view my assigned credit limit and current balance in the Admin Portal so that **I can monitor our available spending capacity**. | H |
| **US-1.8** | As a **Corporate Administrator**, I want to receive notifications when approaching my credit limit (e.g., 80%, 90%, 100%) so that **I can proactively manage spending or request a limit increase**. | M |
| **US-1.9** | As an **MO Admin**, I want to view a dashboard/list of all Corporate mPass accounts I manage so that **I can monitor and oversee my corporate client portfolio**. | H |
| **US-1.10** | As an **MO Admin**, I want to search and filter corporate accounts by name, status, credit limit, or outstanding balance so that **I can quickly find specific accounts**. | M |
| **US-1.11** | As an **MO Admin**, I want to view detailed information for a specific Corporate mPass (company details, credit limit, current balance, status, Admin contact) so that **I can review account health and provide support**. | H |
| **US-1.12** | As an **MO Admin**, I want to view transaction history and spending patterns for a specific Corporate mPass so that **I can assess usage and identify any anomalies**. | M |
| **US-1.13** | As an **MO Admin**, I want to adjust the credit limit for an existing Corporate mPass so that **I can respond to changing business needs or credit profiles**. | M |
| **US-1.14** | As an **MO Admin**, I want to suspend or resume a corporate mPass so that **I can immediately revoke access and prevent further spending from a corporate account with payment issues or suspected fraud**. | H |
| **US-1.15** | As an **MO Admin**, I want to receive alerts when a Corporate mPass exceeds certain thresholds (credit limit reached, unusual spending patterns, overdue payments) so that **I can take proactive action to manage risk**. | M |


#### 2.3.2 Epic 2: User Provisioning

| ID | User Story | Priority |
|----|------------|----------|
| **US-2.1** | As a **Corporate Administrator**, I want to invite an employee via email to create their Individual Corporate mPass so that **I can grant them access to company-funded digital services**. | H |
| **US-2.2** | As a **Corporate Administrator**, I want to upload a file to **invite users in bulk** so that **I can efficiently onboard an entire team or department or company at once**. | H |
| **US-2.3** | As a **Corporate Administrator**, I want to see the results of my bulk upload (successful invitations, errors, duplicates) so that **I can verify the upload and follow up on any issues**. | H |
| **US-2.4** | As a **Corporate Employee**, I want to accept an email invitation and register for my Individual Corporate mPass so that **I can start accessing the digital services my company provides**. | H |
| **US-2.5** | As a **Corporate Administrator**, I want to view a list of all my employees and their activation status (Pending, Active, Suspended) so that **I can track who has successfully onboarded**. | H |
| **US-2.6** | As a **Corporate Administrator**, I want to search and filter my employee list by name, email, status, or User Group so that **I can quickly find specific employees**. | M |
| **US-2.7** | As a **Corporate Administrator**, I want to view detailed information for a specific employee (contact info, activation date, assigned group, current policies, transactions) so that **I can manage their account effectively**. | M |
| **US-2.8** | As a **Corporate Administrator**, I want to resend an invitation email to an employee who hasn't activated their account so that **they can complete registration if they missed or lost the original email**. | H |
| **US-2.9** | As a **Corporate Administrator**, I want to edit an employee's basic information (name, email) so that **I can keep employee records accurate**. | M |
| **US-2.10** | As a **Corporate Administrator**, I want to suspend an employee's mPass so that **I can temporarily revoke access without fully removing them from the system**. | H |
| **US-2.11** | As a **Corporate Administrator**, I want to reactivate a suspended employee's mPass so that **they can resume accessing services when they return to work or resolve issues**. | H |
| **US-2.12** | As a **Corporate Administrator**, I want to permanently de-provision an employee's mPass so that **I can completely remove access when an employee leaves the company**. | H |
| **US-2.13** | As a **Corporate Administrator**, I want to receive notifications when employees activate their Corporate mPass so that **I can track onboarding progress**. | M |
| **US-2.14** | As an **MO Admin**, I want to view the total number of employees and their activation status for each Corporate mPass I manage so that **I can assess account adoption and health**. | M |
| **US-2.15** | As an **MO Admin**, I want to view a list of all employees under a specific Corporate mPass so that **I can provide support to Corporate Admins and monitor account activity**. | M |
| **US-2.16** | As an **MO Admin**, I want to view detailed information for a specific employee's individual Corporate mPass (activation date, transaction history, policies) so that **I can troubleshoot issues or investigate suspicious activity**. | M |
| **US-2.17** | As an **MO Admin**, I want to suspend an individual employee's Corporate mPass so that **I can immediately block access in cases of suspected fraud or policy violations without suspending the entire corporate account**. | M |

#### 2.3.3 Epic 3: User Group Management

| ID | User Story | Priority |
|----|------------|----------|
| **US-3.1** | As a **Corporate Administrator**, I want to create and name a **User Group (Company Department)** so that **I can organize my employees for efficient policy and budget management**. | H |
| **US-3.2** | As a **Corporate Administrator**, I want to view a list of all my User Groups with basic information (name, member count) so that **I can see how my organization is structured**. | H |
| **US-3.3** | As a **Corporate Administrator**, I want to view detailed information for a specific User Group (members list, assigned policies, total spending) so that **I can manage and monitor that department effectively**. | M |
| **US-3.4** | As a **Corporate Administrator**, I want to edit or rename a User Group so that **I can keep group names accurate as my organization evolves**. | M |
| **US-3.5** | As a **Corporate Administrator**, I want to assign an existing user to a **User Group** from the user list so that **they inherit the policies and budgets associated with that group**. | H |
| **US-3.6** | As a **Corporate Administrator**, I want to assign a User Group to an employee during the invitation process so that **new employees are automatically placed in the correct department upon activation**. | M |
| **US-3.7** | As a **Corporate Administrator**, I want to bulk assign multiple employees to a User Group so that **I can efficiently organize large teams without repetitive individual assignments**. | M |
| **US-3.8** | As a **Corporate Administrator**, I want to move an employee from one User Group to another so that **I can reflect organizational changes like transfers or promotions**. | M |
| **US-3.9** | As a **Corporate Administrator**, I want to remove a user from a **User Group** so that **they revert to the company's default policies**. | M |
| **US-3.10** | As a **Corporate Administrator**, I want to delete a User Group and specify what happens to its members (move to another group or revert to company default) so that **I can reorganize without losing control of employee access**. | M |
| **US-3.11** | As an **MO Admin**, I want to view the User Group structure for a specific Corporate mPass so that **I can understand their organizational hierarchy when providing support or reviewing policies**. | L |
| **US-3.12** | As an **MO Admin**, I want to view spending and transaction patterns by User Group for a Corporate mPass so that **I can identify high-risk departments or unusual activity**. | L |

#### 2.3.4 Epic 4: Policy Management

| ID | User Story | Priority |
|----|------------|----------|
| **US-4.1** | As a **Corporate Administrator**, I want to set a master monthly spending limit for the entire company so that **I can enforce our overall budget and prevent overspending**. | H |
| **US-4.2** | As a **Corporate Administrator**, I want to set a monthly spending limit for a User Group so that **I can control budgets by department**. | H |
| **US-4.3** | As a **Corporate Administrator**, I want to set a monthly spending limit for an individual employee so that **I can manage spending for specific roles or special cases**. | H |
| **US-4.4** | As a **Corporate Administrator**, I want to set a company-wide service access policy by whitelisting or blacklisting Publishers and categories so that **I can ensure all employees adhere to a baseline of approved services**. | H |
| **US-4.5** | As a **Corporate Administrator**, I want to set a service access policy for a User Group so that **I can tailor application access for the specific needs of that department**. | M |
| **US-4.6** | As a **Corporate Administrator**, I want to set a service access policy for an individual employee so that **I can make exceptions to grant or restrict access for unique roles**. | H |
| **US-4.7** | As a **Corporate Administrator**, I want to view all existing policies (spending limits and service access) at company, group, and individual levels so that **I can understand my current policy configuration**. | H |
| **US-4.8** | As a **Corporate Administrator**, I want to edit or update an existing policy (spending limit or service access) at any level so that **I can adjust controls as business needs change**. | H |
| **US-4.9** | As a **Corporate Administrator**, I want to remove or reset a policy at group or individual level so that **those entities revert to inheriting from the parent level**. | M |
| **US-4.10** | As a **Corporate Administrator**, I want to receive notifications when policy violations occur (attempted purchases that exceed limits or access blocked services) so that **I can monitor compliance and identify training needs**. | M |
| **US-4.11** | As a **Corporate Administrator**, I want to view a log of all policy changes (who changed what, when) so that **I can maintain accountability and audit our policy management**. | M |
| **US-4.12** | As a **Corporate Employee**, I want to be notified if an attempted purchase is denied due to a policy restriction (spending limit or service access) so that **I understand why the transaction failed and can take appropriate action**. | H |
| **US-4.13** | As a **Corporate Employee**, I want to view my current spending limit and remaining balance for the billing period so that **I can manage my usage responsibly**. | H |
| **US-4.14** | As a **Corporate Employee**, I want to browse the mPass Guide and only see services my active policy permits so that **I can easily find and use the tools I am authorized to access**. | H |
| **US-4.15** | As an **MO**, I must deny any "Subscription Charge Authorization" request that violates any rules defined in the active policy (spending limit or service access) so that **the company is protected from exceeding its approved budgets and unauthorized service usage**. | H |
| **US-4.16** | As an **MO**, I must validate policies in real-time during transaction authorization and return clear error messages when denying requests so that **employees receive immediate feedback on why their request was blocked**. | H |
| **US-4.17** | As an **MO Admin**, I want to view the policy configuration for a specific Corporate mPass so that **I can provide support when Corporate Admins have questions or issues with policy setup**. | L |

#### 2.3.5 Epic 5: Corporate Billing & Basic Reporting

| ID | User Story | Priority |
|----|------------|----------|
| **US-5.1** | As a **Corporate Administrator**, I want to view a real-time, searchable log of all transactions across the company so that **I can have complete visibility into our digital service spending**. | H |
| **US-5.2** | As a **Corporate Administrator**, I want to filter and sort the company's transaction log by employee, User Group, Publisher, and date so that **I can easily analyze spending patterns and prepare internal reports**. | H |
| **US-5.3** | As a **Corporate Administrator**, I want to export the transaction log to CSV or Excel so that **I can perform additional analysis or integrate with our internal systems**. | M |
| **US-5.4** | As a **Corporate Administrator**, I want to view my current outstanding balance and credit utilization in real-time so that **I can monitor our financial position throughout the billing cycle**. | H |
| **US-5.5** | As a **Corporate Administrator**, I want to receive notifications when the billing cycle is ending and payment is due so that **I can prepare for settlement with the MO**. | H |
| **US-5.6** | As a **Corporate Administrator**, I want to receive a *single, consolidated monthly statement* from my MO at the end of each billing cycle so that **I have a simple bill to process**. | H |
| **US-5.7** | As a **Corporate Administrator**, I want to view a detailed, itemized report on my monthly statement broken down by **User Group** and by **individual employees** so that **I can analyze spending and perform internal cost allocation**. | H |
| **US-5.8** | As a **Corporate Administrator**, I want to download/export my monthly statement as PDF so that **I can share it with finance teams or archive it for records**. | M |
| **US-5.9** | As a **Corporate Administrator**, I want to pay my monthly statement to my MO so that **my company's account remains in good standing**. | H |
| **US-5.10** | As a **Corporate Administrator**, I want to receive a payment confirmation and receipt after settling my monthly bill so that **I have proof of payment for our records**. | H |
| **US-5.11** | As a **Corporate Administrator**, I want to view my payment history (past statements, payment dates, amounts) so that **I can track our billing history and verify past payments**. | M |
| **US-5.12** | As a **Corporate Employee**, I want to view my personal transaction history so that **I can track what services I've used and verify charges**. | H |
| **US-5.13** | As a **Corporate Employee**, I want to export my personal transaction history so that **I can keep my own records if needed**. | L |
| **US-5.14** | As an **MO Admin**, I want to view the current billing cycle status for each Corporate mPass (current balance, credit utilization, payment due date) so that **I can monitor account health and collection risk**. | H |
| **US-5.15** | As an **MO Admin**, I want to view all transactions for a specific Corporate mPass within a billing cycle so that **I can verify charges and resolve billing inquiries**. | M |
| **US-5.16** | As an **MO Admin**, I want to generate and send the consolidated monthly statement to a Corporate mPass at the end of each billing cycle so that **the client receives their bill for settlement**. | H |
| **US-5.17** | As an **MO Admin**, I want to receive and process payments from Corporate mPasses so that **I can settle their monthly statements and update their account balance**. | H |
| **US-5.18** | As an **MO Admin**, I want to view payment history for each Corporate mPass so that **I can track their payment behavior and creditworthiness**. | M |
| **US-5.19** | As an **MO Admin**, I want to flag and manage overdue Corporate mPass accounts so that **I can take action on late payments and protect revenue**. | M |
| **US-5.20** | As an **MO Admin**, I want to send payment reminders to Corporate Administrators with overdue balances so that **I can encourage timely payment and reduce delinquency**. | L |

#### 2.3.6 Epic 6: Corporate Dispute Management

| ID | User Story | Priority |
|----|------------|----------|
| **US-6.1** | As a **Corporate Employee**, I want to dispute a transaction from my personal transaction history so that **I can get an immediate automatic credit for a charge I believe is incorrect**. | Done |
| **US-6.2** | As a **Corporate Employee**, I want to provide a reason when disputing a transaction so that **there's a record for my company and the MO to review**. | Done |
| **US-6.3** | As a **Corporate Employee**, I want to receive an immediate notification when my dispute is automatically accepted and credited so that **I know the issue has been resolved**. | Done |
| **US-6.4** | As a **Corporate Employee**, I want to view my personal dispute history (disputed transactions, reasons, credits received) so that **I can track all disputes I've filed**. | Done |
| **US-6.5** | As a **Corporate Administrator**, I want to dispute a transaction directly from the company-wide transaction log so that **I can correct billing errors on behalf of the company or individual employees with immediate automatic compensation**. | M |
| **US-6.6** | As a **Corporate Administrator**, I want to provide a reason when disputing a transaction so that **there's a record of why the charge was contested**. | M |
| **US-6.7** | As a **Corporate Administrator**, I want to receive notifications when employees dispute transactions so that **I'm aware of dispute activity within my organization**. | M |
| **US-6.8** | As a **Corporate Administrator**, I want to view a real-time log of all disputes (employee-initiated and admin-initiated) with their automatic credits so that **I have full visibility into dispute activity and its financial impact**. | H |
| **US-6.9** | As a **Corporate Administrator**, I want to filter and search the dispute log by employee, date, amount, reason, and status so that **I can analyze dispute patterns and identify potential issues**. | M |
| **US-6.10** | As a **Corporate Administrator**, I want to export the dispute log so that **I can analyze dispute data or integrate with internal systems**. | L |
| **US-6.11** | As a **Corporate Administrator**, I want to see all dispute-related credits clearly itemized on my consolidated monthly statement so that **our billing is accurate and transparent**. | H |
| **US-6.12** | As a **Corporate Administrator**, I want to view my company's Corporate Trust Score (CTS) and understand how it's calculated so that **I can monitor our account standing and take action if needed**. | L |
| **US-6.13** | As a **Corporate Administrator**, I want to receive alerts when my Corporate Trust Score drops below certain thresholds so that **I can investigate and address potential dispute patterns before it impacts our account**. | L |
| **US-6.14** | As an **MO**, when a dispute is initiated by either an Employee or an Administrator, I must automatically accept and process a credit to the Corporate Master Account immediately so that **the "customer-first" policy is upheld**. | H |
| **US-6.15** | As an **MO Admin**, I want to view all disputes for a specific Corporate mPass (employee name, transaction details, reason, date, auto-credit amount) so that **I can monitor dispute activity and patterns**. | H |
| **US-6.16** | As an **MO Admin**, I want to filter and search disputes across all my Corporate mPass accounts so that **I can identify accounts with high dispute rates or suspicious patterns**. | M |
| **US-6.17** | As an **MO Admin**, I want to view detailed information for a specific dispute (original transaction, employee who disputed, reason, timestamps, automatic credit) so that **I can review the dispute record**. | M |
| **US-6.18** | As an **MO**, I must automatically calculate and update a "Corporate Trust Score" (CTS) based on dispute frequency, patterns, and account behavior to mitigate abuse so that **the network is protected from fraudulent dispute activity**. | L |
| **US-6.19** | As an **MO Admin**, I want to view the Corporate Trust Score for each Corporate mPass with historical trends so that **I can assess dispute risk and account health over time**. | L |
| **US-6.20** | As an **MO Admin**, I want to receive alerts when a Corporate mPass's CTS drops below critical thresholds so that **I can review the account and take protective action**. | L |
| **US-6.21** | As an **MO Admin**, I want to take action on Corporate mPasses with low CTS (suspend account, reduce credit limit, flag for review) so that **I can prevent continued abuse of the automatic dispute compensation system**. | L |
| **US-6.22** | As an **MO Admin**, I want to manually adjust a Corporate Trust Score when justified (e.g., systemic Publisher issue causing legitimate mass disputes) so that **good-faith corporate clients aren't unfairly penalized by automatic CTS calculations**. | L |

## 3. Non-functional Requirements

### 3.1 Performance

- Admin Portal pages must load in under 3 seconds.
- The "Consumption Authorization Request" check (including policy and financial lookups) must complete in under 500ms.

### 3.2 Security & Compliance

- All data, especially PII and corporate financial data, must be encrypted in transit and at rest.
- The platform must comply with GDPR, CCPA, and other relevant data privacy regulations.
- The Corporate Administrator Portal must support Two-Factor Authentication (2FA).

### 3.3 Scalability

- The platform must support onboarding thousands of corporations, each with tens of thousands of employee mPass users.
- The authorization system must handle millions of concurrent requests.

### 3.4 Accessibility

- The Corporate Administrator Portal and employee-facing pages must be compliant with WCAG 2.1 AA standards.

### 3.5 Browser/Device Support

- The Corporate Administrator Portal must be fully supported on the latest versions of Chrome, Firefox, Safari, and Edge.
- The platform must be responsive for use on both desktop and tablet devices.

## 3. Non-functional Requirements

### 3.1 Performance

- Admin Portal pages must load in under 3 seconds under normal load conditions.
- The "Consumption Authorization Request" check (including policy and hierarchical financial lookups) must complete in under 500ms.
- Transaction log queries must return results within 2 seconds for up to 100,000 transactions.
- Bulk user invitation processing must handle at least 1,000 users within 5 minutes.
- Dispute submission and automatic compensation must complete within 2 seconds.
- Monthly statement generation must complete within 10 minutes for corporations with up to 10,000 employees.
- Real-time balance updates must be reflected within 1 second of transaction completion.

### 3.2 Security & Compliance

- All data, especially PII and corporate financial data, must be encrypted in transit (TLS 1.3+) and at rest (AES-256).
- The platform must comply with GDPR, CCPA, and other relevant data privacy regulations.
- All sensitive actions (user provisioning, policy changes, disputes, payments) must be logged with audit trails including timestamp, user ID, and action details.
- User sessions must timeout after 30 minutes of inactivity in the Admin Portal.
- API endpoints must implement rate limiting to prevent abuse (100 requests per minute per user).
- Payment processing must comply with PCI-DSS standards.
- Personal data must be anonymized or deleted upon account closure per data retention policies.

### 3.3 Scalability

- The platform must support onboarding thousands of corporations, each with up to 1,000 employee mPass users.
- The authorization system must handle thousands of concurrent authorization requests with 99.9% success rate.
- The system must support at least 1,000 concurrent user sessions across all Corporate Admin Portals.
- Transaction processing must support a minimum throughput of 1,000 transactions per second.
- Bulk operations must support uploading files with up to 1,000 records.
- The database architecture must support horizontal scaling to accommodate growth.

### 3.4 Reliability & Availability

- The platform must maintain 99.9% uptime (maximum 43 minutes downtime per month).
- All critical services (authorization, transaction processing, dispute handling) must have redundancy and failover mechanisms.
- Automated backups must occur daily with a Recovery Point Objective (RPO) of 24 hours.
- The system must have a Recovery Time Objective (RTO) of 4 hours for critical services.
- Transaction data must be eventually consistent across all systems within 5 seconds.

### 3.5 Data Integrity & Audit

- All financial transactions must be immutable once recorded.
- The system must maintain complete audit logs for all user actions, policy changes, and financial operations for at least 7 years.
- Audit logs must be tamper-proof and include user ID, timestamp, action type, before/after states, and IP address.
- Corporate Trust Score (CTS) calculations must be auditable with full history and calculation methodology visible to MO Admins.

### 3.6 Integration Requirements

- The platform must integrate with MO Core Systems via secure APIs for identity verification, billing, and payment processing.
- API integrations must support both synchronous (REST) and asynchronous (event-driven) communication patterns.
- Failed integration calls must be retried with exponential backoff up to 3 attempts.
- Integration failures must trigger alerts to MO Admins and Corporate Admins where appropriate.

### 3.7 Notification & Alerting

- Email notifications must be delivered within 5 minutes of the triggering event.
- The system must support configurable notification preferences for Corporate Admins.
- Critical alerts (credit limit exceeded, CTS drops, payment overdue) must be delivered via multiple channels (email, in-app).
- Notification delivery failures must be logged and retried.

### 3.8 Accessibility

- The Corporate Administrator Portal and employee-facing pages must be compliant with WCAG 2.1 AA standards.
- All interactive elements must be keyboard accessible.
- Color contrast ratios must meet WCAG AA requirements (4.5:1 for normal text).
- Forms must have clear labels and error messages for screen readers.

### 3.9 Browser/Device Support

- The Corporate Administrator Portal must be fully supported on the latest versions of Chrome, Firefox, Safari, and Edge.
- The platform must also support the previous major version of each browser (N-1 support).
- The platform must be responsive for use on both desktop (minimum 1280x720) and tablet devices (minimum 768px width).
- Mobile phone support for the Admin Portal is not required in MVP but should be considered in future phases.

### 3.10 Usability

- Corporate Administrators with basic technical proficiency should be able to complete core tasks (invite users, set policies, view reports) without training.
- The Admin Portal should provide inline help text and tooltips for complex features.
- Error messages must be clear, actionable, and user-friendly (avoiding technical jargon).
- Critical actions (suspend account, delete user group) must require confirmation prompts.

## 4. Technical Considerations

### 4.1 System Dependencies

- **Lago+ Engine:** The core billing and metering engine will need significant enhancements to support corporate accounts.
- **MO Core Systems:** Integration is required with MO systems for corporate identity verification, billing, and payment processing.
- **MO Portal:** The Membership Portal will need significant enhancements to support corporate accounts, budget, and policy checks.

### 4.2 Architecture Overview

The solution will extend the existing Moneta microservices architecture. New services will be created for:

- **Corporate mPass Management:** To handle the lifecycle of Corporate mPasses, Admins, User Groups, and Policies.
- **Admin Portal Backend:** A dedicated API to serve the new Corporate Administrator Portal.

The existing authorization and billing services will be modified to query the new Corporate mPass service during their respective workflows.

### 4.3 Data Requirements

- New database schemas are required to represent the hierarchical relationship between a Corporate mPass, User Groups, and individual Employee mPasses.
- A new data model is needed for storing and applying Access Policies.

## 5. Assumptions and Constraints

### 5.1 Assumptions

- MOs have existing relationships with enterprise clients that they can leverage for adoption.
- Corporate Administrators are technically proficient enough to use a self-service web portal.
- Publishers in the Moneta Network will see value in accessing the enterprise market, even with the shared-risk model.

### 5.2 Constraints

- The solution must integrate with the existing Moneta Network infrastructure and cannot be a standalone product.
- All transactions must adhere to the core Moneta principle of the MO being the direct biller.
- A Corporate mPass is a distinct entity and cannot be merged with a personal B2C mPass.

## 6. Success Metrics

| Event | Description | Purpose |
|-------|-------------|---------|
| **Corporate mPass Application Submitted** | A new corporation completes the initial application form. | Measures top-of-funnel interest. |
| **Corporate mPass Approved** | An MO Admin approves an application, making the account active. | Measures successful onboarding and conversion rate. |
| **Employee mPass Activated** | An employee accepts their invitation and creates their Corporate mPass. | Measures user adoption within an enterprise. |
| **Transaction Authorized** | A successful consumption of a digital service by an employee. | Measures core product usage and GMV. |
| **Dispute Submitted** | A Corporate Administrator formally submits an employee-flagged dispute. | Measures customer satisfaction and potential service issues. |

## 7. Appendix

### 7.1 Glossary

| Term | Definition |
|------|------------|
| **Corporate mPass** | The parent entity for an enterprise client, managed by the Admin and billed by the MO. |
| **Corporate Administrator** | The user responsible for managing the Corporate mPass, users, policies, and finances. |
| **User Group** | A collection of employee mPass users within a corporation, used for applying default policies. |
| **Policy** | A set of rules that defines both service access (whitelist/blacklist) and spending limits for a user, group, or company. |
| **MO** | Membership Organization (e.g., Telco, Bank). The direct biller and risk manager. |
| **CTS** | Corporate Trust Score. An internal metric to mitigate abuse of the dispute system. |

### 7.2 References

- [Moneta Payment and Subscription Primer (Parts I-V)]