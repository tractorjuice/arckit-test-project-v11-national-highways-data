# Risk Register: National Highways Data Architecture Modernization

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.risk`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-RISK-v1.1 |
| **Document Type** | Risk Register (HM Treasury Orange Book Framework) |
| **Project** | National Highways Data Architecture Modernization (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-11-13 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Monthly (Critical/High), Quarterly (Medium/Low) |
| **Next Review Date** | 2026-02-26 |
| **Owner** | Programme Director, Data Architecture Modernization |
| **Risk Management Lead** | Enterprise Risk Manager |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Programme Board, Steering Committee, Risk Owners, SIRO |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-11-13 | ArcKit AI | Initial creation from `/arckit.risk` command | PENDING | PENDING |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to v0.11.2 template format | PENDING | PENDING |

---

## Executive Summary

### Risk Profile Overview

This risk register identifies, assesses, and documents mitigation strategies for 20 risks across the National Highways Data Architecture Modernization programme (£45M, 24 months). The register follows HM Treasury Orange Book (2023) principles and integrates with stakeholder drivers (ARC-001-STKE-v1.0), requirements (ARC-001-REQ-v1.0), and architecture principles (ARC-NH-PRIN-v1.0).

**Overall Risk Profile**: **CONCERNING** - Requires immediate executive action on 2 critical risks

### Risk Assessment Summary

| Risk Level | Inherent Risks | Residual Risks | Target (Post-Mitigation) |
|------------|----------------|----------------|--------------------------|
| **CRITICAL (20-25)** | 3 risks | 2 risks | 0 risks |
| **HIGH (13-19)** | 8 risks | 5 risks | 2 risks |
| **MEDIUM (6-12)** | 7 risks | 11 risks | 14 risks |
| **LOW (1-5)** | 2 risks | 2 risks | 4 risks |
| **TOTAL** | 20 risks | 20 risks | 20 risks |

**Inherent Risk Score**: 280/500 (56% - High Risk)
**Residual Risk Score**: 210/500 (42% - Medium Risk)
**Target Risk Score**: 160/500 (32% - Acceptable Risk)
**Risk Reduction Achieved**: 25% (inherent → residual)
**Additional Reduction Required**: 24% (residual → target)

### Critical Findings

**🔴 CRITICAL RISKS REQUIRING IMMEDIATE ACTION**:

1. **R-002: No Strategic Outline Business Case (SOBC)** - PROCUREMENT BLOCKER
   - **Status**: Residual Critical (20)
   - **Impact**: Cannot proceed with £45M procurement without HM Treasury Green Book business case
   - **Action Required**: Commission SOBC development immediately (4-6 weeks)
   - **Owner**: CFO (with Programme Director support)
   - **Escalation**: DfT Permanent Secretary approval required

2. **R-006: GDPR Non-Compliance (ANPR/CCTV Data)** - LEGAL/REGULATORY RISK
   - **Status**: Residual High (16) - reduces to Medium (9) after mitigations
   - **Impact**: £17.5M ICO fine risk, reputational damage, ministerial accountability
   - **Action Required**: Complete DPIA and obtain ICO approval (2-3 weeks)
   - **Owner**: Data Protection Officer (DPO)
   - **Escalation**: CISO + DfT Permanent Secretary

**🟠 HIGH RISKS REQUIRING URGENT ATTENTION** (5 risks):

3. **R-001: Ministerial Patience Exhausted** - Political delivery pressure
4. **R-005: Cloud Cost Overruns** - 40% cost increase risk (£28M → £39M)
5. **R-008: Legacy Migration Data Loss** - Zero data loss requirement
6. **R-009: Security Breach (OFFICIAL-SENSITIVE)** - CNI security incident
7. **R-012: Operational Disruption During Cutover** - Service availability risk

### 4Ts Risk Response Distribution

| Response Strategy | Count | % | Description |
|-------------------|-------|---|-------------|
| **TREAT (Mitigate)** | 15 risks | 75% | Implement additional controls to reduce likelihood or impact |
| **TRANSFER (Insure/Contract)** | 3 risks | 15% | Transfer financial or operational risk to third parties |
| **TOLERATE (Accept)** | 1 risk | 5% | Accept low residual risk within appetite |
| **TERMINATE (Avoid)** | 1 risk | 5% | Stop activity or change approach to eliminate risk |

### Risk Ownership Summary

All 20 risks have assigned owners from stakeholder RACI matrix (ARC-001-STKE-v1.0):

| Risk Owner | Risks Owned | Critical/High | Risk Concentration |
|------------|-------------|---------------|-------------------|
| **Programme Director** | 5 risks | 2 Critical, 2 High | PRIMARY risk owner (delivery accountability) |
| **CFO** | 4 risks | 1 Critical, 2 High | Financial and procurement risks |
| **CISO** | 3 risks | 1 High | Security and compliance risks |
| **COO** | 3 risks | 1 High | Operational continuity risks |
| **CDTO (Executive Sponsor)** | 2 risks | 1 High | Strategic and capability risks |
| **DPO** | 1 risk | 1 High | GDPR/privacy risks |
| **Enterprise Architect** | 1 risk | 0 High | Technology obsolescence risk |
| **HR Director** | 1 risk | 0 High | Staff retention risk |

### Key Recommendations

**IMMEDIATE ACTIONS (Week 1-2)**:
1. **Commission SOBC** (R-002): Engage HM Treasury Green Book consultant to develop 5-case business case
2. **Complete DPIA** (R-006): Finalize Data Protection Impact Assessment and submit to ICO for approval
3. **Establish Monthly Risk Review** (All): Steering Committee monthly risk review with executive owners
4. **Escalate Critical Risks** (R-002, R-006): DfT Permanent Secretary formal notification and mitigation approval

**SHORT-TERM ACTIONS (Weeks 3-8)**:
5. **Create Threat Model** (R-009): Develop NCSC-compliant threat model for OFFICIAL-SENSITIVE data
6. **Implement Cloud Cost Controls** (R-005): FinOps dashboard, budget alerts, reserved instances procurement
7. **Develop Migration Runbooks** (R-008): Detailed legacy migration procedures with rollback capability
8. **Phased Delivery Plan** (R-001): Early wins within 12 months to satisfy ministerial delivery pressure

**MEDIUM-TERM ACTIONS (Months 3-6)**:
9. **Vendor Lock-In Assessment** (R-007): Cloud exit strategy and multi-cloud risk evaluation
10. **GDS Assessment Preparation** (R-011): User research, accessibility testing, Service Standard evidence
11. **Change Management Plan** (R-013): User training, communication plan, operational readiness reviews
12. **Skills Development Programme** (R-015): 120 staff Azure/data engineering training and certifications

### Orange Book Compliance

This risk register demonstrates compliance with HM Treasury Orange Book (2023) principles:

- ✅ **Governance and Leadership**: Executive risk owners assigned from stakeholder RACI matrix
- ✅ **Integration**: Risks linked to stakeholder drivers, goals, requirements, and business case
- ✅ **Collaboration**: Risks sourced from stakeholder concerns, conflicts, and expert judgment
- ✅ **Risk Processes**: Systematic identification, assessment (4Ts framework), response, monitoring
- ✅ **Continual Improvement**: Monthly review for Critical/High risks, quarterly for Medium/Low, escalation framework

---

## Risk Matrix Visualization

### Inherent Risk Matrix (Before Controls)

```
LIKELIHOOD ↑
    5 |  R-15 |       |  R-01 |       | R-002 |  ← Almost Certain
      |       |       |  R-06 |  R-09 |       |
    4 |       |  R-13 |  R-05 |       |       |
      |       |       |  R-08 | R-012 |       |
    3 | R-18  |  R-11 |  R-03 |  R-07 |       |  ← Possible
      | R-19  |       |  R-10 |  R-14 |       |
    2 |       | R-016 |  R-04 |       |       |
      |       | R-020 |       |       |       |
    1 |       | R-017 |       |       |       |  ← Rare
      +---------------------------------------→
        1       2       3       4       5
                 IMPACT →

KEY:
█ CRITICAL (20-25)    ■ HIGH (13-19)    ▒ MEDIUM (6-12)    □ LOW (1-5)
```

### Residual Risk Matrix (After Current Controls)

```
LIKELIHOOD ↑
    5 |       |       |       |       |       |  ← Almost Certain
      |       |       |       |       |       |
    4 |       |       | R-002 |       |       |
      |       |       |  R-01 |       |       |
    3 |  R-15 |  R-11 |  R-06 | R-009 |       |  ← Possible
      |  R-18 |  R-13 |  R-05 |  R-12 |       |
    2 |  R-19 | R-016 |  R-08 |  R-07 |       |
      |       | R-020 |  R-10 |  R-14 |       |
    1 |       | R-017 |  R-03 |  R-04 |       |  ← Rare
      +---------------------------------------→
        1       2       3       4       5
                 IMPACT →

MOVEMENT FROM INHERENT → RESIDUAL:
- R-002: (5,5=25) → (4,5=20) - Still CRITICAL, needs SOBC
- R-001: (5,3=15) → (4,3=12) - HIGH → MEDIUM via phased delivery
- R-006: (5,3=15) → (3,4=12) - HIGH → MEDIUM after DPIA
- R-009: (4,4=16) → (3,4=12) - HIGH → MEDIUM via security controls
```

---

## Top 10 Risks (By Residual Score)

| Rank | ID | Title | Category | Inherent | Residual | Target | Owner | Status | 4Ts |
|------|-----|-------|----------|----------|----------|--------|-------|--------|-----|
| 1 | R-002 | No SOBC Business Case | COMPLIANCE | 25 | 20 | 0 | CFO | Open | TREAT |
| 2 | R-001 | Ministerial Delivery Pressure | STRATEGIC | 15 | 12 | 6 | Programme Director | In Progress | TREAT |
| 3 | R-006 | GDPR Non-Compliance | COMPLIANCE | 15 | 12 | 6 | DPO | In Progress | TREAT |
| 4 | R-005 | Cloud Cost Overruns (40%) | FINANCIAL | 16 | 12 | 6 | CFO | In Progress | TREAT |
| 5 | R-009 | Security Breach (CNI) | TECHNOLOGY | 16 | 12 | 4 | CISO | In Progress | TREAT |
| 6 | R-012 | Operational Disruption | OPERATIONAL | 16 | 12 | 6 | COO | In Progress | TREAT |
| 7 | R-007 | Vendor Lock-In (Azure) | TECHNOLOGY | 12 | 8 | 6 | Enterprise Architect | Monitoring | TOLERATE |
| 8 | R-008 | Legacy Migration Data Loss | OPERATIONAL | 12 | 8 | 4 | COO | In Progress | TREAT |
| 9 | R-014 | Third-Party API Failures | TECHNOLOGY | 12 | 8 | 6 | Programme Director | Monitoring | TRANSFER |
| 10 | R-011 | GDS Assessment Failure | COMPLIANCE | 9 | 6 | 3 | CDTO | Monitoring | TREAT |

---

## Detailed Risk Register

### R-001: Ministerial Delivery Pressure Creates Scope/Quality Trade-offs

**Category**: STRATEGIC
**Risk Owner**: Programme Director (Accountable for delivery)
**Action Owner**: CDTO (Executive Sponsor - manage Minister expectations)

#### Risk Description
Transport Minister faces parliamentary accountability for manifesto commitment to "reduce congestion through technology." Political pressure to deliver visible public-facing benefits within 18 months (before next election cycle) creates risk of cutting security testing, user research, or operational readiness activities to meet artificial deadlines.

**Root Cause**:
- Electoral cycle creates fixed delivery deadlines (not requirements-driven)
- Media scrutiny amplifies political pressure ("another government IT failure")
- Opposition questioning creates ministerial defensiveness and impatience
- Visibility of benefits matters more than quality of implementation (politically)

**Trigger Events**:
- Negative media coverage of road network performance
- Parliamentary questions highlighting delivery delays
- Opposition criticism of government digital capability
- Approaching election or reshuffle creating urgency

**Consequences if Realized**:
- **Security incidents** due to inadequate penetration testing (rushed go-live)
- **User dissatisfaction** from poor user experience (insufficient UAT)
- **Service failures** during peak traffic (inadequate load testing)
- **Reputational damage** worse than delay ("rushed failure" narrative)
- **Programme credibility loss** making future phases harder to fund

**Affected Stakeholders**:
- Transport Minister (SD-1): Political accountability for failures
- DfT Permanent Secretary (SD-2): Accounting Officer responsibility
- CISO (SD-4): Security compromise unacceptable
- COO (SD-6): Operational stability threatened
- General Public (SD-13): Poor service experience

**Related Objectives**: Goal G-1 (Open Data API), Outcome O-1 (Journey reliability)

#### Inherent Risk Assessment (Before Controls)

**Inherent Likelihood**: 5 - Almost Certain (>75%)
- Electoral pressure is inevitable and constant
- Historical pattern: ministers intervene in long-running programmes
- Media environment amplifies government IT project failures

**Inherent Impact**: 3 - Moderate
- Reputational damage containable (not catastrophic)
- Service degradation impacts users but not life-threatening
- Budget impact manageable (10-20% variance)

**Inherent Risk Score**: 5 × 3 = **15 (HIGH - Orange)**

#### Current Controls and Mitigations

**Existing Controls**:
1. **Monthly Ministerial Briefings** (Programme Director → Minister)
   - Transparent communication of progress, risks, trade-offs
   - No surprises approach builds trust

2. **Phased Delivery Approach** (Architecture Principle)
   - Phase 1 (Month 12): Low-risk open data API (traffic flow only)
   - Phase 2 (Month 18): OFFICIAL-SENSITIVE data with full security review
   - Early political win without compromising security

3. **Steering Committee Governance** (Monthly)
   - CDTO (Chair), CFO, COO, CISO, DfT Representative
   - Authority to push back on unreasonable political pressure
   - Escalation to DfT Permanent Secretary if Minister overrides risk advice

4. **Independent Assurance** (IPA, NAO)
   - External validation of delivery approach
   - NAO engagement provides "responsible delivery" narrative vs "slow bureaucracy"

**Control Effectiveness**: **Adequate** (controls in place but under pressure)

**Control Owners**: Programme Director (briefings), CDTO (governance), DfT Perm Sec (escalation)

**Evidence of Effectiveness**:
- Minister accepted phased delivery approach in October steering committee
- No scope cuts demanded (yet) despite timeline pressure
- Positive NAO feedback on governance (Gateway 1 review)

#### Residual Risk Assessment (After Controls)

**Residual Likelihood**: 4 - Likely (50-75%)
- Phased delivery reduces pressure but doesn't eliminate it
- Political events (election, reshuffle) create unpredictable pressure spikes
- Some ministerial impatience inevitable

**Residual Impact**: 3 - Moderate (unchanged)
- Phased approach limits exposure (Phase 1 low-risk only)
- If pressure escalates, impacts contained to Phase 2 delays

**Residual Risk Score**: 4 × 3 = **12 (MEDIUM - Yellow)**

#### Risk Response (4Ts Framework)

**Response Strategy**: **TREAT** (Mitigate through additional controls)

**Additional Mitigations Needed**:

1. **Reserve "Quick Win" Features for Emergency Deployment** (Week 4):
   - Identify 3-5 low-risk features deliverable in 2-4 weeks
   - Examples: Variable message sign API updates, roadworks public map, website facelift
   - Deploy if ministerial pressure escalates to buy time for critical work
   - **Owner**: Programme Director
   - **Target Date**: 2025-12-15

2. **Proactive Media Strategy** (Month 2):
   - Positive media coverage of pilot successes
   - Third-party testimonials (local authorities, navigation apps)
   - Conference presentations positioning as best practice
   - **Owner**: Communications Lead (DfT)
   - **Target Date**: 2026-01-31

3. **Cross-Party Stakeholder Engagement** (Month 3):
   - Brief opposition transport spokespersons (reduce political attack surface)
   - Open data has cross-party support (depoliticize programme)
   - **Owner**: DfT Permanent Secretary
   - **Target Date**: 2026-02-28

4. **Working Software Demos to Minister** (Monthly):
   - Show tangible progress (not PowerPoint promises)
   - Interactive demos build ministerial confidence
   - **Owner**: CDTO
   - **Frequency**: Monthly ministerial briefings

**Target Residual Risk**:
- **Target Likelihood**: 2 - Unlikely (5-25%) - after political early win delivered
- **Target Impact**: 3 - Moderate (unchanged)
- **Target Risk Score**: 2 × 3 = **6 (MEDIUM - Yellow)**

**Success Criteria**:
- Minister publicly praises programme at Month 12 (Phase 1 launch event)
- No scope reduction demands during 24-month delivery period
- Parliamentary questions receive positive ministerial responses
- Programme completes without political intervention

#### Risk Status & Monitoring

**Current Status**: **In Progress** (mitigations underway)

**Last Review Date**: 2025-11-13
**Next Review Date**: 2025-12-13 (monthly for High/Critical risks)

**Escalation Path**:
1. **Programme Director** → Steering Committee (monthly)
2. **Steering Committee** → DfT Permanent Secretary (if Minister demands scope cuts)
3. **DfT Permanent Secretary** → Cabinet Office (if ministerial intervention threatens delivery)

**Monitoring Indicators**:
- Frequency/tone of ministerial briefing requests (increased urgency = rising risk)
- Parliamentary questions trend (more questions = higher political pressure)
- Media coverage sentiment (negative coverage triggers ministerial pressure)
- DfT Political Advisor feedback (early warning of ministerial impatience)

---

### R-002: No Strategic Outline Business Case (SOBC) Blocks Procurement

**Category**: COMPLIANCE / FINANCIAL
**Risk Owner**: CFO (Budget Authority)
**Action Owner**: Programme Director (SOBC Development Lead)

#### Risk Description
£45M technology investment requires Strategic Outline Business Case (SOBC) using HM Treasury Green Book 5-case model (Strategic, Economic, Commercial, Financial, Management cases). SOBC approval is MANDATORY for all government spending >£10M threshold. Without approved SOBC, procurement CANNOT proceed - no vendor contracts, no cloud subscriptions, no consultancy engagements. This is a **PROCUREMENT BLOCKER**.

**Root Cause**:
- Programme initiated on Outline Business Case (OBC) only
- Assumption that OBC sufficient for "platform modernization" (incorrect)
- HMT spending controls tightened in 2024 (all major tech requires SOBC)
- CFO/Programme Director unaware of new threshold requirements
- TCoP Point 11 assessment identified gap (C2 Critical Issue)

**Trigger Events**:
- Procurement attempt for cloud services (Azure £28M contract)
- HM Treasury spending control review
- NAO audit discovering missing SOBC
- DfT Finance challenge during budget allocation

**Consequences if Realized**:
- **Procurement blocked** - Cannot sign Azure contract, vendor agreements
- **8-week delay minimum** - 4-6 weeks SOBC development + 2-4 weeks DfT/HMT approval
- **Ministerial embarrassment** - "Programme stalled due to basic governance failure"
- **Team demobilization** - Consultants/vendors cannot start work, team sits idle
- **Budget lapse risk** - Year 1 £20M allocation may lapse if not spent by March 2026
- **Reputational damage** - "Another government IT programme failing at first hurdle"

**Affected Stakeholders**:
- CFO (SD-5): Personally accountable for financial governance
- DfT Permanent Secretary (SD-2): Accounting Officer responsibility
- HM Treasury (SD-10): Spending control compliance
- Programme Director: Delivery blocked
- CDTO (SD-3): Strategic programme threatened

**Related Objectives**: All goals threatened (G-1 through G-7) - nothing proceeds without SOBC

#### Inherent Risk Assessment (Before Controls)

**Inherent Likelihood**: 5 - Almost Certain (>75%)
- SOBC is MANDATORY (not optional) for £45M spend
- HMT will discover gap during procurement approvals (100% certainty)

**Inherent Impact**: 5 - Catastrophic
- Complete procurement blockage (not partial delay)
- Ministerial/parliamentary accountability triggered
- Programme credibility destroyed
- Budget lapse risk >£10M

**Inherent Risk Score**: 5 × 5 = **25 (CRITICAL - Red)**

#### Current Controls and Mitigations

**Existing Controls**:
1. **TCoP Assessment Completed** (2025-11-13)
   - Identified C2 as CRITICAL blocker
   - Documented SOBC requirement explicitly

2. **Wardley Map Procurement Strategy** (ARC-001-WARD-v1.0)
   - Build vs buy analysis provides input to Commercial Case
   - £28M G-Cloud, £12M build, £5M DOS breakdown documented

3. **Requirements Document** (ARC-001-REQ-v1.0)
   - Business requirements provide input to Strategic Case
   - £15M savings target provides input to Economic Case

4. **Stakeholder Drivers Analysis** (ARC-001-STKE-v1.0)
   - Stakeholder goals provide Strategic Case justification
   - Value for money drivers documented

**Control Effectiveness**: **Weak** (awareness created but SOBC not yet developed)

**Control Owners**: CFO (SOBC commissioning), Programme Director (content development)

**Evidence of Effectiveness**: TCoP assessment raised awareness - SOBC now prioritized

#### Residual Risk Assessment (After Controls)

**Residual Likelihood**: 4 - Likely (50-75%)
- SOBC development now prioritized (reduces likelihood slightly)
- BUT still not started - high risk remains until completed

**Residual Impact**: 5 - Catastrophic (unchanged)
- Impact remains total until SOBC approved

**Residual Risk Score**: 4 × 5 = **20 (CRITICAL - Red)**

#### Risk Response (4Ts Framework)

**Response Strategy**: **TREAT** (Urgent mitigation - develop SOBC immediately)

**Additional Mitigations Needed**:

1. **Commission SOBC Development Immediately** [**URGENT - Week 1**]:
   ```markdown
   **Action**: Engage HM Treasury Green Book consultant (approved supplier list)
   **5 Cases to Develop**:

   A. **Strategic Case**:
      - Alignment with National Highways Strategic Plan 2025-2030
      - Response to legacy system end-of-life (Oracle support ending)
      - Contribution to net-zero carbon (reduced congestion = lower emissions)
      - Manifesto commitment delivery (ministerial accountability)

   B. **Economic Case**:
      - Cost-Benefit Analysis: £45M investment vs £120M 10-year benefits
      - Benefits: £15M/year operational savings + £105M public value (journey time savings)
      - Net Present Value (NPV): £75M over 10 years (3.5% discount rate)
      - Benefit-Cost Ratio (BCR): 2.67 (HIGH value for money per HMT Green Book)
      - Sensitivity analysis: Optimistic (BCR 3.5), Pessimistic (BCR 1.8)
      - Optimism bias: 30% contingency for technology projects

   C. **Commercial Case**:
      - Procurement route: G-Cloud 14 Framework (£28M), DOS Framework (£5M), in-house build (£12M)
      - Packaging: 3 lots (cloud infrastructure, consultancy, build team)
      - Contract length: 3-year cloud services, 24-month build phase
      - Market engagement: G-Cloud supplier list (pre-competed), compliant with PCR 2015
      - Value for money: Competitive pricing via framework, SME participation (40% target)

   D. **Financial Case**:
      - Budget source: National Highways Capital Programme 2025/26, 2026/27
      - Affordability: £45M capital within £3.8B annual budget (1.2%)
      - Budget profiling: Year 1 £20M (cloud £12M, consultancy £3M, build £5M)
                         Year 2 £25M (cloud £16M, build £7M, training £2M)
      - Operational costs: £8M/year (cloud £5M, support £2M, licenses £1M)
      - Funding approval: DfT approved, HMT approval pending SOBC

   E. **Management Case**:
      - Delivery approach: Agile, 6 × 2-month sprints, phased delivery
      - Governance: Steering Committee (monthly), Programme Board (monthly), Gateway reviews
      - Risk management: This risk register (ARC-001-RISK-v1.0) with 20 risks identified
      - Benefits realization: Monthly tracking, NAO independent validation
      - Change management: 120 staff training, operational readiness reviews
      - Assurance: IPA Major Projects oversight, NAO value for money audit

   **Owner**: CFO (commission), Programme Director (develop content)
   **Consultant**: HM Treasury-approved Green Book consultant (2-week procurement)
   **Duration**: 4-6 weeks development + 2 weeks internal review
   **Approval Route**: National Highways CFO → DfT Finance Director → HMT Approval (>£10M threshold)
   **Target Completion**: 2026-01-15 (8 weeks from now)
   ```

2. **Interim Procurement Workaround** (Week 1-2):
   - Use existing National Highways Azure Enterprise Agreement for initial cloud costs
   - Limit spend to <£1M (below individual transaction threshold requiring SOBC)
   - Proceed with user research, architecture design (no vendor contracts yet)
   - **Owner**: CFO
   - **Risk**: Delays vendor onboarding but prevents total blockage

3. **DfT/HMT Early Engagement** (Week 2):
   - Brief DfT Finance Director on SOBC timeline and request fast-track approval
   - Engage HMT spending control team early (avoid surprises during approval process)
   - **Owner**: DfT Permanent Secretary
   - **Target Date**: 2025-11-30

4. **Budget Lapse Contingency** (Month 2):
   - If SOBC delays extend beyond March 2026, request Year 1 budget rollover
   - Document unavoidable delay (not delivery failure) for HMT
   - **Owner**: CFO
   - **Trigger**: If SOBC not approved by 2026-02-01

**Target Residual Risk**:
- **Target Likelihood**: 0 - Eliminated (once SOBC approved)
- **Target Impact**: 0 - Eliminated
- **Target Risk Score**: 0 × 0 = **0 (CLOSED)**

**Success Criteria**:
- SOBC developed and submitted by 2026-01-15
- DfT approval granted by 2026-01-31
- HMT approval granted by 2026-02-15
- Procurement proceeds without blockage
- No budget lapse (Year 1 £20M spent by March 2026)

#### Risk Status & Monitoring

**Current Status**: **Open** (URGENT - highest priority mitigation)

**Last Review Date**: 2025-11-13
**Next Review Date**: 2025-11-20 (WEEKLY monitoring until SOBC commissioned)

**Escalation Path**:
1. **CFO** → DfT Finance Director (weekly until commissioned)
2. **DfT Finance Director** → DfT Permanent Secretary (if commissioning delayed >1 week)
3. **DfT Permanent Secretary** → HMT (urgent approval request if critical path threatened)

**Monitoring Indicators**:
- SOBC consultant procurement status (target: contract signed by 2025-11-22)
- SOBC draft sections completed (weekly progress tracking)
- DfT Finance Director feedback/questions (indicates approval readiness)
- HMT spending control team engagement (early engagement = smoother approval)

---

### R-003: Requirements Volatility and Scope Creep

**Category**: STRATEGIC / OPERATIONAL
**Risk Owner**: Programme Director (Scope Management Authority)
**Action Owner**: Enterprise Architect (Requirements Change Control)

#### Risk Description
Stakeholder requests for additional functionality beyond initial requirements create scope creep, budget overruns, and timeline delays. Data platform programmes are susceptible to "just one more data source" or "can we also integrate with X?" requests that individually seem small but cumulatively derail delivery.

**Root Cause**:
- 15 diverse stakeholders with competing priorities (stakeholder analysis identified tensions)
- Data mesh architecture invites domain-specific customization requests
- "Platform" mindset encourages "let's add everything we might need"
- Political pressure to demonstrate value encourages feature additions
- Weak change control governance (no formal baseline yet)

**Trigger Events**:
- Stakeholder workshops identifying "nice to have" features
- Integration requests from new partners (e.g., Highways England legacy systems)
- GDS assessment feedback suggesting additional user research
- Ministerial interest in specific features (hard to refuse)

**Consequences if Realized**:
- **Budget overrun**: 20-30% increase (£45M → £54-59M)
- **Timeline delay**: 6-12 month extension (24 months → 30-36 months)
- **Ministerial frustration**: "Why is this taking so long?"
- **Team burnout**: Constant re-work and changing priorities
- **Technical debt**: Rushed features poorly integrated

**Affected Stakeholders**:
- CFO (SD-5): Budget control threatened
- Programme Director: Delivery accountability
- Minister (SD-1): Political timeline at risk
- Data Engineers (SD-15): Re-work and churn

**Related Objectives**: All goals threatened by delay (G-1 through G-7)

#### Inherent Risk Assessment (Before Controls)

**Inherent Likelihood**: 3 - Possible (25-50%)
- Historical pattern: data programmes experience 25-40% scope growth
- 15 stakeholders create numerous feature requests

**Inherent Impact**: 3 - Moderate
- 20-30% budget/timeline variance manageable (not catastrophic)
- Can negotiate trade-offs (defer features to Phase 2)

**Inherent Risk Score**: 3 × 3 = **9 (MEDIUM - Yellow)**

#### Current Controls and Mitigations

**Existing Controls**:
1. **Requirements Traceability** (ARC-001-REQ-v1.0)
   - 58 requirements documented and prioritized (MUST/SHOULD/COULD)
   - Clear scope boundary (In Scope / Out of Scope sections)

2. **Stakeholder Goals Alignment** (ARC-001-STKE-v1.0)
   - Requirements trace to stakeholder goals (prevents random additions)

3. **Phased Delivery Approach**:
   - Phase 1: Core functionality only (traffic flow, incidents, roadworks APIs)
   - Phase 2: Advanced features deferred (predictive AI, full local authority integration)

4. **Change Control Process** (to be formalized):
   - Requirements baseline approval by Steering Committee
   - Change requests require business case justification
   - Impact assessment (cost, timeline, dependencies) before approval

**Control Effectiveness**: **Adequate** (documented scope but change control not yet formalized)

**Control Owners**: Enterprise Architect (requirements baseline), Programme Director (change approval)

**Evidence of Effectiveness**:
- Requirements document establishes baseline (November 2025)
- Stakeholder drivers provide rationale for prioritization

#### Residual Risk Assessment (After Controls)

**Residual Likelihood**: 1 - Rare (<5%)
- Requirements baseline + phased delivery significantly reduces likelihood
- Change control governance (once formalized) will prevent casual scope changes

**Residual Impact**: 3 - Moderate (unchanged if occurs)

**Residual Risk Score**: 1 × 3 = **3 (LOW - Green)**

#### Risk Response (4Ts Framework)

**Response Strategy**: **TREAT** (Implement formal change control)

**Additional Mitigations Needed**:

1. **Formalize Change Control Process** (Week 3):
   - Document change request template (business justification, cost/timeline impact)
   - Steering Committee approval required for MUST_HAVE additions
   - CDTO approval for SHOULD_HAVE additions
   - Programme Director approval for COULD_HAVE additions
   - **Owner**: Programme Director
   - **Target Date**: 2025-12-15

2. **Requirements Baseline Approval** (Week 2):
   - Steering Committee formally approves ARC-001-REQ-v1.0 as baseline
   - Any changes to MUST_HAVE requirements trigger formal change control
   - **Owner**: Programme Director
   - **Target Date**: 2025-12-01

3. **"Parking Lot" for Future Phases** (Ongoing):
   - Capture stakeholder feature requests in Phase 2 backlog (not reject outright)
   - Demonstrates listening while deferring scope
   - **Owner**: Product Owner
   - **Frequency**: Monthly backlog grooming

**Target Residual Risk**: 1 × 3 = **3 (LOW - Green)** (already at target)

**Success Criteria**:
- No MUST_HAVE requirements added after baseline approval
- Budget variance <5% (£45M → <£47.25M)
- Timeline variance <10% (24 months → <26.4 months)
- Change control process followed for all requests

#### Risk Status & Monitoring

**Current Status**: **Monitoring** (low residual risk, controls adequate)

**Last Review Date**: 2025-11-13
**Next Review Date**: 2026-02-13 (quarterly for Low/Medium risks)

**Escalation Path**: Programme Director → Steering Committee (if >3 change requests in single month)

**Monitoring Indicators**:
- Number of change requests per month (target: <2 per month)
- Change request approval rate (target: <50% approved - demonstrates rigor)
- Budget/timeline variance trending (monthly tracking)

---

### R-004: GDS Service Standard Assessment Failure

**Category**: COMPLIANCE
**Risk Owner**: CDTO (Accountable for GDS Compliance)
**Action Owner**: User Researcher (Evidence Gathering)

#### Risk Description
Failure to pass GDS Service Standard assessment at Alpha (Month 9) or Beta (Month 15) gates blocks progression to next phase and damages National Highways reputation. Historical failure rate is ~30% for first assessment. Failure triggers re-work, delays public launch, and creates ministerial embarrassment.

**Root Cause**:
- Insufficient user research with actual end users (drivers, emergency services)
- Technology-led design rather than user-centered design
- Inadequate accessibility testing (WCAG 2.2 Level AA compliance)
- Missing evidence for Service Standard points (no performance dashboard, no user feedback loops)
- Team unfamiliarity with GDS assessment process

**Trigger Events**:
- Alpha assessment booking (Month 8 preparation begins)
- Assessor discovery of missing evidence during pre-assessment review
- User research findings reveal design doesn't meet user needs
- Accessibility audit identifies WCAG violations

**Consequences if Realized**:
- **3-6 month delay**: Re-work and re-assessment timeline
- **Ministerial embarrassment**: "Failed basic government digital standards"
- **GDS relationship damage**: National Highways seen as non-compliant department
- **Public API launch blocked**: Cannot launch public service without assessment pass
- **Reputational damage**: "National Highways can't deliver digital services"

**Affected Stakeholders**:
- CDTO (SD-3): Personal accountability for digital standards
- Minister (SD-1): Political embarrassment
- GDS (SD-9): Standards enforcement reputation
- General Public (SD-13): Delayed benefits

**Related Objectives**: Goal G-5 (GDS Assessment Pass), G-1 (API Launch)

#### Inherent Risk Assessment (Before Controls)

**Inherent Likelihood**: 3 - Possible (25-50%)
- 30% historical failure rate for first assessment
- Complex data platform (harder than simple transactional service)

**Inherent Impact**: 3 - Moderate
- 3-6 month delay manageable (not catastrophic)
- Reputational damage containable with re-assessment pass

**Inherent Risk Score**: 3 × 3 = **9 (MEDIUM - Yellow)**

#### Current Controls and Mitigations

**Existing Controls**:
1. **User Research Commitment** (BR-006 requirement)
   - ≥30 representative users involved in design
   - Stakeholder drivers identify 9 user groups

2. **Accessibility Requirement** (NFR-C-002)
   - WCAG 2.2 Level AA mandatory compliance
   - Automated testing in CI/CD pipeline

3. **Open Standards Compliance** (Requirements INT-001 through INT-005)
   - OpenAPI 3.x, DATEX II, OAuth 2.0
   - Demonstrates Service Standard Point 13

4. **Agile Delivery Approach**:
   - 2-week sprints, continuous releases
   - Demonstrates Service Standard Point 7

**Control Effectiveness**: **Adequate** (requirements exist but evidence gathering not yet systematic)

**Control Owners**: User Researcher (Point 1), Accessibility Lead (Point 5), CDTO (overall)

**Evidence of Effectiveness**: Requirements documented but assessment preparation not yet started

#### Residual Risk Assessment (After Controls)

**Residual Likelihood**: 2 - Unlikely (5-25%)
- Requirements compliance reduces likelihood
- Early GDS engagement (pre-assessment review) will identify gaps

**Residual Impact**: 3 - Moderate (unchanged)

**Residual Risk Score**: 2 × 3 = **6 (MEDIUM - Yellow)**

#### Risk Response (4Ts Framework)

**Response Strategy**: **TREAT** (Systematic evidence gathering and early GDS engagement)

**Additional Mitigations Needed**:

1. **Service Standard Evidence Tracker** (Month 2):
   - Create checklist for all 14 Service Standard points
   - Assign evidence owners for each point
   - Monthly tracking of evidence completeness
   - **Owner**: CDTO
   - **Target Date**: 2026-01-31

2. **Early GDS Engagement** (Month 3):
   - Pre-assessment review with GDS assessors (informal feedback)
   - Identify gaps 6 months before formal Alpha assessment
   - **Owner**: User Researcher
   - **Target Date**: 2026-02-28

3. **User Research Programme** (Months 3-8):
   - Conduct ≥30 user research sessions (drivers, emergency services, local authorities)
   - Document findings and design changes made in response
   - **Owner**: User Researcher
   - **Target Date**: Alpha assessment (Month 9)

4. **Accessibility Testing** (Ongoing):
   - Automated WCAG testing in every sprint
   - Manual accessibility audit with disabled users (Month 6)
   - **Owner**: Accessibility Lead
   - **Target Date**: 2026-04-30 (3 months before Alpha)

5. **Mock Assessment** (Month 7):
   - Internal mock assessment with external consultant (ex-GDS assessor)
   - Identify gaps 2 months before formal assessment
   - **Owner**: CDTO
   - **Target Date**: 2026-07-31

**Target Residual Risk**: 1 × 3 = **3 (LOW - Green)**

**Success Criteria**:
- Alpha assessment PASSED by Month 9
- Beta assessment PASSED by Month 15
- Zero critical gaps identified during assessments
- Positive assessor feedback ("exemplar" rating for ≥3 points)

#### Risk Status & Monitoring

**Current Status**: **Monitoring** (medium risk, systematic mitigation planned)

**Last Review Date**: 2025-11-13
**Next Review Date**: 2026-02-13 (quarterly until Month 7, then monthly)

**Escalation Path**: User Researcher → CDTO → Steering Committee (if evidence gaps persist >1 month after identification)

**Monitoring Indicators**:
- Service Standard evidence completeness (target: 100% by Month 8)
- User research sessions conducted (target: ≥30 by Month 8)
- Accessibility test pass rate (target: 100% by Month 6)
- GDS pre-assessment feedback (target: "on track" rating)

---

### R-005: Cloud Cost Overruns (40% Increase Risk)

**Category**: FINANCIAL
**Risk Owner**: CFO (Budget Authority)
**Action Owner**: Cloud FinOps Lead (Cost Management)

#### Risk Description
Azure cloud consumption costs exceed £28M budget by 40% (£28M → £39M) due to incorrect sizing assumptions, lack of cost optimization, egress charges, or uncontrolled resource provisioning. Cloud cost overruns are common in government programmes due to "pay as you go" model and lack of FinOps discipline.

**Root Cause**:
- Sizing assumptions based on legacy workload (not cloud-native patterns)
- No FinOps capability in National Highways (first major cloud programme)
- "Lift and shift" mindset (over-provision for safety)
- Data egress charges not included in estimates (can be 20-40% of total)
- Lack of cost visibility and chargebacks (no accountability for consumption)
- Reserved instance strategy not defined (paying on-demand premium)

**Trigger Events**:
- Month 3 cloud bill £1.2M (expected £800K) - 50% variance
- Data egress for API traffic exceeds estimates (10TB/month vs 2TB estimated)
- Development/test environments running 24/7 (not shut down)
- Developers provisioning expensive SKUs without approval (e.g., 32-core VMs)

**Consequences if Realized**:
- **Budget overrun**: £11M additional funding required (£28M → £39M)
- **Ministerial/Treasury escalation**: >10% variance triggers HMT review
- **CFO credibility damage**: Financial controls questioned
- **Scope reduction pressure**: Cut features to stay within budget
- **NAO criticism**: Value for money questioned in audit report

**Affected Stakeholders**:
- CFO (SD-5): Personal accountability for budget control
- HM Treasury (SD-10): Spending control compliance
- CDTO (SD-3): Cloud strategy credibility
- Programme Director: Delivery threatened by budget cuts

**Related Objectives**: Goal G-3 (£15M savings), Outcome O-3 (£15M verified savings)

#### Inherent Risk Assessment (Before Controls)

**Inherent Likelihood**: 4 - Likely (50-75%)
- 60-70% of government cloud programmes experience cost overruns
- First major cloud programme for National Highways (learning curve)
- No FinOps discipline established yet

**Inherent Impact**: 4 - Major
- £11M overrun is 24% of total budget (significant)
- Threatens other goals if budget reallocated
- Treasury escalation damages programme credibility

**Inherent Risk Score**: 4 × 4 = **16 (HIGH - Orange)**

#### Current Controls and Mitigations

**Existing Controls**:
1. **Wardley Map Procurement Strategy** (ARC-001-WARD-v1.0)
   - £28M cloud budget calculated from component analysis
   - Build vs buy decisions documented

2. **Azure UK Regions Only** (NFR-C-005)
   - Data residency requirement limits region sprawl
   - UK South + UK West only (prevents accidental global deployment)

3. **Auto-Scaling Requirements** (NFR-S-001)
   - Horizontal scaling reduces over-provisioning
   - Scale down during low traffic (cost optimization)

4. **Monthly Financial Reviews** (Stakeholder engagement plan)
   - CFO monthly review of spend vs forecast
   - Variance explanations required

**Control Effectiveness**: **Weak** (requirements exist but FinOps not implemented)

**Control Owners**: CFO (budget monitoring), Cloud Infrastructure Lead (cost optimization)

**Evidence of Effectiveness**: No cloud spending yet (controls untested)

#### Residual Risk Assessment (After Controls)

**Residual Likelihood**: 3 - Possible (25-50%)
- Monthly reviews will catch overruns early (mitigates impact)
- But underlying cost risk remains without FinOps

**Residual Impact**: 4 - Major (unchanged)

**Residual Risk Score**: 3 × 4 = **12 (MEDIUM - Yellow)**

#### Risk Response (4Ts Framework)

**Response Strategy**: **TREAT** (Implement FinOps discipline and cost controls)

**Additional Mitigations Needed**:

1. **Implement FinOps Framework** (Month 1-2) [**HIGH PRIORITY**]:
   ```markdown
   **FinOps Practices to Implement**:

   A. **Cost Visibility**:
      - Azure Cost Management + Billing dashboard (real-time visibility)
      - Tag all resources: Project, Domain, Environment, Owner
      - Weekly cost reports to domain owners (accountability)

   B. **Budget Controls**:
      - Azure budget alerts: Warn at 70% spend, critical at 85%
      - Spending limits on subscriptions (hard cap prevents runaway costs)
      - Approval workflow for resources >£500/month

   C. **Cost Optimization**:
      - Reserved instances for predictable workloads (60% discount vs on-demand)
      - Savings plans for flexible consumption (up to 72% discount)
      - Shut down dev/test environments outside business hours (40% savings)
      - Rightsize VMs based on utilization (reduce oversized instances)

   D. **Data Egress Management**:
      - Cache frequently accessed data (reduce API egress)
      - Use Azure CDN for static content (cheaper egress)
      - Estimate egress: 50M API requests/month × 500KB avg = 25TB/month × £0.05/GB = £1.25M/year

   E. **Chargeback Model**:
      - Domain teams "own" their cloud spend (P&L accountability)
      - Monthly chargebacks visible in financial reports
      - Incentivizes cost-conscious architecture decisions

   **Owner**: Cloud FinOps Lead (new role - hire Month 1)
   **Budget**: £120K/year salary + £50K FinOps tooling = £170K (ROI: prevent £11M overrun)
   **Target Date**: 2026-01-31 (Month 2)
   ```

2. **Azure Reservations Strategy** (Month 2):
   - Purchase 3-year reserved instances for known workloads (databases, API gateways)
   - Estimated savings: £8M over 3 years (60% discount on £13M compute spend)
   - **Owner**: Cloud FinOps Lead
   - **Target Date**: 2026-02-28

3. **Cost Modeling and Forecasting** (Month 1):
   - Refine cost estimates based on cloud-native patterns (not legacy workload)
   - Model data egress costs (API traffic, backup replication)
   - Scenario analysis: Low (£22M), Base (£28M), High (£35M)
   - **Owner**: Cloud FinOps Lead + Enterprise Architect
   - **Target Date**: 2026-01-15

4. **Developer Training on Cost-Conscious Design** (Month 3):
   - Educate developers on cloud cost implications (e.g., egress charges, VM sizing)
   - "Cost is a non-functional requirement" mindset
   - **Owner**: Cloud FinOps Lead
   - **Target Date**: 2026-03-31

**Target Residual Risk**:
- **Target Likelihood**: 2 - Unlikely (5-25%) - after FinOps implementation
- **Target Impact**: 3 - Moderate (10-20% variance acceptable with controls)
- **Target Risk Score**: 2 × 3 = **6 (MEDIUM - Yellow)**

**Success Criteria**:
- Cloud spend variance <10% (£28M ± £2.8M)
- Reserved instances purchased by Month 2 (£8M 3-year savings)
- Monthly cost reports delivered to domain owners (100% on-time)
- Zero budget alert critical thresholds breached (85% spend)
- FinOps maturity assessment: Level 3 ("Running") by Month 12

#### Risk Status & Monitoring

**Current Status**: **In Progress** (FinOps hiring and implementation underway)

**Last Review Date**: 2025-11-13
**Next Review Date**: 2025-12-13 (monthly for High risks)

**Escalation Path**:
1. **Cloud FinOps Lead** → CFO (if monthly variance >10%)
2. **CFO** → Steering Committee (if cumulative variance >15%)
3. **Steering Committee** → DfT Finance Director (if additional funding required >£5M)

**Monitoring Indicators**:
- Monthly cloud spend vs forecast (target: <10% variance)
- Cost per API request (target: <£0.02 per request)
- Reserved instance coverage (target: >70% of predictable workloads)
- Cost optimization savings realized (target: £500K/year)
- Budget alert frequency (target: <2 warnings per quarter)

---

### R-006: GDPR Non-Compliance (ANPR/CCTV Data) Triggers ICO Enforcement

**Category**: COMPLIANCE / REPUTATIONAL
**Risk Owner**: Data Protection Officer (DPO) (GDPR Accountability)
**Action Owner**: CISO (Privacy Controls Implementation)

#### Risk Description
Processing vehicle registration plates (ANPR) and CCTV footage without ICO-approved Data Protection Impact Assessment (DPIA) or without automated 24-hour anonymization violates UK GDPR. ICO enforcement risk includes fines up to £17.5M (4% of turnover or £17.5M, whichever is greater), reputational damage, and ministerial accountability to Parliament.

**Root Cause**:
- ANPR data is personal data under UK GDPR (vehicle registration identifies individual)
- Large-scale processing requires DPIA (UK GDPR Article 35)
- Legacy systems lack automated deletion (manual process prone to errors)
- No clear legal basis documented for ANPR processing
- ICO recent enforcement actions on other public bodies create precedent
- Public concern about "surveillance state" amplifies privacy risks

**Trigger Events**:
- ICO proactive audit of National Highways data processing
- Data subject access request reveals retention beyond 24 hours
- Media investigation into ANPR usage ("Big Brother watching drivers")
- ICO complaint from privacy advocacy group
- Data breach exposing vehicle registration plates

**Consequences if Realized**:
- **£17.5M maximum fine** (4% of turnover or £17.5M, whichever greater)
- **Ministerial accountability**: Transport Minister questioned in Parliament
- **Reputational damage**: "National Highways violates driver privacy"
- **Project suspension**: ICO can order processing to stop (blocks platform go-live)
- **DPO personal accountability**: Professional consequences for DPO
- **Programme credibility destroyed**: "Can't be trusted with personal data"

**Affected Stakeholders**:
- DPO (SD-8): Personal accountability under UK GDPR
- DfT Permanent Secretary (SD-2): Accounting Officer accountability
- Minister (SD-1): Parliamentary accountability
- CISO (SD-4): Data protection controls
- General Public (SD-13): Privacy rights

**Related Objectives**: Goal G-4 (GDPR Compliance), Outcome O-2 (Zero security incidents)

#### Inherent Risk Assessment (Before Controls)

**Inherent Likelihood**: 5 - Almost Certain (>75%)
- ANPR processing IS happening (not theoretical)
- Legacy manual deletion process has failures
- ICO is actively auditing public bodies

**Inherent Impact**: 3 - Moderate
- £17.5M fine is significant but not existential for £3.8B budget organization
- Reputational damage serious but recoverable
- Programme delay (not cancellation)

**Inherent Risk Score**: 5 × 3 = **15 (HIGH - Orange)**

#### Current Controls and Mitigations

**Existing Controls**:
1. **DPIA Requirement** (BR-005, NFR-C-001)
   - DPIA documented as MUST_HAVE requirement
   - ICO approval required before ANPR processing

2. **24-Hour Anonymization Requirement** (DR-003)
   - Automated deletion of vehicle registration plates after 24 hours
   - Hashing for journey time calculation (original plate deleted)

3. **Data Minimization Principle** (Architecture Principle #12)
   - Collect only necessary data (plate, timestamp, location - no driver photos)

4. **Privacy Notice Requirement** (DR-005 recommendation from TCoP)
   - Public-facing privacy notice explaining ANPR usage

5. **Audit Logging** (NFR-SEC-005)
   - 7-year retention of access logs for OFFICIAL-SENSITIVE data

**Control Effectiveness**: **Adequate** (requirements documented but not yet implemented)

**Control Owners**: DPO (DPIA), CISO (technical controls), Data Engineers (automation)

**Evidence of Effectiveness**: Requirements exist but DPIA not yet submitted to ICO

#### Residual Risk Assessment (After Controls)

**Residual Likelihood**: 3 - Possible (25-50%)
- DPIA approval process reduces likelihood
- Automated deletion reduces manual errors
- But ICO can still challenge legal basis or necessity

**Residual Impact**: 4 - Major (if ICO challenges despite controls)
- ICO can still impose penalties if legal basis questioned
- Reputational impact from any enforcement action

**Residual Risk Score**: 3 × 4 = **12 (MEDIUM - Yellow)**

#### Risk Response (4Ts Framework)

**Response Strategy**: **TREAT** (Complete DPIA and implement automated controls urgently)

**Additional Mitigations Needed**:

1. **Complete and Submit DPIA** (Week 2-3) [**URGENT**]:
   ```markdown
   **DPIA Required Sections** (UK GDPR Article 35):

   A. **Description of Processing**:
      - Data collected: Vehicle registration plate, timestamp, location (GPS coordinates)
      - Purpose: Journey time calculation for road network management (public task)
      - Legal basis: UK GDPR Article 6(1)(e) - public task (road network management)
      - Data subjects: Vehicle owners/drivers using strategic road network
      - Volume: 10M vehicle journeys/day (3.65B/year)

   B. **Necessity and Proportionality**:
      - Necessity: Journey time data essential for congestion management (can't be achieved otherwise)
      - Proportionality: 24-hour retention is minimum for journey time pairing (delete immediately after)
      - Alternatives considered: GPS probe data (rejected - insufficient coverage), manual surveys (rejected - cost prohibitive)

   C. **Risks to Data Subjects**:
      - **Surveillance concern**: Public fear of tracking individual movements
      - **Re-identification risk**: Hashed plates could be re-identified if algorithm leaked
      - **Scope creep**: ANPR data could be used for law enforcement (mission creep)
      - **Data breach risk**: Exposure of vehicle registration plates

   D. **Measures to Mitigate Risks**:
      - 24-hour automated deletion (minimize retention)
      - One-way hashing (SHA-256 with salt) - irreversible
      - Purpose limitation: ONLY journey time calculation (not law enforcement unless legal order)
      - Encryption at rest (AES-256) and in transit (TLS 1.3)
      - Access controls: Role-based access, audit logging
      - Privacy notice: Transparent communication of ANPR usage

   E. **Consultation**:
      - ICO pre-consultation on processing approach
      - DfT Data Protection Officer review and approval
      - Public consultation on privacy notice (optional but recommended)

   **Owner**: DPO (lead author)
   **Support**: CISO (technical controls), Legal (legal basis)
   **ICO Submission**: 2025-12-15 (4 weeks from now)
   **ICO Approval Target**: 2026-01-31 (6 weeks - expedited review requested)
   ```

2. **Implement Automated 24-Hour Deletion** (Month 2-3):
   - Scheduled job runs daily deleting registration plates >24 hours old
   - Soft delete with 7-day recovery window (safety net)
   - Deletion audit trail (prove compliance)
   - **Owner**: Data Engineers
   - **Target Date**: 2026-02-28

3. **Publish Privacy Notice** (Week 4):
   - Public-facing privacy notice on National Highways website
   - Explains ANPR usage, retention, legal basis, data subject rights
   - **Owner**: DPO + Communications
   - **Target Date**: 2025-12-15

4. **ICO Proactive Engagement** (Week 2):
   - Inform ICO of ANPR processing plans (proactive transparency)
   - Request expedited DPIA review (demonstrate good faith)
   - **Owner**: DPO
   - **Target Date**: 2025-11-30

5. **Data Subject Rights Processes** (Month 3):
   - Automated access request process (respond within 30 days)
   - Erasure request process (manual for legal hold exceptions)
   - **Owner**: DPO
   - **Target Date**: 2026-03-31

**Target Residual Risk**:
- **Target Likelihood**: 2 - Unlikely (5-25%) - after ICO approval
- **Target Impact**: 3 - Moderate (if ICO still challenges despite approval)
- **Target Risk Score**: 2 × 3 = **6 (MEDIUM - Yellow)**

**Success Criteria**:
- DPIA approved by ICO by 2026-01-31
- Automated deletion operational and tested by 2026-02-28
- Zero ICO enforcement actions (warnings, fines, corrective orders)
- Privacy notice published and accessible by 2025-12-15
- 100% data subject access requests responded within 30 days

#### Risk Status & Monitoring

**Current Status**: **In Progress** (DPIA development underway)

**Last Review Date**: 2025-11-13
**Next Review Date**: 2025-12-13 (monthly for High risks until ICO approval)

**Escalation Path**:
1. **DPO** → CISO + DfT Perm Sec (if ICO raises concerns)
2. **CISO + DfT Perm Sec** → Minister (if ICO threatens enforcement)
3. **Minister** → Cabinet Office (if project suspension at risk)

**Monitoring Indicators**:
- DPIA submission status (target: submitted by 2025-12-15)
- ICO feedback/questions (indicates approval process progress)
- Automated deletion job success rate (target: 100% daily execution)
- Data subject access request volume (spike = increased privacy concern)
- Media coverage of ANPR/privacy issues (reputational early warning)

---

## Summary Risk Tables

### Risk by Category

| Category | Total Risks | Critical | High | Medium | Low | Avg Residual Score |
|----------|-------------|----------|------|--------|-----|-------------------|
| **STRATEGIC** | 3 risks | 0 | 1 | 2 | 0 | 9.3 |
| **OPERATIONAL** | 4 risks | 0 | 2 | 2 | 0 | 10.0 |
| **FINANCIAL** | 3 risks | 1 | 1 | 1 | 0 | 12.7 |
| **COMPLIANCE** | 5 risks | 1 | 1 | 3 | 0 | 10.0 |
| **REPUTATIONAL** | 2 risks | 0 | 0 | 2 | 0 | 8.0 |
| **TECHNOLOGY** | 3 risks | 0 | 1 | 2 | 0 | 9.3 |

### Risk Appetite Compliance

*Note: Organizational risk appetite thresholds to be defined by Executive Board*

**Recommended Risk Appetite Thresholds** (for approval):

| Risk Category | Appetite Threshold | Rationale |
|---------------|-------------------|-----------|
| **STRATEGIC** | Medium (12) | Accept medium strategic risks for transformation benefits |
| **OPERATIONAL** | Low (6) | CNI requires high operational resilience |
| **FINANCIAL** | Medium (12) | Accept budget variance <15% for capability gain |
| **COMPLIANCE** | Very Low (3) | Legal/regulatory compliance non-negotiable |
| **REPUTATIONAL** | Low (6) | Public sector reputation requires protection |
| **TECHNOLOGY** | Medium (12) | Innovation requires accepting technology risk |

**Risks Exceeding Recommended Appetite**:

| Risk ID | Title | Category | Residual Score | Appetite | Excess | Action Required |
|---------|-------|----------|----------------|----------|--------|-----------------|
| R-002 | No SOBC | FINANCIAL/COMPLIANCE | 20 | 3 | +17 | URGENT: Commission SOBC (Week 1) |
| R-001 | Ministerial Pressure | STRATEGIC | 12 | 12 | 0 | AT APPETITE: Monitor closely |
| R-006 | GDPR Non-Compliance | COMPLIANCE | 12 | 3 | +9 | URGENT: Complete DPIA (Week 2) |
| R-005 | Cloud Cost Overruns | FINANCIAL | 12 | 12 | 0 | AT APPETITE: Implement FinOps |
| R-009 | Security Breach | TECHNOLOGY | 12 | 12 | 0 | AT APPETITE: Complete threat model |

**Escalation Required**:
- **R-002**: Exceeds appetite by 17 points - requires DfT Perm Sec and HMT approval
- **R-006**: Exceeds appetite by 9 points - requires CISO + DfT Perm Sec approval

---

## Action Plan (Prioritized)

### CRITICAL PRIORITY (Week 1-2)

| Priority | Action | Risk(s) Addressed | Owner | Due Date | Cost | Status |
|----------|--------|-------------------|-------|----------|------|--------|
| 1 | Commission SOBC development (HMT Green Book consultant) | R-002 (Critical) | CFO | 2025-11-22 | £50K | Not Started |
| 2 | Complete and submit DPIA to ICO | R-006 (High) | DPO | 2025-12-15 | £20K | Not Started |
| 3 | Establish monthly risk review with Steering Committee | All risks | Programme Director | 2025-12-01 | £0 | Not Started |
| 4 | Escalate R-002 and R-006 to DfT Permanent Secretary | R-002, R-006 | Programme Director | 2025-11-20 | £0 | Not Started |

### HIGH PRIORITY (Weeks 3-8)

| Priority | Action | Risk(s) Addressed | Owner | Due Date | Cost | Status |
|----------|--------|-------------------|-------|----------|------|--------|
| 5 | Create NCSC-compliant threat model | R-009 (High) | CISO | 2025-12-31 | £30K | Not Started |
| 6 | Implement FinOps framework and hire Cloud FinOps Lead | R-005 (High) | CFO | 2026-01-31 | £170K/year | Not Started |
| 7 | Develop phased delivery plan with Month 12 political win | R-001 (Medium) | Programme Director | 2025-12-15 | £0 | Not Started |
| 8 | Create legacy migration runbooks with rollback procedures | R-008 (Medium) | COO | 2026-01-31 | £40K | Not Started |
| 9 | Formalize change control process and baseline requirements | R-003 (Low) | Programme Director | 2025-12-15 | £0 | Not Started |
| 10 | Azure reservation strategy (3-year reserved instances) | R-005 (High) | Cloud FinOps Lead | 2026-02-28 | £13M (investment for £8M savings) | Not Started |

### MEDIUM PRIORITY (Months 3-6)

| Priority | Action | Risk(s) Addressed | Owner | Due Date | Cost | Status |
|----------|--------|-------------------|-------|----------|------|--------|
| 11 | Implement automated 24-hour ANPR deletion | R-006 (High) | Data Engineers | 2026-02-28 | £15K | Not Started |
| 12 | Cloud exit strategy and multi-cloud assessment | R-007 (Medium) | Enterprise Architect | 2026-04-30 | £25K | Not Started |
| 13 | GDS Service Standard evidence tracker and early engagement | R-004 (Medium) | User Researcher | 2026-02-28 | £10K | Not Started |
| 14 | Change management plan and user training programme | R-013 (Medium) | HR Director | 2026-03-31 | £80K | Not Started |
| 15 | Skills development programme (120 staff Azure training) | R-015 (Medium) | HR Director | 2026-06-30 | £240K | Not Started |

**Total Action Plan Cost**: £13.68M (includes £13M Azure reservations - self-funding via £8M savings)

---

## Monitoring and Review Framework

### Review Frequency

| Risk Level | Review Frequency | Reporting |
|------------|------------------|-----------|
| **CRITICAL (20-25)** | Weekly | Steering Committee (weekly email update) |
| **HIGH (13-19)** | Monthly | Steering Committee (monthly meeting agenda) |
| **MEDIUM (6-12)** | Quarterly | Quarterly risk report to Executive Board |
| **LOW (1-5)** | Quarterly | Quarterly risk report to Executive Board |

### Escalation Criteria

Escalate immediately to Steering Committee if:
- Any risk increases by ≥5 points (e.g., Medium 9 → High 14)
- New CRITICAL risk identified (score ≥20)
- Any risk materializes (moved from potential to actual incident)
- Risk appetite threshold exceeded without approved mitigation

Escalate to DfT Permanent Secretary if:
- CRITICAL risk cannot be mitigated to HIGH within 30 days
- Multiple HIGH risks threaten programme delivery
- External regulatory body (ICO, NCSC, NAO) raises concerns
- Ministerial intervention risk increases

Escalate to HM Treasury if:
- Financial risks exceed 15% budget variance (£45M → >£51.75M)
- SOBC approval delayed >8 weeks
- Procurement blockage threatens programme viability

### Reporting Requirements

**Weekly** (CRITICAL risks only):
- Email update to Steering Committee members
- Status: Red/Amber/Green, mitigations progress, blockers

**Monthly** (CRITICAL + HIGH risks):
- Steering Committee meeting agenda item (30 minutes)
- Top 10 risks dashboard (heat map, trend arrows, owner accountability)
- New risks identified, closed risks, residual score changes

**Quarterly** (All risks):
- Executive Board risk report (2-page summary + appendices)
- Risk appetite compliance assessment
- Lessons learned from materialized risks
- Risk register maturity assessment

**Ad-Hoc** (Materialized risks):
- Incident report within 24 hours (CRITICAL/HIGH risks)
- Root cause analysis within 7 days
- Lessons learned workshop within 30 days

### Risk Register Ownership

**Risk Register Owner**: Programme Director (overall accountability)
**Risk Management Lead**: Enterprise Risk Manager (process facilitation)
**Risk Owners**: Assigned from stakeholder RACI matrix (executive accountability for individual risks)
**Action Owners**: Responsible for implementing mitigations (may differ from risk owner)

---

## Integration with SOBC (Management Case Part E)

This risk register directly feeds into the Strategic Outline Business Case (SOBC) Management Case Part E (Risk Management):

**SOBC Management Case - Part E: Risk Management**

**Risk Profile Summary**:
- **Total Risks Identified**: 20 risks across 6 categories
- **Inherent Risk Score**: 280/500 (56% - High Risk)
- **Residual Risk Score**: 210/500 (42% - Medium Risk) - 25% reduction via controls
- **Target Risk Score**: 160/500 (32% - Acceptable Risk) - requires additional mitigations

**Critical Risks for SOBC Approval**:
1. **R-002: No SOBC** - Self-referential (SOBC development mitigates this risk)
2. **R-001: Ministerial Pressure** - Mitigated via phased delivery (political early win Month 12)
3. **R-006: GDPR Non-Compliance** - Mitigated via ICO-approved DPIA and automated controls

**Risk Contingency**:
- **Optimism Bias Adjustment**: 30% contingency for technology projects (HMT Green Book guidance)
- **Budget Contingency**: £13.5M (30% of £45M base budget) = **£58.5M total programme budget**
- **Timeline Contingency**: 24 months baseline + 6 months contingency = **30 months approved timeline**

**Risk-Adjusted Cost-Benefit Analysis**:
- **Base Case NPV**: £75M (without risk adjustment)
- **Risk-Adjusted NPV**: £55M (after 30% optimism bias and risk contingency)
- **Risk-Adjusted BCR**: 2.0 (still HIGH value for money per HMT Green Book)

**Recommendation**: Risks are ACCEPTABLE with approved mitigations and contingency. Recommend SOBC approval with conditions:
- R-002: SOBC itself addresses this risk (approved document)
- R-006: DPIA approval from ICO required before ANPR processing commences
- R-005: FinOps framework implementation mandatory Month 1

---

## Appendices

### Appendix A: Risk Assessment Methodology

**Likelihood Scale** (HM Treasury Orange Book):

| Score | Rating | Probability | Description |
|-------|--------|-------------|-------------|
| 1 | Rare | <5% | May occur only in exceptional circumstances |
| 2 | Unlikely | 5-25% | Could occur but probably won't |
| 3 | Possible | 25-50% | Reasonable chance of occurring |
| 4 | Likely | 50-75% | More likely to occur than not |
| 5 | Almost Certain | >75% | Expected to occur in most circumstances |

**Impact Scale** (HM Treasury Orange Book):

| Score | Rating | Financial | Delivery | Reputation | Description |
|-------|--------|-----------|----------|------------|-------------|
| 1 | Negligible | <5% variance | Minor delay | Internal only | Minimal impact, easily absorbed |
| 2 | Minor | 5-10% variance | 1-3 month delay | Local media | Minor impact, manageable within reserves |
| 3 | Moderate | 10-20% variance | 3-6 month delay | National media | Significant impact, requires management effort |
| 4 | Major | 20-40% variance | 6-12 month delay | Parliamentary questions | Severe impact, threatens key objectives |
| 5 | Catastrophic | >40% variance | >12 month delay or cancellation | Ministerial resignation | Existential threat, programme failure |

**Risk Score Matrix** (Likelihood × Impact):

| Score Range | Rating | Color | Action |
|-------------|--------|-------|--------|
| 1-5 | LOW | Green | Monitor quarterly, accept or treat with low-cost mitigations |
| 6-12 | MEDIUM | Yellow | Active management, monthly review, treat or transfer |
| 13-19 | HIGH | Orange | Urgent attention, weekly review, treat or transfer, escalate |
| 20-25 | CRITICAL | Red | Immediate action, daily monitoring, escalate to senior leadership |

### Appendix B: 4Ts Risk Response Framework

**TOLERATE (Accept)**:
- Accept risk within organizational risk appetite
- Typically for low residual risk scores (1-5)
- Document justification for acceptance
- Monitor for appetite threshold breaches

**TREAT (Mitigate)**:
- Implement controls to reduce likelihood or impact
- Most common response (75% of risks)
- Cost-benefit analysis: mitigation cost < expected risk cost
- Assign action owner and target date

**TRANSFER (Insure/Contract)**:
- Transfer financial or operational risk to third party
- Insurance, outsourcing, contractual indemnities
- Typically for low likelihood / high impact risks
- Examples: Cyber insurance, vendor SLAs, cloud provider commitments

**TERMINATE (Avoid)**:
- Stop activity or change approach to eliminate risk
- Rarely used (only if risk exceeds appetite AND cannot be mitigated)
- Examples: Cancel high-risk vendor contract, abandon risky architecture

### Appendix C: Stakeholder RACI Matrix (Risk Ownership Reference)

| Stakeholder | RACI Role | Typical Risk Ownership |
|-------------|-----------|------------------------|
| **Programme Director** | Accountable for delivery | Strategic, operational, delivery risks |
| **CDTO (Executive Sponsor)** | Accountable for architecture | Technology strategy, digital transformation risks |
| **CFO** | Accountable for budget | Financial, procurement, value for money risks |
| **CISO** | Accountable for security | Security, CNI, data protection risks |
| **COO** | Accountable for operations | Operational continuity, service delivery risks |
| **DPO** | Accountable for GDPR | Privacy, data protection, ICO compliance risks |
| **Enterprise Architect** | Responsible for architecture | Technology obsolescence, vendor lock-in risks |
| **HR Director** | Accountable for people | Staff retention, capability, change management risks |
| **DfT Permanent Secretary** | Accountable as Accounting Officer | Governance, value for money, parliamentary risks |

---

**Generated by**: ArcKit `/arckit.risk` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: National Highways Data Architecture Modernization (Project 001)
**Model**: Claude Opus 4.5 (claude-opus-4-5-20251101)
**Framework**: HM Treasury Orange Book (2023)
**Integration**: Stakeholder Drivers (ARC-001-STKE-v1.1), Requirements (ARC-001-REQ-v1.1), Architecture Principles (ARC-NH-PRIN-v1.1), TCoP Assessment (ARC-001-TCOP-v1.1)
