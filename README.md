# Construction Bidding Platform

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An open-source, AI-native preconstruction platform that centralises bid management, subcontractor outreach, and proposal assembly -- replacing fragmented email-and-spreadsheet workflows that still dominate the construction industry.

Construction bidding is one of the highest-risk phases in any building project. General contractors must distribute large drawing sets, track subcontractor responses, manage addenda, and compile competitive proposals -- all under tight deadlines and across dozens of trades. This platform gives GCs and subcontractors a single, open system for the entire bid lifecycle, from invitation to award, with AI capabilities that no incumbent offers end-to-end.

---

## Why Construction Bidding Platform?

- **No open-source alternative exists.** All ten major products surveyed (BuildingConnected, Procore Bid Management, PlanHub, SmartBid, ConstructConnect, Downtobid, BidTracer, PreconSuite, Bid Board Pro, TradeTapp) are proprietary SaaS with no self-hosted or open-source option available.
- **Incumbent pricing excludes small and mid-size contractors.** Well-featured platforms start at $5,000--$25,000/year (SmartBid, BuildingConnected). ConstructConnect charges $1,000+/month. Even PlanHub's sub-side plans run $2,000--$4,400/year. SMB contractors are priced out of serious bid management tooling.
- **AI capabilities are fragmented across products.** Downtobid offers AI scope extraction but lacks bid levelling and planrooms. TradeTapp has AI financial document parsing but no bid workflow. BuildingConnected has a recommendation engine that cannot parse drawings. No single product covers AI scope analysis, AI-assisted invitations, and AI bid levelling in one workflow.
- **Subcontractors are underserved.** Subs receive bid invitations across BuildingConnected, SmartBid, Procore, and PlanHub simultaneously with no unified view, no AI prioritisation, and no fit scoring to help them decide which opportunities to pursue.
- **Vendor lock-in constrains data portability.** Winning bids, subcontractor relationships, and historical performance data are trapped inside proprietary platforms with limited export capabilities, despite the availability of open standards like CSI MasterFormat and IFC.

---

## Key Features

### Bid Package Management
- Create and version bid packages with drawings, specifications, and scope documents
- Distribute addenda with read-confirmation tracking and full audit trail
- Secure planroom with permissioned, version-controlled document access per invited party
- Centralised RFI/Q&A threads per bid package with simultaneous distribution to all bidders

### Subcontractor Outreach & Network
- Searchable subcontractor database with trade classification, geography, and prequalification status filtering
- Email-based invitation-to-bid workflow with bid/no-bid response capture -- no mandatory sub registration required
- DBE/MBE/WBE classification tags for public-project compliance filtering
- AI-powered subcontractor fit-scoring and recommendation engine

### Bid Levelling & Proposal Assembly
- Side-by-side bid comparison with scope gap identification and normalisation
- AI-assisted bid levelling with automated outlier and gap detection
- Tools for assembling the overall GC proposal from sub-bids
- Conversion of winning bids into subcontracts with budget auto-update

### AI Scope Analysis
- Automatic scope-of-work extraction from uploaded drawings and specifications
- AI-generated bid invitation content personalised per trade
- Addenda impact analysis -- flag which scope items and cost estimates are affected by drawing changes
- Contract risk extraction to identify onerous payment terms, liquidated damages, and warranty clauses

### Analytics & Intelligence
- Pipeline dashboards with bid success rates by trade and geography
- Subcontractor response rate tracking and performance analytics
- Predictive win-probability scoring per opportunity
- ITB prioritisation for subcontractors based on project fit, margin opportunity, and crew availability

---

## AI-Native Advantage

Unlike incumbents that bolt on isolated AI features, this platform is designed from the ground up with AI at the core of the bid workflow. AI scope extraction turns uploaded plans and specs into structured scopes of work automatically, eliminating hours of manual takeoff. Subcontractor fit-scoring ranks potential bidders by trade match, proximity, response history, and financial health -- replacing the gut-feel bidder lists that GCs maintain in spreadsheets. AI-assisted bid levelling normalises proposals across dozens of subcontractors, flagging scope gaps and cost outliers that human reviewers routinely miss under deadline pressure.

---

## Tech Stack & Deployment

The platform targets self-hosted, cloud, and hybrid deployment models. It will build on established open standards: CSI MasterFormat for trade classification, IFC for BIM interoperability, OAuth 2.0 for authentication, and PDF/UA for accessible document handling. A REST API with OpenAPI specification and webhook support will enable integration with downstream project management platforms such as Procore, Autodesk Construction Cloud, and CMiC. Large file handling for drawing sets (often hundreds of MB per project) and email-based invitation flows for subcontractors who will not adopt a portal are first-class design considerations.

---

## Market Context

The construction technology market continues to grow, with preconstruction and bid management representing a critical workflow layer between project discovery and contract execution. Incumbent pricing ranges from $150/month (Downtobid Starter) to $25,000+/year (SmartBid enterprise), with enterprise platforms like Procore available only via custom quotes. Primary buyers are general contractors managing commercial and public construction projects, with subcontractors and suppliers as essential network participants who benefit from free-tier access models.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
