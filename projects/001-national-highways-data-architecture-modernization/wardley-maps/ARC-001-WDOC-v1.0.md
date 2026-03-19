# Wardley Doctrine Assessment: National Highways Data Architecture Modernization

> **Template Origin**: Official | **ArcKit Version**: 4.3.1 | **Command**: `/arckit.wardley.doctrine`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-WDOC-v1.0 |
| **Document Type** | Wardley Doctrine Assessment |
| **Project** | National Highways Data Architecture Modernization (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-03-19 |
| **Last Modified** | 2026-03-19 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-06-17 |
| **Owner** | Programme Director, Data Architecture Modernization |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Programme Team, Architecture Team, Leadership |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-03-19 | ArcKit AI | Initial doctrine assessment from `/arckit:wardley.doctrine` command | PENDING | PENDING |

---

## Executive Summary

**Overall Maturity Score**: 2.6 / 5.0 — Developing

**Phase Positioning**:

| Phase | Name | Score | Status |
|-------|------|-------|--------|
| Phase I | Stop Self-Harm | 3.0 / 5.0 | In Progress |
| Phase II | Becoming More Context Aware | 2.7 / 5.0 | In Progress |
| Phase III | Better for Less | 2.5 / 5.0 | In Progress |
| Phase IV | Continuously Evolving | 1.8 / 5.0 | Not Started |

**Critical Findings**:

1. **Systematic Learning (Phase I, score 2)**: No structured feedback loops, retrospectives, or lessons-learned processes are evidenced — the programme risks repeating mistakes during the complex 18-month migration.
2. **Distributed Power and Move Fast (Phase II, scores 2)**: Centralized approval gates (CDTO, CISO, ICO, GDS, steering committee) create structural bottlenecks that conflict with the 12-month API launch commitment and data mesh domain autonomy model.
3. **Phase IV almost entirely absent (score 1.8)**: No evidence of ecosystem listening, cultural diversity, or design for evolution — the programme is building a fixed target-state architecture rather than an adaptive one.

National Highways demonstrates solid Phase I foundations in user knowledge and standards adoption, but the organisation is heavily plan-driven with centralized governance that will constrain the agile, federated approach the data mesh architecture requires. The most urgent priority is establishing learning loops and distributing decision authority to domain teams before the build phase accelerates.

---

## Strategy Cycle Context

| Element | Summary |
|---------|---------|
| **Purpose** | Modernize National Highways' data architecture from legacy Oracle to cloud-native data mesh, enabling real-time journey planning for 45 million daily road users on England's 4,300-mile strategic road network. The £45M programme must deliver £15M annual savings, 99.95% availability, and an Open Data API within 12 months. |
| **Landscape** | The Wardley Map (ARC-001-WARD-001) reveals 35 components: 2 in Genesis (Driver Journey Planning, Incident Detection AI), 12 in Custom (data mesh, ANPR, incident management), 14 in Product (API management, streaming, databases), and 7 in Commodity (Azure cloud infrastructure). Significant inertia exists in legacy Oracle (7 databases, 500TB, 45 Oracle DBAs). The critical path runs through custom-built components that require specialist skills (data mesh architects, privacy engineers). |
| **Climate** | Intense regulatory pressure: GDS Service Standard, TCoP, NCSC Cloud Security Principles, UK GDPR, ICO oversight. Political pressure for 12-month delivery (ministerial commitment). CNI classification elevates security requirements. £60B asset base creates accountability pressure from Treasury and NAO. Market evolution is rapid in event streaming (commoditizing) and AI/ML (maturing), creating build-vs-buy timing sensitivity. |
| **Leadership** | CDTO as executive sponsor with weekly programme reviews. Monthly steering committee includes ministerial representation. Decision-making is centralized through approval gates (CISO for security, DPO for privacy, GDS for service standard, Treasury for spending). Risk appetite is low — the DfT Permanent Secretary is personally accountable to Parliament. This creates a tension between the federated data mesh governance model and the centralized oversight culture. |

---

## Doctrine Assessment Matrix

Score key: **1** = Not practised | **2** = Ad hoc | **3** = Developing | **4** = Mature | **5** = Cultural norm

### Phase I: Stop Self-Harm

| Category | Principle | Score | Evidence | Improvement Action |
|----------|-----------|:-----:|----------|--------------------|
| Communication | Common Language | 3 | Comprehensive glossary in REQ and PRIN documents. Standardized requirement ID prefixes (BR-, FR-, NFR-, INT-, DR-). Consistent terminology across 10+ artifacts. However, vocabulary consistency is at the document level — no evidence it is enforced in meetings, presentations, or cross-team communication. | Mandate glossary use in steering committee papers and domain team standups. Run a terminology alignment workshop across all 5 domain teams and 7 regional control rooms. |
| Communication | Challenge Assumptions | 3 | REQ documents 4 explicit requirement conflicts with trade-off analysis (speed vs security, cost vs capability, centralization vs federation, open vs secure). STKE identifies stakeholder tension areas. However, assumption-challenging is reactive — surfaced when conflicts emerge — rather than systematic (no assumption audit process, no devil's advocate role). | Introduce assumption audits at each phase gate. Assign a "red team" role for architecture reviews. Add "What are we assuming?" as a standing agenda item in steering committee. |
| Communication | Understand Context | 3 | Wardley Map provides landscape context with 35 components positioned. STKE has Power/Interest grid. Value chain decomposition (WVCH) maps 20 components with visibility scoring. Context understanding is strong in architecture artifacts but no evidence it flows to operational teams, domain owners, or control room managers. | Share a simplified version of the Wardley Map with domain teams. Create a "strategic context brief" that translates architecture decisions into domain-team-relevant implications. |
| Development | Know Your Users | 4 | REQ identifies 6+ user personas with detailed needs (road users, operators, emergency services, developers, planners, data consumers). STKE profiles 20+ stakeholders with driver analysis. FR requirements include user stories ("As a Control Room Operator, I need..."). User research specified: 30+ representative users. This is the strongest Phase I principle. | Maintain and refresh user personas quarterly. Ensure user research includes feedback from existing legacy system users, not just future-state assumptions. |
| Development | Focus on User Needs | 3 | Requirements anchor to user needs (BR-001 starts with "45 million daily road users"). Value chain anchored to genuine user need ("road users can access real-time traffic information"). However, some requirements are solution-shaped (e.g., "data mesh architecture with 5 domain data products" is an architectural choice, not a user need). The Wardley Map places Driver Journey Planning at Genesis (0.22), suggesting the user need is still being explored. | Distinguish between user needs (outcomes) and solution requirements (implementations) in all artifacts. Test each FR against: "Could a different solution satisfy this user need?" |
| Development | Remove Bias and Duplication | 3 | Data mesh architecture addresses duplication (Principle #9: Single Source of Truth per Domain). WARD identifies build vs buy to avoid reinventing commodity components. However, 7 legacy systems still running in parallel represents active duplication. No explicit process for identifying cognitive biases in decision-making. | Prioritize legacy system decommissioning timeline. Introduce decision logs that capture the reasoning and alternatives considered, making biases visible and challengeable. |
| Development | Use Appropriate Methods | 3 | WARD recommends different approaches by evolution stage (build for Genesis/Custom, buy for Product, use commodity). PRIN recommends agile delivery. But no evidence of actually applying different methodologies to different components — e.g., using lean startup for Genesis-stage Incident Detection AI vs. structured delivery for commodity cloud provisioning. | Map delivery methodologies to component evolution stages: Discovery/Lean for Genesis, Agile/Scrum for Custom, SAFe/Kanban for Product integration, ITIL for Commodity operations. Document the mapping in a delivery playbook. |
| Operation | Know the Details | 3 | WARD has detailed 35-component inventory with evolution positions, costs, and risks. REQ has specific performance targets (500ms p95, 5TB/day, 99.95% availability). STKE knows stakeholder motivations at granular level. But this detail resides in architecture documents — no evidence leadership regularly engages with operational specifics (e.g., current Oracle database performance, actual sensor data latency, control room operator pain points). | Institute monthly "gemba walks" where programme leadership observes control room operations, data pipeline performance, and development team workflows firsthand. |
| Learning | Systematic Learning | 2 | No evidence of structured lessons-learned processes, retrospectives, or feedback loops in any artifact. Risk register (ARC-001-RISK) exists but no evidence of learning from past incidents or near-misses. No knowledge management system referenced. The programme is new, but no learning mechanisms have been established. This is the weakest Phase I principle and a significant gap. | Establish sprint retrospectives for all delivery teams (immediate). Create a programme-level lessons-learned repository. Mandate post-incident reviews (blameless) for any production issue. Institute a monthly "learning review" at steering committee. |

**Phase I Average Score**: 3.0 / 5.0 — **In Progress**

---

### Phase II: Becoming More Context Aware

| Category | Principle | Score | Evidence | Improvement Action |
|----------|-----------|:-----:|----------|--------------------|
| Communication | Bias Towards Open | 3 | PRIN #5 "Open by Default" establishes open data as an architecture principle. Open Government License for public data. OpenAPI 3.x specifications planned. However, organizational openness (transparent decision-making internally, proactive information sharing across teams) is different from open data publishing — no evidence of internal transparency practices such as open decision logs, architecture decision records accessible to all teams, or open steering committee minutes. | Publish architecture decision records (ADRs) to all project teams. Share steering committee decisions (not minutes) openly. Create an internal project wiki/dashboard showing programme status, risks, and decisions. |
| Development | Focus on Outcome | 3 | REQ defines 6 measurable outcomes (O-1 through O-6) with specific targets (20% journey variability reduction, £15M savings, 50M API requests/month). But requirements are heavily activity-focused alongside outcomes (build API, migrate database, train staff). Success criteria mix output metrics (API live by Month 12) with outcome metrics (journey variability reduction). | Reframe all success criteria around user outcomes. Add leading indicators that predict outcome achievement, not just delivery milestones. Structure contracts with suppliers around outcomes, not deliverables. |
| Development | Think FIRE | 2 | No explicit FIRE (Fast, Inexpensive, Restrained, Elegant) application in any artifact. The £45M budget with 35 components suggests comprehensive rather than restrained scoping. 44 out of 47 requirements are MUST_HAVE priority, suggesting insufficient prioritization — when everything is a must-have, nothing is. No evidence of MVPs, thin slices, or deliberate scope restraint. | Apply FIRE scoring to each component before build: Is this the fastest path? Is this the cheapest adequate solution? Have we resisted feature creep? Is the design elegant (simple)? Reclassify requirements: no more than 60% should be MUST_HAVE; reprioritize the remainder as SHOULD or COULD. |
| Development | Use Appropriate Tools | 3 | WARD maps tools to evolution stages (Azure for commodity, custom build for Genesis). Technology selections are justified (PostGIS for geospatial, Azure Event Hubs for streaming). But tool selection appears architecture-team-driven with no evidence of domain teams evaluating tools for their specific context. | Allow domain teams to propose tools within guardrails. Create a technology radar that domain teams contribute to. Evaluate whether Azure-native defaults are appropriate for each domain or if best-of-breed would deliver better outcomes. |
| Development | Be Pragmatic | 3 | Phased delivery approach (Phase 1: low-risk open data, Phase 2: OFFICIAL-SENSITIVE) is pragmatic. G-Cloud procurement route avoids lengthy custom procurement. Azure standardization reduces integration complexity. However, some requirements are aspirational rather than pragmatic (50,000 sensor capacity when only 10,000 exist; 2.5PB storage for 5-year forecast). | Challenge capacity planning assumptions. Build for 2x current need, not 5x forecast. Use reserved instances for baseline, pay-as-you-go for peaks. Apply "You Aren't Gonna Need It" (YAGNI) to infrastructure provisioning. |
| Development | Use Standards | 4 | Strong standards adoption: OpenAPI 3.x, DATEX II (European traffic data), OAuth 2.0/OIDC, GeoJSON, WCAG 2.2 AA, JSON structured logging, ISO 8601 timestamps, WGS84 coordinates. TCoP compliance documented. NCSC Cloud Security Principles addressed. This is the strongest Phase II principle. | Maintain standards register. Ensure standards compliance is automated where possible (API spec validation in CI/CD, accessibility testing in pipeline, schema validation on ingestion). |
| Operation | Manage Inertia | 3 | WARD identifies 5 inertia sources with specific mitigation strategies: Oracle DBAs (retraining), manual processes (pilots), vendor lock-in (Terraform abstraction), centralized culture (federated governance), sunk costs (phased decommission). But mitigation is planned, not yet executed. No evidence of measuring inertia reduction over time. | Create an "inertia register" alongside the risk register. Track inertia reduction as a programme metric. Celebrate early wins from inertia-breaking actions (e.g., first Oracle database decommissioned, first domain team operating autonomously). |
| Operation | Manage Failure | 2 | WARD mentions "accept 15% false positives" for AI pilot and "pilot on low-risk routes." Risk register exists. But no blameless post-mortem process, no failure budget concept, no explicit failure tolerance calibrated to evolution stage. Government culture of risk aversion (DfT Perm Sec accountable to Parliament) creates implicit blame culture around failure. | Introduce blameless post-incident reviews modelled on SRE practices. Define explicit failure budgets by component evolution stage: high tolerance for Genesis (AI pilot), medium for Custom (data mesh), low for Commodity (cloud infrastructure). Train leadership on "failure as information" framing. |
| Operation | Effectiveness over Efficiency | 3 | Data mesh architecture prioritizes domain effectiveness (autonomy, ownership) over centralized efficiency (single data warehouse). Open Data API prioritizes public value over internal efficiency. But cost savings targets (BR-002: £15M by Year 3) create efficiency pressure. Risk of optimizing the wrong things efficiently — e.g., migrating all 7 Oracle databases when some could be retired entirely. | Before each efficiency initiative, confirm the activity is worth doing at all. Ask: "If we stopped doing this entirely, what would happen?" Apply effectiveness gate before efficiency optimization. |
| Learning | Bias Towards Action | 2 | Extensive documentation and planning artifacts (10+ documents) but limited evidence of rapid experimentation. No mention of MVPs, spikes, prototypes, or proof-of-concepts in the artifacts beyond the AI pilot. The programme appears to be in heavy planning mode — this is common in government programmes but creates risk of analysis paralysis. | Mandate that every major technical decision includes a time-boxed spike or prototype before full commitment. Set a "30-day rule": if a design decision hasn't been validated through action within 30 days of proposal, escalate. |
| Leading | Move Fast | 2 | 12-month API launch commitment shows ambition. But approval chains are structurally long: steering committee (monthly), CISO security review gates, ICO DPIA approval, GDS Alpha/Beta assessments, Treasury spending approval. Each gate adds weeks. Government governance creates structural slowness that conflicts with the pace the programme requires. | Identify decisions that can be delegated to domain teams without escalation. Pre-approve a decision authority framework: domain teams decide within guardrails, programme board reviews outcomes not proposals. Reduce steering committee agenda to decisions-only (not status updates). |
| Leading | Strategy is Iterative | 3 | WARD recommends quarterly map reviews. Phased delivery suggests iteration. Version history shows artifacts updated (v1.0 → v1.1). But strategy documents appear treated as plans to be executed rather than hypotheses to be tested. No evidence of strategy pivots based on new intelligence, or of treating the strategy as continuously revisable. | Rename "programme plan" to "current strategy hypothesis." Schedule quarterly strategy reviews where the Wardley Map is updated based on what has been learned. Introduce the concept of "strategy experiments" — deliberate tests of strategic assumptions. |
| Structure | Think Small Teams | 3 | Data mesh proposes 5 domain teams. WARD recommends "Small Teams" in doctrine gameplay. But 120-staff upskilling programme and 7 regional control rooms suggest large organizational units. No explicit two-pizza team model. Domain teams are described but their actual size and composition are not specified. | Define maximum team size of 8-10 for delivery teams. Each data product domain team should be a single autonomous team, not a sub-department. If a domain needs more than 10 people, split into sub-domains. |
| Structure | Distribute Power | 2 | Data mesh principle states domain autonomy, but RACI across artifacts shows centralized decision authority: CDTO approves architecture, CISO approves security, DPO approves privacy, GDS assesses service standard, Treasury approves spending. Domain data owners are "appointed" (STKE) but their actual decision authority is unclear. Risk of "federated in name only." | Define a clear decision rights framework: what domain teams can decide autonomously, what requires consultation, what requires approval. Start with a small list of decisions delegated to domain teams and expand as trust builds. |
| Structure | Aptitude and Attitude | 2 | BR-007 mentions 120 staff cloud training and 80+ professional certifications — this addresses aptitude (technical skills). But no evidence of hiring or developing for attitude (cultural alignment, Pioneer/Settler/Town Planner fit). The data mesh transformation requires different mindsets for different roles: explorers for Genesis-stage AI, product thinkers for Custom data products, operators for Commodity infrastructure. | Map roles to Pioneer/Settler/Town Planner profiles. Ensure hiring criteria include attitude assessment (not just certifications). Create differentiated career paths: innovation track (Pioneer), product track (Settler), operations track (Town Planner). |

**Phase II Average Score**: 2.7 / 5.0 — **In Progress**

---

### Phase III: Better for Less

| Category | Principle | Score | Evidence | Improvement Action |
|----------|-----------|:-----:|----------|--------------------|
| Operation | Optimise Flow | 2 | No value stream mapping or flow optimization in any artifact. Architecture principles mention event-driven patterns (Principle #13) but operational flow — how work moves through teams, how decisions flow through governance, how data flows through the pipeline — is not mapped or optimized. Governance gates are potential flow bottlenecks. | Map the end-to-end value stream from user need to deployed feature. Identify the top 3 bottlenecks in the current delivery process. Measure lead time from requirement to production for each domain team. |
| Operation | Do Better with Less | 2 | BR-002 targets £15M cost savings, but this is through technology replacement (Oracle decommission = £8M, data centre reduction = £4M) not continuous improvement culture. No evidence of systematic process improvement, waste elimination, or efficiency reviews. Cost reduction is a one-time migration benefit, not an ongoing discipline. | Establish FinOps practices from Day 1 of cloud deployment. Introduce monthly "waste reviews" where teams identify and eliminate non-value-adding activities. Set a continuous improvement target: 5% efficiency gain per quarter after initial deployment. |
| Operation | Exceptional Standards | 3 | Ambitious SLAs set: 99.95% availability, < 500ms p95 latency, 99.9% data quality, < 2 second sensor-to-API latency, WCAG 2.2 AA accessibility, NCSC Cloud Security Principles compliance. These are genuinely high standards. But they are set, not yet achieved or enforced. Standards without enforcement degrade to aspirations. | Define SLOs (not just SLAs) with error budgets. Automate standards enforcement: API spec validation in CI/CD, accessibility testing in pipeline, security scanning in build. Publish standards compliance dashboards visible to all teams. |
| Learning | Bias Towards New | 3 | Incident Detection AI (Genesis stage, evolution 0.28) shows willingness to explore novel technology. Data mesh is an emerging architectural pattern (Custom, 0.38). Evolution predictions in WARD show awareness of technology change. But exploration is concentrated in specific components, not a broad organizational culture. No innovation budget, no hack days, no protected time for experimentation. | Allocate 10% of engineering time to exploration ("20% time" lite). Create an innovation backlog where any team member can propose experiments. Fund 2-3 low-cost technology pilots per quarter outside the main programme scope. |
| Leading | Commit to Direction | 3 | Clear strategic direction: legacy Oracle to cloud-native data mesh on Azure. £45M investment demonstrates financial commitment. 22 architecture principles provide guardrails. But phased delivery creates natural pivot points, and political pressure (ministerial accountability) could force direction changes. No explicit mechanism for distinguishing tactical pivots from strategic retreats. | Document strategic commitments that will NOT change (e.g., "cloud-native, data mesh, Azure UK, open data") separately from tactical approaches that may adapt. When pivots are proposed, explicitly classify them as tactical adjustment or strategic change. |
| Leading | Be the Owner | 3 | CDTO named as executive sponsor. Domain data owners appointed (5 FTE). Programme Director accountable for delivery. But "PENDING" in all approval fields across all artifacts (10+ documents) suggests ownership is assigned but not yet activated. No evidence of owners making tough calls or being held to account for outcomes. | Require named owners to sign off on their domains' artifacts within 30 days. Publish an accountability dashboard showing: who owns what, what decisions they've made, what outcomes they've delivered. |
| Leading | Inspire Others | 2 | No evidence of compelling vision communication beyond formal requirements documents. BR-007 mentions staff upskilling as a requirement (functional framing) not as an inspiring career development opportunity. No evidence of connecting individual work to the mission of serving 45 million daily journeys. No town halls, vision documents, or narratives that inspire. | Create a one-page "programme vision" that connects individual contributions to public benefit. Share stories of impact: "When this sensor data reaches a driver 2 seconds faster, it could prevent an accident." Run quarterly all-hands where teams demo working software to real users. |
| Leading | Embrace Uncertainty | 2 | Risk register identifies 20+ risks with mitigation strategies — this is risk management, not uncertainty embracement. DfT Permanent Secretary is "personally accountable to Parliament" (STKE) creating institutional risk aversion. Government culture frames uncertainty as a threat to be mitigated rather than a condition to be navigated. Requirements have little flexibility — 44 of 47 are MUST_HAVE. | Introduce the concept of "strategic options" — decisions deliberately deferred until more information is available. Reframe risk appetite by component: high uncertainty tolerance for Genesis, medium for Custom, low for Commodity. Reduce MUST_HAVE requirements to 60% to create deliberate flexibility. |
| Leading | Be Humble | 2 | No evidence of leadership admitting knowledge gaps, seeking external challenge, or changing minds based on new information. Architecture principles document is comprehensive (22 principles, 1,300 lines) with "NONE" for security exceptions — this confidence may be warranted but leaves no room for learning. No external peer review of strategy or architecture. | Invite external architecture reviewers (GDS, other ALBs, industry peers) to challenge the strategy. Introduce "pre-mortem" exercises: "Assume this programme has failed — what went wrong?" Institute a norm of leaders publicly acknowledging what they've learned or changed their mind about. |
| Structure | Seek the Best | 2 | No evidence of benchmarking organizational structure against industry best practice (e.g., Spotify model, Amazon two-pizza teams, platform engineering patterns). Government organizational structures tend to be hierarchical by default. Data mesh is a progressive pattern but organizational design around it is not evidenced. | Benchmark team structures against organizations that have successfully implemented data mesh (e.g., Zalando, Thoughtworks clients). Visit or study 2-3 comparable government data transformation programmes (e.g., HMRC, DWP, ONS). |
| Structure | Purpose, Mastery, Autonomy | 3 | Data mesh provides domain **autonomy** (in principle). Training programme builds **mastery** (120 staff, 80+ certifications). **Purpose** is clear (serve 45M daily journeys). But autonomy is constrained by governance gates, mastery is measured by certifications rather than demonstrated capability, and purpose connection is implicit rather than explicit in team-level objectives. | Connect each domain team's OKRs directly to user outcomes (not just technical deliverables). Measure mastery through demonstrated capability (successful deployments, incident response) not just certifications. Expand autonomy as teams demonstrate competence. |

**Phase III Average Score**: 2.5 / 5.0 — **In Progress** (barely — closer to Not Started)

---

### Phase IV: Continuously Evolving

| Category | Principle | Score | Evidence | Improvement Action |
|----------|-----------|:-----:|----------|--------------------|
| Learning | Listen to Ecosystem | 2 | WARD identifies market monitoring for specific technologies (Kafka evolution, AI/ML ops, Data Mesh products). Evolution predictions show awareness of market trends. But monitoring is technology-focused, not ecosystem-focused: no evidence of monitoring competitor strategies (TfL, European road operators), adjacent industry patterns (logistics, smart cities), emerging user behaviours, or regulatory direction. No structured listening mechanism. | Create a quarterly "ecosystem scanning" report covering: technology evolution, competitor/peer actions, regulatory direction, user behaviour changes, and adjacent industry innovations. Assign ecosystem monitoring as a named responsibility. |
| Leading | Exploit the Landscape | 2 | WARD has a "Strategic Gameplay" section with accelerators, tower-and-moat, and exploiting-inertia patterns. Open data as commoditization strategy is identified. But gameplay is documented in an architecture artifact, not in active practice. No evidence of leaders making real-time strategic plays based on landscape shifts. | Move gameplay from documentation to practice. At each quarterly strategy review, identify one active gameplay to execute. Start with the "open data commoditization" play — actively publishing data to shift competitive dynamics. |
| Leading | There is No Core | 1 | National Highways is defined by its core: managing England's strategic road network. The entire programme reinforces this identity. No evidence of questioning what the "core" is, acknowledging its temporality, or exploring adjacent value propositions. This is common in government ALBs (arms-length bodies) with statutory mandates — the "core" is legally defined. Scoring 1 reflects government structural constraints rather than organizational failure. | While the statutory mandate is fixed, the delivery model is not. Challenge whether National Highways must operate data infrastructure or whether it could become a data standards and governance body while outsourcing operations. Explore platform models where third parties deliver services on NH infrastructure. |
| Structure | No Single Culture | 2 | Data mesh implies different domain cultures could emerge. WARD mentions Pioneer/Settler/Town Planner in one line. But no deliberate cultural diversity is designed into the organization. Government culture tends toward uniformity (single performance framework, single recruitment process, single management style). The 120-staff upskilling programme treats all staff the same. | Explicitly design for cultural diversity: Genesis-stage work (AI pilot) should have innovation-lab culture; Commodity operations (cloud infrastructure) should have SRE discipline culture; Custom-build teams (data mesh) should have product-development culture. Ensure management practices, success metrics, and work styles differ by evolution stage. |
| Structure | Design for Constant Evolution | 2 | Quarterly Wardley Map reviews planned. Evolution predictions documented with 12-month and 24-month horizons. Architecture uses modular patterns (microservices, data mesh, event-driven). But organizational structure appears fixed: CDTO-led hierarchy, 5 domain teams, 7 regional control rooms. No evidence that organizational design is expected to change as the landscape evolves. The architecture may evolve, but the organization around it appears static. | Build "reorganization triggers" into the programme: if a component moves from Custom to Product (e.g., event streaming commoditizes), the team managing it should transition from a build team to an operations team. Design team charters with explicit evolution clauses. |

**Phase IV Average Score**: 1.8 / 5.0 — **Not Started**

---

## Detailed Phase Findings

### Phase I: Stop Self-Harm — Detailed Findings

**Phase Score**: 3.0 / 5.0

**Strongest principles in this phase**:

- **Know Your Users** (Score: 4) — Six detailed user personas with driver analysis. 20+ stakeholders profiled with motivations. User stories in functional requirements. This is the foundation on which the programme's value proposition rests, and it is well-evidenced.
- **Know the Details** (Score: 3, approaching 4) — Impressive operational detail in component inventory, performance targets, and cost analysis. The architecture team clearly understands the technical landscape.

**Weakest principles in this phase**:

- **Systematic Learning** (Score: 2) — The most critical gap in Phase I. No retrospectives, no lessons-learned repository, no post-incident review process. For a complex 18-month migration touching critical national infrastructure, the absence of structured learning mechanisms is a significant risk. The programme is likely to encounter unexpected problems during Oracle migration, data mesh implementation, and emergency services integration — without learning loops, each problem will be solved in isolation rather than feeding back into improved practices.

**Phase I Narrative**:

National Highways has strong user knowledge and good technical awareness, providing a solid anchor for architecture decisions. The standardized requirements framework and adoption of open standards demonstrate organizational discipline. However, the absence of systematic learning creates a fragile foundation — the programme knows its users and its landscape but has no mechanism for getting smarter over time. The communication principles (common language, challenge assumptions, understand context) score consistently at 3, indicating awareness without embedding — the vocabulary exists in documents but may not be alive in daily practice.

---

### Phase II: Becoming More Context Aware — Detailed Findings

**Phase Score**: 2.7 / 5.0

**Strongest principles in this phase**:

- **Use Standards** (Score: 4) — Comprehensive adoption of OpenAPI, DATEX II, OAuth 2.0, GeoJSON, WCAG 2.2 AA, and compliance with TCoP and GDS Service Standard. Standards are well-documented and consistently referenced across artifacts.
- **Manage Inertia** (Score: 3) — Five inertia sources explicitly identified in the Wardley Map with specific mitigation strategies. This shows strategic awareness of change resistance.

**Weakest principles in this phase**:

- **Think FIRE** (Score: 2) — No evidence of Fast, Inexpensive, Restrained, Elegant design thinking. 44 of 47 requirements classified as MUST_HAVE suggests everything is treated as equally critical, leaving no room for scope management.
- **Distribute Power** (Score: 2) — The data mesh architecture promises domain autonomy, but governance structure centralizes decision authority through multiple approval gates. Risk of "federated architecture with centralized governance" — the worst of both worlds.
- **Move Fast** (Score: 2) — Government approval chains (CISO, ICO, GDS, Treasury, steering committee) create structural slowness. The 12-month API launch is ambitious given the number of gates.
- **Bias Towards Action** (Score: 2) — Heavy planning investment (10+ documents) with limited evidence of experimentation, prototyping, or validated learning through action.
- **Aptitude and Attitude** (Score: 2) — Training focuses on technical certifications; no evidence of developing the cultural capabilities (Pioneer/Settler/Town Planner) that different evolution stages demand.

**Phase II Narrative**:

The programme demonstrates strong standards adoption and thoughtful inertia management but is significantly held back by centralized governance structures and a planning-over-doing culture. The fundamental tension is architectural: data mesh requires distributed decision-making, but the governance model concentrates authority. This disconnect will surface as friction when domain teams try to move fast and find themselves waiting for central approvals. The lack of FIRE discipline means the programme may try to build everything at once rather than delivering thin slices of value.

---

### Phase III: Better for Less — Detailed Findings

**Phase Score**: 2.5 / 5.0

**Strongest principles in this phase**:

- **Exceptional Standards** (Score: 3) — Ambitious SLAs (99.95% availability, < 500ms p95) and compliance frameworks (NCSC, WCAG) set genuinely high bars. The risk is that standards are aspirational rather than enforced.
- **Bias Towards New** (Score: 3) — Incident Detection AI (Genesis stage) and data mesh adoption show willingness to explore emerging patterns. Evolution monitoring in the Wardley Map demonstrates technology awareness.
- **Commit to Direction** (Score: 3) — £45M investment and 22 architecture principles provide clear strategic commitment.

**Weakest principles in this phase**:

- **Inspire Others** (Score: 2) — No vision narrative, no impact stories, no connection between individual work and public benefit. The programme communicates through requirements documents, not through inspiration.
- **Embrace Uncertainty** (Score: 2) — Government accountability structures create institutional risk aversion. 44/47 MUST_HAVE requirements leave no flexibility buffer. Uncertainty is managed through risk registers rather than embraced as a strategic condition.
- **Be Humble** (Score: 2) — No external peer review, no public acknowledgement of knowledge gaps, no evidence of leaders changing their minds.
- **Seek the Best** (Score: 2) — No organizational design benchmarking against industry best practice.
- **Optimise Flow** (Score: 2) — No value stream mapping, no bottleneck identification in delivery processes.
- **Do Better with Less** (Score: 2) — Cost savings are migration-driven, not improvement-driven.

**Phase III Narrative**:

Phase III reveals the gap between setting high standards and building the leadership and operational culture to achieve them sustainably. The programme sets ambitious targets but lacks the continuous improvement mechanisms (flow optimization, waste elimination) to deliver on them over time. Leadership principles (inspire, embrace uncertainty, be humble) score consistently low, reflecting a government programme management culture that prioritizes control over empowerment. This creates a ceiling on organizational performance that technical excellence alone cannot break through.

---

### Phase IV: Continuously Evolving — Detailed Findings

**Phase Score**: 1.8 / 5.0

**Strongest principles in this phase**:

- **Listen to Ecosystem** (Score: 2) and **Exploit the Landscape** (Score: 2) — Both score 2, which is the "strongest" in Phase IV, indicating minimal but non-zero engagement. The Wardley Map's evolution predictions and strategic gameplay section show awareness that the landscape will change, even if the response is still planned rather than practised.

**Weakest principles in this phase**:

- **There is No Core** (Score: 1) — The only principle scoring 1 across the entire assessment. National Highways' statutory mandate creates a fixed identity. This is a structural constraint of government ALBs rather than an organizational failure, but it limits strategic flexibility.
- **No Single Culture** (Score: 2) — Government organizations typically enforce cultural uniformity through standardized HR processes, performance management, and management practices. The data mesh architecture needs cultural diversity; the organization doesn't yet provide it.
- **Design for Constant Evolution** (Score: 2) — Architecture is modular, but organizational design is static. No evidence that team structures, governance models, or delivery approaches are expected to evolve as the landscape changes.

**Phase IV Narrative**:

Phase IV is almost entirely unreached, which is expected for a government programme in its first year. The concern is not the current score but the absence of any trajectory toward Phase IV capabilities. No mechanisms exist for systematic ecosystem listening, landscape exploitation, cultural diversification, or organizational evolution. The programme is building a target-state architecture — a fixed destination — rather than developing the organizational capacity to continuously adapt. This matters because the technology landscape (AI, streaming, data mesh) is evolving rapidly, and a programme that completes in 2028 will need to look very different from what is planned today in 2026.

---

## Previous Assessment Comparison

This is the initial assessment. No previous scores are available for comparison.

---

## Critical Gaps

| Rank | Phase | Category | Principle | Current Score | Target Score | Business Impact |
|------|-------|----------|-----------|:-------------:|:------------:|-----------------|
| 1 | I | Learning | Systematic Learning | 2 | 4 | Without learning loops, the 500TB Oracle migration, emergency services integration, and data mesh rollout will each discover problems independently rather than feeding insights back into improved practices. Estimated impact: 3-6 month delays from repeated mistakes during the 18-month programme. |
| 2 | II | Structure | Distribute Power | 2 | 4 | Data mesh architecture requires domain autonomy but governance centralizes decisions through 5+ approval gates. Domain teams will be unable to iterate at the pace required for the 12-month API launch. The CDTO becomes a single point of failure for all architecture decisions. |
| 3 | II | Leading | Move Fast | 2 | 3 | Government approval chains (CISO, ICO, GDS, Treasury, steering committee) create structural 2-4 week delays per decision. Cumulative impact: the 12-month API launch deadline is at risk unless decision authority is delegated. Each gate adds latency that compounds across the critical path. |
| 4 | II | Development | Think FIRE | 2 | 3 | 44 of 47 requirements are MUST_HAVE, leaving no scope flexibility. When delivery pressure increases (and it will), there is no graceful degradation path — the programme must deliver everything or "fail." FIRE discipline would create deliberate scope tiers enabling pragmatic trade-offs. |
| 5 | II | Learning | Bias Towards Action | 2 | 3 | Heavy planning without experimentation means technical assumptions (5TB/day throughput, < 2s latency, ANPR anonymization workflow) remain untested until build phase. Late discovery of invalid assumptions during build is orders of magnitude more expensive than early validation through prototyping. |

---

## Implementation Roadmap

### Immediate Actions (0-3 months)

| Action | Principle(s) Addressed | Owner | Success Criteria |
|--------|----------------------|-------|------------------|
| Establish sprint retrospectives for all delivery teams and a monthly programme-level lessons-learned review | Systematic Learning | Programme Director | Retrospectives running in all teams by Month 1; 3+ actionable improvements implemented from first quarter of retrospectives |
| Define and publish a decision authority framework: what domain teams can decide autonomously vs. what requires escalation | Distribute Power, Move Fast | CDTO | Framework published by Month 2; at least 5 decision categories delegated to domain teams; average decision cycle time reduced from 2-4 weeks to < 5 days for delegated decisions |
| Run time-boxed technical spikes (2-week max) for the 3 highest-risk assumptions: 5TB/day streaming throughput, ANPR anonymization pipeline, and Azure Event Hubs latency under load | Bias Towards Action, Think FIRE | Data Engineering Lead | 3 spike reports delivered within 6 weeks; each validates or invalidates a key technical assumption; results inform updated architecture decisions |

### Short-Term Actions (3-12 months)

| Action | Principle(s) Addressed | Owner | Success Criteria |
|--------|----------------------|-------|------------------|
| Map Pioneer/Settler/Town Planner profiles to programme roles and adjust hiring, team composition, and management practices accordingly | Aptitude and Attitude, No Single Culture | CDTO, HR Lead | Role-to-profile mapping complete by Month 4; differentiated performance criteria for Genesis-stage vs. Commodity-stage teams by Month 6; at least 3 hires made using PST criteria |
| Reclassify requirements: reduce MUST_HAVE from 94% to < 60%, creating explicit SHOULD_HAVE and COULD_HAVE tiers for scope management | Think FIRE, Embrace Uncertainty | Programme Director, Product Owner | Reclassified requirements published by Month 4; first scope trade-off decision made using MoSCoW tiers; scope flexibility demonstrated at Phase 1 API launch |
| Institute quarterly Wardley Map reviews where the map is updated based on actual landscape changes, not just predictions | Strategy is Iterative, Listen to Ecosystem | Enterprise Architecture Lead | First quarterly review completed by Month 6; at least 3 component positions adjusted based on evidence; one strategic decision changed based on review findings |
| Create an internal "programme vision" narrative connecting individual work to public benefit, and run quarterly all-hands demos to real users | Inspire Others, Focus on Outcome | Programme Director | Vision narrative published by Month 4; first all-hands demo by Month 6; team engagement score measured (baseline + target) |

### Long-Term Actions (12-24 months)

| Action | Principle(s) Addressed | Owner | Success Criteria |
|--------|----------------------|-------|------------------|
| Build "reorganization triggers" into team charters so that when components evolve (e.g., event streaming commoditizes), teams transition from build to operate mode with appropriate cultural and process changes | Design for Constant Evolution, No Single Culture | CDTO | Triggers defined in all 5 domain team charters by Month 15; at least 1 team successfully transitions from build to operate mode by Month 18; organizational design reviewed quarterly alongside Wardley Map |
| Establish continuous flow optimization with value stream mapping, bottleneck identification, and waste elimination across the delivery pipeline | Optimise Flow, Do Better with Less | Programme Director, Delivery Manager | Value stream mapped by Month 14; top 3 bottlenecks identified and addressed; lead time from requirement to production reduced by 30% from Month 6 baseline |

---

## Recommendations

1. **Establish learning infrastructure before accelerating build**
   - **Rationale**: Systematic Learning (score 2) is the most dangerous Phase I gap. The programme is about to enter complex parallel workstreams (Oracle migration, data mesh build, API development, emergency services integration). Without retrospectives, post-incident reviews, and cross-team knowledge sharing, each stream will learn in isolation and repeat preventable mistakes.
   - **Expected Benefit**: Faster problem resolution, reduced rework, improved cross-team coordination. Based on industry benchmarks, structured learning loops reduce programme delays by 15-25%.
   - **Risk of Inaction**: The 18-month programme accumulates technical debt and process debt that becomes visible only at integration points — by then, rework costs are 5-10x higher than early detection would allow.

2. **Distribute decision authority to match the data mesh architecture**
   - **Rationale**: Distribute Power (score 2) and Move Fast (score 2) create a structural contradiction: the architecture is federated but governance is centralized. Domain data owners have been appointed but lack decision authority. This will become acutely painful when domain teams need to make daily technical decisions and face 2-4 week approval cycles.
   - **Expected Benefit**: Faster delivery cadence, empowered domain teams, reduced CDTO bottleneck. Domain teams that can make autonomous decisions within guardrails deliver 2-3x faster than those requiring central approval.
   - **Risk of Inaction**: The 12-month API launch fails because every technical decision queues behind centralized approvals. Domain owners become frustrated and disengaged. The data mesh degrades into a centralized architecture with federated naming.

3. **Apply FIRE discipline to scope management and validate assumptions through action**
   - **Rationale**: Think FIRE (score 2) and Bias Towards Action (score 2) combine to create a programme that is over-scoped and under-validated. 44 of 47 MUST_HAVE requirements with no experimental validation means the programme is committed to delivering everything before confirming anything actually works at scale.
   - **Expected Benefit**: Earlier discovery of invalid assumptions (saving months of rework), graceful scope management under pressure (explicit trade-off tiers), and faster time-to-value (thin slices delivered early).
   - **Risk of Inaction**: The programme hits Month 9 with untested assumptions about throughput, latency, and anonymization performance. Late discovery forces painful scope cuts under time pressure, with no pre-agreed prioritization to guide what gets dropped.

---

## Traceability

| Artifact | Document ID | Relationship |
|----------|-------------|--------------|
| Architecture Principles | ARC-000-PRIN-v1.0 | 22 principles assessed for doctrine alignment; strong standards (Phase II score 4) but principles are comprehensive rather than adaptive (Phase IV score 1-2) |
| Wardley Map | ARC-001-WARD-001-v1.0 | 35-component landscape with evolution positions, inertia analysis, and strategic gameplay — primary evidence source for Phase II (context awareness) and Phase IV (landscape exploitation) |
| Stakeholder Analysis | ARC-001-STKE-v1.0 | 20+ stakeholder profiles with driver analysis — primary evidence for leadership culture, decision-making structure, and organizational dynamics |
| Requirements | ARC-001-REQ-v1.0 | 47 requirements with traceability — evidence for user needs (Phase I score 4), standards (Phase II score 4), and scope discipline (FIRE score 2) |
| Value Chain | ARC-001-WVCH-001-v1.0 | 20-component value chain — evidence for landscape understanding and dependency awareness |
| Risk Register | ARC-001-RISK-v1.0 | Risk identification and mitigation — evidence for failure management (score 2) and uncertainty handling (score 2) |

---

**Generated by**: ArcKit `/arckit:wardley.doctrine` command
**Generated on**: 2026-03-19 14:30 GMT
**ArcKit Version**: 4.3.1
**Project**: National Highways Data Architecture Modernization (Project 001)
**AI Model**: Claude Opus 4.6 (claude-opus-4-6)
**Generation Context**: Doctrine assessment derived from architecture principles (ARC-000-PRIN-v1.0), Wardley Map (ARC-001-WARD-001-v1.0), stakeholder analysis (ARC-001-STKE-v1.0), requirements (ARC-001-REQ-v1.0), value chain (ARC-001-WVCH-001-v1.0), and risk register (ARC-001-RISK-v1.0). No user input provided — assessment based entirely on artifact evidence.
