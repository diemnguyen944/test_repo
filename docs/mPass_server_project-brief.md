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
We will build the **mPass Personal Data Framework**, a federated data ecosystem that allows Askii.ai to function as a hyper-personalized AI assistant. Instead of creating a centralized data vault, this framework enables Askii.ai to securely access a user's distributed personal data where it already lives (e.g., in their MO's systems, Gmail, etc.) via MCP (Model Context Protocol). Every data access request is authenticated and explicitly consented to in real-time by the user through their mPass, which is anchored in the trusted relationship they have with their Membership Organization (MO).

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

*   **Profile:** Tech-savvy professionals, managers, and knowledge workers who are existing members of a partner MO (e.g., a telco, airline, or professional association). They are early adopters of AI tools but are frustrated by the need to constantly provide context.
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

*   **Ecosystem Activation (Year 1):** Onboard at least 3 flagship Membership Organizations (MOs) and 5 strategic third-party data partners to the mPass Personal Data Framework.
*   **Drive Askii.ai Adoption (Year 1):** Achieve a 40% adoption rate of the hyper-personalization features among the active Askii.ai users from our partner MOs.
*   **Elevate MO Stickiness (Year 2):** Reduce member churn by 15% for partner MOs who actively promote the framework to their user base.
*   **Establish Strategic Moat (Year 2):** Position the mPass framework as the leading trusted, federated AI data solution, securing partnerships that competitors cannot easily replicate.

### **User Success Metrics**

*   **Rapid Time-to-Value:** 70% of new users connect at least one third-party data source within their first week of using the feature.
*   **Deep Integration:** The average active user has 3+ data sources connected (including their MO data) after 90 days.
*   **High-Quality Synthesis:** 80% of AI-generated responses that utilize federated data are rated as "highly useful" by users.
*   **Reduced Friction:** A 50% reduction in session length for complex, context-dependent queries, indicating users are getting to their answers faster.

### **Key Performance Indicators (KPIs)**

*   **Partner Adoption Rate:** Number of new MO and Third-Party partners joining the framework per quarter. (Target: 1 MO, 2 partners per quarter after launch).
*   **Federated Queries per User:** The average number of queries per week that successfully utilize data from at least two different sources (e.g., MO + Gmail). (Target: 5 federated queries/user/week).
*   **Consent Rate:** Percentage of users who approve a new data connection when prompted contextually by the AI. (Target: >60%).
*   **Ecosystem Health Score:** A composite metric tracking API uptime, data sync latency, and successful consent handshakes across the federated network. (Target: >99.9% uptime).

## MVP Scope

### **Core Features (Must Have)**

*   **MO Data MCP Server (Single Data Point):** A production-ready MCP server that exposes a single, high-value data point from the MO's database (e.g., Transaction History, as we brainstormed). This is the foundational trust anchor.
*   **mPass Consent Gateway:** The core service that handles the consent flow. It must be able to generate the consent UI, manage the secure handshake between Askii.ai, the MO, and the third-party service, and securely store consent tokens.
*   **Askii.ai Integration (Single Third-Party Service):** Askii.ai must be able to detect when a query requires data from the MO *and* one specific, high-value third-party service (e.g., Google Calendar). It must be able to trigger the mPass consent flow for this single service.
*   **End-to-End User Consent Flow:** The full, multi-screen user journey we storyboarded, from the contextual AI prompt to the final success confirmation, must be flawlessly implemented.
*   **Basic Consent Management Dashboard:** A simple interface within the mPass app or Askii.ai where a user can see which services they have connected and have a one-click option to "disconnect" or revoke access.

### **Out of Scope for MVP**

*   **Multiple Third-Party Integrations:** The MVP will focus on proving the model with just *one* strategic third-party partner (e.g., Google Calendar). Onboarding a second partner is a fast-follow, not part of the initial MVP.
*   **Advanced Data Synthesis:** The AI's ability to combine data will be functional but not highly advanced. It will answer direct queries that require two sources, but won't yet provide proactive, unsolicited insights.
*   **Granular, Sub-Service Permissions:** The initial consent will be at the service level (e.g., "access your calendar"). The ability to grant permission to only *some* calendars or *some* types of events will be a future enhancement.
*   **Complex Consent Auditing:** While the system will log consent, a detailed, user-facing audit trail of every data access request is not part of the MVP.
*   **MO-to-MO Data Portability:** The framework will not initially support transferring consent or data between different MOs.

### **MVP Success Criteria**

The MVP will be considered a success when we can successfully demonstrate a single user asking a single question in Askii.ai that triggers a consent request for their MO data and a third-party service, have the user grant that consent via the mPass flow, and receive a correct, synthesized answer, with the entire flow feeling secure and intuitive.

## Post-MVP Vision

### **Phase 2 Features (Fast Follows)**

*   **Expanded Partner Ecosystem:** Rapidly onboard the next 5-10 strategic third-party data partners, focusing on high-value domains like email, project management, and health. Develop a partner SDK and documentation to simplify and accelerate the integration process.
*   **Granular Permission Controls:** Move beyond service-level consent to allow users to grant permissions for specific subsets of their data (e.g., only the "Work" calendar, only emails from a specific domain, only "read-only" access).
*   **Proactive AI Insights:** Enhance the AI to not only answer direct questions but to proactively identify and surface insights by synthesizing data from multiple connected sources (e.g., "Your upcoming flight booking conflicts with a meeting on your work calendar").
*   **User-Facing Consent Dashboard:** Build out the full consent management dashboard in the mPass app, including a detailed, user-friendly audit trail of all data access requests and approvals.

### **Long-term Vision**

The long-term vision is to establish the mPass Personal Data Framework as the de facto industry standard for trusted, user-centric AI data access. The framework will evolve into a dynamic, intelligent ecosystem where:
*   **AI becomes a true agent:** Askii.ai will move from a passive assistant to a proactive agent, capable of performing multi-step tasks across different services on the user's behalf (e.g., "Find a flight that works for my meeting next week, check it against my budget, and then book it.").
*   **The Ecosystem becomes a Marketplace:** Third-party services will compete to offer unique data and tools through the framework, creating a vibrant marketplace of AI-ready capabilities for users to choose from.
*   **mPass becomes the User's Digital Steward:** The mPass will evolve beyond a simple credential into the central control panel for a user's entire digital identity and AI-accessible memory, solidifying the MO's role as the most trusted entity in their members' digital lives.

### **Expansion Opportunities**

*   **Enterprise & B2B:** Adapt the framework for enterprise use cases, allowing employees to securely connect their corporate accounts (e.g., Salesforce, Jira, Teams) to a company-managed Askii.ai instance.
*   **New Verticals:** Expand into highly regulated industries like healthcare and finance by building specialized, compliant versions of the consent and data access framework.
*   **White-Labeling:** License the mPass consent framework to other large organizations who want to build their own trusted AI ecosystems for their customers or members.

## Technical Considerations

### **Platform Requirements**

*   **Target Platforms:** The framework itself is a backend system of services and APIs. The primary user-facing components (consent flow, management dashboard) must be available within Askii.ai's web platform and the mPass mobile app.
*   **Performance Requirements:** Consent flows must be highly responsive, completing in under 3 seconds (excluding user sign-in time with third parties). Federated data queries for the AI should have a target latency of under 2 seconds to feel seamless in conversation.

### **Technology Preferences**

*   **Backend:** A microservices architecture is preferred, likely using Node.js/TypeScript or Go for high-performance services like the mPass Consent Gateway. Services should be containerized with Docker.
*   **Database:** A combination of databases may be needed. A relational database (like PostgreSQL) for storing consent records and audit trails, and a key-value store (like Redis) for caching session tokens.
*   **Hosting/Infrastructure:** The framework should be designed to be cloud-native, with a preference for AWS or a similar major cloud provider to ensure scalability and reliability.

### **Architecture Considerations**

*   **Service Architecture:** A decoupled, microservices-based architecture is critical. Key services would include: 1) MO Data MCP Server, 2) mPass Consent Gateway, 3) Partner Integration Service, 4) Consent Audit Service.
*   **Integration Requirements:** The system will require robust, secure APIs for interaction between Askii.ai, the mPass Consent Gateway, MOs' internal systems, and third-party MCP servers. All APIs must be authenticated.
*   **Security/Compliance:** Security is paramount. All data in transit must be encrypted with TLS. All sensitive data at rest (like consent tokens) must be encrypted. The system must be designed for GDPR and CCPA compliance from day one, with a clear data processing agreement for partners.

## Constraints & Assumptions

### **Constraints**

*   **Timeline:** A functional, end-to-end MVP must be ready for a pilot with at least one MO and one third-party partner within 9 months.
*   **Resources:** The core framework development will be handled by a dedicated team of 5-7 engineers (backend, security, and integration specialists). This does not include the resources needed from partner MOs or third parties.
*   **MO Technical Readiness:** We are constrained by the technical capabilities of our initial MO partners. The MVP design must be flexible enough to accommodate MOs with varying levels of API maturity.
*   **Protocol Dependency:** The framework is fundamentally dependent on the MCP standard. Any limitations or immaturities in the protocol itself will be constraints on our system.

### **Key Assumptions**

*   **MOs are Willing Partners:** We assume that MOs will see the strategic value in becoming "digital stewards" and will be willing to invest the necessary technical resources to integrate with the framework.
*   **Third Parties Will Adopt MCP:** We assume that with the right incentives (access to a large, engaged user base), third-party services will see a positive ROI in building an MCP server and integrating with our mPass consent flow.
*   **Users Will Trust the MO Anchor:** We assume that the user's trust in their MO is transferable and will be sufficient to overcome their hesitation in connecting multiple, sensitive data sources to an AI.
*   **Performance is Solvable:** We assume that the potential latency issues of a federated system can be acceptably mitigated through smart caching, asynchronous processing, and a robust infrastructure.
*   **The "Amnesiac AI" is a High-Value Problem:** We assume that the problem of contextless AI is significant enough that users will go through a multi-step consent process to solve it.

## Risks & Open Questions

### **Key Risks**

*   **Ecosystem Adoption Risk (High):** The entire model hinges on convincing both MOs and third-party services to adopt MCP and integrate with our framework. If they perceive the cost/effort to be too high or the ROI to be too low, the ecosystem will fail to launch.
*   **Technical Complexity Risk (High):** Building a secure, reliable, and low-latency federated consent and data access system is extremely complex. Any security flaw in the consent gateway could have catastrophic consequences for user trust and the brand.
*   **Poor User Experience Risk (Medium):** If the consent flow is confusing, intrusive, or creates too much friction, users will simply not adopt it, regardless of the potential benefits. "Consent fatigue" is a major UX challenge to overcome.
*   **Competitive Risk (Medium):** A major platform player (like Google, Apple, or a large identity provider like Okta) could launch a competing, proprietary AI memory framework, potentially leveraging their existing ecosystem to accelerate adoption and block us out.

### **Open Questions**

*   **Partner Incentives:** What is the precise, quantifiable business case for a third-party service to join our ecosystem? What is the revenue share or value proposition we will offer them?
*   **MO Onboarding:** What is the technical and business "playbook" for onboarding a new MO? What level of technical support will we need to provide them?
*   **Data Governance & Liability:** In a federated model, who is ultimately liable for a data breach or misuse? How will data governance policies be enforced across dozens of independent partners?
*   **User Support Model:** When a user's data sync fails, who do they contact for support? Askii.ai, their MO, or the third-party service? A clear support model is needed.

### **Areas Needing Further Research**

*   **MCP Protocol Maturity Assessment:** A deep technical dive into the current state of the MCP standard, its production-readiness, and the availability of developer tools.
*   **Market Survey of Potential Partners:** Formal research to gauge the interest and perceived barriers to entry for both MOs and key third-party services (e.g., SaaS companies).
*   **Legal and Compliance Framework:** A thorough legal review to develop a standardized data processing agreement and define the liability and governance model for all ecosystem partners.
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
