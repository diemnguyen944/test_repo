# mPass Personal Data Framework Product Requirements Document (PRD)

## Goals and Background Context

### Goals

*   To establish a federated data ecosystem allowing Askii.ai to access distributed user data with explicit consent via the mPass.
*   To solve the "Amnesiac AI" problem by transforming Askii.ai into a hyper-personalized assistant anchored by the user's trusted MO relationship.
*   To create a secure, user-centric framework where data remains at its source, overcoming user distrust of centralized data vaults.
*   To build a scalable, open ecosystem using the MCP standard that encourages third-party service integration.
*   To position the mPass framework as the leading solution for trusted, personalized AI, creating a strategic moat for the Moneta ecosystem.

### Background Context

The mPass Personal Data Framework addresses a critical limitation in modern AI assistants: their lack of memory and personal context. Currently, users engage in repetitive, "contextless" conversations with Askii.ai, manually providing information that is siloed across various services. This project aims to solve this "Amnesiac AI" problem by creating a novel federated system.

Instead of building another data silo, the framework will enable Askii.ai to securely access a user's data where it resides (e.g., within their Membership Organization's database, Gmail, etc.). This is achieved through the mPass, which acts as a universal key for authentication and real-time user consent, all anchored by the existing trusted relationship between the user and their MO. This approach directly addresses user privacy concerns and the friction of using generic AI, aiming to evolve Askii.ai into an indispensable, hyper-personalized digital companion.

### Change Log

| Date | Version | Description | Author |
| :--- | :--- | :--- | :--- |
|      | 0.1 | Initial Draft | John (PM) |

## Requirements

### Functional Requirements

*   **FR1:** The system must provide a production-ready MCP server to expose a high-value data point from a partner Membership Organization (MO), serving as the foundational trust anchor.
*   **FR2:** The system must include a central **mPass Consent Gateway** service to manage the secure, real-time consent flow between Askii.ai, the MO, and connected third-party services.
*   **FR3:** The mPass Consent Gateway must be capable of generating a user-facing interface to handle the explicit consent process.
*   **FR4:** Askii.ai must be able to detect when a user query requires data from a connected service and correctly trigger the mPass consent flow if access has not yet been granted.
*   **FR5:** The end-to-end user consent journey—from the contextual AI prompt, through the mPass flow, to the final confirmation—must be fully implemented.
*   **FR6:** A basic consent management dashboard must be provided, allowing users to view all connected services and revoke access with a single action.
*   **FR7:** The system must securely store and manage the consent tokens granted by the user.

### Non-Functional Requirements

*   **NFR1:** The user-facing consent flow must be highly responsive, completing in under 3 seconds (excluding user sign-in time with third parties).
*   **NFR2:** The end-to-end latency for an AI query that uses federated data should be under 2 seconds to ensure a conversational feel.
*   **NFR3:** Security is paramount: All data in transit must be encrypted with TLS, and all sensitive data at rest (e.g., consent tokens) must be encrypted.
*   **NFR4:** The system architecture must be designed for GDPR and CCPA compliance from day one, including clear data processing agreements for partners.
*   **NFR5:** The system shall be built on a decoupled, microservices-based architecture to ensure scalability and separation of concerns.
*   **NFR6:** The framework's user-facing components (e.g., consent UI) must be accessible within both the Askii.ai web platform and the mPass mobile app.
*   **NFR7:** All consent grants, denials, and revocations must be logged for auditing and support purposes.

## User Interface Design Goals

### Overall UX Vision

The user experience must be anchored in **trust and transparency**. Every interaction, especially the consent flow, should feel secure, clear, and user-centric. The user must feel like they are in complete control, simply granting permission to an AI they already trust, rather than navigating a complex technical process. The design should be minimalist, professional, and reassuring.

### Key Interaction Paradigms

*   **Contextual Consent:** The primary interaction is initiating the consent flow directly from a conversational prompt in Askii.ai. The transition from chat to consent modal should be seamless and feel like a natural part of the conversation.
*   **One-Click Revocation:** In the management dashboard, revoking access to a connected service must be a simple, single-click action, reinforcing the user's sense of control.
*   **Clear and Simple Language:** All user-facing text must use plain, non-technical language to explain what data is being requested and why. Avoid jargon like "OAuth" or "API access."

### Core Screens and Views

*   **Contextual Consent Prompt (within Askii.ai):** A non-intrusive banner or modal that appears when Askii.ai needs permission.
*   **mPass Consent UI:** A multi-step modal view that clearly presents the service requesting access, the specific permissions needed, and provides clear "Allow" / "Deny" actions. This UI is launched from Askii.ai but is visually branded as part of the trusted mPass system.
*   **Consent Success/Failure Confirmation:** A simple screen confirming the outcome of the consent flow and guiding the user back to their chat.
*   **Basic Consent Management Dashboard:** A simple list view (within Askii.ai settings or the mPass app) showing connected services with a prominent "Disconnect" button for each.

### **Accessibility: WCAG AA**

The consent flow is a critical-path user interaction and must be accessible to all users. We will adhere to WCAG 2.1 Level AA as a minimum standard.

### Branding

The consent UI must prominently feature the mPass and the partner MO's branding to leverage the existing trust relationship. The look and feel should be consistent with the mPass mobile application to ensure familiarity and reinforce security.

### **Target Device and Platforms: Cross-Platform**

The user-facing components must be fully responsive and functional across the Askii.ai web platform and the mPass mobile app (iOS and Android).

## Technical Assumptions

### **Repository Structure: Monorepo**

All services for the mPass Personal Data Framework (e.g., mPass Consent Gateway, MO Data MCP Server wrapper, etc.) will be managed within a single monorepo.

### Service Architecture

The system will be built using a **decoupled, microservices-based architecture** as mandated by the project brief. Key services for the MVP will include:
1.  **mPass Consent Gateway:** Manages the OAuth-like consent flow, token exchange, and secure storage of consent records.
2.  **MO Data MCP Server:** A service that acts as a wrapper or proxy for the partner MO's internal APIs, exposing the required data via a compliant MCP interface.
3.  **Partner Integration Service:** A service to manage the configurations and logic for interacting with various third-party MCP servers.

### Testing Requirements

The MVP will require, at a minimum, **comprehensive Unit and Integration testing**.
*   **Unit Tests:** Each microservice's internal logic, models, and helpers must have thorough unit test coverage.
*   **Integration Tests:** We must have tests that verify the interactions *between* the core services (e.g., can Askii.ai successfully trigger the Consent Gateway, which then successfully calls the Partner Integration Service?).

### Additional Technical Assumptions and Requests

*   **Backend Technology:** Services will be developed using **Node.js/TypeScript or Go**, chosen for high performance in I/O-bound operations and strong typing.
*   **Containerization:** All services must be containerized using **Docker** from day one to ensure consistent development and deployment environments.
*   **Database:** The system will use **PostgreSQL** for storing structured, relational data like consent records and audit logs, and **Redis** for caching session data and tokens.
*   **Infrastructure:** The framework will be designed as cloud-native, targeting **AWS** for its scalability, security, and managed service offerings (e.g., RDS for Postgres, ElastiCache for Redis).
*   **Protocol Dependency:** The entire framework's success is critically dependent on the stability and feature set of the **Model Context Protocol (MCP)** standard. The implementation must adhere strictly to this standard.

## Epic List

*   **Epic 1: Foundational Services & MO Data Integration:** Build the foundational connection that allows Askii.ai to securely access a user's data from their primary Membership Organization, establishing the core trust anchor of the system.
*   **Epic 2: End-to-End Consent Flow for a Single Third-Party Service:** Develop the complete, user-facing consent flow that allows a user to safely connect their first external service (like Google Calendar) to Askii.ai through the secure mPass system.
*   **Epic 3: Basic Consent Management & Production Readiness:** Create the dashboard that allows users to easily see and manage their connected services, and finalize the security and monitoring needed for a safe and reliable launch.

## Epic 1: Foundational Services & MO Data Integration

**Goal:** This epic focuses on building the core technical foundation of the mPass framework. The objective is to establish the project's infrastructure and create the first critical data link: a secure, functioning MCP server that allows Askii.ai to access a single, high-value piece of data from a partner Membership Organization. This proves the viability of the core connection and establishes the trusted data anchor for the entire system.

### **Technical Story 1.1: Project Foundation & CI/CD**

**As a** developer,
**I want** a new monorepo set up with a basic CI/CD pipeline,
**so that** I can ensure all future code is automatically tested and deployed in a consistent and reliable manner.

#### Acceptance Criteria

1.  A new monorepo is created in the version control system.
2.  A basic CI/CD pipeline (e.g., using GitHub Actions) is configured to trigger on every push to the main branch.
3.  The pipeline successfully runs a linting step and a placeholder test script.
4.  A "hello-world" service is created within the monorepo that can be successfully built and deployed to the development environment by the pipeline.
5.  The deployed service has a public health-check endpoint that returns a `200 OK` status.

### **Technical Story 1.2: MO Data MCP Server Implementation**

**As a** developer,
**I want** to build an MCP-compliant server that exposes a single, high-value data point from a partner MO's database,
**so that** we have a secure and standardized component for other services to consume.

#### Acceptance Criteria

1.  A new microservice, the "MO Data MCP Server," is created within the monorepo.
2.  The server implements the necessary endpoints required by the MCP standard.
3.  The server includes a secure mechanism to authenticate requests coming from Askii.ai.
4.  Initially, the server's MCP endpoint returns a hardcoded, valid mock data response for a single data point (e.g., a sample transaction history).
5.  The implementation includes comprehensive unit tests for the server's logic and MCP interface.
6.  The service is successfully deployed to the development environment and its health can be monitored.

### **User Story 1.3: Use My Real, Live MO Data**

**As an** end user,
**I want** the connection to my Membership Organization to use my actual, real-time data,
**so that** the personalized answers I get from Askii.ai are accurate and up-to-date.

#### Acceptance Criteria

1.  The MCP server is configured with secure credentials to access the partner MO's database or API.
2.  The server's logic is updated to fetch live data for the specified data point (e.g., a user's transaction history) based on an incoming user identifier.
3.  The fetched data is correctly transformed into the MCP-compliant format before being returned.
4.  Error handling is implemented to gracefully manage cases where the MO's data source is unavailable or returns an error.
5.  Integration tests are written to verify that the service can successfully connect to the MO's data source and return valid data.
6.  No sensitive MO credentials are hardcoded; they are managed via a secure secrets management system (e.g., AWS Secrets Manager).

## Epic 2: End-to-End Consent Flow for a Single Third-Party Service

**Goal:** This epic's objective is to build and integrate the complete, user-facing consent flow. It involves creating the central mPass Consent Gateway service and connecting it to Askii.ai. By the end of this epic, a user should be able to respond to a contextual prompt in Askii.ai, go through a secure and clear consent process, and successfully connect their first third-party service (e.g., Google Calendar) to the framework.

### **Technical Story 2.1: mPass Consent Gateway Service Foundation**

**As a** developer,
**I want** to create the foundational mPass Consent Gateway microservice,
**so that** we have a central, secure system for managing consent states and storing user permissions.

#### Acceptance Criteria

1.  A new microservice, the "mPass Consent Gateway," is created in the monorepo.
2.  A database schema (using PostgreSQL) is created to store consent records, including user ID, service ID, status (granted/revoked), and timestamps.
3.  The service exposes secure, internal API endpoints to:
    *   Create a new consent record in a "pending" state.
    *   Update a consent record's state to "granted" or "revoked".
    *   Query the current consent status for a given user and service.
4.  The service includes robust unit tests for all database interactions and API endpoints.
5.  The service is deployed to the development environment and its health can be monitored.

### **User Story 2.2: Provide Clear and Informed Consent via mPass**

**As an** end user,
**I want** to see a clear and trustworthy **mPass consent interface** when a service asks for permission to access my data,
**so that** I can make an informed decision and feel secure knowing the request is handled by my trusted mPass system.

#### Acceptance Criteria

1.  A new frontend application is created for the consent UI, which will be displayed in a modal or new window.
2.  The UI dynamically displays the name and icon of the service requesting access.
3.  The UI clearly lists the specific permissions being requested in plain, non-technical language.
4.  The UI presents clear "Allow" and "Deny" buttons.
5.  Clicking "Allow" calls the Consent Gateway's API to update the consent status to "granted".
6.  Clicking "Deny" closes the flow and updates the consent status to "denied".
7.  The UI is styled to be consistent with the mPass branding to reinforce trust.

### **User Story 2.3: Use My Existing Logins via the mPass Flow**

**As an** end user,
**I want** to use my existing login credentials (like my Google account) when the **mPass consent flow** securely hands me off to the third-party service,
**so that** I don't have to create new passwords and can trust the authentication process is handled by the service provider.

#### Acceptance Criteria

1.  When a user clicks "Allow" in the consent UI, they are securely redirected to the third-party provider's (e.g., Google's) OAuth screen.
2.  The Consent Gateway correctly handles the OAuth callback, exchanging the authorization code for an access token and refresh token.
3.  The obtained tokens are securely encrypted and stored, associated with the user's consent record.
4.  The system implements the logic to use the refresh token to obtain new access tokens when they expire.
5.  Robust error handling is in place for all potential OAuth failures (e.g., user denies permission, invalid code, provider error).

### **User Story 2.4: Grant Permission via a Contextual Prompt in Askii.ai**

**As an** end user,
**I want** **Askii.ai to prompt me** to connect a new service at the exact moment it's needed,
**so that** I can seamlessly begin the consent process through my trusted mPass system right when it's most relevant.

#### Acceptance Criteria

1.  Askii.ai's backend is able to query the mPass Consent Gateway to check if a user has valid consent for a specific service.
2.  If consent is not present, Askii.ai's backend can request a new consent flow from the Gateway and receive a unique URL for the consent UI.
3.  The **Askii.ai frontend** can display a contextual prompt (e.g., a banner or button) with the unique consent URL.
4.  Clicking the prompt launches the **mPass consent UI** flow in a secure modal or popup window.
5.  After the flow completes, the Askii.ai interface is notified of the success or failure.

## Epic 3: Basic Consent Management & Production Readiness

**Goal:** This epic delivers the final core user-facing feature for the MVP: the ability for users to manage their connections. The objective is to build a simple but clear dashboard where users can see which services they've connected and easily revoke access. This epic also includes the critical "last mile" work of hardening the system with robust logging, monitoring, and security checks to ensure it is safe and reliable for launch.

### **User Story 3.1: See All My Connected Services**

**As an** end user,
**I want** to see a simple list of all the third-party services I have connected to Askii.ai,
**so that** I have a clear overview of what applications have access to my data.

#### Acceptance Criteria

1.  A new "Connected Services" page or section is created within the Askii.ai settings or the mPass app.
2.  The UI makes a secure API call to the mPass Consent Gateway to fetch the list of all services with a "granted" consent status for the logged-in user.
3.  The UI displays a list of the connected services, showing the name and icon for each one.
4.  If the user has not connected any services, the UI displays a clear "empty state" message.
5.  The UI is responsive and functions correctly on both web and mobile platforms.

### **User Story 3.2: Control My Connections**

**As an** end user,
**I want** a simple, one-click way to disconnect a service from the management dashboard,
**so that** I feel in complete control and can revoke access instantly if I change my mind.

#### Acceptance Criteria

1.  Each connected service listed in the dashboard has a clearly visible "Disconnect" or "Revoke" button.
2.  Clicking the "Disconnect" button prompts the user with a confirmation dialog to prevent accidental revocations.
3.  Upon confirmation, the UI calls a new secure endpoint on the mPass Consent Gateway to update the service's consent status to "revoked".
4.  The gateway service also triggers a call to the third-party provider's API to properly revoke the OAuth token, if required by the provider.
5.  After a successful revocation, the service is immediately removed from the list in the UI.
6.  Integration tests are written to verify the end-to-end revocation flow.

### **Technical Story 3.3: Ensure a Secure and Reliable Platform**

**As a** developer,
**I want** to implement comprehensive logging, monitoring, and security checks across all new services,
**so that** we can ensure the framework is stable, secure, and supportable before launching to pilot users.

#### Acceptance Criteria

1.  **Logging:** All services (MO Data Server, Consent Gateway) must implement structured logging (e.g., JSON format) for all critical events, errors, and API requests.
2.  **Monitoring:** A monitoring dashboard (e.g., in AWS CloudWatch or Datadog) is created to track the health, performance (latency, error rate), and resource usage of each microservice.
3.  **Alerting:** Automated alerts are configured to notify the development team of critical errors, performance degradation, or security anomalies (e.g., a spike in failed consent attempts).
4.  **Security Audit:** A final security review of the authentication, encryption, and data handling practices is conducted and any identified vulnerabilities are remediated.
5.  All non-functional requirements regarding performance (**NFR1, NFR2**) and security (**NFR3, NFR4**) are formally tested and verified.
