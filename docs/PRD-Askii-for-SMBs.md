# Askii for SMBs MVP Product Requirements Document (PRD)

## Goals and Background Context

### Goals

*   To solve the critical need for a centrally managed, secure, and collaborative AI platform for Small and Medium Businesses (SMBs).
*   To provide SMB administrators with essential tools for user management, cost control, and data security.
*   To enable employees within an SMB to have both a private, personal workspace and a shared, secure company workspace under a single login.
*   To launch a Minimum Viable Product (MVP) that is commercially viable, competitive, and provides immediate value to our new business customers.

### Background Context

Askii has proven to be a successful AI platform for individual users. However, to expand into the lucrative SMB market, we must address a set of needs that our current B2C product does not. SMBs require robust administrative controls, guarantees of data privacy, and tools for internal collaboration that are absent in a consumer-grade product.

This PRD outlines the requirements for an MVP of "Askii for SMBs," which is based on a flexible and industry-standard "Workspace Model." This model will allow us to deliver a secure, multi-user environment that gives SMBs the confidence and control they need to adopt Askii as their company's primary AI platform, all while leveraging Moneta's mPass for authentication.

### Change Log

| Date       | Version | Description               | Author |
| :--------- | :------ | :------------------------ | :----- |
| 2025-11-03 | 1.0     | Initial draft of the PRD. | John   |

## Requirements

### Functional Requirements

**Account & Workspace Management**
*   **FR1:** The system shall create a private "Personal Workspace" for any new user upon their first sign-in.
*   **FR2:** The system shall present a "Choose Your Business Plan" and subscription checkout flow to a user whose mPass contains a `role: "admin"` claim if they are the first user from their `corporate_id`.
*   **FR3:** Only after a successful subscription shall the system trigger the "Create Company Workspace" wizard.
*   **FR4:** Upon the creation of a Company Workspace, the system shall automatically find and add all existing users who share the same `corporate_id`.
*   **FR5:** The user interface shall provide a control that allows users to switch between their Personal and any Company Workspaces they are a member of.
*   **FR6:** The system shall manage billing and subscriptions at the workspace level, allowing for independent billing for personal and company workspaces.

**User Management**
*   **FR7:** The system shall automatically create a user account and add it to the correct Company Workspace when a new employee with a recognized `corporate_id` signs in for the first time.
*   **FR8:** The admin dashboard shall display a list of all members of the Company Workspace.
*   **FR9:** An administrator shall be able to remove a user from their Company Workspace, revoking their access to its resources.
*   **FR10:** The system shall support two user roles: "Admin" and "Member." An existing Admin shall be able to promote a Member to an Admin, and demote an Admin to a Member.

**Cost & Usage Control**
*   **FR11:** The admin dashboard shall include a unified "Usage & Billing" page.
*   **FR12:** The dashboard must display the workspace's current AskiiCoin balance, a history of monthly coin consumption, and a button to purchase more AskiiCoins.
*   **FR13:** The dashboard must display the top users by AskiiCoin consumption, the total number of queries, and the most used assistants.

**Data & Resource Management**
*   **FR14:** Any member of a Company Workspace shall be able to create new AI assistants and knowledge bases within that workspace.
*   **FR15:** When creating a resource, a user shall be able to set its visibility to either "Private to me" or "Share with Everyone" in the workspace.
*   **FR16:** The admin dashboard shall include a page to view and manage all resources (both private and shared) created within the workspace.

**Content & Security Policy**
*   **FR17:** An administrator shall be able to disable the ability for non-admins to share conversations publicly via a toggle in the admin settings.
*   **FR18:** The admin dashboard shall include a read-only "Activity Log" that records key events (user added/removed, policies changed, resources shared).

### Non-Functional Requirements

*   **NFR1 (Security):** Data from one Company Workspace must be logically and cryptographically isolated and inaccessible to any other workspace or user.
*   **NFR2 (Compliance):** All data within a Company Workspace, including user queries and knowledge base content, shall not be used for the training of any AI models (either first-party or third-party). This must be a firm product guarantee.
*   **NFR3 (Usability):** The process for a new employee to join an existing workspace must be seamless and fully automated, requiring no manual action from an administrator.
*   **NFR4 (Performance):** The workspace switcher UI must allow users to change contexts with minimal and acceptable latency.

## User Interface Design Goals

**Overall UX Vision**
The introduction of "Askii for SMBs" should feel like a natural and seamless extension of the existing platform. The primary vision is to maintain the clean, intuitive user experience of the personal product while layering in powerful administrative controls.

**Key Interaction Paradigms**
*   **The Workspace as the Primary Context:** The "Workspace" will be the core organizational paradigm.
*   **The Workspace Switcher:** A new, persistent, and highly visible UI element for switching between personal and company workspaces.
*   **The Admin Settings Panel:** A new, secure area of the application, accessible only to Admins.

**Core Screens and Views**
1.  **"Choose Your Business Plan" Page & Checkout Flow**
2.  **First-Time Admin "Create Company Workspace" Wizard**
3.  **Admin "Setup Your Workspace" Guide**
4.  **The Workspace Switcher Component**
5.  **The Admin Settings Panel** (with pages for User Management, Usage & Billing, Resource Management, Policies, and Activity Log)
6.  **Resource Creation/Sharing Controls** (updated modals)
7.  **"Employee First" Blocking Page**

**Accessibility & Branding**
All new UI components must adhere to the existing branding, style guide, and accessibility standards (WCAG AA).

## Technical Assumptions

**Repository & Architecture**
*   **Repository Structure:** All work will be done within the existing Askii platform's monorepo.
*   **Service Architecture:** The solution will be built by extending existing services, introducing the "Workspace" as a core primitive in our data models and APIs.

**Integration with Moneta mPass**
*   **Critical Dependency:** The entire B2B authentication and user management model is critically dependent on our integration with Moneta mPass.
*   **Required mPass Claims:** The mPass JWT must be configurable to include `corporate_id` and `role: "admin"`.

**Testing & Performance**
*   **Testing Requirements:** Comprehensive unit, integration, and end-to-end tests are required for all new business logic.
*   **Performance:** The workspace model should not introduce noticeable performance degradation.

**Data Model**
*   **Workspace as a Core Primitive:** "Workspace" will be a central entity in our database schema, with users, resources, and subscriptions associated with a workspace ID.

## Epic List

*   **Epic 1: The Foundational Workspace & Admin Experience.**
    *   **Goal:** To build the core B2B infrastructure, including the new Workspace data model, the automated onboarding and user provisioning flows, and the essential administrative dashboards.

*   **Epic 2: In-Workspace Collaboration & Resource Management.**
    *   **Goal:** To enable the powerful, bottom-up creation and sharing of resources within a Company Workspace and provide administrators with oversight tools.

## Epic 1: The Foundational Workspace & Admin Experience

**Goal:** To build the core B2B infrastructure, including the new Workspace data model, the automated onboarding and user provisioning flows, and the essential administrative dashboards for managing users, billing, and security policies.

#### Story 1.1: A New User Gets a Personal Workspace by Default
*   **As a** new user,
*   **I want** a personal workspace to be automatically created for me on my first sign-in,
*   **so that** I have a private, default space to use the platform for my own purposes.

**Acceptance Criteria:**
1.  When a user with a previously unseen mPass ID successfully authenticates, a new user account is created.
2.  Simultaneously, a new "Personal Workspace" is created and associated with that user account.
3.  The user is logged in and their initial context is set to their new Personal Workspace.

#### Story 1.2: A New Admin Subscribes to a Business Plan to Create Their Workspace
*   **As a** new Administrator,
*   **I want** to be prompted to choose and subscribe to an "Askii for Business" plan when I first sign up,
*   **so that** I can unlock the ability to create a secure, collaborative workspace for my company.

**Acceptance Criteria:**
1.  If a new user's mPass contains a `role: "admin"` claim and their `corporate_id` is new, they are directed to a "Choose Your Business Plan" page.
2.  After selecting a plan, the admin is taken through a checkout flow.
3.  Only after a successful subscription is the "Create Company Workspace" wizard triggered.
4.  If the user abandons the subscription flow, the Company Workspace is not created.

#### Story 1.3: The UI Provides a Clear Workspace Switcher
*   **As a** user who is a member of multiple workspaces,
*   **I want** a clear and simple UI control to switch between my workspaces,
*   **so that** I can seamlessly navigate between my personal and professional contexts.

**Acceptance Criteria:**
1.  A persistent UI element lists all workspaces the user is a member of.
2.  Selecting a workspace reloads the context and displays the resources of that workspace.

#### Story 1.4: New Employees are Automatically Added to the Company Workspace
*   **As an** Administrator,
*   **I want** new employees from my company to be automatically added to our workspace when they sign in for the first time,
*   **so that** the user onboarding process is fully automated.

**Acceptance Criteria:**
1.  When a new Company Workspace is created, the system identifies all existing users with the same `corporate_id` and adds them as Members.
2.  When a new user signs up and their `corporate_id` matches an existing Company Workspace, they are automatically added as a Member.

#### Story 1.5: Admins Can Manage Users in a Central Dashboard
*   **As an** Administrator,
*   **I want** a central dashboard to see all the members of my workspace and manage their roles and access,
*   **so that** I have full control over who is in my company's secure environment.

**Acceptance Criteria:**
1.  An "Admin Settings" area is accessible only to users with the Admin role.
2.  A "User Management" page lists all workspace members.
3.  An Admin can promote a Member to an Admin.
4.  An Admin can demote another Admin to a Member (as long as one Admin remains).
5.  An Admin can remove a user from the workspace.

#### Story 1.6: Admins Can Manage Billing and Usage
*   **As an** Administrator,
*   **I want** a single dashboard to monitor my team's AskiiCoin consumption and activity,
*   **so that** I can manage our budget and understand how the team is using the platform.

**Acceptance Criteria:**
1.  A "Usage & Billing" page is available in the Admin Settings.
2.  The page displays the current AskiiCoin balance, a chart of monthly consumption, and a button to buy more coins.
3.  The page displays the top users by coin consumption, total queries, and most used assistants.

#### Story 1.7: Admins Can Set Basic Security Policies
*   **As an** Administrator,
*   **I want** to be able to set basic security policies for my workspace,
*   **so that** I can ensure my company's data is being handled safely.

**Acceptance Criteria:**
1.  A "Policies" page is available in the Admin Settings.
2.  This page contains a toggle to "Disable Conversation Sharing," which is on by default.
3.  A read-only "Activity Log" is present, showing key administrative events.

## Epic 2: In-Workspace Collaboration & Resource Management

**Goal:** To enable the powerful, bottom-up creation and sharing of resources within a Company Workspace, empowering team members while providing administrators with the necessary tools for oversight.

#### Story 2.1: Any Workspace Member Can Create a New Resource
*   **As a** team member in a Company Workspace,
*   **I want** to be able to create a new AI assistant or a new knowledge base,
*   **so that** I can build tools that help me and my team do our jobs more effectively.

**Acceptance Criteria:**
1.  When a user is inside a Company Workspace, the UI presents options to "Create New Assistant" and "Create New Knowledge Base."
2.  The new resource is created and associated with the Company Workspace's ID.

#### Story 2.2: Users Can Set the Visibility of Their Created Resources
*   **As a** team member who has created a new resource,
*   **I want** to be able to control who can see and use it,
*   **so that** I can work on things in private before sharing them.

**Acceptance Criteria:**
1.  When a user creates a resource, they must choose a visibility setting: "Private to me" or "Share with Everyone in the Workspace."
2.  The creator can change the visibility setting at any time.

#### Story 2.3: Admins Have an Oversight Dashboard for All Workspace Resources
*   **As an** Administrator,
*   **I want** a central dashboard where I can see every resource created within my workspace,
*   **so that** I have full visibility and can manage the content being created.

**Acceptance Criteria:**
1.  A "Resource Management" page is available in the Admin Settings.
2.  This page displays a list of all resources, who created them, and their sharing status.
3.  An admin can delete any resource on this list.
