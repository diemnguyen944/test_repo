# Project Brief: mPass Personal Data Framework

## Executive Summary

The mPass Personal Data Framework aims to solve the "Amnesiac AI" problem by transforming Askii.ai from a generic assistant into a hyper-personalized digital companion. The core of the project is to create a federated ecosystem where Askii.ai can securely access a user's fragmented personal data (from their Membership Organization and third-party services like Gmail) with their explicit, real-time consent. This is anchored by the trusted relationship the user has with their MO, using the mPass as the universal key for authentication and consent management. The primary value proposition is to enable a deeply contextual AI that understands the user's entire digital life, moving beyond simple queries to provide synthesized, proactive insights, all while keeping the user in full control of their data.

## Problem Statement

**Current State and Pain Points:**
Askii.ai, despite its powerful LLM capabilities, currently operates with a significant handicap: it has no memory. Users engage in "contextless first dates" with the AI, forced to manually provide relevant personal information for every new query. A user's valuable context—their preferences, history, relationships, and goals—is fragmented and siloed across dozens of services like their MO's database, their email, work applications, and health platforms. This fragmentation creates immense friction and prevents the AI from achieving true, deep personalization.

**Impact of the Problem:**
- **Generic, Low-Value Responses:** AI answers are often superficial because they lack the specific context that would make them truly insightful.
- **Repetitive User Effort:** Users waste time and effort repeatedly feeding the same background information to the AI for different tasks.
- **Lack of Trust in Centralized "Vaults":** Users are justifiably wary of standalone "memory vault" services that require them to upload their entire digital life to a new, unproven entity, creating concerns over data ownership, security, and vendor lock-in.

**Why Existing Solutions Fall Short:**
Current solutions are inadequate. Standalone AI tools lack access to a user's distributed data, while data aggregation platforms often become proprietary silos that users don't trust. No solution has effectively leveraged an existing, trusted relationship (like the one between a user and their MO) to create a secure, user-centric bridge to their fragmented digital self.

**Urgency and Importance:**
As AI becomes more integrated into daily life, the demand for hyper-personalization will become a standard expectation. The platform that solves the "Amnesiac AI" problem in a trustworthy, user-controlled way will build an incredibly deep, defensible moat. Solving this now is critical to elevating Askii.ai from a smart tool to an indispensable digital companion and positioning the Moneta ecosystem at the forefront of the new AI era.

## Proposed Solution

**Core Concept and Approach:**
We will build the **mPass Personal Data Framework**, a federated data ecosystem that allows Askii.ai to function as a hyper-personalized AI assistant. Instead of creating a centralized data vault, this framework enables Askii.ai to securely access a user's distributed personal data where it already lives (e.g., in their MO's systems) via MCP (Model Context Protocol). Users authenticate and provide explicit consent through their mPass when connecting to each MCP server, establishing an ongoing trusted connection anchored in their relationship with their Membership Organization (MO).

**Key Differentiators from Existing Solutions:**
- **Leverages Existing Trust:** The framework is built on the pre-existing, trusted relationship between the user and their MO, overcoming the major trust hurdle faced by new, standalone "memory vault" services.
- **Federated, Not Centralized:** Data remains with its original, trusted source. We facilitate secure access; we don't ingest and store the data ourselves, which is a major privacy and security advantage.
- **User Control at the Core:** The mPass provides a single, unified interface for users to grant, manage, and revoke granular consent for all connected data sources, ensuring true user agency.
- **Open Standards-Based:** By utilizing MCP, we create a scalable and open ecosystem that any third-party service can potentially join, rather than a proprietary, closed system.

**Why This Solution Will Succeed:**
This approach succeeds because it solves the AI memory problem without asking users to compromise on trust or control. It leverages existing relationships (user-MO), existing infrastructure (mPass), and open standards (MCP) to create a uniquely defensible ecosystem. By making the MO the "trusted digital steward," we align with user desires for data ownership and create a powerful incentive for both users and third-party services to participate.

**High-level Vision:**
The mPass Personal Data Framework will power an Askii.ai that truly knows and serves the user, acting as an indispensable digital companion that can synthesize information from across their entire digital life. This will elevate the role of the MO in the AI era and position the Moneta ecosystem as the leader in trustworthy, personalized AI.

## Target Users

### **Primary User Segment: The "Delegator" Professional**

*   **Profile:** Tech-savvy professionals, managers, and knowledge workers who are existing members of a partner MO (e.g., a telco, airline, or professional association,...). They are early adopters of AI tools but are frustrated by the need to constantly provide context.
*   **Behaviors:** They live in their email and calendars, manage complex projects, and interact with multiple SaaS tools daily. They value efficiency and are willing to adopt new technology if it saves them significant time and mental energy.
*   **Needs & Pains:**
    *   They need an AI that "just knows" the context of their work and personal life without constant re-explanation.
    *   They are frustrated by having to copy-paste information between their tools and the AI.
    *   They desire a "set it and forget it" system they can trust, rather than having to manage dozens of individual integrations.
*   **Goals:** To delegate more complex, context-dependent tasks to their AI assistant; to reduce the friction of using AI; to get proactive insights based on a holistic view of their data.

### **Secondary User Segment: The "Steward" Membership Organization (MO)**

*   **Profile:** Forward-thinking Membership Organizations (telcos, airlines, financial institutions, professional associations) who are looking for new ways to provide value and deepen their relationship with their members.
*   **Behaviors:** They are experienced custodians of sensitive member data and are focused on maintaining member trust and loyalty. They are actively exploring how to leverage AI to enhance their member services.
*   **Needs & Pains:**
    *   They need to stay relevant in the AI era and avoid being disintermediated by large tech platforms.
    *   They are looking for a secure, low-risk way to enable AI-driven personalization for their members without having to build a massive, complex AI infrastructure themselves.
    *   They are concerned about the reputational risk of data breaches or misuse of member data.
*   **Goals:** To elevate their role from a simple service provider to a "trusted digital steward" for their members; to increase member engagement and loyalty; to create a powerful, defensible differentiator against competitors.

## Goals & Success Metrics

### **Business Objectives**

*   **Ecosystem Activation:** Onboard at least 3 flagship Membership Organizations (MOs) and 5 strategic third-party data partners to the mPass Personal Data Framework.
*   **Drive Askii.ai Adoption:** Achieve a 40% adoption rate of the hyper-personalization features among the active Askii.ai users from our partner MOs.
*   **Elevate MO Stickiness:** Reduce member churn by 15% for partner MOs who actively promote the framework to their user base.
*   **Establish Strategic Moat:** Position the mPass framework as the leading trusted, federated AI data solution, securing partnerships that competitors cannot easily replicate.

### **User Success Metrics**

*   **Rapid Time-to-Value:** 70% of new users connect at least one third-party data source within their first week of using the feature.
*   **Deep Integration:** The average active user has 3+ data sources connected (including their MO data) after 90 days.
*   **High-Quality Synthesis:** 80% of AI-generated responses that utilize federated data are rated as "highly useful" by users.
*   **Reduced Friction:** A 50% reduction in session length for complex, context-dependent queries, indicating users are getting to their answers faster.

### **Key Performance Indicators (KPIs)**

*   **Partner Adoption Rate:** Number of new MO and Third-Party partners joining the framework per quarter. (Target: 1 MO, 2 partners per quarter after launch).
*   **Federated Queries per User:** The average number of queries per week that successfully utilize data from at least two different sources (e.g., MO). (Target: 5 federated queries/user/week).
*   **Consent Rate:** Percentage of users who approve a new data connection when prompted contextually by the AI. (Target: >60%).
*   **Ecosystem Health Score:** A composite metric tracking API uptime, data sync latency, and successful consent handshakes across the federated network. (Target: >99.9% uptime).

## MVP Scope

For the MVP, we will deliver two core user-facing capabilities, built on a common technical foundation.

### Capability 1: Accessing Membership Organization (MO) Data

This capability allows Askii.ai to securely access a user's data from their MO.

*   **MO Data MCP Server:** We will produce a self-contained **MO Data MCP Server Package** for MOs to deploy within their own infrastructure. This ensures MOs retain full data control and compliance, while Moneta's role is strictly limited to package development and maintenance, with no access to member data.
*   **MO Data MCP Server Connection via mPass:** To enable data access, the user performs a connection to their MO's MCP server. This follows the flow: the user authenticates with mPass and then approves a consent screen detailing the permissions requested.
*   **Intelligent Data Retrieval:** Once the connection is established, Askii.ai will intelligently detect when a user's query requires MO data (e.g., transaction history, member status) and will make the appropriate MCP tool calls to retrieve it.

### Capability 2: Connecting to mPass-Integrated Partner Services

This capability allows Askii.ai to securely access data and resources from third-party services that are MCP-enabled and have integrated with mPass.

*   **MCP-Enabled Partner Services:** To be supported, third-party services must expose their data and functions via an MCP server and use mPass for authentication.
*   **Partner Service Connection via mPass:** Users connect these services using the same trusted mPass flow: authenticating with their mPass and approving a consent screen that details the requested permissions.
*   **Utilizing Partner Services:** Once connected, Askii.ai can invoke the partner's specific MCP tools, allowing it to access their unique data and resources to provide richer, more comprehensive answers.

### **Out of Scope for MVP**

*   **Expansive mPass Consent Gateway:** A standalone, central gateway for all third-party services is explicitly out of scope. Consent is handled within the MO Data MCP server flow, and authentication for other services leverages existing MCP server capabilities.
*   **Advanced Data Synthesis:** The AI's ability to combine data will be functional but not highly advanced. It will answer direct queries that require data, but won't yet provide proactive, unsolicited insights.
*   **Granular, Sub-Service Permissions:** The initial consent will be at the service level. Granular permissions are a future enhancement.
*   **Complex Consent Auditing:** While the system will log consent, a detailed, user-facing audit trail of every data access request is not part of the MVP.
*   **MO-to-MO Data Portability:** The framework will not initially support transferring consent or data between different MOs.

### **MVP Success Criteria**

The MVP will be considered a success when we can clearly demonstrate the successful, end-to-end operation of both core capabilities:

1.  **Successful MO Data Retrieval:** A user can ask a question in Askii.ai that requires data from their MO. This action should correctly trigger the one-time mPass connection flow (authenticate and consent), and result in Askii.ai providing a correct, contextual answer powered by the retrieved MO data.
2.  **Successful Partner Service Connection:** A user can successfully connect a third-party, mPass-integrated service to Askii.ai. This must use the same mPass authentication and consent flow, resulting in a successfully established connection that the user can manage.

Both user flows must feel secure, intuitive, and seamless.

## Post-MVP Vision

### **Phase 2 Features (Fast Follows)**

*   **Expanded Partner Ecosystem:** With the core framework validated, rapidly onboard the next 5-10 strategic third-party partners. Develop a **Partner SDK and Onboarding Guide** to help new services build their own MCP servers and integrate with the mPass framework, accelerating ecosystem growth.
*   **Granular Permission Controls:** Move beyond service-level consent to allow users to grant permissions for specific subsets of their data (e.g., only the "Work" calendar, only emails from a specific domain, only "read-only" access).
*   **Proactive AI Insights:** Enhance the AI to not only answer direct questions but to proactively identify and surface insights by synthesizing data from multiple connected sources (e.g., "Your upcoming flight booking conflicts with a meeting on your work calendar").
*   **User-Facing Consent Dashboard:** Build out the full consent management dashboard in the mPass app, including a detailed, user-friendly audit trail of all data access requests and approvals.

### **Long-term Vision**

The long-term vision is to establish the mPass Personal Data Framework as the de facto industry standard for trusted, user-centric AI data access. The framework will evolve into a dynamic, intelligent ecosystem where:
*   **AI becomes a true agent:** Askii.ai will move from a passive assistant to a proactive agent, capable of performing multi-step tasks across different services on the user's behalf (e.g., "Find a flight that works for my meeting next week, check it against my budget, and then book it.").
*   **The Ecosystem becomes a Marketplace:** Third-party services will compete to offer unique data and tools through the framework, creating a vibrant marketplace of AI-ready capabilities for users to choose from.
*   **mPass becomes the User's Digital Steward:** The mPass will evolve beyond a simple credential into the central control panel for a user's entire digital identity and AI-accessible memory, solidifying the MO's role as the most trusted entity in their members' digital lives.



## Technical Considerations

### **Platform Requirements**

*   **Target Platforms:** The framework itself is a backend system of services and APIs. The primary user-facing components (consent flow, management dashboard) must be available within Askii.ai's web platform and the mPass mobile app.
*   **Performance Requirements:** Consent flows must be highly responsive, completing in under 3 seconds (excluding user sign-in time with third parties). Federated data queries for the AI should have a target latency of under 2 seconds to feel seamless in conversation.

### **Technology Preferences**

*   **Backend:** The **MO Data MCP Server Package** should be a self-contained, distributable application with a minimal, clearly defined set of external dependencies.
*   **Database:** Askii.ai will require a database to securely store connection metadata and user consent tokens.
*   **Hosting/Infrastructure:** The MO Data MCP Server Package must be designed to be cloud-agnostic, capable of running in any standard containerized environment.

### **Architecture Considerations**

*   **Service Architecture:** The architecture consists of two main parts: 1) The **distributable MO Data MCP Server Package**, and 2) **Askii.ai's internal services** for managing connections, invoking MCP tools, and handling the user-facing experience. The consent flow is an integrated component of the connection process orchestrated by Askii.ai and the mPass service.
*   **Integration Requirements:** The system will require robust, secure APIs for interaction between Askii.ai, the mPass authentication service, and the various deployed MCP servers (both MO and partner).
*   **Security/Compliance:** Security is paramount. All data in transit must be encrypted with TLS. All sensitive data at rest (like connection tokens) must be encrypted. The MO Data MCP Server package must be built to the highest security standards, but the ultimate compliance of the deployed environment (GDPR, CCPA, etc.) is the responsibility of the MO.

## Constraints & Assumptions

### **Constraints**

*   **Timeline:** A functional, end-to-end MVP must be ready for a pilot by November 2025.
*   **Resources:** The core framework and package development will be handled by a dedicated team of 3 engineers. This does not include the resources needed from partner MOs for deployment and testing.
*   **MO Technical Readiness:** We are constrained by the ability of our initial MO partners to deploy and operate containerized applications within their infrastructure. The package design must be as simple and dependency-free as possible.
*   **Protocol Dependency:** The framework is fundamentally dependent on the MCP standard. Any limitations or immaturities in the protocol itself will be constraints on our system.

### **Key Assumptions**

*   **MOs Can Deploy Our Package:** We assume that MOs will see the strategic value in becoming "digital stewards" and will have the technical capability to deploy and maintain our standardized MCP server package.
*   **Existing Partners for MVP:** We assume that we can launch the MVP with at least one strategic third-party service that is already MCP-enabled and integrated with mPass. The assumption of convincing new partners to adopt MCP is for the post-MVP phase.
*   **Users Will Trust the MO Anchor:** We assume that the user's trust in their MO is transferable and will be sufficient to overcome their hesitation in connecting multiple, sensitive data sources to an AI.
*   **Performance is Solvable:** We assume that the potential latency issues of a federated system can be acceptably mitigated through smart caching, asynchronous processing, and a robust infrastructure.
*   **The "Amnesiac AI" is a High-Value Problem:** We assume that the problem of contextless AI is significant enough that users will go through a multi-step consent process to solve it.

## Risks & Open Questions

### **Key Risks**

*   **Deployment & Operations Risk (High):** The success of the model hinges on MOs being able to successfully deploy, configure, and maintain the MCP server package. A complex installation process, unclear documentation, or high operational overhead could prevent adoption.
*   **Technical Complexity Risk (High):** Building a secure, reliable, and easy-to-maintain distributable package that can run in diverse environments is extremely complex. A security flaw in the package could have catastrophic consequences, as it would be deployed across multiple independent infrastructures.
*   **Poor User Experience Risk (Medium):** If the connection and consent flow is confusing, intrusive, or creates too much friction, users will simply not adopt it, regardless of the potential benefits. "Consent fatigue" is a major UX challenge to overcome.
*   **Competitive Risk (Medium)**:A major platform player could launch a competing, proprietary AI memory framework, potentially leveraging their existing ecosystem to accelerate adoption and block us out.

### **Open Questions**

*   **Partner Incentives:** Post-MVP, what is the precise business case for a new third-party service to build an MCP server and integrate with our ecosystem?
*   **MO Onboarding Playbook:** What is the detailed technical and business "playbook" for onboarding a new MO? This must include deployment guides, security best practices, and the support model for the packaged server.
*   **Data Governance & Liability:** In a federated model, who is ultimately liable for a data breach or misuse—Moneta as the package developer, or the MO as the host and operator? How will data governance policies be enforced?
*   **User Support Model:** When a user's data sync fails, who do they contact for support? A clear, tiered support model involving Askii.ai, the MO, and the third-party service is needed.

### **Areas Needing Further Research**

*   **MCP Protocol Maturity Assessment:** A deep technical dive into the current state of the MCP standard, its production-readiness, and the availability of developer tools.
*   **MO Deployment Infrastructure Survey:** Formal research to understand the typical containerization and deployment infrastructure available at our target MOs to ensure our package is compatible.
*   **Legal and Compliance Framework:** A thorough legal review to develop a standardized **Software Distribution and Data Processing Agreement** that clearly defines the liability and governance model for MOs deploying the package.
*   **User Trust and Consent UX Study:** Formal user research and usability testing focused on the consent flow to ensure it is clear, trustworthy, and minimizes friction.

## Next Steps

### **Immediate Actions**

1.  **Constitute the Core Framework Team:** Formally assign the dedicated 5-7 person team to begin the deep research and prototyping phase.
2.  **Initiate Partner Outreach:** Begin exploratory conversations with 3-5 high-potential MOs and 5-10 strategic third-party services to validate our core assumptions and gauge interest, using this Project Brief as the primary discussion document.
3.  **Launch Technical Research Sprints:** Immediately kick off the "Areas Needing Further Research" identified in the previous section, with a 4-6 week timeline to deliver initial findings on:
    *   MCP Protocol Maturity
    *   Legal and Compliance Framework
    *   User Consent UX Prototypes
4.  **Develop a Partner Pitch Deck:** Create a compelling presentation for potential MO and third-party partners that clearly articulates the value proposition, incentives, and technical requirements for joining the ecosystem.
5.  **Create a High-Level Technical Roadmap:** Based on the MVP scope, develop a more detailed technical roadmap and initial backlog for the first 3 months of development.
6.  **Schedule a Formal Kick-off:** Plan a formal project kick-off meeting with all key stakeholders (including initial interested partners) in 6-8 weeks to present the research findings and the finalized roadmap.

### **PM Handoff**

This Project Brief provides the full context for the **mPass Personal Data Framework**. Please start in 'PRD Generation Mode', review the brief thoroughly to work with the user to create the PRD section by section as the template indicates, asking for any necessary clarification or suggesting improvements.
