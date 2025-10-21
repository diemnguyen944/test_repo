# Moneta for Enterprise (Corporate mPass) UI/UX Specification

## Introduction

This document defines the user experience goals, information architecture, user flows, and visual design specifications for the Moneta for Enterprise (Corporate mPass)'s user interface. It serves as the foundation for visual design and frontend development, ensuring a cohesive and user-centered experience.

### Overall UX Goals & Principles
#### Target User Personas
*   **Corporate Administrator (Admin):** An IT, Finance, or Operations Manager who needs to control costs, manage access, and simplify billing for all digital services their employees use.
*   **Corporate Employee (mPass User):** Any employee who needs seamless, on-demand access to premium digital tools for their job without using personal payment methods or filing expense reports.
*   **MO Admin:** An enterprise account manager at an MO who needs a system to onboard, manage risk for, and support their corporate clients.

#### Usability Goals
*   **Ease of Learning:** A new administrator should be able to successfully onboard their first employee and set a company-wide policy within 10 minutes of their first login, without needing a tutorial.
*   **Efficiency of Use:** An experienced admin should be able to perform common, frequent tasks (e.g., invite a user, suspend a user, find a transaction) in three clicks or less from the main dashboard.
*   **Error Prevention:** The interface must prevent users from making critical financial or security errors. All destructive actions (deleting a group, removing a user) must have a clear confirmation step. Policy controls must provide clear feedback about their impact.
*   **Clarity & Confidence:** The admin should always feel confident about the state of the system, particularly regarding spending, credit limits, and who has access to what. The UI must present this information clearly and unambiguously.

#### Design Principles
1.  **Effortless Control:** The UI should empower admins with powerful controls that feel simple and intuitive. Complexity should be hidden until needed (Progressive Disclosure).
2.  **Clarity Above All:** Financial and access-control data must be presented with absolute clarity. Avoid ambiguity in labels, data visualizations, and status indicators.
3.  **Trustworthy & Professional:** The visual design must be clean, professional, and secure. As a platform managing company finances, it must inspire confidence at every step.
4.  **Provide Immediate Feedback:** Every user action must result in a clear, immediate, and visible system response (e.g., a success toast, a status update in a table).

### Change Log

| Date         | Version | Description                           | Author     |
| :----------- | :------ | :------------------------------------ | :--------- |
| Oct 20, 2025 | 1.0     | Initial draft based on the PRD v1.3.0 | Sally (UX) |

## 2. Information Architecture (IA)

### Site Map / Screen Inventory

This diagram provides a comprehensive, hierarchical view of the entire Corporate mPass Platform, breaking down the distinct portals for Corporate Administrators, MO Administrators, and Corporate Employees.

```mermaid
graph TD
    Root[Corporate mPass Platform]
    
    Root --> CorpAdmin[Corporate Administrator Portal]
    Root --> mPassApp[mPass App - Corporate Employee]
    Root --> MOAdmin[MO Admin Portal]
    
    %% Corporate Administrator Portal
    CorpAdmin --> AdminDash[Dashboard]
    CorpAdmin --> UserMgmt[User Management]
    CorpAdmin --> PolicyMgmt[Policy Management]
    CorpAdmin --> Billing[Billing & Reporting]
    CorpAdmin --> Disputes[Dispute Management]
    CorpAdmin --> AdminSettings[Account Settings]
    
    %% User Management Section
    UserMgmt --> EmpList[Employee List]
    UserMgmt --> InviteUser[Invite Users]
    UserMgmt --> UserGroups[User Groups]
    
    EmpList --> EmpDetails[Employee Details]
    EmpDetails --> SuspendEmp[Suspend/De-provision]
    
    InviteUser --> SingleInvite[Single Email Invite]
    InviteUser --> BulkInvite[Bulk Upload]
    
    UserGroups --> CreateGroup[Create Group]
    UserGroups --> GroupList[View Groups]
    GroupList --> GroupDetails[Group Details]
    GroupDetails --> AssignUsers[Assign Users]
    GroupDetails --> RemoveUsers[Remove Users]
    GroupDetails --> DeleteGroup[Delete Group]
    
    %% Policy Management Section
    PolicyMgmt --> CompanyPolicy[Company-Wide Policies]
    PolicyMgmt --> GroupPolicy[Group Policies]
    PolicyMgmt --> IndividualPolicy[Individual Policies]
    
    CompanyPolicy --> CompanySpending[Spending Limits]
    CompanyPolicy --> CompanyAccess[Service Access Control]
    
    GroupPolicy --> GroupSpending[Group Spending Limits]
    GroupPolicy --> GroupAccess[Group Service Access]
    
    IndividualPolicy --> IndSpending[Individual Spending Limits]
    IndividualPolicy --> IndAccess[Individual Service Access]
    
    CompanyAccess --> Whitelist[Whitelist Publishers/Categories]
    CompanyAccess --> Blacklist[Blacklist Publishers/Categories]
    
    %% Billing & Reporting Section
    Billing --> TransLog[Transaction Log]
    Billing --> Statements[Monthly Statements]
    Billing --> Reports[Reports & Analytics]
    Billing --> Payment[Make Payment]
    
    TransLog --> FilterTrans[Filter & Sort Transactions]
    TransLog --> DisputeTrans[Dispute Transaction]
    
    Reports --> GroupReport[By User Group]
    Reports --> EmployeeReport[By Employee]
    Reports --> ExportReport[Export Data]
    
    %% Dispute Management Section
    Disputes --> DisputeLog[Dispute Log]
    Disputes --> ViewCredits[View Compensations]
    
    %% mPass App - Corporate Employee Experience
    mPassApp --> Guide[mPass Guide - Filtered]
    mPassApp --> History[Transaction History]
    mPassApp --> Profile[Profile]
    
    Guide --> BrowseServices[Browse Services - Policy-Based]
    BrowseServices --> SelectService[Select Service]
    SelectService --> Authorize[Authorization Request]
    Authorize --> PolicyCheck[Policy & Budget Check]
    
    History --> ViewTrans[View Transactions]
    ViewTrans --> DisputeAction[Dispute Transaction]
    
    Profile --> EmpSettings[Settings]
    Profile --> Notifications[Notifications]
    Notifications --> PolicyDenial[Policy Denial Alerts]
    
    %% MO Admin Portal
    MOAdmin --> MODash[Dashboard]
    MOAdmin --> AppQueue[Application Queue]
    MOAdmin --> CorpAccounts[Corporate Accounts]
    MOAdmin --> EnterpriseBilling[Enterprise Billing & Transactions]
    MOAdmin --> MOReports[Reports & Analytics]
    MOAdmin --> RiskMgmt[Risk Management]
    
    %% Application Queue
    AppQueue --> PendingApps[Pending Applications]
    AppQueue --> ReviewedApps[Reviewed Applications]
    
    PendingApps --> ReviewApp[Review Application]
    ReviewApp --> ApproveApp[Approve]
    ReviewApp --> DenyApp[Deny]
    ApproveApp --> SetLimit[Set Credit Limit]
    
    %% Corporate Accounts Management
    CorpAccounts --> ActiveAccounts[Active Accounts]
    CorpAccounts --> SuspendedAccounts[Suspended Accounts]
    
    ActiveAccounts --> CorpDetails[Account Details]
    CorpDetails --> SuspendCorp[Suspend Account]
    CorpDetails --> ResumeCorp[Resume Account]
    CorpDetails --> ViewActivity[View Activity]
    CorpDetails --> AdjustLimit[Adjust Credit Limit]
    
    %% Enterprise Billing & Transactions
    EnterpriseBilling --> AllCorpTransactions[All Corporate Transactions]
    EnterpriseBilling --> CorpStatements[Corporate Statements]
    EnterpriseBilling --> PaymentTracking[Payment Tracking]
    EnterpriseBilling --> DisputeMonitoring[Dispute Monitoring]
    
    AllCorpTransactions --> FilterByCompany[Filter by Company]
    AllCorpTransactions --> FilterByDate[Filter by Date]
    AllCorpTransactions --> TransactionDetails[Transaction Details]
    
    CorpStatements --> PendingStatements[Pending Statements]
    CorpStatements --> PaidStatements[Paid Statements]
    CorpStatements --> OverdueStatements[Overdue Statements]
    
    PendingStatements --> StatementDetails[Statement Details]
    StatementDetails --> ViewLineItems[View Line Items]
    StatementDetails --> ViewDisputes[View Statement Disputes]
    
    PaymentTracking --> ReceivedPayments[Received Payments]
    PaymentTracking --> PendingPayments[Pending Payments]
    PaymentTracking --> FailedPayments[Failed Payments]
    
    DisputeMonitoring --> AllDisputes[All Corporate Disputes]
    DisputeMonitoring --> DisputeTrends[Dispute Trends]
    AllDisputes --> DisputeByCompany[By Company]
    AllDisputes --> DisputeByStatus[By Status]
    
    %% Risk Management
    RiskMgmt --> CTSScores[Corporate Trust Scores]
    RiskMgmt --> RiskAlerts[Risk Alerts]
    RiskMgmt --> CreditUtilization[Credit Utilization]
    
    CTSScores --> LowScoreAccounts[Low Score Accounts]
    CTSScores --> ScoreHistory[Score History]
    
    RiskAlerts --> HighDisputeRate[High Dispute Rate]
    RiskAlerts --> CreditLimitAlerts[Credit Limit Alerts]
    RiskAlerts --> SuspiciousActivity[Suspicious Activity]
    
    %% Styling
    classDef adminClass fill:#e1f5ff,stroke:#0288d1,stroke-width:2px
    classDef mpassClass fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef moClass fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    classDef rootClass fill:#e8f5e9,stroke:#388e3c,stroke-width:3px
    
    class CorpAdmin,AdminDash,UserMgmt,PolicyMgmt,Billing,Disputes,AdminSettings,EmpList,InviteUser,UserGroups,EmpDetails,SuspendEmp,SingleInvite,BulkInvite,CreateGroup,GroupList,GroupDetails,AssignUsers,RemoveUsers,DeleteGroup,CompanyPolicy,GroupPolicy,IndividualPolicy,CompanySpending,CompanyAccess,GroupSpending,GroupAccess,IndSpending,IndAccess,Whitelist,Blacklist,TransLog,Statements,Reports,Payment,FilterTrans,DisputeTrans,GroupReport,EmployeeReport,ExportReport,DisputeLog,ViewCredits adminClass
    
    class mPassApp,Guide,History,Profile,BrowseServices,SelectService,Authorize,PolicyCheck,ViewTrans,DisputeAction,EmpSettings,Notifications,PolicyDenial mpassClass
    
    class MOAdmin,MODash,AppQueue,CorpAccounts,EnterpriseBilling,MOReports,RiskMgmt,PendingApps,ReviewedApps,ReviewApp,ApproveApp,DenyApp,SetLimit,ActiveAccounts,SuspendedAccounts,CorpDetails,SuspendCorp,ResumeCorp,ViewActivity,AdjustLimit,AllCorpTransactions,CorpStatements,PaymentTracking,DisputeMonitoring,FilterByCompany,FilterByDate,TransactionDetails,PendingStatements,PaidStatements,OverdueStatements,StatementDetails,ViewLineItems,ViewDisputes,ReceivedPayments,PendingPayments,FailedPayments,AllDisputes,DisputeTrends,DisputeByCompany,DisputeByStatus,CTSScores,RiskAlerts,CreditUtilization,LowScoreAccounts,ScoreHistory,HighDisputeRate,CreditLimitAlerts,SuspiciousActivity moClass
    
    class Root rootClass
```

### Navigation Structure

*   **Primary Navigation (Admin Portals):** After login, a persistent vertical sidebar will provide access to the main sections of either the MO or Enterprise Admin portal. This ensures that core features are always just one click away.
*   **Secondary Navigation:** Not required for the MVP, as the application structure is relatively flat within each primary section.
*   **Breadcrumb Strategy:** Breadcrumbs will be used to show the user's current location when they navigate into nested views. For example: `User Management > User Groups > Marketing Team`.

## 3. User Flows

This section provides detailed, step-by-step diagrams for key user workflows within the platform.

### 4.1. Flow 1: New Enterprise Onboarding

This flow describes how a new enterprise registers for the Corporate mPass service and gets approved by the Membership Organization (MO).

```mermaid
graph TD
    subgraph "Phase 1: Web - Enterprise Admin"
        A[Admin visits Corporate mPass registration page] --> B[Fills out company details & admin info]
        B --> C[Submits Application]
        C --> D((System: Application Submitted))
        D --> E[Admin sees 'Application Pending Review' screen]
    end

    subgraph "Phase 2: MO Admin Portal - MO Admin"
        F((System: Notifies MO of new application)) --> G[MO Admin logs in and reviews application in queue]
        G --> H{Approve or Deny?}
        H -- Deny --> I[MO Admin provides reason for denial]
        I --> J((System: Notifies Admin of Denial))
        J --> EndDeny((Flow Ends))
        H -- Approve --> K[MO Admin sets initial credit limit for the enterprise]
        K --> L((System: Approves Account))
    end

    subgraph "Phase 3: Email & Web - Enterprise Admin"
        L --> M[Admin receives 'Application Approved' email]
        M --> N[Email link directs to password creation page]
        N --> O[Admin sets a secure password]
        O --> P((System: Activates Admin Account))
        P --> Q[Admin is redirected to the Login page]
        Q --> Success((Flow Complete: Admin can now log in))
    end
```

### 4.2. Flow 2: Inviting a New Employee (Single)

This flow covers the process for an admin inviting a single employee to the corporate mPass program.

```mermaid
graph TD
    A[Admin navigates to 'User Management'] --> B[Clicks 'Invite Users' button]
    B --> C[Invite Employee modal appears]
    C --> D[Admin enters employee's email address]
    D --> E[Admin optionally assigns the employee to one or more groups]
    E --> F[Clicks 'Send Invite']
    F --> G((System Processing))
    G --> H{Is email valid and not already in use?}
    H -- No --> I[Show inline error in modal: 'This email is already registered.']
    I --> D
    H -- Yes --> J((System: Sends Invitation Email))
    J --> K[Close modal]
    K --> L[Show success toast: 'Invitation has been sent to john.smith@company.com.']
    L --> M[The invited user appears in the employee list with 'Pending' status]
    M --> Success((Flow Complete))
```

### 4.3. Flow 3: Bulk Inviting New Employees

This flow allows admins to invite multiple employees at once by uploading a CSV file.

```mermaid
graph TD
    A[Admin navigates to 'User Management'] --> B[Clicks 'Invite Users' button]
    B --> C[Invite modal appears, admin selects 'Bulk Invite' tab]

    subgraph "Step 1: Download & Prepare"
        C --> D[Admin clicks 'Download CSV Template']
        D --> E[Admin opens the template and adds employee emails and optional group assignments]
    end

    subgraph "Step 2: Upload & Preview"
        E --> F[Admin drags & drops or browses for the completed CSV file]
        F --> G((System: Parses and validates the CSV))
        G --> H{File valid?}
        H -- No --> I[Show validation errors in modal, e.g., 'Row 5: Invalid email address.']
        I --> F
        H -- Yes --> J[Display a preview of users to be invited]
    end

    subgraph "Step 3: Confirmation"
        J --> K[Admin reviews the list and clicks 'Send Invites']
        K --> L((System: Queues and sends invitation emails))
        L --> M[Close modal]
        M --> N[Show success toast: 'Invitations are being sent to 50 users.']
        N --> O[Invited users appear in the list with 'Pending' status]
        O --> Success((Flow Complete))
    end
```

### 4.4. Flow 4: Employee Invitation Acceptance & Activation (App-Based)

This flow details how an invited employee activates their corporate mPass using the mobile app.

```mermaid
graph TD
    A[Employee receives invitation email on their desktop] --> B{Has mPass app installed?};
    B -- No --> C[Email prompts user to download mPass app from App Store / Google Play];
    C --> D[User installs and opens mPass app];
    B -- Yes --> D;

    D --> E[In mPass app, user selects 'Add Corporate mPass'];
    E --> F[App opens camera to scan QR code];
    
    subgraph "Scanning the QR Code"
      G[User points phone camera at QR code in the email on their desktop screen];
    end

    F --> G;
    G --> H((System: Validating QR Code...));
    H --> I{QR Code Valid?};
    I -- "No (e.g., expired, already used)" --> J[App shows error: 'Invalid invitation. Please contact your administrator.'];
    J --> End((Flow Ends));
    I -- Yes --> K[App prompts for biometric confirmation using Face ID or Fingerprint];
    K --> L[App communicates with server to provision the new corporate mPass];
    L --> M[A new corporate-branded mPass appears in the user's app];
    M --> N[User sees a 'Welcome' screen with a success message];
    N --> O((System: Update user status to 'Active' in Admin Portal));
    O --> Success((Flow Complete));
```

### 4.5. Flow 5: Employee Lifecycle Management

This flow shows how an admin can suspend, reactivate, or permanently remove an employee account.

```mermaid
graph TD
    A[Admin navigates to 'User Management' page] --> B[Finds a specific employee in the list]
    B --> C[Clicks the action menu for that employee]
    C --> D{Selects Action}
    D -- Suspend --> E1[Confirmation Modal: 'Are you sure you want to suspend John Smith? They will lose all access immediately.']
    D -- Reactivate --> E2[Confirmation Modal: 'Are you sure you want to reactivate Jane Doe? Their previous permissions will be restored.']
    D -- Remove --> E3[Confirmation Modal: 'PERMANENTLY remove Pat Jones? This cannot be undone.']

    E1 -- Confirms --> F((System Processing))
    E2 -- Confirms --> F
    E3 -- Confirms --> F

    F --> G{Action Successful?}
    G -- No --> H[Show error toast, e.g., 'Failed to update user.']
    G -- Yes --> I[Show success toast, e.g., 'John Smith has been suspended.']
    I --> J[Employee's status is updated in the list]
    J --> Success((Flow Complete))
```

### 4.6. Flow 6: User Group Creation

This flow outlines the simple process of creating a new user group.

```mermaid
graph TD
    A[Admin navigates to 'User Groups' page] --> B[Clicks 'Create New Group' button]
    B --> C[Create Group modal appears with a single 'Group Name' field]
    C --> D[Admin enters a name for the group, e.g., 'Engineering']
    D --> E[Admin clicks 'Create']
    E --> F((System Processing))
    F --> G{Creation Successful?}
    G -- "No, name already exists" --> H[Show inline error in modal]
    H --> D
    G -- "Yes" --> I[Close modal]
    I --> J[Show success toast: Group Engineering has been created.]
    J --> K[The new group appears in the list with 0 members]
    K --> Success((Flow Complete))
```

### 4.7. Flow 7: Managing Group Membership

This flow details how an admin assigns and removes employees from a specific group.

```mermaid
graph TD
    A[Admin navigates to 'User Groups' page] --> B[Clicks 'Manage Members' on a specific group]
    B --> C[Manage Members page/modal appears]

    subgraph "Dual-List Interface"
        C --> D[Left List: 'Available Employees' (shows all users not in the group)]
        C --> E[Right List: 'Members of [Group Name]' (shows current members)]
    end
    
    D --> F{Admin selects employees to add}
    F --> G[Clicks '>' button to move them to the 'Members' list]

    E --> H{Admin selects members to remove}
    H --> I[Clicks '<' button to move them to the 'Available' list]

    G --> J[Admin clicks 'Save Changes']
    I --> J
    
    J --> K((System Processing))
    K --> L{Save Successful?}
    L -- No --> M[Show error toast]
    L -- Yes --> N[Show success toast: '[Group Name] updated with 15 members.']
    N --> O[Admin is returned to the main 'User Groups' page]
    O --> P[Member count for the group is updated]
    P --> Success((Flow Complete))
```

### 4.8. Flow 8: Centralized Policy Management

This flow describes the high-level process of an admin managing policies from the central Policy Management page.

```mermaid
graph TD
    A[Admin navigates to 'Policy Management'] --> B[Sees three tabs: Company-Wide, Groups, Individuals]
    
    subgraph "Company-Wide Policy"
        B -- Selects 'Company-Wide' tab --> C[Views global spending limits and service access rules]
        C --> D[Clicks 'Edit']
        D --> E[Makes changes in a dedicated form/modal]
        E --> F[Saves changes, which apply to ALL users]
    end
    
    subgraph "Group Policies"
        B -- Selects 'Groups' tab --> G[Views a list of all groups and their policy status]
        G --> H[Clicks 'Manage Policy' for a specific group]
        H --> I[Sets spending limits and service access for that group]
        I --> J[Saves changes, which apply to all members of that group]
    end
    
    subgraph "Individual Policies"
        B -- Selects 'Individuals' tab --> K[Views a list of all users with individual policy overrides]
        K --> L[Admin can search for a user]
        L --> M[Clicks 'Manage Policy' for a specific user]
        M --> N[Sets more restrictive limits for that individual]
        N --> O[Saves changes, creating an individual override]
    end

    F --> Success((Flow Complete))
    J --> Success
    O --> Success
```

### 4.9. Flow 9: Transaction Monitoring & Review

This flow shows how an admin monitors company transactions.

```mermaid
graph TD
    A[Admin navigates to 'Billing & Reporting'] --> B[Views the 'Transaction Log' tab by default]
    B --> C[Sees a real-time, paginated list of all employee transactions]
    C --> D{Needs to find a specific transaction?}
    D -- Yes --> E[Uses search bar to find by employee or service]
    D -- No --> F[Browses the list]

    E --> G[Uses filters to narrow by date range, amount, or group]
    G --> F
    
    F --> H[Clicks on a transaction row to view details]
    H --> I[Transaction Details modal appears with full information]
    I --> J[Admin reviews the details]
    J --> K{Is there an issue?}
    K -- Yes --> L[Clicks 'Initiate Dispute']
    L --> M((Redirect to Dispute Flow))
    K -- No --> N[Closes modal]
    N --> Success((Flow Complete))
```

### 4.10. Flow 10: Dispute Initiation and Tracking (with Automatic Compensation)

This flow details how a dispute is initiated and automatically handled.

```mermaid
graph TD
    A[Admin is viewing a transaction detail] --> B[Clicks 'Initiate Dispute' button]
    B --> C[Dispute Modal appears]
    C --> D[Admin selects a reason for the dispute (e.g., 'Duplicate Charge')]
    D --> E[Admin adds optional notes]
    E --> F[Clicks 'Submit Dispute']
    
    F --> G((System Processing))
    G --> H[System automatically marks transaction as 'Disputed']
    H --> I[System immediately applies a credit for the disputed amount to the corporate account]
    
    subgraph "Admin Confirmation"
        I --> J[Modal closes]
        J --> K[Success toast: 'Dispute submitted. A credit of $45.00 has been applied.']
        K --> L[Transaction in the log now shows a 'Disputed/Compensated' status]
        L --> M[The dispute is logged in the 'Dispute Management' section]
    end

    M --> Success((Flow Complete))
```

### 4.11. Flow 11: Viewing & Downloading Statements

This flow shows how an admin can view and download monthly billing statements.

```mermaid
graph TD
    A[Admin navigates to 'Statements' page] --> B[Views a list of all past monthly statements, sorted by date]
    B --> C[Each statement shows billing period, total amount, and status]
    C --> D{Admin selects an action for a specific statement}
    
    subgraph Actions
        D -- Clicks 'View Details' --> E[Displays detailed, read-only, paginated view of all transactions]
        D -- Clicks 'Download' --> F[Presents options: 'Download as PDF' or 'Download as CSV']
    end

    E --> H[Admin can return to statements list]
    F -- Selects Format --> G((System generates and initiates file download))
    G --> Success((Flow Complete))
```

### 4.12. MO Admin Flows

#### MO Flow 1: New Enterprise Application Review

```mermaid
graph TD
    A[MO Admin logs in to the MO Portal] --> B[Navigates to the 'Application Queue']
    B --> C[Views a list of pending corporate applications]
    C --> D[Selects an application to review]
    D --> E[Views all submitted company and admin details]
    E --> F{Decision Time}
    F -- Deny --> G[Clicks 'Deny']
    G --> H[Enters reason for denial in a modal]
    H --> I((System: Notifies enterprise admin of denial))
    I --> J[Application moves to 'Reviewed' queue with 'Denied' status]
    J --> End((Flow Complete))

    F -- Approve --> K[Clicks 'Approve']
    K --> L[Approval modal appears]
    L --> M[MO Admin sets the initial monthly credit limit for the enterprise]
    M --> N[Clicks 'Confirm Approval']
    N --> O((System: Creates corporate account, sends approval email))
    O --> P[Application moves to 'Reviewed' queue with 'Approved' status]
    P --> End
```

#### MO Flow 2: Corporate Account Lifecycle Management

```mermaid
graph TD
    A[MO Admin navigates to 'Corporate Accounts'] --> B[Searches for a specific company]
    B --> C[Finds the company and views its details page]
    C --> D{Selects an Action}
    
    D -- Suspend Account --> E1[Clicks 'Suspend']
    E1 --> F1[Confirmation modal appears with warning]
    F1 --> G1[Confirms suspension]
    G1 --> H((System: Temporarily deactivates account and notifies admin))
    H --> I[Account status changes to 'Suspended']
    I --> Success((Flow Complete))
    
    D -- Reactivate Account --> E2[Clicks 'Reactivate']
    E2 --> F2[Confirmation modal appears]
    F2 --> G2[Confirms reactivation]
    G2 --> H
    
    D -- Adjust Credit Limit --> E3[Clicks 'Adjust Credit Limit']
    E3 --> F3[Modal appears to enter new limit]
    F3 --> G3[Enters new limit and saves]
    G3 --> H
```

#### MO Flow 3: Monthly Statement Generation

```mermaid
graph TD
    A[End of the billing cycle occurs] --> B((System: Automatically generates draft statements for all corporate accounts))
    B --> C[MO Admin navigates to 'Enterprise Billing' -> 'Statements']
    C --> D[Admin filters for 'Draft' statements for the previous month]
    D --> E[Admin can spot-check a few statements for accuracy]
    E --> F{Ready to finalize?}
    F -- No --> G[Admin makes manual adjustments if needed (rare)]
    F -- Yes --> H[Admin selects all draft statements]
    H --> I[Clicks 'Finalize & Send Statements']
    I --> J((System: Processes the queue))
    J --> K[Statements are finalized and status changed to 'Unpaid']
    K --> L[System sends email notifications to all enterprise admins with a link to view and pay their statement]
    L --> Success((Flow Complete))
```

## 5. Wireframes

This section provides low-fidelity wireframes for the key screens and interactive components of the Corporate Admin Portal.

### 5.1. Onboarding & Authentication

#### Wireframe: Corporate mPass Registration Page

-   **Purpose**: To allow a new enterprise to apply for the Corporate mPass service.
-   **Layout**: A clean, single-column form focused on capturing essential information without overwhelming the user.

```
+-------------------------------------------------------------+
| [MO Logo]                                                   |
|                                                             |
|                  Corporate mPass Registration               |
|                                                             |
| --- Company Information ---                                 |
| [ Company Name*         ]                                   |
| [ Business Registration # ]                                 |
| [ Company Address*        ]                                   |
|                                                             |
| --- Administrator Details ---                               |
| [ Full Name*            ]                                   |
| [ Job Title*            ]                                   |
| [ Work Email*           ]                                   |
| [ Phone Number*         ]                                   |
|                                                             |
| [x] I agree to the [Terms of Service] and [Privacy Policy]  |
|                                                             |
|                  [ Submit Application ]                     |
|                                                             |
|         Already have an account? [Log In]                   |
+-------------------------------------------------------------+
```

#### Wireframe: Login Screen

-   **Purpose**: To provide secure access for registered enterprise administrators.
-   **Layout**: A simple, centered modal-style card to focus the user on the task of logging in.

```
+-------------------------------------------------------------+
|                                                             |
|                        [MO Logo]                            |
|                                                             |
|                 Welcome Back, Admin                         |
|                                                             |
|   [ Email Address*        ]                                 |
|                                                             |
|   [ Password*             ]                                 |
|                                                             |
|   [ Remember Me ]         [ Forgot Password? ]              |
|                                                             |
|                     [ Log In ]                              |
|                                                             |
+-------------------------------------------------------------+
```

### 5.2. Main Portal Screens

#### Wireframe: Enterprise Admin Portal - Main Dashboard

-   **Purpose**: To provide a high-level overview of account activity and quick access to common tasks upon login.
-   **Layout**: A card-based design that surfaces key metrics and recent activity.

```
+--------------------------------------------------------------------------------------+
| [Logo]            | [Header: Dashboard]                                                |
|-------------------|--------------------------------------------------------------------|
| NAVIGATION        |                                                                    |
| -> Dashboard      |  [Card: Total Spend (Month)]  [Card: Active Users]  [Card: Pending] |
| -> User Mgmt      |   - $12,450.78 / $50,000      - 75 / 80             - 2 Invites     |
| -> Policy Mgmt    |                                                                    |
| -> Billing        |  [Section: Quick Actions]                                          |
| -> Disputes       |   [Invite User] [Create Group] [View Statement] [Make Payment]     |
| -> Settings       |                                                                    |
|                   |  [Section: Recent Activity]                                        |
| [User Profile]    |   - Jane Doe was added to the 'Sales' group. (1h ago)              |
| [Logout]          |   - A dispute for $45.00 was initiated. (3h ago)                   |
|                   |   - A new policy was set for the 'Engineering' group. (Yesterday)    |
|                   |                                                                    |
+--------------------------------------------------------------------------------------+
```

#### Wireframe: Enterprise Admin Portal - User Management Page

-   **Purpose**: To provide a central place for admins to view, search, and manage all employees (both active and pending).
-   **Layout**: A robust data table that allows for efficient scanning and action-taking.

```
+--------------------------------------------------------------------------------------+
| [Logo]            | [Header: User Management]                                          |
|-------------------|--------------------------------------------------------------------|
| NAVIGATION        |                                                                    |
| -> Dashboard      |  [Search by name/email...] [Filter by Status] [Filter by Group]    |
| -> User Mgmt      |                                                     [Invite Users] |
| -> Policy Mgmt    |--------------------------------------------------------------------|
| -> Billing        |                                                                    |
| -> Disputes       |  [User Data Table]                                                 |
| -> Settings       |  +----------+----------------------+----------+----------+--------+ |
|                   |  | Name     | Email                | Status   | Groups   | Action | |
| [User Profile]    |  +----------+----------------------+----------+----------+--------+ |
| [Logout]          |  | John S.  | john.s@...           | [Active] | Sales    | [...]  | |
|                   |  | Jane D.  | jane.d@...           | [Active] | Mrkt, Dev| [...]  | |
|                   |  | Pat J.   | pat.j@...            | [Pending]|          | [...]  | |
|                   |  +----------+----------------------+----------+----------+--------+ |
|                   |                                         [Pagination: 1 2 3 ... 10] |
+--------------------------------------------------------------------------------------+
```

### 5.3. User Management Modals & Pages

#### Wireframe: Invite Employee Modal (Single)

-   **Purpose**: A quick, focused form for inviting one employee at a time.

```
+--------------------------------------------------+
| Invite Employee                              [X] |
|--------------------------------------------------|
|                                                  |
|   [ Email Address*         ]                     |
|                                                  |
|   [ Assign to Group(s) (Optional)   v ]          |
|    - [x] Engineering                             |
|    - [ ] Marketing                               |
|                                                  |
|                         [Cancel] [Send Invite]   |
+--------------------------------------------------+
```

#### Wireframe: Invite Employees Modal (Bulk)

-   **Purpose**: A two-step process for uploading a CSV of multiple employees.

```
+--------------------------------------------------+
| Invite Employees (Bulk)                        [X] |
|--------------------------------------------------|
|  Step 1: Upload File                             |
|   Download our [template.csv] to get started.    |
|                                                  |
|   [ Drag & Drop CSV here or Click to Browse ]    |
|                                                  |
|  Step 2: Preview & Confirm (disabled)            |
|                                                  |
|                         [Cancel] [Next >]        |
+--------------------------------------------------+
```

#### Wireframe: User Groups Main Page

-   **Purpose**: To list all created user groups and provide entry points for managing them.
-   **Layout**: A card-based view that provides key information at a glance.

```
+--------------------------------------------------------------------------------------+
| [Logo]            | [Header: User Groups]                                              |
|-------------------|--------------------------------------------------------------------|
| NAVIGATION        |                                                                    |
| -> Dashboard      |  [Search groups...]                           [Create New Group]   |
| -> User Mgmt      |--------------------------------------------------------------------|
| -> ...            |                                                                    |
|                   |  [Card: Engineering]     [Card: Marketing]     [Card: Sales]       |
|                   |   - 75 Members           - 22 Members          - 35 Members        |
|                   |   - Policy: Custom       - Policy: Default     - Policy: Custom    |
|                   |   - [...]                - [...]               - [...]             |
|                   |                                                                    |
+--------------------------------------------------------------------------------------+
```

#### Wireframe: Manage Group Membership Page/Modal

-   **Purpose**: To allow admins to easily add and remove users from a specific group.
-   **Layout**: A dual-list (or "picklist") pattern, which is the standard and most intuitive UI for this task.

```
+------------------------------------------------------------------+
| Manage Members: Engineering                                    [X] |
|------------------------------------------------------------------|
|                                                                  |
| [Available Employees (25)]      [<]      [Group Members (75)]    |
| [Search...]                     [>]      [Search...]             |
| +-------------------------+              +---------------------+ |
| | [ ] Alex Green          |              | [x] Barry White     | |
| | [ ] Brenda Blue         |              | [x] Chris Black     | |
| | ...                     |              | ...                 | |
| +-------------------------+              +---------------------+ |
|                                                                  |
|                                       [Cancel] [Save Changes]    |
+------------------------------------------------------------------+
```

### 5.4. Policy Management

#### Wireframe: Policy Management Main Page

-   **Purpose**: A unified interface to manage all company-wide, group, and individual policies.
-   **Layout**: A tabbed interface to separate the three levels of the policy hierarchy.

```
+--------------------------------------------------------------------------------------+
| [Logo]            | [Header: Policy Management]                                        |
|-------------------|--------------------------------------------------------------------|
| NAVIGATION        |                                                                    |
| -> Dashboard      |  [  Company-Wide  ]  [   Groups   ]  [  Individuals  ]             |
| -> ...            |--------------------------------------------------------------------|
|                   |                                                                    |
|                   | [Section: Company-Wide Policy]                                     |
|                   |  [Card: Global Spending Limit]             ( Edit )                |
|                   |   - Monthly Limit: $50,000                                         |
|                   |  [Card: Global Service Access]             ( Edit )                |
|                   |   - Allowed: Business Tools | Blocked: Netflix, Spotify            |
|                   |                                                                    |
+--------------------------------------------------------------------------------------+
```

### 5.5. Billing & Reporting

#### Wireframe: Billing & Reporting Page (Statements Tab)

-   **Purpose**: To provide a clear history of all monthly statements and allow for easy viewing and downloading.
-   **Layout**: A clean data table listing all statements chronologically.

```
+--------------------------------------------------------------------------------------+
| [Logo]            | [Header: Billing & Reporting]                                      |
|-------------------|--------------------------------------------------------------------|
| NAVIGATION        |                                                                    |
| -> Dashboard      |  [ Transaction Log ]  [  Statements  ]  [  Reports  ]              |
| -> ...            |--------------------------------------------------------------------|
|                   |                                                                    |
|                   |  [Statements Table]                                                |
|                   |  +---------------+--------------+------------+----------+---------+ |
|                   |  | Period        | Total Amount | Status     | Due Date | Actions | |
|                   |  +---------------+--------------+------------+----------+---------+ |
|                   |  | Nov 1-30, 2024| $12,450.78   | [Paid]     | 12/15/24 | [View]  | |
|                   |  | Oct 1-31, 2024| $11,980.12   | [Paid]     | 11/15/24 | [View]  | |
|                   |  +---------------+--------------+------------+----------+---------+ |
|                   |                                                                    |
+--------------------------------------------------------------------------------------+
```

### 5.6. Dispute Management

#### Wireframe: Dispute Management Page

-   **Purpose**: A comprehensive view of all disputes, their statuses, and associated details.
-   **Layout**: A data table with filtering and search capabilities.

```
+--------------------------------------------------------------------------------------+
| [Logo]            | [Header: Dispute Management]                                       |
|-------------------|--------------------------------------------------------------------|
| NAVIGATION        |                                                                    |
| -> Dashboard      |  [Search Bar]                    [Filter] [Export]                 |
| -> ...            |--------------------------------------------------------------------|
|                   |                                                                    |
|                   |  [Dispute Log Table]                                               |
|                   |  +------------+----------+-----------+-------------+---------------+ |
|                   |  | Status     | Employee | Amount    | Date        | Action        | |
|                   |  +------------+----------+-----------+-------------+---------------+ |
|                   |  | [Compensated] | John S.  | $45.00    | Dec 15, 2024| [View Details]| |
|                   |  +------------+----------+-----------+-------------+---------------+ |
|                   |                                                                    |
+--------------------------------------------------------------------------------------+
```

#### Wireframe: View Dispute Details Modal

-   **Purpose**: To provide all relevant information about a specific dispute in a scannable format.

```
+------------------------------------------------------------------+
| Dispute Details                                              [X] |
|------------------------------------------------------------------|
|                                                                  |
|  [Dispute Information]                                           |
|   - Status: Compensated                                          |
|   - Employee: John Smith (john.smith@company.com)                |
|                                                                  |
|  [Original Transaction Details]                                  |
|   - Service: Adobe Creative Cloud | Amount: $45.00               |
|                                                                  |
|  [Employee Notes]                                                |
|   "I was charged twice for the same service."                    |
|                                                                  |
|                                       [View Transaction] [Close] |
+------------------------------------------------------------------+
```

## 6. Component Library

A consistent and reusable component library is essential for building the Enterprise Admin Portal efficiently and ensuring a cohesive user experience. This library will be the single source of truth for all UI elements.

### 5.1. Strategy: Theming & White-Labeling

The portal must be themeable to align with the branding of different Membership Organizations (MOs). Our strategy will be:

-   **CSS Variables**: All core style values (colors, fonts, spacing, etc.) will be defined as CSS variables.
-   **Theme Files**: Each MO can be provided with a simple CSS file that overrides these variables to apply their brand. This allows for extensive visual customization without touching the underlying component logic.
-   **Default Theme**: A clean, professional Moneta Network theme will be provided as the default.

### 5.2. Core Components

This is an initial list of components required to build the wireframed pages.

| Component             | Description                                                                                             | Used In                                                                  |
| --------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Button**            | Primary, Secondary, Tertiary, and Destructive (e.g., Delete) styles. Supports icons.                     | Everywhere (e.g., "Invite Employee", "Create Group", "Save Policy")      |
| **Input Field**       | Standard text, email, number, and password inputs with validation states (error, success).              | Login, Registration, Invite Modals, Policy Forms                         |
| **Modal**             | A flexible modal container for dialogs, confirmations, and forms.                                       | Invite Employee, Create Group, Confirmation Dialogs                      |
| **Data Table**        | A robust table component with support for sorting, filtering, pagination, and row-level actions.          | User Management, Policy Management, Transaction Log, Statements          |
| **Tabs**              | A navigation component for switching between different views within the same context.                     | Policy Management, Billing & Reporting                                   |
| **Dropdown / Select** | A styled dropdown for selecting options from a list. Supports search.                                   | Filtering controls, Assigning users to groups                            |
| **Search Bar**        | A dedicated input component for searching lists and tables.                                             | User Management, Policy Management                                       |
| **Toast / Notification** | A small, non-intrusive message that appears to provide feedback on an action (e.g., "User invited").    | After almost every form submission (Create, Update, Delete)              |
| **Card**              | A flexible container for grouping related information. Used for dashboards and list views.              | Dashboard (Stat Cards), User Groups page                                 |
| **Pagination**        | Controls for navigating through paginated data in tables.                                               | All Data Tables                                                          |
| **File Uploader**     | A component for selecting and uploading files, with a drag-and-drop area.                                 | Bulk Invite Employees (CSV upload)                                       |
| **Dual List / Picklist** | A component for moving items between two lists. Essential for assigning/un-assigning members.         | Manage Group Membership                                                  |
| **Chart**             | Components for data visualization (Bar, Line, Pie charts).                                              | Reports & Analytics tab                                                  |

## 6. Branding & Style Guide

This style guide defines the default visual identity for the Corporate mPass Admin Portal. The white-labeling capability will allow MOs to override these styles with their own branding.

### 6.1. Color Palette

The palette is designed to be clean, professional, and accessible.

| Role              | Color         | Hex Code  | Usage                                                              |
| ----------------- | ------------- | --------- | ------------------------------------------------------------------ |
| **Primary**       | `primary-blue`  | `#0052CC` | Main call-to-action buttons, links, active navigation, focus states. |
| **Secondary**     | `secondary-teal`| `#00B8D9` | Secondary actions, highlights, charts, and illustrative elements.  |
| **Neutral (Text)**| `neutral-dark`  | `#172B4D` | Body text, headlines, and primary content.                         |
| **Neutral (UI)**  | `neutral-light` | `#F4F5F7` | Backgrounds for pages, cards, and sections.                        |
| **Neutral (Border)**| `neutral-mid`   | `#DFE1E6` | Borders for inputs, cards, and table cells.                        |
| **Success**       | `success-green` | `#36B37E` | Success messages, validation, "Active" status.                     |
| **Warning**       | `warning-yellow`| `#FFAB00` | Warning messages, "Pending" status.                                |
| **Danger**        | `danger-red`    | `#FF5630` | Error messages, destructive actions (e.g., delete), "Suspended".   |

### 6.2. Typography

We will use a modern, sans-serif font stack for readability and a professional feel.

-   **Font Family**: `Inter`, with fallbacks to `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif`.
-   **Headings**:
    -   `H1` (Page Titles): 28px, Bold (`700`)
    -   `H2` (Section Titles): 24px, Bold (`700`)
    -   `H3` (Card/Modal Titles): 20px, Semi-Bold (`600`)
-   **Body Text**: 16px, Regular (`400`)
-   **UI Text** (Buttons, Labels): 14px, Medium (`500`)
-   **Line Height**: `1.5` for all body and heading text to ensure readability.

### 6.3. Iconography

-   **Style**: Icons should be simple, clean, and line-based. They must be easily recognizable.
-   **Library**: We will use a consistent icon library like `Feather Icons` or `Material Symbols (Outlined)` to ensure visual harmony.
-   **Usage**: Icons should always be accompanied by a text label for clarity, except in universally understood cases (e.g., a close 'X' in a modal). All interactive icons must have appropriate ARIA labels for accessibility.

### 6.4. Spacing & Layout

-   **Base Unit**: `8px`. All padding, margins, and layout spacing will be in multiples of this base unit (e.g., 8px, 16px, 24px) to create a consistent vertical and horizontal rhythm.
-   **Layout**: The main application layout will consist of a fixed sidebar for navigation and a main content area.
-   **Max Width**: The main content area will have a max-width of `1200px` and be centered on larger screens to ensure comfortable readability.

## 7. Accessibility

The Corporate mPass Admin Portal must be accessible to all users, including those with disabilities. We are committed to meeting the **Web Content Accessibility Guidelines (WCAG) 2.1 Level AA** standard.

Adherence to this standard will be a requirement for all new features and components.

### 7.1. Key Requirements

-   **Keyboard Navigation**: All interactive elements—including links, buttons, form fields, and menu items—must be fully navigable and operable using only a keyboard. The tab order must be logical and predictable.
-   **Focus Indicators**: A clear and highly visible focus indicator must be present on all interactive elements when they receive keyboard focus. The default browser outline should be enhanced with a style that meets our brand guidelines while ensuring high visibility.
-   **Semantic HTML**: Use proper, semantic HTML5 elements (`<nav>`, `<main>`, `<header>`, `<footer>`, `<button>`, etc.) to define the structure of the page. This is crucial for screen reader users to understand and navigate the content.
-   **ARIA Roles & Attributes**: For complex components like modals, tabs, data tables, and custom dropdowns, appropriate ARIA (Accessible Rich Internet Applications) roles, states, and properties must be used to communicate their function to assistive technologies.
-   **Color Contrast**: All text and meaningful UI elements must meet the WCAG 2.1 AA minimum contrast ratio of `4.5:1` (or `3:1` for large text). The color palette defined in the Style Guide has been selected with this in mind, but all new combinations must be verified.
-   **Forms & Labels**: Every form input must have a programmatically associated `<label>`. Placeholder text is not a substitute for a label. Error messages must be clear, easy to understand, and programmatically linked to the relevant input field.
-   **Images & Icons**: All `<img>` tags must have descriptive `alt` attributes. For icons that convey meaning (e.g., a "delete" trash can icon), an `aria-label` or visually-hidden text must be provided to describe the action. Decorative images and icons should have an empty `alt=""` attribute.
-   **Content Scaling**: The user interface must remain fully readable and functional when the browser zoom is increased up to 200%. Layouts should reflow gracefully without requiring horizontal scrolling.
-   **Screen Reader Testing**: The application will be periodically tested with modern screen readers (e.g., NVDA, VoiceOver) to ensure a usable experience for visually impaired users.
