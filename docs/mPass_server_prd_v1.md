# mPass Personal Data Framework Product Requirements Document (PRD)

## Change Log

| Date | Version | Description | Author |
| :--- | :--- | :--- | :--- |
|   11 Aug 2025   | 1.0     | Initial draft   | Diem Nguyen |

## Goals and Background Context

### Goals

*   Transform Askii.ai from a generic assistant into a hyper-personalized digital companion by solving the "Amnesiac AI" problem.
*   Enable Askii.ai to securely access user's fragmented personal data from their Membership Organizations (MO) and other mPass integrated services.
*   Empower users with full control over their data through a unified, mPass-based consent and authentication system.
*   Elevate the role of the MO to a "trusted digital steward" in the AI era.
*   Establish the mPass Personal Data Framework as the leading solution for trustworthy, user-centric AI personalization.

### Background Context

Askii.ai currently operates with a significant handicap: it has no memory of user context, forcing users to repeatedly provide the same information. A user's valuable data is siloed across various services, preventing the AI from delivering truly insightful, personalized experiences. Existing solutions fall short, as they either lack access to this distributed data or require users to move their information to new, untrusted centralized vaults.

This project addresses this critical gap by creating a federated data ecosystem. Instead of centralizing data, the mPass Personal Data Framework enables Askii.ai to securely access data where it already lives, anchored by the trusted relationship between a user and their MO. By using mPass as the key for authentication and consent, we can solve the "Amnesiac AI" problem in a way that respects user privacy and control, unlocking the next level of hyper-personalized AI assistance.

## Requirements

### Functional

1.  **FR1: MO Data MCP Server Package:** Moneta shall develop and maintain a self-contained, distributable MCP server package that MOs can deploy within their own infrastructure.
2.  **FR2: MO Data MCP Server Data Exposure:** The MO Data MCP Server package must expose user data (e.g., personal profile, preferences, behavioral data, transaction history) via a set of standardized, versioned MCP tools.
3.  **FR3: Connection to MO Data MCP Server:** A user must be able to initiate a connection to their MO's Data MCP Server through the Askii.ai interface.
4.  **FR4: mPass Authentication:** The connection process must use mPass as the primary authentication mechanism.
5.  **FR5: Connection Consent:** After successful mPass authentication, the user must be presented with a consent screen that clearly lists the specific data permissions being requested by Askii.ai.
6.  **FR6: Durable Authorization:** Upon user approval of the consent screen, a durable authorization token must be created and securely stored, allowing Askii.ai to make subsequent data requests without requiring the user to re-authenticate or re-consent.
7.  **FR7: mPass-Integrated Partner Service Connection:** A user must be able to connect Askii.ai to third-party services that are MCP-enabled and already integrated with mPass, using the same mPass authentication and consent flow (FR4, FR5, FR6).
8.  **FR8: MO Data Retrieval:** Askii.ai must be able to detect when a user query requires data from a connected MO and invoke the appropriate MCP tool(s) to retrieve it.
9.  **FR9: mPass-Integrated Partner Data Retrieval:** Askii.ai must be able to invoke the MCP tools of a connected partner service to retrieve data or execute actions.
10. **FR10: Connection Management:** A user must be able to view their active MCP server connections (both MO and partner) and revoke access for any connection from within Askii.ai.

### Non-Functional

1.  **NFR1: Security of Package:** The distributable MO Data MCP Server Package must be built to the highest security standards, with all data encrypted in transit (TLS) and all sensitive configuration values encrypted at rest.
2.  **NFR2: Security of Connection Tokens:** All authorization tokens for MCP connections must be stored securely, using state-of-the-art encryption at rest.
3.  **NFR3: Performance:** The mPass connection and consent flow should complete in under 3 seconds (excluding user interaction time). Federated data queries via MCP tools should have a target latency of under 2 seconds to feel seamless in conversation.
4.  **NFR4: Deployability:** The MO Data MCP Server Package must be cloud-agnostic and capable of running in any standard containerized environment with minimal, clearly documented dependencies.
5.  **NFR5: Data Privacy:** Moneta shall have no technical access to any user data hosted and served by the MO-deployed MCP server. Moneta's role is strictly limited to package development and maintenance.
6.  **NFR6: Compliance:** The MO is responsible for the compliance (e.g., GDPR, CCPA) of the environment where the MCP server package is deployed. The package itself must provide the necessary configurations and capabilities to enable compliance.

## User Interface Design Goals

### Overall UX Vision

The user experience for connecting MO data sources to Askii.ai must be **secure, transparent, and simple**. The user should feel in complete control at all times, understanding exactly what they are granting access to. The design should leverage the trust already established with mPass and feel like a natural extension of that secure ecosystem, rather than a new, unfamiliar process.

### Key Interaction Paradigms

*   **Dual Initiation Model:** Users can initiate a new service connection in two ways:
    *   **Contextual Prompt:** A suggestion to connect appears when Askii.ai needs a service to fulfill a request.
    *   **Manual Setup:** A dedicated service management area where users can proactively browse and connect available services.
*   **Familiar OAuth Pattern:** The mPass authentication and consent flow should mirror the familiar, industry-standard pattern that users already recognize.
*   **Centralized Management in Askii.ai:** Users will have a single, clear location within the Askii.ai application to view and manage all connected services.

### Core Screens and Views

Conceptually, the following UI components are required:

1.  **Connection Prompt (within Askii.ai conversation):** A non-intrusive prompt that appears when Askii.ai determines it needs access to a new data source to answer a query.
2.  **Service Management View (within Askii.ai settings):** A dashboard where users can see all available and connected services, and initiate new connections manually.
3.  **mPass Authentication Screen:** The standard, secure mPass login interface.
4.  **Consent Screen (via mPass):** A clear, concise screen that lists the service requesting access and the specific data permissions it requires. It must have obvious "Approve" and "Deny" actions.

### Accessibility: WCAG AA

All UI components related to the connection and consent flow must meet WCAG 2.1 AA standards to ensure they are usable by people with disabilities.

### Branding

The flow will use the established branding of Askii.ai for the initial prompt and the established branding of mPass for the authentication and consent screens to maintain user trust and context.

### Target Device and Platforms: Web Responsive

The initial UI components will be delivered as part of the Askii.ai responsive web application and the mPass mobile/web views.

## Technical Assumptions

### Repository Structure

*   **Requirement:** The engineering team should determine the optimal repository structure to facilitate code sharing and dependency management between Askii.ai services and the MO Data MCP Server Package.
*   **Considerations:** The chosen structure should enable efficient CI/CD pipelines and maintain consistency across the framework components.

### Service Architecture

*   **Requirement:** The system must support a federated architecture model where MCP servers are deployed independently by third parties.
*   **Key Components:** 
    1.  The **distributable MO Data MCP Server Package**, deployed and operated by MOs within their own infrastructure.
    2.  The **core Askii.ai backend services**, which orchestrate connections and consume data from the deployed packages.
*   **Constraint:** The architecture must enable secure communication between federated services while maintaining data sovereignty for MOs.
*   **Note:** The engineering team will determine and update the specific service architecture implementation details during the architecture design and implementation phases.

### Testing Requirements: Unit & Integration Testing

*   **Assumption:** The team will be responsible for comprehensive unit and integration tests for all code.
*   **Rationale:** Given the security-sensitive nature of this framework, a robust testing strategy is critical.
    *   **Unit Tests:** Every component of the Askii.ai backend and the MCP Server Package must have thorough unit tests.
    *   **Integration Tests:** We must test the integration points between Askii.ai services and the mPass service, as well as the interaction with a sample deployment of the MCP Server Package. End-to-end testing will be part of the pilot phase with partner MOs.

### Additional Technical Assumptions and Requests

*   **Containerization:** The `MO Data MCP Server Package` must be delivered as a standard, self-contained containerized application (e.g., a Docker image).
*   **Cloud Agnostic Package:** The server package must be cloud-agnostic and able to run in any standard container orchestration environment (like Kubernetes or Amazon ECS) with minimal configuration.
*   **Askii.ai Database:** The core Askii.ai platform will require its own database (e.g., PostgreSQL) to securely store connection metadata and user consent tokens. This database is separate from any MO database.
*   **API Security:** All APIs between Askii.ai and the deployed MCP servers must be secured using industry-standard authentication and authorization mechanisms.

## Epic List

### Epic 1: MO Data MCP Server

*   **Goal:** Design and build the self-contained, distributable `MO Data MCP Server Package` that MOs can deploy within their own infrastructure. This includes creating the containerized application, implementing standardized MCP tools for exposing user data (personal profile, preferences, behavioral data, transaction history), and ensuring it's cloud-agnostic and production-ready.

### Epic 2: mPass Authentication and Consent

*   **Goal:** Integrate the existing mPass authentication and implement consent to enable connections to MO Data MCP servers and MCP-enabled mPass-integrated partner services. Deliver consent UI, secure token storage, and connection management (view/revoke).

### Epic 3: MO Data Retrieval

*   **Goal:** Integrate the MO Data MCP server package with Askii.ai to achieve complete end-to-end functionality. This includes connecting to deployed MO servers via mPass authentication and consent, implementing intelligent query detection, invoking appropriate MCP tools, and integrating retrieved MO data into contextual AI responses.

### Epic 4: MCP-Enabled mPass-Integrated Partner Service Integration

*   **Goal:** Extend the proven mPass authentication and MCP integration pattern to support third-party services that are MCP-enabled and already integrated with mPass. This delivers the second core capability of the MVP and completes the full framework scope.

## Epic 1: Distributable MO Data MCP Server

**Epic Goal:** Design and build the self-contained, distributable `MO Data MCP Server Package` that MOs can deploy within their own infrastructure. This includes creating the containerized application, implementing standardized MCP tools for exposing user data (personal profile, preferences, behavioral data, transaction history), and ensuring it's cloud-agnostic and production-ready.

### Story 1.1: Create Self-Contained MCP Server Package

As a **developer**,
I want **to build a containerized MCP server package that includes all dependencies**,
so that **MOs can deploy it without external requirements**.

#### Acceptance Criteria

1. Package runs in Docker with no external dependencies
2. Includes health check endpoint
3. Generates deployment logs

### Story 1.2: Implement MO Data Access Layer

As a **developer**,
I want **to create a secure data access interface within the MCP server**,
so that **member data can be retrieved safely**.

#### Acceptance Criteria

1. Data queries are authenticated
2. Responses are encrypted
3. Includes audit logging of all data access

### Story 1.3: Build MCP Tool Definitions for Member Data

As a **developer**,
I want **to define MCP tools for common member data queries**,
so that **Askii.ai can retrieve user personal profile, preferences, behavioral data, and transaction history**.

#### Acceptance Criteria

1. Tools return structured data for personal profile, preferences, behavioral data, and transaction history with proper error handling

### Story 1.4: Create MCP Server Installation Documentation

As an **MO technical team member**,
I want **step-by-step deployment instructions**,
so that **I can install the MCP server in our infrastructure**.

#### Acceptance Criteria

1. Documentation covers prerequisites, installation steps, configuration options, and troubleshooting

### Story 1.5: Implement Server Health Monitoring

As an **MO technical team member**,
I want **built-in monitoring endpoints**,
so that **I can verify the MCP server is running properly**.

#### Acceptance Criteria

1. Health check returns server status, connection status, and basic metrics via REST endpoint

## Epic 2: mPass Authentication and Consent

**Epic Goal:** Integrate the existing mPass authentication and implement consent to enable connections to MO Data MCP servers and mPass-integrated partner services. Includes consent UI, secure token storage, and connection management.

### Story 2.1: Integrate Existing mPass Authentication

As a **user**,
I want **to authenticate with mPass when connecting to my MO Data MCP server**,
so that **I can securely grant Askii.ai access to my MO data using my trusted mPass credentials**.

#### Acceptance Criteria

1. Integrate with existing mPass authentication API using the standard flow
2. Secure handling of authentication tokens and session management
3. Authentication flow redirects properly between Askii.ai and mPass
4. Error handling for failed authentication attempts with clear user messaging
5. Token refresh mechanism to maintain persistent authentication

### Story 2.2: MO Data Connection Consent UI

As a **user**,
I want **to see a clear consent screen that shows exactly what MO data access I'm granting**,
so that **I can make an informed decision about connecting my MO Data MCP server**.

#### Acceptance Criteria

1. Consent screen displays the requesting service name and requested permissions clearly
2. Granular permission list shows specific data types being accessed (e.g., transaction history, profile data)
3. Clear "Approve" and "Deny" buttons with no ambiguous actions
4. Consent screen follows WCAG AA accessibility standards
5. User can cancel the flow at any point and return to Askii.ai safely

### Story 2.3: Connection Token Storage and Management

As a **system**,
I want **to securely store and manage connection authorization tokens**,
so that **users don't need to re-authenticate for each data request and tokens are protected from unauthorized access**.

#### Acceptance Criteria

1. Authorization tokens are encrypted at rest using industry-standard encryption
2. Database schema supports multiple connections per user with proper indexing
3. Token expiration tracking with automatic cleanup of expired tokens
4. Secure token retrieval for MCP server requests with proper validation
5. Connection metadata stored (service name, granted permissions, connection date)

### Story 2.4: MCP Connection Management Dashboard

As a **user**,
I want **to view and manage all my connected MO MCP servers in one place**,
so that **I can see what's connected to Askii.ai and revoke access when needed**.

#### Acceptance Criteria

1. Dashboard shows all active connections with service names and connection dates
2. Each connection displays the permissions granted and last access time
3. One-click "Disconnect" action for any service with confirmation dialog
4. Connection status indicators (active, expired, error) with appropriate visual cues
5. Dashboard accessible from Askii.ai settings with proper navigation flow

### Story 2.5: Contextual MO Data Connection Prompts

As a **user**,
I want **to be prompted to connect my MO Data MCP server when Askii.ai needs my personal data**,
so that **I can grant access only when it's actually needed for my queries**.

#### Acceptance Criteria

1. Smart prompts appear when AI detects a query could benefit from external data
2. Prompt clearly explains why the connection would help answer the user's question
3. Prompt includes preview of what data would be accessed with the connection
4. User can dismiss prompts without connecting and continue with available data
5. Prompts are non-intrusive and don't disrupt the conversation flow

## Epic 3: MO Data Retrieval

**Epic Goal:** Integrate the MCP server package with Askii.ai and mPass authentication to achieve complete end-to-end functionality. This includes connecting to deployed MO servers, implementing intelligent query detection, invoking appropriate MCP tools, and integrating retrieved MO data into contextual AI responses.

### Story 3.1: Query Intelligence and MCP Tool Detection

As a **user**,
I want **Askii.ai to intelligently detect when my questions could benefit from my MO data**,
so that **I get personalized responses automatically, plus the ability to explicitly request my data when needed**.

#### Acceptance Criteria

1. Natural language processing identifies queries that could benefit from MO data (financial, personal, account-related)
2. Query classification determines which specific MCP tools would be most relevant
3. Confidence scoring prevents unnecessary data requests for ambiguous queries
4. User can explicitly request MO data with phrases like "check my account" or "use my data"
5. Clear user feedback when MO data could help but isn't connected yet

### Story 3.2: Secure MCP Tool Invocation with Error Handling

As a **system**,
I want **to reliably invoke MCP tools with comprehensive error handling**,
so that **users get consistent responses even when MO servers have issues**.

#### Acceptance Criteria

1. Tool invocation uses valid, non-expired authorization tokens with automatic refresh
2. User context (user ID, permissions) properly passed to MCP server for data scoping
3. Comprehensive error handling: server down, timeout, permission denied, invalid response
4. All tool invocations logged with user ID, timestamp, tool name, and success/failure status
5. Graceful degradation with informative user messages when MO data is unavailable

### Story 3.3: MO Data Integration into AI Responses

As a **user**,
I want **my MO data seamlessly integrated into Askii.ai's responses with clear attribution**,
so that **I get personalized, contextual answers while understanding what data was used**.

#### Acceptance Criteria

1. Retrieved MO data properly formatted and contextualized within AI responses
2. Data sources clearly attributed (e.g., "Based on your recent transactions from [MO name]...")
3. Responses maintain conversational flow while incorporating personal data insights
4. Sensitive data handled appropriately - no unnecessary exposure of private details
5. Fallback responses when MO data is unavailable, with explanation of limitations

## Epic 4: Partner Service Integration

**Epic Goal:** Extend the proven mPass authentication and MCP integration pattern to support third-party services that are MCP-enabled and already integrated with mPass. This delivers the second core capability of the MVP and completes the full framework scope.

### Story 4.1: Partner Authentication and Tool Integration

As a **user**,
I want **to connect to a partner service using the same mPass flow and access their tools seamlessly**,
so that **I have a consistent experience across all connected services**.

#### Acceptance Criteria

1. Partner service connections use identical mPass authentication flow as MO connections
2. Same consent UI pattern with partner-specific permission requests and branding
3. Partner service tools integrated into existing tool discovery and routing system
4. Unified connection management - partner services appear alongside MO connections in dashboard
5. Error handling and fallback mechanisms apply consistently to partner services

### Story 4.2: Basic Partner Data Usage in Responses

As a **user**,
I want **Askii.ai to use data from connected partner services in my responses**,
so that **I get enhanced answers that include information from my connected third-party services**.

#### Acceptance Criteria

1. Query intelligence detects when partner service tools could enhance responses
2. Partner service data properly integrated into AI responses with clear attribution
3. Responses indicate which partner service provided specific information
4. Graceful handling when partner services are unavailable
5. Consistent privacy and security standards applied to partner service data



## Checklist Results Report

### Executive Summary

- **Overall PRD Completeness**: 88% complete
- **MVP Scope Appropriateness**: Just Right - properly scoped for MVP delivery
- **Readiness for Architecture Phase**: Ready - PRD provides sufficient guidance for architectural design
- **Most Critical Gaps**: Missing some technical constraint details and integration specifics

### Category Analysis Table

| Category                         | Status  | Critical Issues |
| -------------------------------- | ------- | --------------- |
| 1. Problem Definition & Context  | PASS    | None - well articulated with clear business context |
| 2. MVP Scope Definition          | PASS    | Good separation of MVP vs post-MVP features |
| 3. User Experience Requirements  | PASS    | Clear UI/UX vision with accessibility considerations |
| 4. Functional Requirements       | PASS    | Well-structured FR/NFR with clear acceptance criteria |
| 5. Non-Functional Requirements   | PARTIAL | Missing some integration details and error handling specs |
| 6. Epic & Story Structure        | PASS    | Logical sequence, appropriate sizing, clear dependencies |
| 7. Technical Guidance            | PARTIAL | Good architecture direction but needs integration details |
| 8. Cross-Functional Requirements | PARTIAL | Data requirements clear, but operational details light |
| 9. Clarity & Communication       | PASS    | Well-organized, consistent terminology, good structure |

### Top Issues by Priority

**MEDIUM Priority:**
- Error handling patterns across all epics could be more comprehensive
- Performance monitoring and operational requirements need expansion

**LOW Priority:**
- Additional user research validation would strengthen the foundation
- More detailed data retention and privacy policies for production

### MVP Scope Assessment

- **Scope is appropriate**: The four-epic structure properly sequences from foundation to full capability
- **No essential features missing**: Both core capabilities (MO data and partner services) are covered
- **Complexity is manageable**: Each epic delivers incremental value and can be tested independently
- **Timeline is realistic**: With the refined scope, particularly the simplified Epic 4, the timeline appears achievable

### Technical Readiness

- **Architecture constraints are clear**: Federated model, containerization, cloud-agnostic requirements well defined
- **Identified technical risks**: MCP protocol maturity, MO deployment complexity, performance at scale
- **Areas for architect investigation**: MCP server package deployment patterns, mPass integration specifics

### Recommendations

1. **Add integration diagrams** showing the flow between Askii.ai, mPass, and MCP servers
2. **Expand error handling patterns** to be consistent across all epics
3. **Detail operational monitoring** requirements for production deployment
4. **Proceed to architecture phase** - the PRD provides sufficient foundation

### Final Decision

**✅ READY FOR ARCHITECT**: The PRD and epics are comprehensive, properly structured, and ready for architectural design.

## Next Steps

### UX Expert Prompt

Review the mPass Personal Data Framework PRD and create user experience designs focusing on the mPass authentication and consent flow, connection management dashboard, and contextual connection prompts within Askii.ai.

### Architect Prompt

Use this PRD to design the technical architecture for the mPass Personal Data Framework, focusing on the federated MCP server deployment model, mPass integration patterns, and secure data flow between Askii.ai and distributed MO/partner services.
