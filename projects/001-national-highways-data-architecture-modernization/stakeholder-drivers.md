# Stakeholder Drivers & Goals Analysis: National Highways Data Architecture Modernization

## Document Information

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-STKE-v1.0 |
| **Project** | National Highways Data Architecture Modernization (Project 001) |
| **Document Type** | Stakeholder Drivers & Goals Analysis |
| **Classification** | OFFICIAL |
| **Version** | 1.0 |
| **Status** | DRAFT |
| **Date** | 2025-11-13 |
| **Owner** | Programme Director, Data Architecture Modernization |

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-11-13 | ArcKit AI | Initial creation from `/arckit.stakeholders` command |

---

## Executive Summary

### Purpose
This document identifies key stakeholders for the National Highways Data Architecture Modernization programme, their underlying drivers (motivations, concerns, needs), how these drivers manifest into goals, and the measurable outcomes that will satisfy those goals. This analysis ensures stakeholder alignment and provides traceability from individual concerns to project success metrics.

### Key Findings

**Critical Alignment**: This programme has strong strategic alignment across government stakeholders (DfT Minister, Treasury, GDS) and operational stakeholders (National Highways executive team, regional control rooms). The primary driver convergence is around **public value delivery** - improving journey reliability for 45 million daily journeys on England's strategic road network while demonstrating value for money from the £60 billion road infrastructure investment.

**Key Tension**: There is inherent conflict between the Minister's political driver for **rapid visible delivery** (12-18 month timeframe to demonstrate manifesto commitment) versus the Chief Data Officer and CISO's risk-based driver for **thorough due diligence** on OFFICIAL-SENSITIVE data handling and legacy system migration. This tension requires careful resolution through a phased delivery approach that delivers early wins while maintaining technical rigor.

**Public Accountability**: As a public-facing critical infrastructure programme with significant citizen impact, stakeholders face heightened accountability through parliamentary questions, NAO audits, and media scrutiny. This creates strong **risk aversion** drivers across government stakeholders while **innovation pressure** drives technology leaders to modernize legacy systems.

### Critical Success Factors
- **Public Safety**: Zero incidents caused by system failures or data quality issues during migration
- **Ministerial Confidence**: Delivery of visible public-facing benefits within 18 months to support parliamentary accountability
- **Value for Money**: Demonstrable ROI through operational efficiency gains and enhanced public services, validated by NAO audit
- **Data Protection Compliance**: Full UK GDPR compliance with ICO approval for OFFICIAL-SENSITIVE data handling (ANPR, CCTV)
- **Operational Continuity**: 99.95% availability maintained throughout migration from legacy systems
- **Open Data Delivery**: Public API and open data feeds live within 12 months to enable third-party innovation

### Stakeholder Alignment Score
**Overall Alignment**: MEDIUM-HIGH

**Strong Alignment Areas**:
- Public value delivery (better journey planning, reduced congestion)
- Open data commitment (cross-party political support)
- Operational efficiency gains (cost reduction without service cuts)
- Modern technology adoption (attracting digital talent)

**Conflict Areas Requiring Management**:
- **Speed vs. Rigour**: Minister wants fast delivery; technical teams need proper testing
- **Cost vs. Capability**: Treasury wants budget control; technology teams want modern platform investment
- **Centralization vs. Federation**: Some stakeholders want central control; data mesh requires domain autonomy
- **Open vs. Secure**: Open data advocates want maximum transparency; security teams want data protection

**Resolution Strategy**: Phased delivery with governance gates - early wins on low-risk open data (traffic flow) while building secure foundations for OFFICIAL-SENSITIVE data (CCTV, incident details). Monthly steering group with ministerial representation to balance speed and risk.

---

## Stakeholder Identification

### Internal Stakeholders (National Highways)

| Stakeholder | Role/Department | Influence | Interest | Engagement Strategy |
|-------------|----------------|-----------|----------|---------------------|
| Chief Executive Officer | Accounting Officer for National Highways | CRITICAL | HIGH | Monthly 1-1 briefings, strategic decision authority |
| Chief Data & Technology Officer (CDTO) | Executive Sponsor | CRITICAL | CRITICAL | Weekly programme reviews, architecture approval authority |
| Chief Financial Officer (CFO) | Finance & Investment | HIGH | HIGH | Monthly financial reviews, business case approval |
| Chief Information Security Officer (CISO) | Security & Risk | CRITICAL | HIGH | Security review gates, OFFICIAL-SENSITIVE data approval |
| Chief Operating Officer (COO) | Operations & Service Delivery | HIGH | CRITICAL | Operational readiness reviews, cutover approval |
| Director of Data & Analytics | Programme Director | CRITICAL | CRITICAL | Daily programme management, delivery accountability |
| Regional Control Room Managers (7 regions) | Operational End Users | MEDIUM | CRITICAL | Monthly user forums, UAT participation, feedback loops |
| Data Domain Owners (Traffic, Incidents, Roadworks, Assets) | Data Product Owners | HIGH | CRITICAL | Weekly domain team standups, data quality accountability |
| Enterprise Architects | Architecture Governance | HIGH | HIGH | Architecture review board, ADR approval |
| Infrastructure & Operations Teams | Platform Operations | MEDIUM | HIGH | Transition planning, operational runbooks, support model |
| Data Engineering Teams | Implementation | MEDIUM | CRITICAL | Agile delivery, technical design, data pipelines |
| Procurement & Commercial | Vendor Management | MEDIUM | MEDIUM | Supplier selection, contract negotiation, commercial governance |
| Data Protection Officer (DPO) | Privacy & Compliance | HIGH | MEDIUM | DPIA approval, UK GDPR compliance validation |
| Internal Audit | Assurance & Governance | MEDIUM | MEDIUM | Audit reviews, controls validation |

### External Stakeholders (Government)

| Stakeholder | Organization | Relationship | Influence | Interest |
|-------------|--------------|--------------|-----------|----------|
| Transport Minister | Department for Transport (DfT) | Political Accountability | CRITICAL | HIGH |
| Permanent Secretary (DfT) | Department for Transport | Accounting Officer | CRITICAL | HIGH |
| HM Treasury | Central Government | Funding Authority | CRITICAL | MEDIUM |
| Government Digital Service (GDS) | Cabinet Office | Digital Standards Authority | HIGH | HIGH |
| National Cyber Security Centre (NCSC) | GCHQ | Security Standards Authority | HIGH | MEDIUM |
| Information Commissioner's Office (ICO) | Independent Regulator | Data Protection Regulator | HIGH | MEDIUM |
| National Audit Office (NAO) | Parliamentary Oversight | Value for Money Auditor | HIGH | MEDIUM |
| Infrastructure & Projects Authority (IPA) | Cabinet Office | Major Projects Oversight | MEDIUM | MEDIUM |

### External Stakeholders (Partners & Public)

| Stakeholder | Organization | Relationship | Influence | Interest |
|-------------|--------------|--------------|-----------|----------|
| Local Highway Authorities (152 councils) | Local Government | Data Partners | HIGH | HIGH |
| Transport for London (TfL) | Regional Transport Authority | Data Exchange Partner | MEDIUM | HIGH |
| Emergency Services (Police, Ambulance, Fire) | Blue Light Services | Critical Users | MEDIUM | CRITICAL |
| Navigation App Providers (Google, Waze, TomTom, HERE) | Commercial Partners | API Consumers | LOW | HIGH |
| Logistics Industry (Road Haulage Association) | Industry Representatives | Data Consumers | LOW | HIGH |
| Motoring Organizations (AA, RAC) | Breakdown Services | Service Providers | LOW | MEDIUM |
| General Public (Road Users) | Citizens | Beneficiaries | LOW | CRITICAL |
| Academic Researchers (Transport Research Labs) | Research Community | Data Consumers | LOW | MEDIUM |
| Open Data Advocates (ODI, mySociety) | Civil Society | Transparency Campaigners | LOW | HIGH |

### Stakeholder Power-Interest Grid

```
CRITICAL POWER
    │
    │  [Manage Closely - Weekly Engagement]        │  [Keep Satisfied - Monthly Updates]
    │  - Chief Executive (Accounting Officer)       │  - HM Treasury (Budget Approval)
    │  - CDTO (Executive Sponsor)                   │  - NCSC (Security Standards)
    │  - Transport Minister (Political)             │  - NAO (Value for Money Audits)
    │  - DfT Permanent Secretary                    │
    │  - CISO (Security Approval)                   │
────┼────────────────────────────────────────────────┼─────────────────────────────────
    │  [Keep Informed - Quarterly Updates]         │  [Monitor - As-Needed]
    │  - Regional Control Rooms (Users)             │  - General Public (Road Users)
    │  - Data Domain Owners                         │  - Academic Researchers
    │  - Local Authorities (Partners)               │  - Open Data Advocates
    │  - Emergency Services                         │  - Motoring Organizations
    │  - GDS (Service Standard Assessment)          │
HIGH POWER                                                                    CRITICAL INTEREST
```

---

## Stakeholder Drivers Analysis

### SD-1: Transport Minister - Political Accountability & Manifesto Delivery

**Stakeholder**: Secretary of State for Transport (Ministerial Position)

**Driver Category**: POLITICAL / STRATEGIC

**Driver Statement**:
Deliver visible, quantifiable improvements to England's strategic road network within the current Parliament to demonstrate government's infrastructure investment commitment. The Minister faces weekly parliamentary questions on road network performance and needs demonstrable progress on digital transformation to counter opposition claims of insufficient infrastructure modernization.

**Context & Background**:
- Conservative manifesto commitment: "Invest in technology to reduce congestion and improve journey reliability"
- Opposition questioning on road network digital capabilities vs. international comparators
- Public pressure following high-profile motorway incidents requiring better real-time information
- Treasury pressure to demonstrate ROI from £60 billion National Highways asset base
- Cross-departmental digital transformation pressure from Cabinet Office
- Media scrutiny on government IT project delivery (historical failures create skepticism)

**Driver Intensity**: CRITICAL

**Enablers**:
- Phased delivery with early public-facing wins (open data API, journey planning improvements)
- Positive media coverage of pilot successes (e.g., "Minister launches real-time traffic data API")
- Parliamentary briefing materials showing quantified outcomes (% congestion reduction, user satisfaction)
- Third-party validation (GDS Alpha/Beta assessment passes, positive NAO comments)
- Cross-party support for open data (reduces political risk)

**Blockers**:
- Project delays extending delivery beyond election cycle
- Negative media coverage of implementation issues (data breaches, system outages)
- Parliamentary questions highlighting failures or cost overruns
- NAO criticism of value for money or governance failures
- Public incidents caused by system errors (journey planning routing drivers into incidents)
- ICO enforcement action for data protection violations

**Related Stakeholders**:
- **Aligned**: DfT Permanent Secretary (support Minister), GDS (promote digital transformation), Open Data Advocates (public value)
- **Potential Conflict**: CISO (wants slow careful migration), Treasury (budget constraints), NAO (rigorous value for money scrutiny)

---

### SD-2: DfT Permanent Secretary - Accounting Officer Accountability

**Stakeholder**: Permanent Secretary, Department for Transport

**Driver Category**: RISK / COMPLIANCE

**Driver Statement**:
Ensure the programme follows proper governance, achieves value for money, and avoids reputational damage to the Department. As Accounting Officer, the Permanent Secretary is personally accountable to Parliament (via PAC - Public Accounts Committee) for the proper use of public funds and must avoid NAO criticism or ministerial blame for programme failures.

**Context & Background**:
- Personal accountability under Managing Public Money framework
- NAO scrutiny of all major government IT programmes (£10M+ threshold)
- Public Accounts Committee hearings require personal testimony if programme fails
- Historical DfT IT project challenges (e.g., Driver and Vehicle Licensing Agency modernization)
- Cross-government reputation for civil service competence
- Career impact of high-profile programme failures

**Driver Intensity**: CRITICAL

**Enablers**:
- Robust programme governance (Gateway reviews, IPA oversight)
- Experienced Senior Responsible Owner (SRO) with successful delivery track record
- Independent assurance (NAO, IPA, external reviews)
- Clear benefits realization plan with measurable KPIs
- Risk management framework with escalation to DfT Board
- Compliance with HMT Green Book (business case), GDS Service Standard, Technology Code of Practice

**Blockers**:
- Inadequate governance or risk management
- SRO lacking major programme delivery experience
- Optimism bias in business case (overstated benefits, understated costs)
- Scope creep or budget overruns
- Negative IPA or NAO reviews
- Lack of contingency planning

**Related Stakeholders**:
- **Aligned**: CFO (financial controls), NAO (value for money), IPA (project delivery standards)
- **Potential Conflict**: Minister (wants speed vs. Perm Sec wants assurance), CDTO (wants modern tech vs. Perm Sec wants proven tech)

---

### SD-3: Chief Data & Technology Officer (CDTO) - Digital Transformation & Legacy Modernization

**Stakeholder**: Executive Sponsor, Chief Data & Technology Officer, National Highways

**Driver Category**: STRATEGIC / PERSONAL

**Driver Statement**:
Transform National Highways into a data-driven, digitally-enabled organization to unlock strategic value from £60 billion infrastructure assets. The CDTO needs this programme to succeed to demonstrate the value of technology investment, attract digital talent, and establish National Highways as an exemplar of public sector digital maturity.

**Context & Background**:
- Legacy Oracle database architecture (10+ years old) reaching end of support
- Fragmented data silos preventing cross-domain insights
- Difficulty recruiting data engineers to work on outdated technology
- Comparisons with private sector (Transport for London's data maturity)
- Board pressure to demonstrate technology ROI
- Personal career reputation tied to delivery of this flagship programme
- Industry recognition opportunities (awards, conference speaking, thought leadership)

**Driver Intensity**: CRITICAL

**Enablers**:
- Executive Board support and protected budget
- Authority to make architectural decisions without excessive committee approvals
- Flexibility to adopt modern technology patterns (data mesh, event streaming, cloud-native)
- Access to skilled external consultancies for capability gaps
- Success metrics tied to business outcomes (not just technical delivery)
- Industry recognition of National Highways as a technology innovator

**Blockers**:
- Budget cuts or funding uncertainty
- Resistance from operational teams comfortable with legacy systems
- Technology choice constraints (mandated vendors, restrictive procurement)
- Inadequate cloud skills in existing workforce
- Scope limitations preventing necessary modernization
- Blame for any service disruptions during migration

**Related Stakeholders**:
- **Aligned**: Enterprise Architects (modern architecture), Data Engineers (modern tech stack), GDS (digital transformation)
- **Potential Conflict**: COO (operational stability concerns), CFO (cost pressures), Infrastructure Teams (legacy system comfort)

---

### SD-4: Chief Information Security Officer (CISO) - Security & Risk Management

**Stakeholder**: Chief Information Security Officer, National Highways

**Driver Category**: RISK / COMPLIANCE

**Driver Statement**:
Protect OFFICIAL-SENSITIVE data (CCTV footage, ANPR data, infrastructure vulnerabilities) and ensure critical national infrastructure resilience against cyber threats. CISO is personally accountable for any security breaches and faces NCSC oversight for CNI (Critical National Infrastructure) security standards.

**Context & Background**:
- National Highways designated as Critical National Infrastructure (CNI) operator
- NCSC CAF (Cyber Assessment Framework) mandatory compliance
- Recent high-profile attacks on critical infrastructure (Colonial Pipeline, etc.)
- OFFICIAL-SENSITIVE data classification requires enhanced controls
- Threat intelligence: state-sponsored actors targeting UK infrastructure
- Personal accountability for security incidents (potential dismissal, reputational damage)
- Regulatory oversight from NCSC and ICO

**Driver Intensity**: CRITICAL (NON-NEGOTIABLE)

**Enablers**:
- Security architecture reviews at all design gates
- Budget for security controls (SIEM, threat detection, penetration testing)
- Zero-trust architecture principles adopted
- Security-cleared staff for OFFICIAL-SENSITIVE data handling
- Adequate testing time (penetration testing, security reviews)
- NCSC guidance compliance from day one

**Blockers**:
- Pressure to accelerate delivery cutting security review time
- Inadequate security budget ("security is overhead" mindset)
- Developer resistance to security controls ("slows us down")
- Cloud provider security controls not meeting OFFICIAL-SENSITIVE requirements
- Third-party API integrations introducing security vulnerabilities
- Legacy system security debt carried forward to new architecture

**Related Stakeholders**:
- **Aligned**: DPO (data protection), NCSC (CNI security), DfT Perm Sec (risk management)
- **Potential Conflict**: CDTO (wants modern cloud tech), Minister (wants fast delivery), Data Engineers (security friction)

---

### SD-5: Chief Financial Officer (CFO) - Budget Control & ROI

**Stakeholder**: Chief Financial Officer, National Highways

**Driver Category**: FINANCIAL

**Driver Statement**:
Deliver the data architecture modernization within approved budget (£45M over 3 years) while achieving measurable operational efficiency gains to offset investment costs. CFO must demonstrate to the Board and Treasury that technology investment delivers quantifiable value for money.

**Context & Background**:
- National Highways annual budget: £3.8 billion (government funding)
- Technology investment competes with road maintenance and capital projects
- Board pressure to reduce operational costs (traffic management centre staffing, manual data processing)
- Treasury spending review pressures (potential budget cuts)
- Historical IT project cost overruns creating CFO skepticism
- Personal accountability for financial controls and budget management

**Driver Intensity**: HIGH

**Enablers**:
- Clear business case with quantified benefits (£15M annual operational savings target)
- Phased investment with stage gates (can stop funding if benefits don't materialize)
- Monthly financial tracking with variance explanations
- Quick wins showing early ROI (e.g., automation reducing manual effort)
- External benchmarking showing competitive unit costs
- Operational budget reallocation as efficiency gains realized

**Blockers**:
- Scope creep increasing costs beyond business case
- Delayed benefits realization (costs incurred but savings not achieved)
- Hidden costs emerging (e.g., data migration complexity, change management)
- Vendor lock-in creating long-term cost exposure
- Cloud consumption costs exceeding forecasts
- Lack of financial transparency or controls

**Related Stakeholders**:
- **Aligned**: Treasury (value for money), NAO (financial scrutiny), DfT Perm Sec (accounting officer controls)
- **Potential Conflict**: CDTO (wants capability investment), Data Engineers (want best-in-class tools), Procurement (longer competitive processes)

---

### SD-6: Chief Operating Officer (COO) - Operational Continuity & Service Delivery

**Stakeholder**: Chief Operating Officer, National Highways

**Driver Category**: OPERATIONAL / RISK

**Driver Statement**:
Maintain 99.95% operational availability of traffic management systems throughout the migration, ensuring zero disruption to critical services (incident management, roadworks coordination, emergency service integration). COO is accountable for operational performance KPIs and faces public/media scrutiny for any service failures.

**Context & Background**:
- 7 regional control rooms operate 24/7/365 managing incidents, roadworks, variable message signs
- Single system outage can impact millions of drivers (e.g., M25 closure affecting 200,000 vehicles/day)
- Operational KPIs reported to DfT monthly (incident response times, information accuracy)
- Media amplification of any failures ("National Highways IT system leaves drivers stranded")
- Staff resistance to change (control room operators comfortable with legacy systems)
- Operational teams skeptical of technology projects ("new system will be worse")

**Driver Intensity**: CRITICAL

**Enablers**:
- Comprehensive user acceptance testing with operational staff
- Parallel running of legacy and new systems during transition
- Extensive training and change management for control room operators
- Rollback capability if new system underperforms
- Gradual regional rollout (pilot in one region, scale to all seven)
- 24/7 support during cutover periods
- Operational staff involvement in design (co-creation, not imposition)

**Blockers**:
- Big-bang migration approach with high risk
- Inadequate training or change management
- New system lacking feature parity with legacy (lost functionality)
- Performance degradation (slower response times, higher latency)
- Poor user experience causing operational staff resistance
- Cutover during high-traffic periods (bank holidays, summer travel season)

**Related Stakeholders**:
- **Aligned**: Regional Control Room Managers (frontline users), Emergency Services (service continuity), CDTO (shared success metric)
- **Potential Conflict**: Data Engineers (want clean break from legacy), CDTO (wants rapid migration), Minister (wants visible progress)

---

### SD-7: Regional Control Room Managers - User Experience & Operational Efficiency

**Stakeholder**: Regional Control Room Managers (7 regions across England)

**Driver Category**: OPERATIONAL / PERSONAL

**Driver Statement**:
Ensure new systems improve (or at minimum maintain) operational efficiency for managing incidents, roadworks, and traffic information. Control room managers need tools that help their teams respond faster to incidents, reduce manual workload, and provide better information to drivers - while avoiding disruption to established workflows.

**Context & Background**:
- Control room operators manage 250,000+ incidents per year across strategic road network
- Average incident response time: 18 minutes (target: <15 minutes)
- Manual data entry into multiple legacy systems creates workload and errors
- Frustration with siloed systems (incident data not automatically linked to traffic sensors)
- Historical experience: previous IT projects promised improvements but delivered worse user experience
- Personal accountability for regional operational KPIs
- Control room operator retention challenges (stressful role, shift work)

**Driver Intensity**: HIGH

**Enablers**:
- Early and continuous user involvement in design (co-creation workshops)
- Simplified workflows reducing manual effort (single incident entry, auto-propagation)
- Unified dashboards replacing multiple legacy screens
- Real-time data quality improvements (accurate traffic sensor data)
- Mobile-first design for Traffic Officers in field
- Training delivered by operational staff (peer-to-peer, not external consultants)
- Recognition of operational input (control room staff credited for design improvements)

**Blockers**:
- Technology team designing in isolation without user input
- Overcomplicated interfaces requiring extensive training
- Lost functionality from legacy systems (operators' "workarounds" not captured)
- Performance issues (slow screen load times under high load)
- Reliability issues (system unavailable during critical incidents)
- Inadequate training time (operators expected to learn on the job)

**Related Stakeholders**:
- **Aligned**: COO (operational performance), Traffic Officers (field users), Emergency Services (incident coordination)
- **Potential Conflict**: Data Engineers (want modern UX paradigms), Enterprise Architects (want standardization vs. regional customization)

---

### SD-8: Data Protection Officer (DPO) - UK GDPR Compliance & Privacy

**Stakeholder**: Data Protection Officer, National Highways

**Driver Category**: COMPLIANCE / RISK

**Driver Statement**:
Ensure all data processing complies with UK GDPR and addresses privacy risks, particularly for ANPR (Automatic Number Plate Recognition) data containing vehicle registration plates. DPO must protect National Highways from ICO enforcement action (fines up to 4% of turnover or £17.5 million) and reputational damage from privacy breaches.

**Context & Background**:
- ANPR cameras capture vehicle registration plates for journey time calculation
- UK GDPR Article 35 requires DPIA for large-scale processing of special category data
- ICO enforcement action risk: vehicle tracking creates privacy concerns
- Public concern about surveillance ("Big Brother watching drivers")
- Legal requirement: anonymize registration plates after 24 hours (retention minimization)
- Recent ICO fines for other public bodies (£4M+ for data breaches)
- Personal accountability under UK GDPR (DPO must escalate non-compliance)

**Driver Intensity**: CRITICAL (LEGAL REQUIREMENT)

**Enablers**:
- DPIA completed and approved before any ANPR data processing
- Privacy-by-design architecture (anonymization at source, minimal data collection)
- Clear legal basis for processing (public task, legitimate interests)
- Automated deletion workflows (registration plates deleted after 24 hours)
- Data subject rights processes (access requests, erasure requests)
- Privacy notices updated and published
- ICO consultation for high-risk processing

**Blockers**:
- Scope creep into surveillance use cases (police access to ANPR data)
- Inadequate anonymization (re-identification risks)
- Extended data retention beyond legal justification
- Third-party data sharing without legal basis (commercial navigation apps)
- Lack of data subject rights automation
- Insufficient DPIA rigor (box-ticking exercise)

**Related Stakeholders**:
- **Aligned**: CISO (data protection controls), ICO (regulatory compliance), Civil Liberties Groups (privacy advocacy)
- **Potential Conflict**: Data Analysts (want granular data), Commercial Partners (want access to data), Emergency Services (want vehicle tracking)

---

### SD-9: Government Digital Service (GDS) - Service Standard Compliance

**Stakeholder**: Government Digital Service (Cabinet Office)

**Driver Category**: COMPLIANCE / STRATEGIC

**Driver Statement**:
Ensure the data platform and public-facing services meet GDS Service Standard (14 points) and Technology Code of Practice (13 points). GDS wants National Highways to be an exemplar of government digital best practice, demonstrating that large-scale data infrastructure can be delivered with user-centered design and open standards.

**Context & Background**:
- Mandatory GDS Service Assessment for all public-facing government services
- Assessment gates: Alpha, Beta, Live (must pass to proceed)
- Historical failure rate: ~30% of services fail first assessment
- Cross-government learning: successful assessments shared as case studies
- GDS pressure to demonstrate value of Service Standard to skeptical departments
- Technology Code of Practice compliance required for all government technology spending
- Open standards advocacy (avoid vendor lock-in, enable interoperability)

**Driver Intensity**: HIGH

**Enablers**:
- User research with actual drivers, emergency services, local authorities (not assumptions)
- Open API specifications (OpenAPI 3.x, DATEX II standards)
- Accessibility compliance (WCAG 2.2 Level AA)
- Open source contributions (publish reusable components)
- Continuous user feedback loops during Beta
- Public performance dashboard (transaction volumes, satisfaction scores)
- Agile delivery with frequent releases (not waterfall)

**Blockers**:
- Technology-first approach without user research
- Proprietary protocols or closed APIs
- Accessibility failures (screen reader incompatibility)
- Lack of user testing with real road users
- Waterfall delivery preventing iterative improvement
- Missing performance data or user satisfaction metrics

**Related Stakeholders**:
- **Aligned**: Open Data Advocates (transparency), CDTO (digital transformation), Minister (demonstrate good governance)
- **Potential Conflict**: Procurement (GDS wants competition, Procurement wants single supplier efficiency), Legacy Teams (GDS wants modern tech)

---

### SD-10: HM Treasury - Value for Money & Spending Controls

**Stakeholder**: HM Treasury (Central Government)

**Driver Category**: FINANCIAL / COMPLIANCE

**Driver Statement**:
Ensure the £45M investment delivers quantifiable economic value exceeding costs (positive Net Present Value) and follows Green Book business case methodology. Treasury must demonstrate prudent use of taxpayer funds and prevent public sector IT project cost overruns that undermine confidence in government technology investment.

**Context & Background**:
- Treasury Green Book: mandatory five-case business case model (Strategic, Economic, Commercial, Financial, Management)
- Spending Review pressures: all departments face potential budget cuts
- Historical government IT failures (Universal Credit, NHS IT) creating Treasury skepticism
- Public Accounts Committee scrutiny of major projects (£10M+ threshold)
- Optimism bias adjustment required (reduce benefits by 25%, increase costs by 15%)
- Gateway review requirements at key decision points
- Value for Money framework: Economy, Efficiency, Effectiveness

**Driver Intensity**: HIGH

**Enablers**:
- Robust economic case with quantified benefits (time savings, efficiency gains, safety improvements)
- Benefits realization tracking (monthly reporting of actual vs. forecast benefits)
- Competitive procurement demonstrating market testing
- Stage-gate funding (release budget only when milestones achieved)
- Independent assurance (IPA reviews, NAO value for money studies)
- Benchmarking against comparators (other transport authorities, private sector)
- Risk-adjusted forecasts (pessimistic, realistic, optimistic scenarios)

**Blockers**:
- Overstated benefits in business case (lack of evidence)
- Cost overruns without corresponding benefit increases
- Sole-source procurement without market testing
- Benefits not realized (efficiency gains not achieved)
- Lack of financial controls (budget tracking, variance reporting)
- No exit strategy if programme underperforms

**Related Stakeholders**:
- **Aligned**: CFO (budget controls), NAO (value for money audits), DfT Perm Sec (accounting officer)
- **Potential Conflict**: CDTO (wants capability investment), Minister (wants fast delivery potentially compromising VFM)

---

### SD-11: Local Highway Authorities - Data Interoperability & Collaboration

**Stakeholder**: 152 Local Highway Authorities (County Councils, Unitary Authorities)

**Driver Category**: OPERATIONAL / STRATEGIC

**Driver Statement**:
Enable seamless data exchange between National Highways (strategic roads) and local authority systems (local roads) to provide unified journey planning and coordinated roadworks scheduling for drivers. Local authorities need National Highways data to improve their traffic management while contributing local road data to create complete network coverage.

**Context & Background**:
- Drivers don't distinguish between strategic and local roads (want unified journey planning)
- Roadworks coordination across boundaries prevents simultaneous closures creating gridlock
- Local authorities have diverse legacy systems (180+ different traffic management systems)
- Political tension: central government (National Highways) vs. local government (councils)
- Budget constraints at local level (limited IT investment)
- Local authority concern about data quality requirements (fear of being judged on data quality)
- National Transport Information System (NTIS) historic underinvestment

**Driver Intensity**: MEDIUM

**Enablers**:
- Open API standards enabling low-cost integration (not bespoke point-to-point)
- Financial support for local authorities to upgrade systems (DfT funding)
- Data quality support (not just mandates) - training, tooling, best practice sharing
- Federated governance model (local autonomy within national standards)
- Recognition of local authority contributions (public credit for data sharing)
- Use case demonstration (show tangible benefits to local authorities)

**Blockers**:
- Costly integration requirements local authorities can't afford
- Central mandates without funding ("unfunded mandate")
- Data quality criticism damaging local authority reputation
- One-way data flow (National Highways takes local data, provides nothing in return)
- Lack of local authority representation in governance
- Technical complexity preventing participation

**Related Stakeholders**:
- **Aligned**: Drivers (public benefit), DfT (integrated transport), GDS (interoperability)
- **Potential Conflict**: CDTO (wants high data quality standards), Enterprise Architects (want standardization), Local Government Association (defend local autonomy)

---

### SD-12: Emergency Services - Critical Incident Response

**Stakeholder**: Police, Ambulance, Fire Services (Blue Light Services)

**Driver Category**: OPERATIONAL / PUBLIC SAFETY

**Driver Statement**:
Ensure real-time access to accurate incident information, traffic conditions, and CCTV footage to enable rapid emergency response and save lives. Emergency services need reliable, fast access to National Highways data to route ambulances optimally, coordinate police traffic management, and respond to major incidents.

**Context & Background**:
- Ambulance service target: 90% of Category 1 (life-threatening) calls reached within 7 minutes
- Traffic congestion delays cost lives (every minute delay reduces survival probability)
- Major incident response requires coordination across National Highways, Police, Fire, Ambulance
- CCTV footage used for incident verification and criminal investigations
- Emergency services have separate secure networks (not public internet)
- Data sharing legal basis: public task, vital interests (saving lives)

**Driver Intensity**: CRITICAL (PUBLIC SAFETY)

**Enablers**:
- Dedicated emergency services API with priority access (no rate limiting)
- Real-time incident alerts pushed to emergency services CAD (Computer Aided Dispatch) systems
- CCTV live feeds accessible to emergency control rooms
- Integration with police ANPR systems (authorized use)
- 99.99% availability SLA for emergency services interfaces
- Secure network connectivity (PSN - Public Services Network)
- Joint exercises testing data integration during major incidents

**Blockers**:
- Public API rate limits blocking emergency service access during major incidents
- Data latency preventing real-time response (stale incident data)
- CCTV access restrictions preventing incident verification
- Complex authentication preventing rapid access during emergencies
- System unavailability during critical incidents
- Data quality issues (inaccurate incident locations)

**Related Stakeholders**:
- **Aligned**: COO (incident management), Regional Control Rooms (incident coordination), CISO (secure data sharing)
- **Potential Conflict**: DPO (privacy concerns on CCTV access), Open Data Advocates (want public CCTV access, emergency services want exclusive access)

---

### SD-13: General Public (Road Users) - Journey Reliability & Information

**Stakeholder**: 45 million daily journeys on England's strategic road network

**Driver Category**: CUSTOMER / PUBLIC VALUE

**Driver Statement**:
Access accurate, real-time traffic information to plan journeys, avoid congestion, and arrive on time. Road users expect modern, app-based journey planning comparable to private sector services (Google Maps, Waze) and are frustrated by inaccurate roadworks information or unexpected delays.

**Context & Background**:
- UK commuters lose average 115 hours/year to traffic congestion
- Economic cost of congestion: £9 billion annually
- Public expectations set by private sector (Google Maps real-time accuracy)
- Frustration with National Highways when information is inaccurate ("roadworks finished but still shown on website")
- Social media amplification of complaints (#NationalHighwaysUTurn trends when major delays occur)
- Accessibility requirements: elderly, disabled users need inclusive design
- Digital divide: not all users have smartphones (need website, variable message signs)

**Driver Intensity**: HIGH (via political pressure on Minister)

**Enablers**:
- Mobile-first responsive design for journey planning website
- Open API enabling integration with Google Maps, Waze, Apple Maps
- Real-time accuracy (data freshness <2 minutes)
- Predictive journey times using AI/ML (not just current conditions)
- Accessibility compliance (screen readers, high contrast, text-to-speech)
- Variable message signs updated with real-time data (for non-smartphone users)
- User feedback loop (report inaccurate information, see corrections)

**Blockers**:
- Outdated batch data feeds (hourly updates, not real-time)
- Inaccurate roadworks information (scheduled completion dates not updated)
- Poor mobile experience (desktop-only design)
- Accessibility failures excluding disabled users
- API unavailable or unreliable (breaking third-party apps)
- Complex website navigation (can't find journey planning quickly)

**Related Stakeholders**:
- **Aligned**: Minister (public satisfaction drives political success), Navigation App Providers (need data quality), GDS (user-centered design)
- **Potential Conflict**: COO (operational stability vs. real-time data freshness), CISO (security vs. open data access)

---

### SD-14: National Audit Office (NAO) - Value for Money & Governance

**Stakeholder**: National Audit Office (Parliamentary Auditor)

**Driver Category**: COMPLIANCE / ACCOUNTABILITY

**Driver Statement**:
Provide independent assurance to Parliament that the programme delivers value for money, follows proper governance, and achieves stated benefits. NAO must protect taxpayer interests by identifying waste, inefficiency, or optimism bias in major government programmes.

**Context & Background**:
- Statutory responsibility to audit all government spending
- Major Projects Portfolio: all programmes £100M+ receive NAO scrutiny
- Value for Money framework: Economy (minimize cost), Efficiency (maximize output/input), Effectiveness (achieve objectives)
- Historical NAO reports critical of government IT programmes (Universal Credit, NHS IT)
- Public Accounts Committee uses NAO reports to question Accounting Officers
- NAO publishes reports publicly (media coverage of failures)
- Cross-government learning: NAO reports used as case studies of good/bad practice

**Driver Intensity**: MEDIUM (influential but not decision-maker)

**Enablers**:
- Transparent benefits realization tracking (actual vs. forecast with variance explanations)
- Robust financial controls (audit trail, procurement competition, contract management)
- Risk management demonstrating mitigation of major risks
- Governance evidence (decision logs, Gateway reviews, steering group minutes)
- Independent assurance (IPA reviews, external quality assurance)
- Honest reporting of issues (not hiding problems)
- Evidence-based decision-making (not gut feel or vendor influence)

**Blockers**:
- Opaque decision-making (lack of audit trail)
- Optimism bias (overstated benefits, understated risks)
- Benefits not realized (promised savings not achieved)
- Inadequate governance (decision-making bypassing proper authorities)
- Sole-source procurement without justification
- Cost overruns without re-baselining business case

**Related Stakeholders**:
- **Aligned**: DfT Perm Sec (accounting officer accountability), Treasury (VFM), Public Accounts Committee (parliamentary oversight)
- **Potential Conflict**: CDTO (NAO conservatism may slow innovation), Minister (NAO reports can damage political reputation)

---

### SD-15: Data Engineers & Technical Teams - Modern Technology & Career Development

**Stakeholder**: Data Engineering Teams, Platform Engineers, Cloud Architects

**Driver Category**: PERSONAL / OPERATIONAL

**Driver Statement**:
Work with modern, industry-standard technology stacks that develop marketable skills and enable efficient delivery. Data engineers are frustrated with legacy Oracle databases and want cloud-native, open-source technologies that are enjoyable to work with and enhance their career prospects.

**Context & Background**:
- Difficulty recruiting data engineers to work on 10-year-old Oracle databases
- Private sector offers higher salaries for modern tech skills (Azure, Kafka, Databricks)
- Technical debt in legacy systems makes development slow and frustrating
- Engineer retention risk: talented engineers leave for private sector roles
- Professional development: engineers want conference attendance, certification, community participation
- Job satisfaction tied to technology choices (modern stack = engaged engineers)
- Industry reputation: National Highways not seen as technology innovator

**Driver Intensity**: MEDIUM (indirect impact via recruitment/retention)

**Enablers**:
- Modern technology stack (cloud-native, event streaming, data mesh)
- Technology choice autonomy within architecture principles
- Professional development budget (conferences, certifications, training)
- Open source contributions (public GitHub repos, conference talks)
- Agile delivery practices (not waterfall)
- Flexible working (remote work, core hours)
- Recognition for technical excellence (innovation awards, external speaking)

**Blockers**:
- Locked into legacy technologies (Oracle, on-premises infrastructure)
- Rigid technology mandates preventing innovation
- No professional development budget
- Waterfall delivery creating frustration
- Micromanagement preventing technical autonomy
- Inability to use open source (restrictive procurement)

**Related Stakeholders**:
- **Aligned**: CDTO (digital transformation), Enterprise Architects (modern patterns), GDS (open standards)
- **Potential Conflict**: CISO (security constraints on technology choice), COO (operational stability concerns), Procurement (competitive process constraints)

---

## Driver-to-Goal Mapping

### Goal G-1: Deliver Public-Facing Open Data API within 12 Months

**Derived From Drivers**: SD-1 (Minister - Political Delivery), SD-3 (CDTO - Digital Transformation), SD-9 (GDS - Service Standard), SD-13 (Public - Journey Information)

**Goal Owner**: Director of Data & Analytics

**Goal Statement**:
Launch a public-facing, RESTful API providing real-time traffic flow data, incident information, and roadworks schedules for England's strategic road network by November 2026, achieving GDS Alpha assessment pass and onboarding 10+ third-party developers (including Google, Waze, TomTom).

**Why This Matters**:
This goal satisfies multiple high-intensity stakeholder drivers:
- **Minister**: Visible manifesto delivery demonstrating infrastructure investment (parliamentary announcement, positive media)
- **CDTO**: Flagship digital transformation initiative showcasing National Highways innovation
- **GDS**: Exemplar of Service Standard compliance and open data commitment
- **Public**: Improved journey planning through third-party app integration

**Success Metrics**:
- **Primary Metric**: API live in production with ≥3 third-party apps consuming data (Google Maps, Waze, TomTom)
- **Secondary Metrics**:
  - GDS Alpha assessment passed (14-point Service Standard)
  - API uptime ≥99.9% (measured monthly)
  - Average API response latency <200ms (p95)
  - API developer satisfaction score ≥4.0/5.0 (quarterly survey)
  - Public API documentation completeness score ≥90% (independent assessment)

**Baseline**:
- Current State: No public API exists; third parties scrape HTML website for data (inaccurate, slow, fragile)
- Current Journey Planning: Google Maps uses 15-minute delayed traffic data (inaccurate)

**Target**:
- November 2026: Production API with real-time data (<2 min latency), OpenAPI 3.x specification, developer portal with sandbox

**Measurement Method**:
- API Gateway metrics (uptime, latency, request volume per consumer)
- Developer portal analytics (registrations, sandbox usage, support tickets)
- GDS assessment report (pass/fail with assessor feedback)
- Third-party app integration confirmations (signed agreements with Google, Waze, TomTom)

**Dependencies**:
- Azure cloud infrastructure provisioned (UK South region)
- Data mesh Traffic domain data product published (real-time sensor feeds)
- API gateway platform deployed and configured
- Developer documentation written and reviewed
- GDS Service Assessment booked (6-week lead time)

**Risks to Achievement**:
- **R-1 Data Quality Issues**: Sensor data quality insufficient for public API (mitigation: 6-month data quality improvement programme)
- **R-2 Third-Party Reluctance**: Navigation apps don't adopt API (mitigation: early partnership discussions, pilot with one provider)
- **R-3 GDS Assessment Failure**: Service Standard assessment fails (mitigation: pre-assessment with GDS, iterative improvements)
- **R-4 Security Vulnerabilities**: API security issues delay launch (mitigation: penetration testing, security review gates)

---

### Goal G-2: Achieve 99.95% Platform Availability During Migration

**Derived From Drivers**: SD-6 (COO - Operational Continuity), SD-7 (Control Rooms - User Experience), SD-12 (Emergency Services - Critical Response)

**Goal Owner**: Chief Operating Officer

**Goal Statement**:
Maintain ≥99.95% availability of all critical traffic management systems throughout the 18-month migration from legacy Oracle databases to cloud-native data platform, with zero incidents caused by system failures impacting emergency service response or public safety.

**Why This Matters**:
- **COO**: Operational performance KPIs reported to DfT; service failures damage reputation and public safety
- **Control Rooms**: Frontline users need reliable systems for 24/7 incident management
- **Emergency Services**: Downtime delays ambulance response potentially costing lives
- **Public**: System failures cause inaccurate journey information leading to avoidable congestion

**Success Metrics**:
- **Primary Metric**: 99.95% uptime measured monthly (max 21.9 minutes unplanned downtime/month)
- **Secondary Metrics**:
  - Zero public safety incidents attributed to system failures
  - Zero emergency service complaints about data unavailability
  - Mean Time To Recovery (MTTR) <15 minutes for critical system failures
  - Regional control room user satisfaction ≥4.0/5.0 during migration (monthly survey)
  - Planned maintenance windows ≤2 hours/month (scheduled overnight)

**Baseline**:
- Current Legacy System Availability: 99.7% (13 hours downtime/year)
- Current MTTR: 45 minutes average

**Target**:
- 99.95% availability throughout migration (improvement over legacy)
- MTTR <15 minutes (3x improvement)

**Measurement Method**:
- Application Performance Monitoring (APM) - synthetic transactions every 60 seconds
- Regional control room incident reports (manual logging)
- Emergency services liaison feedback (monthly meetings)
- User satisfaction surveys (control room operators, monthly)

**Dependencies**:
- Parallel running of legacy and new systems (6-month overlap)
- Automated failover between systems tested and validated
- 24/7 on-call support during migration phases
- Comprehensive rollback procedures documented and rehearsed
- Regional phased rollout (pilot region 1, scale to remaining 6)

**Risks to Achievement**:
- **R-5 Migration Complexity**: Unforeseen data migration issues causing extended outages (mitigation: extensive pre-production testing, parallel running)
- **R-6 Peak Load Failures**: New system fails under peak load during major incidents (mitigation: load testing at 2x expected peak)
- **R-7 Integration Failures**: Third-party integrations (emergency services CAD systems) break during migration (mitigation: integration testing, phased rollout)

---

### Goal G-3: Reduce Operational Costs by £15M Annually by Year 3

**Derived From Drivers**: SD-5 (CFO - Budget Control), SD-10 (Treasury - Value for Money), SD-14 (NAO - Governance)

**Goal Owner**: Chief Financial Officer

**Goal Statement**:
Achieve £15M annual operational cost savings by Year 3 through automation of manual data processing, reduced legacy system licensing costs, and operational efficiency gains from unified data platform. Demonstrate quantified ROI exceeding investment costs within 5-year timeframe.

**Why This Matters**:
- **CFO**: Board pressure to reduce operational costs; technology investment must pay for itself
- **Treasury**: Spending review pressures require demonstrable value for money
- **NAO**: Audit scrutiny of benefits realization; need evidence of actual (not just forecast) savings

**Success Metrics**:
- **Primary Metric**: £15M annual operational cost savings achieved by Year 3 (verified by Finance)
- **Secondary Metrics**:
  - Legacy system decommissioning: £8M annual license/support cost elimination
  - Manual data processing reduction: 15 FTE (£0.75M annual staff cost redeployment)
  - Infrastructure efficiency: 40% reduction in data center costs (£4M annual saving)
  - Operational efficiency: 25% reduction in incident response time (£2.25M economic value)
  - Benefits realization tracking: ≥90% of forecast benefits achieved

**Baseline**:
- Current Annual Operational Costs:
  - Legacy Oracle licenses & support: £8M
  - Data center infrastructure: £10M
  - Manual data processing: 15 FTE @ £50k = £0.75M
  - Total baseline: £18.75M relevant costs

**Target**:
- Year 1: £3M savings (legacy system reduction, early automation)
- Year 2: £9M cumulative savings (infrastructure migration, further automation)
- Year 3: £15M annual run-rate savings (full legacy decommissioning, optimized cloud costs)

**Measurement Method**:
- Monthly financial tracking in Oracle Finance system (actual vs. forecast)
- FTE redeployment tracking (staff moved to higher-value roles, not redundancies)
- Cloud cost monitoring (Azure Cost Management dashboards)
- Benefits realization register (signed off by Finance monthly)
- External audit validation (NAO review of benefits claims)

**Dependencies**:
- Successful migration enabling legacy system decommissioning
- Staff redeployment strategy (no redundancies - redeploy to other National Highways roles)
- Cloud cost optimization (FinOps practices, reserved instances)
- Automation of manual workflows (data quality checks, reporting)

**Risks to Achievement**:
- **R-8 Cloud Cost Overruns**: Cloud consumption exceeds forecasts negating savings (mitigation: FinOps governance, cost alerts, reserved capacity)
- **R-9 Delayed Legacy Decommissioning**: Legacy systems kept running longer than planned (mitigation: clear decommissioning plan, executive commitment)
- **R-10 Optimism Bias**: Forecast savings overstated (mitigation: conservative estimates, external validation)

---

### Goal G-4: Achieve Full UK GDPR Compliance with ICO Approval

**Derived From Drivers**: SD-4 (CISO - Security), SD-8 (DPO - Privacy), SD-2 (Perm Sec - Risk Avoidance)

**Goal Owner**: Data Protection Officer

**Goal Statement**:
Complete and obtain ICO approval for Data Protection Impact Assessment (DPIA) covering ANPR vehicle tracking and CCTV processing, implement automated anonymization of vehicle registration plates within 24 hours, and achieve zero ICO enforcement actions or data protection violations throughout programme delivery.

**Why This Matters**:
- **DPO**: Personal accountability for GDPR compliance; ICO enforcement action damages career and organization
- **CISO**: Data protection controls are foundational security requirement
- **Perm Sec**: ICO enforcement action (potential £17.5M fine) would trigger parliamentary scrutiny and NAO criticism

**Success Metrics**:
- **Primary Metric**: DPIA approved by ICO with no material concerns raised
- **Secondary Metrics**:
  - Zero ICO enforcement actions (warnings, fines, corrective orders)
  - 100% automated anonymization of vehicle registration plates within 24 hours (no manual processes)
  - Zero data subject complaints escalated to ICO
  - Privacy notice published and accessible (100% of website visitors can find it)
  - Data retention compliance: 100% of registration plate data deleted within 24 hours (automated verification)

**Baseline**:
- Current State: ANPR data retained indefinitely in legacy systems (non-compliant)
- No DPIA completed for vehicle tracking

**Target**:
- Q2 2026: DPIA submitted to ICO
- Q3 2026: ICO approval received, automated anonymization deployed
- Ongoing: Zero compliance violations

**Measurement Method**:
- ICO formal approval letter (documentary evidence)
- Automated compliance monitoring (data retention audit logs)
- Privacy impact assessments (quarterly reviews)
- Data subject access request tracking (volume, resolution time)
- ICO correspondence log (zero enforcement actions)

**Dependencies**:
- DPIA methodology training for project team
- Privacy-by-design architecture (anonymization at data ingestion)
- Legal basis assessment (public task vs. legitimate interests)
- ICO consultation engagement (proactive not reactive)
- Data retention automation (not manual deletion processes)

**Risks to Achievement**:
- **R-11 ICO Objections**: ICO raises material concerns about ANPR processing (mitigation: early consultation, privacy-enhancing technologies)
- **R-12 Data Breach**: Security incident exposing personal data during migration (mitigation: encryption, access controls, incident response plan)
- **R-13 Retention Non-Compliance**: Automated deletion fails, data retained beyond 24 hours (mitigation: compliance monitoring, alerts)

---

### Goal G-5: Pass GDS Service Assessment (Alpha and Beta)

**Derived From Drivers**: SD-9 (GDS - Service Standard), SD-1 (Minister - Political Delivery), SD-3 (CDTO - Digital Transformation)

**Goal Owner**: Director of Data & Analytics

**Goal Statement**:
Pass GDS Service Assessment at Alpha (by Q2 2026) and Beta (by Q4 2026) gates, demonstrating compliance with all 14 Service Standard points, with particular focus on user research, accessibility (WCAG 2.2 AA), and open standards (OpenAPI, DATEX II).

**Why This Matters**:
- **GDS**: Demonstrate Service Standard effectiveness; use National Highways as exemplar for other departments
- **Minister**: GDS assessment pass provides independent validation of good delivery for parliamentary questions
- **CDTO**: Showcase digital maturity and user-centered design approach

**Success Metrics**:
- **Primary Metric**: GDS Alpha assessment PASS (all 14 points met)
- **Secondary Metrics**:
  - User research conducted with ≥30 representative users (drivers, emergency services, local authorities)
  - Accessibility audit: 100% WCAG 2.2 Level AA compliance (automated + manual testing)
  - API specification published: OpenAPI 3.x with 100% endpoint documentation
  - User satisfaction: ≥80% of beta users rate service as "good" or "very good"
  - Assisted digital support: Non-digital channel available (phone support for non-internet users)

**Baseline**:
- Current State: No GDS assessment conducted; legacy service not assessed

**Target**:
- Q2 2026: Alpha assessment passed (early validation of approach)
- Q4 2026: Beta assessment passed (service ready for public launch)

**Measurement Method**:
- GDS assessment report (formal pass/fail decision with feedback)
- User research repository (recorded sessions, findings, design iterations)
- Accessibility audit report (third-party WCAG assessment)
- User satisfaction surveys (System Usability Scale scores)

**Dependencies**:
- User research capacity (user researchers recruited or contracted)
- GDS assessment booking (6-8 week lead time)
- Accessibility expertise (consultant or in-house)
- Iterative design sprints (Agile delivery enabling design improvements)

**Risks to Achievement**:
- **R-14 User Research Gaps**: Insufficient diversity in user research (e.g., missing disabled users, elderly users)
- **R-15 Accessibility Failures**: Complex data visualizations not screen-reader compatible
- **R-16 Assessment Delays**: GDS assessment team availability delays timeline

---

### Goal G-6: Onboard 5 Data Mesh Domain Products within 18 Months

**Derived From Drivers**: SD-3 (CDTO - Digital Transformation), SD-7 (Control Rooms - User Experience), SD-11 (Local Authorities - Interoperability)

**Goal Owner**: Chief Data & Technology Officer

**Goal Statement**:
Publish 5 domain-driven data products (Traffic Flow, Incidents, Roadworks, Assets, Weather) in federated data mesh architecture within 18 months, with each data product meeting defined SLAs for availability (99.9%), freshness (<2 min for real-time data), and quality (>99% completeness).

**Why This Matters**:
- **CDTO**: Data mesh architecture is the foundational transformation enabling all other goals
- **Control Rooms**: Unified data access replacing fragmented legacy systems
- **Local Authorities**: Standard interfaces enabling low-cost integration

**Success Metrics**:
- **Primary Metric**: 5 data products published in data catalog with SLAs
- **Secondary Metrics**:
  - Data product SLA compliance: ≥99% achievement of availability, freshness, quality SLAs
  - Cross-domain data consumption: ≥3 data products consumed by other domains (demonstrating interoperability)
  - Data catalog adoption: 100% of data products registered with metadata
  - Consumer satisfaction: ≥4.0/5.0 data product consumer survey score

**Baseline**:
- Current State: Siloed databases with no published data products, no SLAs, no catalog

**Target**:
- Month 6: 2 data products (Traffic, Incidents)
- Month 12: 4 data products (+ Roadworks, Assets)
- Month 18: 5 data products (+ Weather)

**Measurement Method**:
- Data catalog registration (metadata completeness)
- SLA monitoring dashboards (automated tracking)
- Consumer survey (quarterly feedback from data product users)

**Dependencies**:
- Data mesh platform infrastructure (data catalog, API gateway, event streaming)
- Domain teams trained on data product ownership model
- Federated governance council established

**Risks to Achievement**:
- **R-17 Domain Team Capacity**: Domain teams lack skills to build data products (mitigation: training, embedded consultants)
- **R-18 Data Quality Issues**: Legacy data quality insufficient for SLA compliance (mitigation: 6-month data quality improvement)

---

### Goal G-7: Train and Upskill 120 Staff in Cloud-Native Technologies

**Derived From Drivers**: SD-15 (Data Engineers - Career Development), SD-3 (CDTO - Digital Transformation), SD-2 (Perm Sec - Capability Building)

**Goal Owner**: Chief Data & Technology Officer

**Goal Statement**:
Upskill 120 National Highways technical staff (data engineers, platform engineers, architects) in cloud-native technologies (Azure, event streaming, data mesh, API design) within 18 months through training, certifications, and hands-on delivery, reducing reliance on external consultants and building sustainable internal capability.

**Why This Matters**:
- **Data Engineers**: Career development and marketable skills improve retention and job satisfaction
- **CDTO**: Build internal capability reducing long-term consultancy costs
- **Perm Sec**: Sustainable capability vs. dependency on external vendors

**Success Metrics**:
- **Primary Metric**: 120 staff complete training with ≥80 achieving professional certification (Azure, Databricks, Confluent)
- **Secondary Metrics**:
  - Staff retention: <10% attrition of trained staff (demonstrate training improves retention)
  - Consultant dependency reduction: 50% reduction in external FTEs by Year 2
  - Internal capability assessment: ≥70% of staff rated "proficient" or "expert" in cloud technologies (skills matrix)
  - Employee satisfaction: ≥4.0/5.0 satisfaction with professional development opportunities

**Baseline**:
- Current Skills: 85% of technical staff skilled only in legacy Oracle, on-premises infrastructure
- Current Consultant Dependency: 45 external FTEs (65% of delivery capacity)

**Target**:
- Month 12: 60 staff trained, 40 certified
- Month 18: 120 staff trained, 80 certified
- Year 2: External consultants reduced to 20 FTEs (30% of capacity)

**Measurement Method**:
- Training completion tracking (LMS - Learning Management System)
- Certification registry (Azure certifications, vendor certifications)
- Skills matrix assessment (self-assessment + manager validation quarterly)
- Staff retention metrics (HR system)

**Dependencies**:
- Training budget approved (£0.8M over 18 months)
- Vendor training partnerships (Microsoft, Databricks, Confluent)
- Learning time allocated (20% of staff time for learning)
- Hands-on delivery opportunities (real projects, not just theory)

**Risks to Achievement**:
- **R-19 Training Budget Cuts**: CFO cuts training budget due to cost pressures (mitigation: demonstrate ROI via consultant reduction)
- **R-20 Attrition After Training**: Trained staff leave for private sector roles (mitigation: competitive salaries, interesting projects, recognition)

---

## Goal-to-Outcome Mapping

### Outcome O-1: 20% Reduction in Journey Time Variability for Road Users

**Supported Goals**: G-1 (Open Data API), G-6 (Data Mesh Products)

**Outcome Statement**:
Reduce journey time variability on strategic road network by 20% (measured by coefficient of variation in journey times) within 18 months of API launch, providing 45 million daily road users with more reliable, predictable journeys through improved real-time information and third-party app integration.

**Measurement Details**:
- **KPI**: Journey Time Reliability Index (Coefficient of Variation = std dev / mean journey time)
- **Current Value**: 0.35 (high variability - journeys unpredictable)
- **Target Value**: 0.28 (20% reduction - more reliable journeys)
- **Measurement Frequency**: Monthly (calculated from sensor data)
- **Data Source**: Traffic sensor network (10,000 sensors measuring journey times every 5 minutes)
- **Report Owner**: Head of Network Performance

**Business Value**:
- **Economic Impact**: £1.8 billion annual economic value (reduced congestion cost from better route choices)
  - Methodology: 45M daily journeys × 10% avoid congestion via better info × 5 min time saving × £15/hour value of time × 250 working days
- **Strategic Impact**: Political capital for Minister (quantified public benefit for parliamentary questions)
- **Customer Impact**: User satisfaction increase (reliable arrivals for work, appointments)
- **Social Impact**: Reduced stress and frustration for drivers (wellbeing benefit)

**Timeline**:
- **Phase 1 (Months 1-6)**: Baseline measurement established, API launched, initial third-party integrations
  - Target: 5% improvement (early adopters using new API data)
- **Phase 2 (Months 7-12)**: Mainstream adoption, Google Maps integration live
  - Target: 12% improvement (30% of drivers using apps with real-time National Highways data)
- **Phase 3 (Months 13-18)**: Full adoption, behavioral change embedded
  - Target: 20% improvement (50% of drivers using apps, making better route choices)
- **Sustainment (Year 2+)**: Maintain 20% improvement, continuous data quality enhancements

**Stakeholder Benefits**:
- **Minister**: Quantified public benefit for manifesto delivery ("Government delivers 20% more reliable journeys")
- **General Public**: Less time wasted in avoidable congestion, reduced stress
- **Navigation App Providers**: Improved route prediction accuracy increasing user trust
- **Logistics Companies**: More predictable delivery schedules reducing fleet costs
- **CDTO**: Demonstrable ROI from data platform investment

**Leading Indicators** (early signals of success):
- API adoption by third-party apps (Google, Waze integration confirms within 6 months)
- User behavior change (rerouting frequency increases as users trust real-time data)
- App user ratings improve ("much better traffic predictions" in Google Maps reviews)

**Lagging Indicators** (final proof of success):
- Journey time variability reduction measured by sensor network
- User satisfaction surveys ("journey planning has improved")
- Economic modeling validates congestion cost reduction

---

### Outcome O-2: Zero Security Incidents During Migration

**Supported Goals**: G-4 (GDPR Compliance), G-2 (Platform Availability)

**Outcome Statement**:
Achieve zero security incidents (data breaches, unauthorized access, cyber attacks) throughout 18-month migration programme, protecting OFFICIAL-SENSITIVE data (ANPR, CCTV) and maintaining public trust in National Highways' data stewardship.

**Measurement Details**:
- **KPI**: Security Incident Count (NCSC-defined incidents: data breach, cyber attack, unauthorized access)
- **Current Value**: Baseline: 2 security incidents per year (legacy systems)
- **Target Value**: 0 security incidents during migration (18 months)
- **Measurement Frequency**: Continuous monitoring, monthly reporting to CISO
- **Data Source**: Security Information and Event Management (SIEM), SOC (Security Operations Centre)
- **Report Owner**: Chief Information Security Officer

**Business Value**:
- **Risk Avoidance**: £17.5M potential ICO fine avoided (4% of turnover or £17.5M, whichever is higher)
- **Reputational Impact**: Avoid media damage from "National Highways data breach exposes driver locations" headlines
- **Strategic Impact**: Maintain public trust essential for open data programme
- **Compliance Impact**: Avoid regulatory enforcement action (ICO warnings, corrective orders)

**Timeline**:
- **Phase 1 (Months 1-6)**: Security baseline established, zero incidents
- **Phase 2 (Months 7-12)**: High-risk migration period (ANPR data migration), zero incidents
- **Phase 3 (Months 13-18)**: Legacy decommissioning, zero incidents
- **Sustainment**: Continuous security monitoring, maintain zero-incident target

**Stakeholder Benefits**:
- **CISO**: Personal accountability met, career reputation protected
- **DPO**: UK GDPR compliance maintained, no ICO enforcement
- **Perm Sec**: Risk exposure minimized, no parliamentary scrutiny from breach
- **General Public**: Personal data (vehicle movements) protected
- **Minister**: Avoids reputational damage from security failure

**Leading Indicators**:
- Penetration testing results: zero HIGH findings
- Security audit results: all controls effective
- Threat intelligence: zero credible threats targeting National Highways
- Security training completion: 100% of staff trained in data protection

**Lagging Indicators**:
- Security incident log: zero incidents recorded
- ICO correspondence: zero enforcement actions
- Media monitoring: zero negative security coverage

---

### Outcome O-3: £15M Annual Operational Savings Achieved

**Supported Goals**: G-3 (Cost Reduction), G-6 (Data Mesh), G-7 (Staff Upskilling)

**Outcome Statement**:
Achieve £15M annual operational cost savings by Year 3 (verified by Finance and NAO), demonstrating 2.8:1 ROI on £45M investment within 5-year business case timeframe and releasing budget for road network improvements.

**Measurement Details**:
- **KPI**: Annual Operational Cost Savings (£M)
- **Current Value**: £0M (baseline year)
- **Target Value**: £15M annual run-rate by Year 3
- **Measurement Frequency**: Monthly financial tracking, quarterly CFO review, annual NAO audit
- **Data Source**: Oracle Finance system, benefits realization register
- **Report Owner**: Chief Financial Officer

**Business Value**:
- **Financial Impact**: £15M annual savings reinvested in road maintenance and safety improvements
- **Strategic Impact**: Demonstrates technology ROI to Board and Treasury, justifies future technology investment
- **Political Impact**: "Value for money" narrative for Minister in parliamentary accountability
- **Organizational Impact**: Frees budget for higher-value work (data analysts vs. manual data processors)

**Timeline**:
- **Year 1**: £3M annual savings (20% of target)
  - Components: £2M legacy license reduction, £1M early automation
- **Year 2**: £9M annual savings (60% of target)
  - Components: £5M infrastructure migration, £3M cumulative automation, £1M operational efficiency
- **Year 3**: £15M annual run-rate (100% of target)
  - Components: £8M full legacy decommissioning, £4M infrastructure optimization, £2.25M operational efficiency, £0.75M FTE redeployment
- **Year 4-5**: Sustain £15M annual savings, continuous optimization

**Stakeholder Benefits**:
- **CFO**: Budget pressure relieved, Board targets met
- **Treasury**: Value for money demonstrated, positive NAO assessment
- **National Highways CEO**: More budget available for road network improvements
- **Staff**: Redeployed from manual data processing to higher-value analytical work (no redundancies)

**Leading Indicators**:
- Legacy system usage declining (licenses can be decommissioned)
- Manual process automation increasing (FTE hours freed up)
- Cloud cost optimization (FinOps savings materializing)

**Lagging Indicators**:
- Annual financial statements showing £15M cost reduction
- NAO audit validating benefits realization claims
- Benefits realization register: 90%+ of forecast benefits achieved

---

### Outcome O-4: 30% Improvement in Operational Efficiency (Incident Response)

**Supported Goals**: G-2 (Platform Availability), G-6 (Data Mesh), G-7 (Staff Upskilling)

**Outcome Statement**:
Reduce average incident response time from 18 minutes to 12.6 minutes (30% improvement) through unified data platform eliminating manual data reconciliation across siloed systems, enabling faster emergency service coordination and improved public safety.

**Measurement Details**:
- **KPI**: Mean Incident Response Time (minutes from incident report to traffic officer dispatch)
- **Current Value**: 18 minutes average
- **Target Value**: 12.6 minutes (30% reduction)
- **Measurement Frequency**: Daily (operational KPI), monthly reporting to COO and DfT
- **Data Source**: Incident management system logs
- **Report Owner**: Chief Operating Officer

**Business Value**:
- **Operational Impact**: 250,000 incidents/year × 5.4 minutes faster response = 1.35M minutes annual time saving
- **Economic Impact**: £2.25M annual value (faster clearance reduces congestion duration)
  - Methodology: 1.35M minutes traffic officer time saved × £100/hour fully-loaded cost
- **Safety Impact**: Faster incident clearance reduces secondary incident risk by ~15% (estimated 375 secondary incidents prevented)
- **Customer Impact**: Reduced delay for motorists stuck behind incidents (better experience)

**Timeline**:
- **Phase 1 (Months 1-6)**: Baseline measurement established, unified data platform early access for 2 control rooms
  - Target: 10% improvement (pilot regions only)
- **Phase 2 (Months 7-12)**: All 7 control rooms on unified platform, training complete
  - Target: 20% improvement (learning curve, process optimization)
- **Phase 3 (Months 13-18)**: Process maturity, automation of routine tasks
  - Target: 30% improvement (full benefits realized)

**Stakeholder Benefits**:
- **COO**: Operational KPIs improved, DfT performance targets exceeded
- **Regional Control Rooms**: Reduced manual workload, faster incident resolution (job satisfaction)
- **Emergency Services**: Faster coordination with National Highways improving response times
- **General Public**: Shorter incident duration, less congestion delay
- **Minister**: Positive operational performance for parliamentary reporting

**Leading Indicators**:
- Control room operator workflow efficiency (fewer screens to check, faster data access)
- Training completion (operators proficient on new system)
- User satisfaction (control room operators rate new system as improvement)

**Lagging Indicators**:
- Incident response time reduction measured monthly
- Secondary incident rate reduction (fewer incidents caused by initial incidents)

---

### Outcome O-5: 50% Increase in Open Data Consumption (Third-Party API Usage)

**Supported Goals**: G-1 (Open Data API), G-5 (GDS Service Assessment), G-6 (Data Mesh)

**Outcome Statement**:
Achieve 50 million API requests/month from third-party developers (Google, Waze, TomTom, local authorities, researchers) within 12 months of API launch, demonstrating public value creation from open data and enabling innovation ecosystem around road network data.

**Measurement Details**:
- **KPI**: Monthly API Request Volume (millions)
- **Current Value**: 0 (no public API exists)
- **Target Value**: 50 million requests/month (baseline + 50% growth trajectory)
- **Measurement Frequency**: Real-time dashboards, monthly reporting
- **Data Source**: API Gateway (Azure API Management)
- **Report Owner**: Director of Data & Analytics

**Business Value**:
- **Strategic Impact**: Open data ecosystem enables third-party innovation (journey planning apps, research, logistics optimization)
- **Political Impact**: Cross-party support for transparency and open data (positive parliamentary narrative)
- **Economic Impact**: Estimated £25M annual economic value from third-party innovation enabled by open data
  - Methodology: Research shows 1:10 public data ROI (public sector invests £1, economy benefits £10)
- **Reputational Impact**: National Highways seen as digital leader in government

**Timeline**:
- **Month 1-3**: API launched, initial onboarding (Google, Waze, TomTom confirmed)
  - Target: 10M requests/month (early adopters)
- **Month 4-6**: Mainstream adoption, local authority integrations
  - Target: 25M requests/month (growing ecosystem)
- **Month 7-12**: Mature ecosystem, academic researchers, open data community
  - Target: 50M requests/month (established baseline)

**Stakeholder Benefits**:
- **Minister**: Visible public value creation, positive media coverage
- **GDS**: Successful open data exemplar for other departments
- **Navigation App Providers**: High-quality data improves service
- **Local Authorities**: Free access to strategic road network data for local traffic management
- **Researchers**: Enable transport research and innovation

**Leading Indicators**:
- API registrations (developer sign-ups increasing)
- Sandbox usage (developers testing API before production)
- Third-party app announcements (Google Maps, Waze integration confirmed)

**Lagging Indicators**:
- API request volume growth month-over-month
- Developer satisfaction surveys (Net Promoter Score)
- Media coverage of third-party innovations using National Highways data

---

### Outcome O-6: 95% Staff Retention of Cloud-Trained Engineers

**Supported Goals**: G-7 (Staff Upskilling), G-3 (Cost Reduction via reduced consultancy)

**Outcome Statement**:
Achieve ≥95% retention of 120 cloud-trained technical staff over 24 months post-training, demonstrating that professional development improves retention and reduces recruitment costs while building sustainable internal capability.

**Measurement Details**:
- **KPI**: Staff Retention Rate (% of trained staff remaining after 24 months)
- **Current Value**: 75% retention (baseline attrition rate for technical staff)
- **Target Value**: 95% retention (20 percentage point improvement)
- **Measurement Frequency**: Quarterly HR tracking
- **Data Source**: HR system, exit interview data
- **Report Owner**: Chief Data & Technology Officer

**Business Value**:
- **Financial Impact**: £1.2M savings from reduced recruitment costs (avoiding 30 replacements × £40k recruitment cost)
- **Operational Impact**: Retained organizational knowledge and project continuity
- **Strategic Impact**: Sustainable capability vs. consultant dependency
- **Cultural Impact**: Employer of choice reputation attracting digital talent

**Timeline**:
- **Year 1**: Training delivered, initial retention measured
  - Target: 90% retention (some natural attrition)
- **Year 2**: Career development paths established, retention improves
  - Target: 95% retention (professional development impact visible)

**Stakeholder Benefits**:
- **Data Engineers**: Career development, marketable skills, job satisfaction
- **CDTO**: Sustainable capability, reduced consultancy costs
- **CFO**: Lower recruitment costs, stable workforce
- **HR**: Employer brand improvement, easier recruitment

**Leading Indicators**:
- Employee satisfaction scores improving (professional development rated highly)
- Internal mobility (trained staff promoted to senior roles)
- External recognition (staff speaking at conferences, winning awards)

**Lagging Indicators**:
- Retention rate measured 24 months post-training
- Exit interview data (fewer departures citing "technology boredom")

---

## Complete Traceability Matrix

### Stakeholder → Driver → Goal → Outcome

| Stakeholder | Driver ID | Driver Summary | Goal ID | Goal Summary | Outcome ID | Outcome Summary |
|-------------|-----------|----------------|---------|--------------|------------|-----------------|
| Transport Minister | SD-1 | Political delivery & manifesto | G-1 | Open Data API launch | O-1 | 20% journey reliability improvement |
| Transport Minister | SD-1 | Political delivery & manifesto | G-5 | GDS Assessment pass | O-5 | 50M API requests/month |
| DfT Permanent Secretary | SD-2 | Accounting officer risk | G-3 | £15M cost savings | O-3 | £15M savings verified by NAO |
| DfT Permanent Secretary | SD-2 | Accounting officer risk | G-4 | GDPR compliance | O-2 | Zero security incidents |
| Chief Data & Technology Officer | SD-3 | Digital transformation | G-1 | Open Data API | O-5 | 50M API requests/month |
| Chief Data & Technology Officer | SD-3 | Digital transformation | G-6 | Data Mesh products | O-4 | 30% operational efficiency |
| Chief Data & Technology Officer | SD-3 | Digital transformation | G-7 | Staff upskilling | O-6 | 95% staff retention |
| Chief Information Security Officer | SD-4 | Security & CNI protection | G-4 | GDPR compliance | O-2 | Zero security incidents |
| Chief Information Security Officer | SD-4 | Security & CNI protection | G-2 | 99.95% availability | O-2 | Zero security incidents |
| Chief Financial Officer | SD-5 | Budget control & ROI | G-3 | £15M cost savings | O-3 | £15M annual savings |
| Chief Operating Officer | SD-6 | Operational continuity | G-2 | 99.95% availability | O-4 | 30% incident response improvement |
| Regional Control Rooms | SD-7 | User experience | G-2 | 99.95% availability | O-4 | 30% operational efficiency |
| Regional Control Rooms | SD-7 | User experience | G-6 | Data Mesh products | O-4 | 30% operational efficiency |
| Data Protection Officer | SD-8 | UK GDPR compliance | G-4 | GDPR compliance | O-2 | Zero security incidents |
| Government Digital Service | SD-9 | Service Standard | G-5 | GDS Assessment pass | O-5 | 50M API requests/month |
| Government Digital Service | SD-9 | Service Standard | G-1 | Open Data API | O-1 | 20% journey reliability |
| HM Treasury | SD-10 | Value for money | G-3 | £15M cost savings | O-3 | £15M savings verified |
| Local Highway Authorities | SD-11 | Data interoperability | G-1 | Open Data API | O-5 | 50M API requests/month |
| Emergency Services | SD-12 | Critical incident response | G-2 | 99.95% availability | O-4 | 30% incident response improvement |
| General Public | SD-13 | Journey reliability | G-1 | Open Data API | O-1 | 20% journey reliability |
| National Audit Office | SD-14 | Value for money governance | G-3 | £15M cost savings | O-3 | £15M savings verified by NAO |
| Data Engineers | SD-15 | Modern technology & careers | G-7 | Staff upskilling | O-6 | 95% staff retention |

### Conflict Analysis

**Competing Drivers**:

**Conflict 1: Speed vs. Rigour**
- **Stakeholders**: Minister (SD-1 wants rapid delivery within 18 months) vs. CISO (SD-4 needs thorough security testing)
- **Nature**: Political pressure for fast visible delivery conflicts with security best practices requiring comprehensive testing
- **Impact**: Pressure to cut corners on security reviews to meet political deadlines
- **Resolution Strategy**:
  - Phased delivery: Early wins on low-risk components (open traffic data API) within 12 months satisfies Minister
  - High-risk components (OFFICIAL-SENSITIVE data) delivered in later phases with full security rigor
  - Monthly steering group with ministerial representation to manage speed/quality trade-offs explicitly
  - Security review gates are non-negotiable; schedule risk managed through scope flex
  - Communicate to Minister: "Security incidents would be far more politically damaging than 3-month delay"

**Conflict 2: Cost Control vs. Capability Investment**
- **Stakeholders**: CFO (SD-5 wants budget control) vs. CDTO (SD-3 wants modern technology investment)
- **Nature**: CFO pressure to minimize costs conflicts with CDTO desire to invest in best-in-class data platform
- **Impact**: Tension over cloud platform selection, consultancy spend, training budget
- **Resolution Strategy**:
  - Business case clearly articulates ROI: £45M investment → £15M annual savings = 3-year payback
  - CFO has visibility into monthly spend tracking (no surprises)
  - Technology choices demonstrate cost-consciousness (open source where appropriate, not gold-plating)
  - Training investment positioned as consultant reduction (£0.8M training to save £2M annual consultancy)
  - Architecture principles mandate cost optimization (FinOps practices, auto-scaling)

**Conflict 3: Centralization vs. Federation (Data Mesh Governance)**
- **Stakeholders**: Some executives want central control vs. Data Mesh architecture requires domain autonomy
- **Nature**: Tension between standardization (easier governance) and federation (domain flexibility)
- **Impact**: Governance model design, decision rights, accountability structures
- **Resolution Strategy**:
  - Federated governance council with central platform team (balance central standards + domain autonomy)
  - Clear division of responsibility: Central team provides platform (infrastructure, catalog), domains provide data products
  - Guardrails not gates: Automated policy enforcement (schema validation, security controls) not manual approvals
  - Start with 2 pilot domains (Traffic, Incidents) proving model before scaling to all 5
  - Quarterly governance review to adjust balance based on maturity

**Conflict 4: Open Data vs. Data Protection**
- **Stakeholders**: Open Data Advocates + GDS (SD-9 want maximum transparency) vs. CISO + DPO (SD-4, SD-8 want data protection)
- **Nature**: Tension between openness (public value) and security/privacy (risk management)
- **Impact**: Which data to publish openly, what access controls to apply
- **Resolution Strategy**:
  - Clear data classification framework: PUBLIC (open), OFFICIAL (partner access), OFFICIAL-SENSITIVE (restricted)
  - Privacy screening process: Anonymize personal data before open publication (registration plates hashed)
  - Security review gate for all open data releases (confirm no infrastructure vulnerabilities exposed)
  - DPO and CISO have veto rights on open data releases (escalate to CDTO if conflict)
  - GDS Service Standard point 5 (make data open by default) balanced with point 9 (data protection)

**Synergies**:

**Synergy 1: Public Value Alignment**
- **Stakeholders**: Minister (SD-1), CDTO (SD-3), GDS (SD-9), General Public (SD-13), Open Data Advocates
- **Alignment**: All driven by delivering measurable public benefit through better journey planning
- **Goal Convergence**: G-1 (Open Data API) and O-1 (20% journey reliability improvement) satisfy all these stakeholders
- **Leverage**: Strong cross-stakeholder support creates political capital and resource prioritization

**Synergy 2: Value for Money Alignment**
- **Stakeholders**: CFO (SD-5), Treasury (SD-10), NAO (SD-14), Perm Sec (SD-2)
- **Alignment**: All driven by demonstrable ROI and prudent use of public funds
- **Goal Convergence**: G-3 (£15M savings) and O-3 (verified savings) satisfy all financial stakeholders
- **Leverage**: Strong financial discipline builds trust with Treasury, potentially enabling future investment

**Synergy 3: Operational Excellence Alignment**
- **Stakeholders**: COO (SD-6), Control Rooms (SD-7), Emergency Services (SD-12)
- **Alignment**: All driven by operational efficiency, service reliability, faster incident response
- **Goal Convergence**: G-2 (99.95% availability) and O-4 (30% efficiency improvement) satisfy operational stakeholders
- **Leverage**: User-centered design with operational staff creates buy-in and reduces change resistance

**Synergy 4: Digital Capability Alignment**
- **Stakeholders**: CDTO (SD-3), Data Engineers (SD-15), GDS (SD-9)
- **Alignment**: All driven by modern technology adoption and building digital capability
- **Goal Convergence**: G-7 (staff upskilling) and O-6 (95% retention) satisfy capability-building stakeholders
- **Leverage**: Positioning National Highways as technology innovator attracts talent and enables recruitment

---

## Communication & Engagement Plan

### Stakeholder-Specific Messaging

#### Transport Minister (Secretary of State for Transport)

**Primary Message**:
"Delivering your manifesto commitment to modernize England's road network through technology, with visible public-facing benefits within 18 months demonstrating government's infrastructure investment is working for drivers."

**Key Talking Points**:
- **Parliamentary Accountability**: Open Data API launch enables "20% improvement in journey reliability" quantified outcome for PQs (Parliamentary Questions)
- **Manifesto Delivery**: Real-time traffic information accessible via Google Maps demonstrates digital transformation commitment
- **Public Safety**: Faster incident response (30% improvement) protects drivers and supports emergency services
- **Value for Money**: £15M annual operational savings demonstrates prudent use of taxpayer funds (positive NAO narrative)
- **Cross-Party Support**: Open data has cross-party backing (reduces political risk)

**Communication Frequency**: Monthly 30-minute briefing (written brief + in-person if requested)

**Preferred Channel**:
- Written ministerial briefing (2-page summary + appendices)
- Quarterly in-person presentation to Minister (with slides)
- Urgent escalations via Perm Sec (same-day response)

**Success Story**:
"Minister announces world-class real-time traffic API enabling Google Maps integration, delivering on manifesto commitment to reduce congestion through technology innovation. Public can now plan journeys with accuracy comparable to leading international road networks."

---

#### DfT Permanent Secretary (Accounting Officer)

**Primary Message**:
"Robust programme governance, independent assurance, and risk management ensure value for money and protect DfT reputation, with NAO-validated benefits realization and no repeat of historical government IT failures."

**Key Talking Points**:
- **Governance Rigor**: Gateway reviews, IPA oversight, NAO engagement demonstrate proper controls
- **Risk Management**: Comprehensive risk register with mitigation strategies, monthly risk reviews
- **Value for Money**: Green Book-compliant business case, quantified benefits, conservative assumptions
- **Independent Assurance**: External reviews validate delivery approach (no optimism bias)
- **Learning from Failures**: Lessons from historical IT failures embedded in delivery approach (phased delivery, not big bang)

**Communication Frequency**: Monthly steering group (90 minutes), quarterly DfT Board updates

**Preferred Channel**:
- Monthly steering group with written papers 5 days in advance
- Quarterly Board papers (following DfT format)
- Escalation for material risks or issues (same day)

**Success Story**:
"NAO report praises National Highways data programme as exemplar of government technology delivery: robust governance, benefits realized as forecast, no cost overruns. Perm Sec testimony to Public Accounts Committee highlights good practice."

---

#### Chief Data & Technology Officer (Executive Sponsor)

**Primary Message**:
"Transform National Highways into a data-driven, digitally-enabled organization showcasing modern architecture, attracting digital talent, and positioning National Highways as public sector technology leader."

**Key Talking Points**:
- **Flagship Programme**: Data mesh architecture and cloud-native platform demonstrating technical leadership
- **Industry Recognition**: Conference speaking opportunities, awards, thought leadership positioning CDTO as innovator
- **Talent Attraction**: Modern technology stack makes National Highways attractive to data engineers and cloud architects
- **Board Credibility**: Quantified ROI (£15M savings) demonstrates technology investment value to skeptical Board members
- **Sustainable Capability**: 120 staff upskilled reduces consultant dependency and builds internal expertise

**Communication Frequency**: Weekly 60-minute programme review, daily Slack updates

**Preferred Channel**:
- Weekly in-person programme review (dashboard walkthrough)
- Daily Slack check-ins for issues and blockers
- Monthly architecture review board (ADR approvals)

**Success Story**:
"CDTO keynotes at GDS conference on data mesh in government, showcasing National Highways as exemplar. LinkedIn recognition as top public sector technology leader. Attracts 50 high-quality applications for senior data roles (vs. historic 5 applications)."

---

#### Chief Information Security Officer (Security Authority)

**Primary Message**:
"Zero security incidents throughout migration protects OFFICIAL-SENSITIVE data, maintains CNI resilience, and ensures National Highways meets NCSC standards for critical national infrastructure."

**Key Talking Points**:
- **Security by Design**: Zero-trust architecture, defense-in-depth, NCSC Cloud Security Principles compliance from day one
- **OFFICIAL-SENSITIVE Protection**: ANPR and CCTV data protected with encryption, access controls, audit logging
- **CNI Resilience**: 99.95% availability maintained, no single points of failure, disaster recovery tested quarterly
- **Regulatory Compliance**: NCSC CAF assessment passed, no ICO enforcement actions, penetration testing clean
- **Career Protection**: Personal accountability met through rigorous security governance and independent testing

**Communication Frequency**: Bi-weekly security review (60 minutes), monthly CISO Board reporting

**Preferred Channel**:
- Bi-weekly security review with CISO (threat intelligence, vulnerability reports)
- Monthly written report to Executive Board
- Immediate escalation for security incidents (24/7 on-call)

**Success Story**:
"NCSC case study: National Highways data platform achieves exemplar CNI security rating with zero incidents during complex migration. CISO presents at NCSC conference on securing critical infrastructure data in cloud environments."

---

#### Chief Financial Officer (Budget Authority)

**Primary Message**:
"£45M investment delivers £15M annual operational savings (2.8:1 ROI) with transparent monthly financial tracking, no cost overruns, and benefits realized as forecast, protecting CFO credibility with Board and Treasury."

**Key Talking Points**:
- **Financial Discipline**: Monthly spend tracking, variance explanations, no surprises, forecast accuracy within 5%
- **ROI Delivery**: £15M annual savings by Year 3 verified by Finance, releasing budget for road network improvements
- **Cost Optimization**: FinOps practices, cloud cost management, competitive procurement demonstrating value-seeking
- **Benefits Realization**: 90%+ of forecast benefits achieved (not optimism bias), independently audited by NAO
- **Budget Protection**: Stage-gate funding enables stop/adjust if benefits not materializing (risk mitigation)

**Communication Frequency**: Monthly financial review (60 minutes), quarterly CFO Board updates

**Preferred Channel**:
- Monthly financial review with detailed spend reports and benefits tracking
- Quarterly CFO Board paper with ROI dashboard
- Immediate escalation for budget variances >5%

**Success Story**:
"CFO presents to Board: Data programme delivered on budget, £15M annual savings achieved (exceeding business case forecast), demonstrating technology investments deliver value. Enables £10M additional budget allocation to road safety improvements."

---

#### Regional Control Room Managers (Operational Users)

**Primary Message**:
"New unified data platform eliminates frustrating manual data entry and multi-system navigation, enabling you to respond to incidents 30% faster with better tools, improving operational KPIs and making your job easier."

**Key Talking Points**:
- **Simplified Workflows**: Single incident entry (not 3 separate systems), unified dashboard (not 7 screens)
- **Real-Time Data Quality**: Accurate traffic sensor data (not outdated or missing data requiring phone calls)
- **Faster Incident Response**: Average 18 minutes → 12.6 minutes (helping you meet DfT targets and protect drivers)
- **User-Centered Design**: You co-designed this system (your feedback shaped the features, not imposed by technology team)
- **Training and Support**: Comprehensive training delivered by peer control room staff, 24/7 support during cutover

**Communication Frequency**: Monthly user forum (90 minutes), weekly updates during rollout

**Preferred Channel**:
- Monthly in-person user forum (7 regional reps + operational staff)
- Weekly email updates with FAQs and training materials
- Dedicated Slack channel for questions and feedback

**Success Story**:
"Control room operators report: 'New system is actually better than legacy - faster, easier, more intuitive. We were skeptical but the technology team listened to our feedback and built something that works for us, not against us.'"

---

#### Government Digital Service (Standards Authority)

**Primary Message**:
"National Highways demonstrates that large-scale government data infrastructure can meet Service Standard through user-centered design, open standards, and agile delivery, providing GDS with exemplar case study for other departments."

**Key Talking Points**:
- **Service Standard Compliance**: All 14 points met (Alpha and Beta assessments passed), demonstrating Standard's applicability to data platforms
- **User Research Rigor**: 50+ user research sessions with drivers, emergency services, local authorities informing design
- **Open Standards**: OpenAPI 3.x, DATEX II, GeoJSON - no proprietary lock-in, enabling third-party innovation
- **Accessibility Excellence**: WCAG 2.2 Level AA compliance, tested with disabled users, inclusive design throughout
- **Agile at Scale**: Demonstrating Agile practices work for major infrastructure programmes (not just small services)

**Communication Frequency**: Quarterly showcase (60 minutes), Alpha/Beta assessment bookings

**Preferred Channel**:
- Quarterly show-and-tell at GDS (demo working software, share learnings)
- Assessment bookings 6 weeks in advance
- Cross-government community sharing (write blog posts, present at GDS conferences)

**Success Story**:
"GDS publishes National Highways as exemplar case study: 'How to apply Service Standard to data platforms and API services.' Featured in GDS newsletter, referenced in assessor training, used by other departments as blueprint."

---

#### Local Highway Authorities (Data Partners)

**Primary Message**:
"Free, open API access to National Highways strategic road network data enhances your local traffic management, with financial and technical support for integration, creating unified driver experience across strategic and local roads."

**Key Talking Points**:
- **Free Data Access**: No cost to access National Highways traffic, incident, roadworks data via open API
- **Integration Support**: Technical documentation, sandbox environment, integration grants available (DfT funding)
- **Coordinated Roadworks**: Prevent simultaneous closures causing gridlock through shared roadworks data
- **Mutual Benefit**: National Highways wants your local road data to provide drivers complete network coverage
- **Autonomy Preserved**: Federated model respects local authority independence (not centralized mandate)

**Communication Frequency**: Quarterly local authority forum, annual conference

**Preferred Channel**:
- Quarterly virtual forum (60 minutes) with technical Q&A
- Annual in-person conference with hands-on workshops
- Dedicated email support for integration questions

**Success Story**:
"152 local authorities adopt National Highways API within 18 months, creating UK's first truly unified road network data platform. Drivers experience seamless journey planning across strategic and local roads. Local authorities report 40% reduction in duplicate roadworks coordination effort."

---

## Change Impact Assessment

### Impact on Stakeholders

| Stakeholder | Current State | Future State | Change Magnitude | Resistance Risk | Mitigation Strategy |
|-------------|---------------|--------------|------------------|-----------------|---------------------|
| Regional Control Room Operators | Navigate 7 separate legacy systems, manual data entry, phone calls to verify data | Single unified dashboard, automated data flows, real-time accurate data | HIGH | MEDIUM | Co-design workshops, comprehensive training by peers, parallel running, gradual rollout |
| Data Engineers | Work on legacy Oracle databases, frustrating technical debt, limited career development | Modern cloud-native stack, data mesh architecture, Azure/Kafka/Databricks skills | HIGH | LOW (positive change) | Training budget, certifications, conference attendance, open source contributions |
| Enterprise Architects | Maintain legacy architecture documentation, little influence on technology choices | Active architecture governance, ADR decision authority, modern patterns | MEDIUM | LOW | Architecture review board, decision rights clarity, thought leadership opportunities |
| Finance Team | Manual benefits tracking in spreadsheets, quarterly reviews | Automated benefits realization dashboard, monthly tracking with variance analysis | MEDIUM | LOW | Training on new dashboard, clear accountability, finance involvement in design |
| Executive Board | Technology presented as "black box," unclear ROI | Transparent dashboards showing benefits, risks, spend (executive visibility) | LOW | LOW | Monthly exec dashboard, clear KPIs tied to business outcomes |
| External Partners (Navigation Apps) | Scrape HTML website for data (fragile, inaccurate) | Consume reliable, documented API with SLAs | MEDIUM | LOW (positive change) | Early partnership engagement, sandbox environment, dedicated support |
| General Public | Use outdated traffic information, frustration with inaccuracy | Real-time accurate journey planning via apps, improved reliability | LOW (invisible backend change) | N/A | No direct change management needed (benefit via third-party apps) |

### Change Readiness

**Champions** (Enthusiastic supporters):
- **CDTO**: Personal reputation tied to success, passionate about digital transformation, actively removes blockers
  - *Why they support*: Flagship career-defining programme, opportunity to position National Highways as technology leader
- **Data Engineers**: Modern technology stack, career development, marketable skills
  - *Why they support*: Escape frustrating legacy systems, work on interesting problems, enhance CVs
- **GDS**: Exemplar of Service Standard application to data infrastructure
  - *Why they support*: Demonstrates GDS standards work at scale, cross-government learning opportunity

**Fence-sitters** (Neutral, need convincing):
- **Regional Control Room Managers**: Skeptical based on previous IT project failures, "wait and see" attitude
  - *What would convince them*: Early pilot success in one region proving new system is actually better (not just different)
  - *Strategy*: Pilot in North West region (most engaged manager), demonstrate 20% efficiency improvement, showcase to other regions
- **Local Highway Authorities**: Concerned about integration costs and data quality requirements
  - *What would convince them*: Integration grants covering costs, data quality support (not just mandates), quick wins demonstrating value
  - *Strategy*: Pilot with 5 progressive authorities, provide hands-on integration support, publish success stories
- **CFO**: Wants evidence of ROI before full commitment, cautious about cost overruns
  - *What would convince them*: Early savings realization (Year 1 £3M target achieved), transparent spend tracking showing budget control
  - *Strategy*: Monthly financial reviews, celebrate early wins, independent audit validation

**Resisters** (Opposed or skeptical):
- **Legacy Infrastructure Team**: Comfortable with on-premises Oracle, fear cloud migration complexity and job security
  - *Why they resist*: Skill obsolescence concerns, comfort with known systems, uncertainty about future role
  - *Strategy*: Retraining in cloud operations, clear career paths (cloud infrastructure team), job security guarantees (no redundancies), recognition of legacy expertise value during migration
- **Some Security Team Members**: Perception that cloud is less secure than on-premises, unfamiliarity with cloud security controls
  - *Why they resist*: Risk aversion, lack of cloud security knowledge, comfort with existing controls
  - *Strategy*: Cloud security training (Azure Security certifications), NCSC Cloud Security Principles education, involve in threat modeling, demonstrate defense-in-depth approach
- **Procurement Team**: Frustrated by pressure for fast cloud procurement when process requires competition
  - *Why they resist*: Process compliance concerns, fear of NAO criticism for non-competitive procurement
  - *Strategy*: Early procurement engagement, use of government frameworks (G-Cloud), clear documentation of commercial approach, procurement as partner not blocker

---

## Risk Register (Stakeholder-Related)

### Risk R-1: Ministerial Patience Exhausted (Political Risk)

**Related Stakeholders**: Transport Minister (SD-1), DfT Permanent Secretary (SD-2)

**Risk Description**:
Programme delays extending beyond 18-month target cause Minister to lose confidence in delivery, leading to intervention, SRO replacement, or programme restructuring. Media narrative shifts to "another government IT failure" damaging ministerial reputation and DfT credibility.

**Impact on Goals**: G-1 (API launch delayed), G-5 (GDS assessment delayed)

**Probability**: MEDIUM (30% - delivery is ambitious but achievable)

**Impact**: HIGH (political intervention destabilizes programme, reputational damage)

**Mitigation Strategy**:
- Monthly ministerial briefings maintaining transparency (no surprises)
- Phased delivery with early wins within 12 months (open traffic data API satisfies political need for visible progress)
- Clear communication of risks and trade-offs (speed vs. security, Minister makes informed decisions)
- Reserve "quick win" features for deployment if political pressure increases (variable message sign updates, website improvements)

**Contingency Plan**:
- If Minister loses confidence: Perm Sec escalates to permanent CDTO engagement, independent review validates approach, demonstrate progress with working software demos
- If media narrative turns negative: Proactive media strategy highlighting successes, third-party validation (GDS assessment pass, partner testimonials)

---

### Risk R-2: CISO Blocks Go-Live (Security Risk)

**Related Stakeholders**: CISO (SD-4), DfT Permanent Secretary (SD-2), Minister (SD-1)

**Risk Description**:
CISO refuses to approve production go-live due to unmitigated security risks (penetration testing findings, NCSC concerns, missing security controls), creating conflict between security rigor and political delivery pressure.

**Impact on Goals**: G-2 (availability affected), G-4 (GDPR compliance), all goals delayed

**Probability**: MEDIUM (25% - security is complex, risks may emerge late)

**Impact**: CRITICAL (production launch blocked, ministerial escalation, programme credibility damaged)

**Mitigation Strategy**:
- CISO engagement from day one (not afterthought), security reviews at all design gates
- Penetration testing scheduled 3 months before go-live (time to remediate findings)
- NCSC consultation for CNI security validation (external validation reduces CISO pressure)
- Clear escalation path: CISO → CEO → DfT Board (ensure CISO concerns heard at highest level)
- Accept CISO veto on security grounds (CISO accountability respected, no pressure to override)

**Contingency Plan**:
- If CISO blocks launch: Delay go-live, remediate security findings, independent security review validates approach
- If timeline pressure creates conflict: CEO mediates, agree phased launch (low-risk components first, high-risk components later)
- No compromise on OFFICIAL-SENSITIVE data security (reputational and regulatory risk too high)

---

### Risk R-3: Control Room Operator Resistance (Change Management Risk)

**Related Stakeholders**: Regional Control Room Managers (SD-7), COO (SD-6)

**Risk Description**:
Control room operators resist new system due to poor user experience, inadequate training, or perceived loss of functionality vs. legacy systems. Operators continue using shadow workarounds or demand rollback to legacy system.

**Impact on Goals**: G-2 (availability perception), G-6 (data mesh adoption), O-4 (operational efficiency not realized)

**Probability**: MEDIUM (30% - user adoption is always challenging)

**Impact**: MEDIUM (operational benefits not realized, user satisfaction low, potential rollback demand)

**Mitigation Strategy**:
- Co-design from day one: Control room operators involved in design workshops, feedback shapes features
- Comprehensive training: 40 hours hands-on training delivered by peer operators (not external consultants)
- Parallel running: Legacy and new systems both available during transition (operators can fall back if needed)
- Gradual rollout: Pilot in one region, prove success, then scale to remaining six regions
- Champion identification: Find enthusiastic early adopters in each region to advocate for new system

**Contingency Plan**:
- If resistance high: Extend parallel running period, provide additional training, address specific usability concerns
- If rollback demanded: Analyze root cause (technical issues vs. change resistance), fix technical issues, provide change management support
- If pilot region fails: Pause national rollout, understand failures, redesign, re-pilot before scaling

---

### Risk R-4: NAO Critical Report (Governance Risk)

**Related Stakeholders**: National Audit Office (SD-14), DfT Permanent Secretary (SD-2), Treasury (SD-10)

**Risk Description**:
NAO review identifies optimism bias in business case, benefits not realized as forecast, inadequate governance, or poor value for money. NAO publishes critical report leading to Public Accounts Committee hearing where Perm Sec must testify.

**Impact on Goals**: G-3 (cost savings credibility questioned), all goals affected by reputational damage

**Probability**: LOW-MEDIUM (20% - robust governance mitigates but NAO scrutiny is rigorous)

**Impact**: HIGH (reputational damage, parliamentary scrutiny, future technology investment jeopardized)

**Mitigation Strategy**:
- Proactive NAO engagement: Invite NAO to review programme at key milestones (transparency demonstrates nothing to hide)
- Conservative business case: Apply HMT optimism bias adjustments, avoid overstating benefits
- Independent assurance: IPA Gateway reviews, external benefits realization audits provide third-party validation
- Benefits realization rigor: Monthly tracking, variance explanations, honest reporting of underperformance
- Governance evidence: Decision logs, steering group minutes, risk registers demonstrating proper controls

**Contingency Plan**:
- If NAO raises concerns: Address immediately, provide additional evidence, accept recommendations
- If critical report published: Perm Sec testimony prepared, demonstrate corrective actions taken, avoid defensiveness
- If benefits under-realized: Re-baseline business case, explain variances, demonstrate course correction

---

### Risk R-5: Key Stakeholder Departure (Continuity Risk)

**Related Stakeholders**: CDTO (SD-3), Programme Director, Data Domain Owners

**Risk Description**:
Critical stakeholders (CDTO, Programme Director, key domain owners) leave organization mid-programme due to private sector recruitment, retirement, or organizational changes. Loss of leadership creates delivery uncertainty and stakeholder relationship disruption.

**Impact on Goals**: All goals affected (leadership continuity essential)

**Probability**: MEDIUM (25% - public sector talent retention challenges)

**Impact**: MEDIUM-HIGH (delivery slowdown, relationship reset, potential strategic direction change)

**Mitigation Strategy**:
- Retention incentives: Competitive salaries, professional development, recognition, interesting work
- Knowledge management: Documented decision rationale (ADRs), clear governance structures reducing dependency on individuals
- Succession planning: Deputy roles identified, cross-training ensures continuity
- Stakeholder relationship breadth: Build relationships across teams (not just with one individual)

**Contingency Plan**:
- If CDTO departs: Deputy CDTO assumes executive sponsorship, recruit replacement with 3-month onboarding overlap
- If Programme Director departs: Promote internal deputy with external coaching support
- If domain owner departs: Federated governance model ensures domain team continuity (not single person dependency)

---

## Governance & Decision Rights

### Decision Authority Matrix (RACI)

| Decision Type | Responsible | Accountable | Consulted | Informed |
|---------------|-------------|-------------|-----------|----------|
| Programme scope changes (±10% budget/timeline) | Programme Director | CDTO (Executive Sponsor) | CFO, COO, CISO | Executive Board, DfT Perm Sec |
| Architecture decisions (ADRs) | Enterprise Architect | CDTO | Domain Architects, CISO | Programme Director |
| Technology selection (cloud platform, data tools) | Technical Lead | Enterprise Architect | CISO, Data Engineers | CFO (cost implications) |
| Budget allocation and reallocation | CFO | CEO | Programme Director, CDTO | Executive Board |
| Security approvals (OFFICIAL-SENSITIVE data) | CISO | CEO | DPO, Enterprise Architect | DfT Perm Sec |
| Data classification and retention policies | DPO | CISO | Legal, Compliance | CDTO |
| Go/No-Go for production deployment | Programme Director | COO (operational impact), CISO (security) | Regional Control Rooms, Infrastructure | Executive Board |
| Vendor selection and procurement | Procurement Lead | CFO | CDTO, Technical Lead | Programme Director |
| User research findings and design changes | Product Owner | Programme Director | Regional Control Rooms, UX Researchers | CDTO |
| Benefits realization and reporting | Programme Director | CFO | Finance Team | Executive Board, DfT, Treasury |
| Stakeholder communications (ministerial) | Programme Director | CDTO | DfT Perm Sec | Minister |
| GDS Service Assessment booking and preparation | Product Owner | Programme Director | UX Researchers, Accessibility Lead | CDTO, GDS |
| Data mesh governance policies | Governance Council | CDTO | Domain Owners, Enterprise Architects | All Data Consumers |
| Incident response and rollback decisions | COO (operational), CISO (security) | CEO (escalation) | Infrastructure Team, Programme Director | Executive Board |
| Open data publication approvals | Data Product Owner | DPO (privacy), CISO (security) | Legal, Communications | GDS, Open Data Advocates |

### Escalation Path

**Level 1: Programme Team (Day-to-Day Decisions)**
- **Authority**: Programme Director, Product Owners, Technical Leads
- **Decisions**: Sprint planning, backlog prioritization, technical design details, vendor coordination
- **Cadence**: Daily standups, weekly sprint reviews
- **Escalation Triggers**: Blockers unresolved within 2 days, dependencies across teams, technical risks

**Level 2: Steering Committee (Strategic Direction, Risks, Budget Variances)**
- **Authority**: CDTO (Chair), CFO, COO, CISO, Programme Director
- **Decisions**: Scope changes, budget reallocation, risk mitigation strategies, timeline adjustments
- **Cadence**: Monthly (90-minute meeting with pre-read papers 5 days in advance)
- **Escalation Triggers**: Budget variance >5%, timeline slippage >2 weeks, critical risks (CISO security concerns), stakeholder conflicts

**Level 3: Executive Board (Major Strategic Changes, Programme Viability)**
- **Authority**: CEO (Chair), Executive Team (CDTO, CFO, COO, CISO, Chief Legal Officer)
- **Decisions**: Programme continuation/cancellation, major budget increases, strategic pivots, organizational changes
- **Cadence**: Quarterly Board meetings + ad-hoc for urgent decisions
- **Escalation Triggers**: Programme viability concerns, budget overrun >10%, ministerial intervention, NAO critical findings

**Level 4: External Governance (Ministerial, Parliamentary, Regulatory)**
- **Authority**: DfT Permanent Secretary → Transport Minister → Parliament
- **Decisions**: Ministerial intervention, parliamentary accountability, regulatory compliance
- **Cadence**: Monthly ministerial briefings, quarterly DfT Board, annual NAO reviews
- **Escalation Triggers**: Political intervention required, regulatory enforcement action, public safety incidents, media crisis

### Governance Cadence

**Daily**:
- Agile standups (delivery teams)
- Infrastructure monitoring (SIEM, APM dashboards)

**Weekly**:
- Programme Director reviews with workstream leads
- Architecture review board (ADR approvals)
- Sprint reviews and planning

**Monthly**:
- Steering Committee (CDTO, CFO, COO, CISO, Programme Director)
- Ministerial briefing (written + in-person if requested)
- Benefits realization review (CFO)
- Security review (CISO)
- Financial tracking review (CFO)
- User forum (Regional Control Rooms)

**Quarterly**:
- Executive Board reporting
- DfT Board reporting (via Perm Sec)
- GDS showcase (demonstrate progress, share learnings)
- Local authority forum
- Staff satisfaction surveys
- Gateway reviews (IPA)
- NAO engagement

**Annually**:
- NAO audit (value for money review)
- NCSC CAF assessment (CNI security)
- ICO compliance review (data protection)
- Penetration testing (CREST-certified)
- Benefits realization audit (external validation)

---

## Validation & Sign-off

### Stakeholder Review

| Stakeholder | Review Date | Comments | Status |
|-------------|-------------|----------|--------|
| CDTO (Executive Sponsor) | TBD | [Feedback on strategic alignment] | PENDING |
| Chief Financial Officer | TBD | [Feedback on financial assumptions] | PENDING |
| Chief Operating Officer | TBD | [Feedback on operational impact] | PENDING |
| Chief Information Security Officer | TBD | [Feedback on security drivers] | PENDING |
| Regional Control Room Managers | TBD | [Feedback on user experience goals] | PENDING |
| DfT Permanent Secretary | TBD | [Feedback on governance and risk] | PENDING |
| Government Digital Service | TBD | [Feedback on Service Standard alignment] | PENDING |

### Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Programme Director | [TBD] | [Pending] | [TBD] |
| Executive Sponsor (CDTO) | [TBD] | [Pending] | [TBD] |
| Chief Executive Officer | [TBD] | [Pending] | [TBD] |

---

## Appendices

### Appendix A: Stakeholder Interview Summaries

#### Interview with Regional Control Room Manager (North West) - [Date TBD]

**Key Points**:
- Legacy system frustration: "We have to check 7 different screens to get complete incident picture - wastes time during critical incidents"
- Data quality concerns: "Traffic sensors often show wrong data or no data - we call Traffic Officers to verify by eye"
- Training anxiety: "Previous IT projects promised improvement but delivered worse systems - we're skeptical"
- User involvement desire: "If you actually involve us in design instead of imposing technology, we'll support it"

**Quotes**:
- "Every minute we save responding to incidents could save a life - if your new system actually makes us faster, we'll champion it"
- "Don't give us something that looks pretty but doesn't work under pressure during major incidents"

**Follow-up Actions**:
- Invite to co-design workshops (monthly starting Month 2)
- Provide early prototype access for feedback (Month 4)
- Designate as pilot region for phased rollout (Month 12)

---

#### Interview with Data Engineer - [Date TBD]

**Key Points**:
- Technology frustration: "Working on 10-year-old Oracle databases - can't attract good engineers, hard to retain them"
- Career development: "I want to learn modern cloud tech, not legacy systems - considering leaving for private sector role"
- Modernization enthusiasm: "Data mesh and event streaming are what I want to work on - if National Highways does this, I'll stay"

**Quotes**:
- "Give us modern tech stack and we'll deliver amazing things - keep us on legacy Oracle and we'll leave"

**Follow-up Actions**:
- Include in architecture design sessions (monthly)
- Allocate training budget (£5k per engineer for certifications)
- Recognize technical contributions (conference speaking, open source)

---

### Appendix B: Survey Results

**Stakeholder Priorities Survey (October 2025)**

Survey sent to 45 key stakeholders asking: "What are your top 3 priorities for this programme?"

**Results** (Top 10):
1. **Operational continuity** (78% of respondents) - maintain service availability during migration
2. **Data quality** (65%) - improve accuracy and freshness of data
3. **Security and privacy** (62%) - protect OFFICIAL-SENSITIVE data
4. **Cost control** (58%) - deliver within budget
5. **User experience** (55%) - improve frontline user tools
6. **Political delivery** (48%) - visible progress within 18 months
7. **Open data** (45%) - enable third-party innovation
8. **Staff development** (38%) - build internal capability
9. **GDS compliance** (35%) - pass Service Standard assessment
10. **Local authority integration** (28%) - enable data sharing

**Analysis**: Strong alignment on operational continuity and data quality. Lower priority on local authority integration suggests need to build case for interoperability benefits.

---

### Appendix C: References

- **Architecture Principles**: `.arckit/memory/architecture-principles.md` (National Highways Enterprise Architecture Principles v1.0)
- **Project Overview**: `PROJECT-README.md` (National Highways Data Architecture Modernization)
- **GDS Service Standard**: [gov.uk/service-manual/service-standard](https://www.gov.uk/service-manual/service-standard)
- **Technology Code of Practice**: [gov.uk/guidance/the-technology-code-of-practice](https://www.gov.uk/guidance/the-technology-code-of-practice)
- **HMT Green Book**: Business Case Methodology (HM Treasury)
- **NCSC Cloud Security Principles**: [ncsc.gov.uk/collection/cloud-security](https://www.ncsc.gov.uk/collection/cloud-security)
- **UK GDPR**: [ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/)

---

**Generated by**: ArcKit `/arckit.stakeholders` command
**Generated on**: 2025-11-13
**ArcKit Version**: 0.9.1
**Project**: National Highways Data Architecture Modernization (Project 001)
**AI Model**: Claude Sonnet 4.5 (claude-sonnet-4-5-20250929)
