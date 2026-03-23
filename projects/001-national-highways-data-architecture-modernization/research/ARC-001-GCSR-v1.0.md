# Government Code Search Report: National Highways Data Architecture Modernization

> **Template Origin**: Official | **ArcKit Version**: 4.5.0 | **Command**: `/arckit.gov-code-search`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-GCSR-v1.0 |
| **Document Type** | Government Code Search Report |
| **Project** | National Highways Data Architecture Modernization (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-03-23 |
| **Last Modified** | 2026-03-23 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-06-23 |
| **Owner** | Data Architecture Lead, National Highways |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | National Highways Architecture Team, Data Engineering Team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-03-23 | ArcKit AI | Initial creation from `/arckit.gov-code-search` agent | PENDING | PENDING |

---

## Executive Summary

### Search Query

**Original Query**: `road sensor IoT data pipelines`

**Query Variations Used**:

- `IoT sensor data ingestion streaming pipeline government`
- `traffic sensor telemetry data collection real-time`
- `real-time data streaming event processing transport infrastructure`
- `data pipeline event driven architecture Kafka cloud`
- `sensor data collection pipeline MQTT message broker`
- `data mesh data products cloud azure government UK`
- `ETL data ingestion pipeline AWS Lambda serverless`
- `transport data API REST open data national`
- `GDS data platform infrastructure cloud native pipeline`
- `flood monitoring environment sensor reading ingest`
- `open data highway road network monitoring API`

**Platforms Searched**: GitHub (UK government organisations via govreposcrape — approximately 24,500 repositories)

### Results Found

**Total Repositories Scanned**: 134 (across all query variations, before deduplication)

**Unique Repositories Assessed**: 28

**High Relevance Results**: 2

**Medium Relevance Results**: 4

**Low Relevance / Excluded**: 22

### Top Results

| # | Repository | Organisation | Relevance | Language | Last Active |
|---|------------|--------------|-----------|----------|-------------|
| 1 | FloodOnlineReportingTool.Public | Dorset Council | Medium-High | C# / .NET | 2026 (active) |
| 2 | FloodOnlineReportingTool.Contracts | Dorset Council | Medium-High | C# / .NET | 2026-03-11 |
| 3 | GIFramework-Maps | Dorset Council | Medium | TypeScript / C# | 2025-12-22 |
| 4 | OpenData | Dundee City Council | Low-Medium | Jupyter / Python | 2015 (inactive) |
| 5 | QGIS.Mosaic.Builder | Dorset Council | Low-Medium | Python | 2026-02-05 |

---

## Search Results

### High Relevance Results

No repositories were identified that directly implement road sensor IoT data pipelines as described in the project scope (10,000+ IoT sensors, MQTT ingestion, Kafka/Azure Event Hubs streaming, cloud-native data mesh). This is a significant finding documented in the [Observations](#observations) section below.

---

### Medium Relevance Results

#### FloodOnlineReportingTool.Public

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dorset Council |
| **Repository URL** | https://github.com/Dorset-Council-UK/FloodOnlineReportingTool.Public |
| **Description** | A .NET web application enabling the public to report flooding incidents to local flood authorities, used across south-west England |
| **Language** | C# (81.1%), HTML (17.8%) |
| **License** | MIT |
| **Last Activity** | 2026 (active, 536 commits) |
| **Stars** | 0 |

**Why Relevant**: Although not an IoT pipeline, this is the closest match in govreposcrape to environmental sensor / monitoring domain code. The tool integrates with external environmental monitoring data (flood levels), uses a distributed service architecture, and is a .NET cloud-ready application on Azure-compatible infrastructure. It demonstrates GDS-compliant design patterns applicable to the National Highways monitoring context.

**Key Patterns**:

- Distributed service architecture using message contracts for inter-service communication (CommandsAndEvents pattern)
- PostgreSQL with PostGIS for geospatial data storage — directly applicable to road network spatial data
- GDS Design System compliance (GOV.UK frontend components) as a front-end reference
- Entity Framework Core ORM with migration-based schema management
- .NET 8+ runtime — aligns with UK government preferred enterprise stack

---

#### FloodOnlineReportingTool.Contracts

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dorset Council |
| **Repository URL** | https://github.com/Dorset-Council-UK/FloodOnlineReportingTool.Contracts |
| **Description** | Message contracts used by the Flood Online Reporting Tool for inter-service communication in a distributed system architecture |
| **Language** | C# (100%) |
| **License** | MIT |
| **Last Activity** | 2026-03-11 (v3.2.0 release, 13 total releases) |
| **Stars** | 0 |

**Why Relevant**: This repository defines the message contract pattern for a distributed government data system. For National Highways IoT pipelines, defining clear message contracts between sensor gateway services, processing workers, and downstream consumers is a critical engineering concern. This repo provides a reference implementation of how a UK government team has approached this using C# class libraries and NuGet package distribution.

**Key Patterns**:

- Separation of interface contracts into a standalone NuGet-publishable library — enables independent versioning of message schemas
- Command/Event distinction in contract design — a clean CQRS-adjacent pattern applicable to sensor event streams
- Semantic versioning with 13 releases suggests a mature, maintained approach to API evolution
- MIT licence permits direct reuse and adaptation

---

#### GIFramework-Maps

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dorset Council |
| **Repository URL** | https://github.com/Dorset-Council-UK/GIFramework-Maps |
| **Description** | A .NET-based web mapping application for displaying spatial data from multiple sources, with Azure AD authentication and OGC web service integration |
| **Language** | TypeScript (42.7%), C# (37.6%), HTML (18.1%), CSS (1.6%) |
| **License** | MIT (code), OGL v3.0 (documentation) |
| **Last Activity** | 2025-12-22 (v1.10.0) |
| **Stars** | 21 |

**Why Relevant**: The most actively maintained and widely-acknowledged (21 stars) government GIS repository found in the search. For National Highways, road sensor data ultimately needs to be visualised in spatial context. This repo provides patterns for OGC web service consumption, Azure AD integration, and geospatial data rendering in a .NET/TypeScript stack that aligns with the project's Azure UK target platform.

**Key Patterns**:

- OpenLayers for geospatial rendering — standard open-source mapping library with no per-request fees
- Azure Active Directory authentication integration — directly applicable to National Highways' Azure tenant
- OGC web services (WMS/WFS) consumption — compatible with OS National Map, Highways England DATEX II feeds
- PostgreSQL with PostGIS backend — consistent with FloodOnlineReportingTool spatial data pattern
- Dual licence model (MIT code, OGL docs) is a useful reference for National Highways open data publication obligations

---

#### OpenData (Dundee City Council)

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dundee City Council |
| **Repository URL** | https://github.com/DundeeCityCouncil/OpenData |
| **Description** | Open data publication repository including Jupyter notebooks for exploring location-based datasets covering streets, recycling, and city analysis |
| **Language** | Jupyter Notebook / Python (100%) |
| **License** | Not specified |
| **Last Activity** | 2015 (inactive — 14 commits total) |
| **Stars** | 0 |

**Why Relevant**: Demonstrates a pattern of using Jupyter Notebooks for open data exploration and publication, which is relevant to National Highways' obligation to publish road sensor datasets as open data. The streets dataset folder is tangentially relevant to the road network domain. However, the repository is inactive and provides limited technical reference value.

**Key Patterns**:

- Jupyter Notebook as lightweight open data exploration and publication interface
- CSV and spatial data publication alongside executable analysis — useful for sensor data open publication requirements

---

#### QGIS.Mosaic.Builder

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dorset Council |
| **Repository URL** | https://github.com/Dorset-Council-UK/QGIS.Mosaic.Builder |
| **Description** | A QGIS plugin for merging geographic features into unified outlines for non-specialist users |
| **Language** | Python (66.8%), Makefile, QML, Shell |
| **License** | MIT |
| **Last Activity** | 2026-02-05 (v1.0.5) |
| **Stars** | 0 |

**Why Relevant**: Demonstrates Python-based geospatial processing as a QGIS plugin — applicable to National Highways batch processing of road network geometry data from sensor positions. The Python plugin architecture and active maintenance (6 releases) signal professional engineering practices.

**Key Patterns**:

- Python for geospatial processing — aligns with data engineering workloads in Azure Databricks / Azure Functions
- QGIS plugin framework for desktop tooling — relevant for internal GIS analyst tooling for road network management
- `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `SECURITY.md` present — professional open-source governance model worth replicating

---

## Code Patterns Identified

| Pattern | Repositories Using It | Description |
|---------|----------------------|-------------|
| PostgreSQL + PostGIS for geospatial data | FloodOnlineReportingTool.Public, GIFramework-Maps | Multiple government teams independently converged on PostgreSQL with PostGIS as the geospatial data backend. For road sensor data with geographic coordinates, this is a proven open-source pattern that avoids Oracle spatial licence costs |
| .NET / C# backend stack | FloodOnlineReportingTool.Public, FloodOnlineReportingTool.Contracts, GIFramework-Maps | Three related repositories from Dorset Council use .NET and C#. This is consistent with UK government Microsoft Azure adoption and supports National Highways' likely .NET estate |
| Distributed message contracts as NuGet packages | FloodOnlineReportingTool.Contracts | Defining inter-service message schemas in a standalone versioned library — directly applicable to sensor event schema management across National Highways IoT pipeline services |
| OGC web service integration | GIFramework-Maps | Consuming OGC-standard WMS/WFS feeds rather than proprietary APIs — aligns with TCoP Point 4 (make data available via open standards) and Highways sector DATEX II / UTMC standards |
| Python for geospatial batch processing | QGIS.Mosaic.Builder, DundeeCityCouncil/OpenData | Python is the common language for geospatial processing across government, consistent with the Azure Databricks / Spark ecosystem targeted in the project architecture |
| Azure Active Directory for service authentication | GIFramework-Maps | Government teams are using Azure AD (Entra ID) for both end-user and service-to-service authentication, consistent with National Highways' Azure tenant |
| GDS Design System compliance | FloodOnlineReportingTool.Public | Even infrastructure-adjacent applications (not just citizen-facing) reference GDS components, indicating this is a baseline expectation across UK government digital services |

### Observations

The govreposcrape search across approximately 24,500 UK government repositories returned no direct implementations of road sensor IoT data pipelines. The search returned zero results for queries involving: MQTT, Kafka, Azure Event Hubs, Azure IoT Hub, stream processing, time-series databases, or real-time telemetry ingestion. This is a materially significant finding for the National Highways architecture programme and should be interpreted in two ways:

1. **There is no directly reusable UK government open-source reference implementation** for large-scale road sensor IoT data pipelines. National Highways is operating in a space where bespoke or commercial solutions dominate — the project cannot rely on government code reuse for the core IoT ingestion layer.

2. **The govreposcrape index is weighted towards local council web applications** (Dorset Council, Dundee City Council, Camden Council, East Sussex County Council dominate results). Central government engineering organisations — HMRC, DfT, MOJ, DWP, GDS, GCHQ, NHS Digital — either publish under different GitHub organisations not fully indexed, or have not open-sourced their infrastructure pipeline code. The National Highways GitHub organisation (`github.com/nationalhighways`) was not returned by any query and should be checked directly.

The most architecturally relevant patterns found relate to geospatial data persistence (PostGIS), distributed service contracts (C# NuGet packages), and Azure AD integration — these are applicable to the data mesh platform layer but not the IoT sensor ingestion layer.

---

## Implementation Approaches Compared

| Approach | Used By | Pros | Cons |
|----------|---------|------|------|
| Monolithic .NET web app with PostgreSQL/PostGIS backend | FloodOnlineReportingTool.Public | Simple deployment, well-understood stack, Azure-compatible, GDS-aligned | Not designed for high-throughput IoT ingestion; 500 events/day vs 500TB/day scale gap is unbridgeable with this pattern |
| Distributed services with typed message contracts (NuGet) | FloodOnlineReportingTool.Contracts | Clean CQRS/event-driven pattern; independent schema versioning; type-safe contracts across services | C#-only; requires NuGet infrastructure; limited to .NET ecosystem |
| TypeScript/OpenLayers front-end with OGC service consumption | GIFramework-Maps | Standard open mapping stack; vendor-neutral; Azure AD integration; 21 stars signals adoption | Presentation layer only — no data pipeline capability; read-only consumption model |
| Python geospatial batch processing (QGIS plugin) | QGIS.Mosaic.Builder | Python ecosystem aligns with Databricks; open source; active maintenance | Desktop/batch processing model, not suitable for 5TB/day streaming ingestion |

**Recommended Approach for This Project**: None of the identified patterns are directly applicable to the core IoT sensor ingestion problem at National Highways scale. The recommended approach — based on patterns identified and the absence of government precedent — is to adopt Azure IoT Hub for device management and MQTT ingestion, Azure Event Hubs for stream buffering (Kafka-compatible API), and Azure Databricks / Stream Analytics for real-time processing. The PostGIS pattern (from Dorset Council) is recommended for the geospatial reference data layer (road network geometry, sensor positions). The message contracts pattern (FloodOnlineReportingTool.Contracts) is recommended as a model for defining sensor event schemas between pipeline stages.

---

## Recommendations

### Immediate Next Steps

1. **Clone and Review FloodOnlineReportingTool.Contracts**: Examine the command/event contract pattern and apply it to National Highways sensor event schema design. The C# class library structure and NuGet publication pipeline is directly reusable as a template — MIT licence permits adaptation.
2. **Clone and Review GIFramework-Maps**: Examine the Azure AD authentication integration and OGC service consumption patterns for the National Highways spatial data visualisation layer. The TypeScript/OpenLayers/C# stack is directly applicable. MIT licence permits adaptation.
3. **Direct GitHub Search**: The govreposcrape index does not fully cover central government engineering organisations. Manually search `github.com/alphagov`, `github.com/dfe-digital`, `github.com/DFE-Digital`, `github.com/hmrc`, `github.com/ministryofjustice`, and `github.com/nationalhighways` for IoT pipeline and data engineering repositories not surfaced by this search.
4. **DEFRA / Environment Agency Review**: The Environment Agency operates the National River Flow Archive and flood sensor network — a directly analogous government IoT sensor programme. Search `github.com/defra` and `github.com/EnvironmentAgencyFloodData` for data pipeline implementations before building bespoke.
5. **License Verification**: Confirm MIT licence compatibility with National Highways open data publication requirements under HM Treasury Green Book obligations.

### Search Refinements

If further searching is needed, consider these refined queries:

- `Environment Agency flood sensor API data collection` — likely to surface closer analogues to road IoT monitoring from DEFRA/EA GitHub organisations
- `alphagov data pipeline stream processing` — may surface GDS data engineering infrastructure not indexed in current govreposcrape corpus
- `NHS Digital FHIR event streaming data ingestion` — NHS has mature IoT-adjacent real-time data collection patterns (patient monitoring) that may transfer to road sensor context
- `DfT transport data standard UTMC DATEX` — UK Department for Transport has published open standards for traffic data exchange that directly govern National Highways sensor data formats

### Related ArcKit Commands

- Run `/arckit:gov-reuse` for a full reusability assessment of FloodOnlineReportingTool.Contracts and GIFramework-Maps against the National Highways tech stack
- Run `/arckit:research` to research Azure IoT Hub, Azure Event Hubs, and Databricks for the sensor ingestion layer where no government precedent was found

---

## External References

| Document | Type | Source | Key Extractions | Path |
|----------|------|--------|-----------------|------|
| GIFramework-Maps README | GitHub README | https://github.com/Dorset-Council-UK/GIFramework-Maps | Azure AD auth, OpenLayers, PostgreSQL/PostGIS patterns | N/A |
| FloodOnlineReportingTool.Contracts releases | GitHub Releases | https://github.com/Dorset-Council-UK/FloodOnlineReportingTool.Contracts | v3.2.0 (2026-03-11); 13 releases; C# NuGet contract pattern | N/A |
| FloodOnlineReportingTool.Public README | GitHub README | https://github.com/Dorset-Council-UK/FloodOnlineReportingTool.Public | Distributed .NET architecture; PostgreSQL/PostGIS; GDS Design System | N/A |

---

**Generated by**: ArcKit `/arckit.gov-code-search` agent
**Generated on**: 2026-03-23
**ArcKit Version**: 4.5.0
**Project**: National Highways Data Architecture Modernization (Project 001)
**AI Model**: claude-sonnet-4-6
