# Project Brief: Askii for SMBs MVP

## 1. Project Overview

**Date:** 2025-11-03

**Author:** Mary, Business Analyst

Askii is a successful AI platform serving individual users, offering access to multiple LLMs, pre-built assistants, and knowledge collections. The platform is now poised to expand into the Small and Medium Business (SMB) market. This document outlines the project brief for a Minimum Viable Product (MVP) to deliver a commercially viable and competitive B2B offering. The core challenge is to build upon the existing individual user experience by adding the essential layers of administrative control, security, and collaboration that businesses require. All authentication will be handled via Moneta's mPass system.

## 2. Problem Statement

SMBs need access to powerful AI tools to improve productivity, but they cannot adopt platforms designed for individual users. They face several key problems that a generic B2C product does not solve:

*   **Lack of Centralized Management:** They have no way to manage users, control access, or ensure that all employees are using the same set of approved tools.
*   **No Cost Control or Visibility:** They cannot track their team's usage, manage a centralized budget, or prevent unexpected costs.
*   **Serious Security & Compliance Risks:** They have no guarantee that their proprietary company data is kept private and not used for model training, and they cannot prevent employees from accidentally sharing sensitive information.
*   **Inability to Collaborate:** They lack the tools to create and share centralized, private knowledge bases and AI assistants for specific teams or departments.

## 3. Proposed Solution: The "Askii for SMBs" MVP

The proposed solution is to create a new "Askii for SMBs" plan that introduces a **Workspace Model**, the industry standard for B2B collaboration platforms. This model provides a secure, multi-user environment with a clear separation between a user's personal space and their company's shared space.

The MVP will focus on delivering a robust and intuitive administrative experience that directly solves the problems listed above. It will provide the essential features for an SMB to confidently and securely adopt Askii as their company's primary AI platform.

## 4. Key Features for the MVP

The MVP is defined by the following 18 features, grouped into 5 key administrative areas:

#### Account & Workspace Management
1.  **Default Personal Workspace:** Every user gets a private "Personal Workspace" on their first sign-in.
2.  **Admin-Triggered Company Workspace:** A user with a `role: "admin"` claim in their mPass is guided to create the official "Company Workspace."
3.  **Retroactive User Onboarding:** The system automatically adds existing users from a company to the workspace right after it's created.
4.  **UI Workspace Switcher:** A clear UI control allows users to switch between their Personal and Company workspaces.
5.  **Workspace-Specific Billing:** Billing is managed at the workspace level, enabling separate personal and company subscriptions.

#### User Management
6.  **"Just-in-Time" User Provisioning:** New employees with the company's `corporate_id` are automatically added to the workspace on their first sign-in.
7.  **User Management Dashboard:** A simple admin page to view all workspace members.
8.  **Manual User Removal:** A tool for admins to revoke a user's access to the Company Workspace.
9.  **Two-Role System (Admin/Member):** The MVP will support "Admin" and "Member" roles, with the admin status being controlled via an mPass claim.

#### Cost & Usage Control
10. **Unified "Usage & Billing" Dashboard:** A single admin page for a comprehensive overview of cost and activity.
11. **Cost Metrics:** The dashboard will display the "Current AskiiCoin Balance," "Monthly Coin Consumption," a "Buy More AskiiCoins" button, and "Top Users by AskiiCoin Consumption."
12. **Activity Metrics:** The dashboard will also show "Total Queries" and the "Most Used Assistants."

#### Data & Resource Management
13. **Permissive Resource Creation:** Any workspace member can create new AI assistants and knowledge bases.
14. **Simple In-Workspace Sharing:** Users can keep resources "Private to me" or "Share with Everyone" in the workspace.
15. **Admin Resource Oversight:** An admin dashboard to view and manage all resources created within the workspace.

#### Content & Security Policy
16. **Data Privacy Guarantee:** A foundational promise that company data is never used for model training and is kept secure and isolated.
17. **Conversation Sharing Policy:** A default-on admin setting to "Disable Conversation Sharing" outside the workspace.
18. **Basic Admin Activity Log:** A read-only log tracking key administrative and security events.

## 5. Next Steps

*   **Stakeholder Review:** Share this project brief with all key stakeholders to ensure alignment and secure buy-in.
*   **PRD Creation:** Upon approval, the Product Manager will create a detailed Product Requirements Document (PRD) with user stories for each of the 18 defined features.
*   **Technical Scoping:** The engineering team will begin a technical discovery and scoping process based on the PRD.
