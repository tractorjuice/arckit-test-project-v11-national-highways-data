# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is **arckit-test-project-v11-national-highways-data** - an ArcKit demonstration project for National Highways data architecture modernization. It showcases enterprise architecture governance using the ArcKit toolkit.

**Organization**: National Highways (UK Government)
**Scope**: England's strategic road network (£60B digital assets)
**Mission**: Modernize data architecture from legacy Oracle to cloud-native data mesh

## Using ArcKit Commands

This project uses ArcKit slash commands to generate architecture artifacts. Commands are invoked as `/arckit.{name}`:

```
/arckit.principles     Create/update architecture principles
/arckit.stakeholders   Analyze stakeholder drivers and goals
/arckit.requirements   Generate comprehensive requirements
/arckit.risk           Create Orange Book risk register
/arckit.data-model     Design data model with ERD
/arckit.wardley        Create Wardley Maps for strategy
/arckit.research       Research technology options (web search)
/arckit.tcop           Technology Code of Practice assessment
/arckit.secure         Secure by Design assessment
/arckit.analyze        Governance quality analysis
```

Full command reference: See README.md "Complete Command Reference" section.

## Project Structure

```
.arckit/
├── memory/architecture-principles.md   # Global principles (read by all commands)
├── templates/                          # Document templates
└── scripts/bash/                       # Helper scripts (create-project.sh, etc.)

projects/001-national-highways-data-architecture-modernization/
├── stakeholder-drivers.md              # Stakeholder analysis
├── risk-register.md                    # Orange Book risk register
├── requirements.md                     # BR/FR/NFR/INT/DR requirements
├── data-model.md                       # ERD and data governance
├── project-plan.md                     # GDS phases with Gantt chart
├── tcop-assessment.md                  # TCoP compliance review
├── ukgov-secure-by-design.md          # Security assessment
├── analysis-report.md                  # Governance quality analysis
└── wardley-maps/                       # Strategic Wardley Maps
```

## Key Patterns

**Traceability Chain**: Stakeholders → Goals → Requirements (BR/FR/NFR/INT/DR) → Data Model → Components

**Requirement ID Prefixes**:
- BR-xxx: Business Requirements
- FR-xxx: Functional Requirements
- NFR-xxx: Non-Functional (NFR-P-xxx Performance, NFR-SEC-xxx Security)
- INT-xxx: Integration Requirements
- DR-xxx: Data Requirements

**Token Limit Handling**: For large document generation, instruct Claude to use the Write tool directly:
```
/arckit.requirements but write directly to file using Write tool, show me only a summary
```

## Technology Context

- **Current State**: Legacy on-premises Oracle databases, fragmented data sources
- **Target State**: Cloud-native data mesh with federated data products (Azure UK regions)
- **Data Sources**: 10,000+ IoT sensors, 3,500 CCTV cameras, roadworks/incident systems
- **Data Volume**: 500TB historical + 5TB/day real-time

## UK Government Compliance

This project targets UK public sector compliance frameworks:
- GDS Service Standard (14 points)
- Technology Code of Practice (13 points)
- NCSC Secure by Design / Cyber Assessment Framework
- UK GDPR / DPA 2018
- HM Treasury Orange Book (risk management)
- HM Treasury Green Book (business case)
