# Standards & API Reference

> Project: Construction Bidding Platform · Generated: 2026-05-07

---

## Industry Standards & Specifications

### ISO Standards

**ISO 16739-1:2024 — Industry Foundation Classes (IFC)**
- URL: https://www.iso.org/standard/70303.html
- Open, vendor-neutral data schema for sharing building information across construction software. A bidding platform that imports drawing sets should understand IFC-structured models to automate scope extraction and trade classification.

**ISO 19650-1:2018 — BIM Information Management (Concepts and Principles)**
- URL: https://www.iso.org/standard/68078.html
- Defines how building information (including project documents) should be structured, named, versioned, and distributed throughout a project lifecycle. Directly applicable to planroom document management, addenda versioning, and audit trail requirements in a bidding platform.

**ISO 19650-2 — BIM Information Management (Asset Delivery Phase)**
- URL: https://www.iso.org/standard/68081.html
- Covers the delivery phase — the period during which bids are solicited and contracts are awarded. Sets out requirements for a Common Data Environment (CDE) that a bidding platform effectively implements.

**ISO/IEC 27001:2022 — Information Security Management Systems**
- URL: https://www.iso.org/standard/27001
- The primary international standard for ISMS. Relevant for a bidding platform because it handles commercially sensitive bid data, financial statements, and proprietary drawing sets. ISO 27001 certification is often required when bidding for government and enterprise contracts, making it a trust signal for GC customers.

**ISO/IEC 27017:2015 — Cloud Security Controls**
- URL: https://www.iso.org/standard/43757.html
- Extends ISO 27001 with cloud-specific controls. Applicable when hosting planroom documents and bid data in cloud storage (S3, Azure Blob, GCS).

**ISO/IEC 27018:2019 — PII Protection in Public Clouds**
- URL: https://www.iso.org/standard/76559.html
- Relevant if the platform processes personal data of subcontractor representatives (names, emails, financial data). Required for GDPR alignment in European markets.

---

### W3C & IETF Standards

**W3C WCAG 2.2 — Web Content Accessibility Guidelines**
- URL: https://www.w3.org/TR/WCAG22/
- Level AA compliance is mandated for government-connected procurement platforms in many jurisdictions. Relevant because public works bidding portals (US federal, state, UK public sector) must be accessible. Applies to the web interface and any PDFs published through the platform.

**RFC 9110 — HTTP Semantics**
- URL: https://www.rfc-editor.org/rfc/rfc9110
- Foundational standard for REST API design. All REST endpoints in a construction bidding platform API should comply with HTTP semantics for status codes, caching, content negotiation, and method semantics.

**RFC 8288 — Web Linking**
- URL: https://www.rfc-editor.org/rfc/rfc8288
- Defines the `Link` header and relation types used in hypermedia APIs (HATEOAS). Recommended for API pagination and resource linking in bid, document, and invitation resources.

**RFC 6749 — OAuth 2.0 Authorization Framework**
- URL: https://www.rfc-editor.org/rfc/rfc6749
- The foundation for API authentication. All competing platforms (Procore, BuildingConnected, PlanHub) use OAuth 2.0 for developer integrations. A construction bidding platform API must implement OAuth 2.0 to be compatible with GC and sub systems.

**RFC 7519 — JSON Web Tokens (JWT)**
- URL: https://www.rfc-editor.org/rfc/rfc7519
- Standard for bearer tokens in OAuth 2.0 flows. Used by Autodesk Platform Services and Procore; should be adopted for the platform's own API token format.

**RFC 5321 — Simple Mail Transfer Protocol (SMTP)**
- URL: https://www.rfc-editor.org/rfc/rfc5321
- Core email delivery protocol. Bidding platforms are heavily email-driven (ITBs, addenda, Q&A responses). SMTP compliance with SPF, DKIM, and DMARC is critical for inbox deliverability of bid invitations.

**RFC 7807 — Problem Details for HTTP APIs**
- URL: https://www.rfc-editor.org/rfc/rfc7807
- Standard error response format for REST APIs. Should be adopted for the platform API to ensure consistent, machine-readable error responses.

---

### Data Model & API Specifications

**CSI MasterFormat (Construction Specifications Institute)**
- URL: https://www.csiresources.org/standards/overview
- The North American standard for organising construction specifications and bid packages into 50 numbered divisions. MasterFormat division numbers are the lingua franca for trade classification in every bidding platform. A construction bidding platform must use MasterFormat division codes for subcontractor trade tagging, bid package scoping, and reporting.

**UniFormat (CSI / ASTM E1557)**
- URL: https://www.csiresources.org/standards/overview
- Organises construction elements by building system (A=Substructure, B=Shell, etc.) rather than work result. Used in early design cost estimating. An AI-native platform could accept either UniFormat (early-stage bids) or MasterFormat (detailed bid packages) inputs.

**OmniClass Construction Classification System**
- URL: https://www.omniclass.org/
- Broader classification framework covering project types, work results, products, phases, and properties. Enables richer filtering and reporting in a bid management database (e.g., filter subs by project type experience).

**OpenAPI Specification 3.1**
- URL: https://spec.openapis.org/oas/v3.1.0
- The industry standard for documenting REST APIs. The platform's API should be specified in OpenAPI 3.1 to support auto-generated SDKs, Postman collections, and developer portal documentation — consistent with how Autodesk and Procore expose their APIs.

**JSON Schema (draft-07 / 2020-12)**
- URL: https://json-schema.org/
- Standard for validating API request/response payloads. Should be embedded in the OpenAPI spec to define bid package, bid invitation, proposal, and subcontractor data models.

**PDF/UA (ISO 14289-1)**
- URL: https://www.iso.org/standard/64599.html
- Accessibility standard for PDF documents. Construction drawings, specifications, and bid forms are distributed as PDFs. When the platform generates proposal PDFs or exports bid tabs, PDF/UA compliance ensures accessibility for screen reader users on government projects.

**IFC BCF (BIM Collaboration Format) — buildingSMART**
- URL: https://technical.buildingsmart.org/standards/bcf/
- Open XML/JSON format for communicating model issues and RFIs in BIM workflows. Future integration point: RFIs raised during bidding could be structured as BCF issues, enabling seamless handoff into model coordination tools.

---

### Security & Authentication Standards

**OAuth 2.0 (RFC 6749) with PKCE (RFC 7636)**
- URL: https://www.rfc-editor.org/rfc/rfc7636
- PKCE (Proof Key for Code Exchange) extends OAuth 2.0 for public clients (mobile apps, SPAs). Required for any browser-based or mobile subcontractor-facing bid access portal.

**OpenID Connect 1.0**
- URL: https://openid.net/specs/openid-connect-core-1_0.html
- Identity layer on top of OAuth 2.0. Provides standardised user identity tokens. Enables SSO compatibility with Autodesk, Procore, and enterprise identity providers (Okta, Azure AD) that GC firms use.

**OWASP Application Security Verification Standard (ASVS) Level 2**
- URL: https://owasp.org/www-project-application-security-verification-standard/
- Defines security requirements for web applications. Level 2 (Standard) is appropriate for a construction bidding platform handling commercially sensitive bid data and financial statements.

**OWASP API Security Top 10 (2023)**
- URL: https://owasp.org/www-project-api-security/
- Specific guidance for REST API security. Critical for a platform where API endpoints expose bid data, subcontractor financial information, and project documents.

**NIST SP 800-63B — Digital Identity Guidelines (Authentication)**
- URL: https://pages.nist.gov/800-63-3/sp800-63b.html
- US federal authentication standard. Relevant for any US government or public-sector construction bidding portal. Defines password policy, MFA requirements, and authenticator assurance levels.

**SOC 2 Type II (AICPA)**
- URL: https://www.aicpa-cima.com/resources/landing/soc-2-academy
- Enterprise GCs require SOC 2 Type II attestation from SaaS vendors before procurement approval. Not a standard per se but a compliance audit framework that maps directly to ISO 27001 controls.

---

### MCP Server Specifications

The Model Context Protocol (MCP) is applicable if the platform exposes an AI assistant layer or integrates with AI coding/project tools.

**Model Context Protocol (MCP) — Anthropic**
- URL: https://modelcontextprotocol.io/docs
- Standardised protocol for AI models to interact with external tools and data sources. Relevant if the platform provides an MCP server so that AI assistants (Claude, Copilot) can query bid packages, subcontractor databases, and proposal data on behalf of users — enabling natural-language bid management queries.

---

## Similar Products — Developer Documentation & APIs

### BuildingConnected / TradeTapp (Autodesk Platform Services)

- **Description:** Cloud-based bid management and subcontractor prequalification platform. API provides read/write access to bids, bid packages, contacts, and opportunity data.
- **API Documentation:** https://aps.autodesk.com/en/docs/buildingconnected/v2/developers_guide/overview/
- **SDKs/Libraries:** Postman collection — https://github.com/autodesk-platform-services/aps-buildingconnected.api-postman.collection; Python SDK: acc_sdk on PyPI
- **Developer Guide:** https://aps.autodesk.com/buildingconnected-cover-page
- **Standards:** REST/JSON, OpenAPI; hosted on Autodesk Platform Services (APS)
- **Authentication:** OAuth 2.0 (2-legged and 3-legged flows via APS Authentication API)

---

### Procore

- **Description:** Enterprise construction management platform with a comprehensive bid management module covering bid package creation, ITB distribution, bid levelling, and contract award.
- **API Documentation:** https://developers.procore.com/documentation/rest-api-overview
- **SDKs/Libraries:** No official SDK; community SDKs for Ruby and Python; Postman collection available through developer portal
- **Developer Guide:** https://developers.procore.com/documentation/introduction
- **Standards:** REST/JSON, REST v2 (released 2024), OpenAPI; Webhooks for event-driven integration
- **Authentication:** OAuth 2.0 (authorization code and client credentials flows); endpoints documented at https://developers.procore.com/documentation/oauth-endpoints

---

### PlanHub

- **Description:** Construction bidding and planroom platform with a large subcontractor network. API provides access to project leads data for CRM and ERP integration.
- **API Documentation:** https://planhub.com/api/
- **SDKs/Libraries:** Not publicly documented; integration positioned as data feed for CRM systems
- **Developer Guide:** Available on request; contact sales team
- **Standards:** REST/JSON; implementation takes 3–5 days per vendor documentation
- **Authentication:** API key (inferred from documentation; OAuth details not publicly disclosed)

---

### SmartBid / ConstructConnect

- **Description:** GC-focused bid management platform with subcontractor database, planroom, bid tabs, and project lead discovery. Open API available for integration partners.
- **API Documentation:** Not publicly accessible; available to integration partners on request via https://smartbid.co/construction-bid-software-integrations
- **SDKs/Libraries:** Not publicly documented
- **Developer Guide:** Contact ConstructConnect integration team
- **Standards:** REST/JSON (inferred); partner integrations with Procore and Autodesk BIM 360 confirm REST compatibility
- **Authentication:** OAuth 2.0 (inferred from Procore and Autodesk integration patterns)

---

### Autodesk Construction Cloud (ACC) — Core Platform

- **Description:** Broad construction management platform underpinning BuildingConnected, Docs, Build, and Cost Management. The ACC API is the foundation for document management and project data integration.
- **API Documentation:** https://aps.autodesk.com/en/docs/acc/v1/overview/
- **SDKs/Libraries:** Python SDK — https://pypi.org/project/acc_sdk/; JavaScript via APS Forge SDKs; https://github.com/realdanielbyrne/acc_sdk
- **Developer Guide:** https://aps.autodesk.com/developer/documentation
- **Standards:** REST/JSON, OpenAPI 3.0; GraphQL not used; Webhooks supported
- **Authentication:** OAuth 2.0 via APS Authentication API — https://aps.autodesk.com/en/docs/oauth/v2; 2-legged and 3-legged flows

---

### Sage Construction (Sage 300 CRE / Sage Estimating)

- **Description:** ERP and estimating platform widely used by GCs. Bidding platforms that integrate with Sage can import subcontractor and cost data from the GC's accounting system.
- **API Documentation:** https://developer.sage.com/construction/
- **SDKs/Libraries:** .NET SDK for Sage 300 CRE; REST APIs for Sage Intacct Construction
- **Developer Guide:** https://developer.sage.com/construction/docs/
- **Standards:** REST/JSON (Intacct); ODBC/COM connectors for legacy Sage 300 CRE
- **Authentication:** OAuth 2.0 (Intacct); session-based for legacy desktop products

---

### CMiC Construction Platform

- **Description:** Enterprise ERP for large GCs covering financials, project management, and HR. Integration point for subcontractor prequalification data (financial statements) flowing into a bidding platform's risk scoring.
- **API Documentation:** https://support.cmic.ca/hc/en-us/categories/developers (requires partner access)
- **SDKs/Libraries:** REST API; no public SDK
- **Developer Guide:** Available to certified integration partners
- **Standards:** REST/JSON, SOAP (legacy modules)
- **Authentication:** OAuth 2.0

---

### Dodge Construction Network (formerly Dodge Data & Analytics)

- **Description:** North American construction project intelligence database. Integration with a bidding platform's lead discovery module provides verified pre-bid project data including owner, architect, bidding date, and CSI divisions.
- **API Documentation:** https://www.construction.com/api (contact required)
- **SDKs/Libraries:** Not publicly documented
- **Developer Guide:** Partner programme; contact Dodge sales
- **Standards:** REST/JSON
- **Authentication:** API key

---

## Notes

- **No open standard for bid exchange exists.** Unlike fields such as insurance (ACORD) or healthcare (HL7/FHIR), construction bidding has no open, machine-readable format for transmitting bid invitations or proposals between systems. This is a significant interoperability gap and an opportunity for an open-source platform to define a de-facto standard.
- **CSI MasterFormat is the most important domain standard** for a construction bidding platform. It should drive the subcontractor trade taxonomy, bid package section structure, and all reporting dimensions.
- **ISO 19650 is growing in mandatory adoption.** UK, Australian, and Singapore governments mandate ISO 19650 compliance on public projects. A platform targeting international markets should align its CDE (planroom) and document naming conventions with ISO 19650.
- **Email deliverability is a de-facto operational standard.** SPF (RFC 7208), DKIM (RFC 6376), and DMARC (RFC 7489) configuration is not optional — several competitors (PreconSuite) explicitly market their email deliverability. Bidding platforms live or die by invitation emails reaching subcontractor inboxes.
- **MCP server opportunity.** No existing construction bidding platform has published an MCP server. An open-source platform that exposes MCP endpoints for bid package queries, subcontractor lookup, and proposal comparison could become the data layer for AI assistants used by estimators and preconstruction teams.
