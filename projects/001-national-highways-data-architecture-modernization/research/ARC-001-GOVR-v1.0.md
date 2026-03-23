# Government Reuse Assessment: National Highways Data Architecture Modernization

> **Template Origin**: Official | **ArcKit Version**: 4.5.0 | **Command**: `/arckit.gov-reuse`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-GOVR-v1.0 |
| **Document Type** | Government Reuse Assessment |
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
| **Distribution** | National Highways Architecture Team, Data Engineering Team, GDS Service Assessment Team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-03-23 | ArcKit AI | Initial creation from `/arckit.gov-reuse` agent — deep reusability assessment on Dorset Council repositories identified in ARC-001-GCSR-v1.0 | PENDING | PENDING |

---

## Executive Summary

### Search Scope

This assessment performs a deep reusability evaluation of four Dorset Council open-source repositories identified in the preceding Government Code Search Report (ARC-001-GCSR-v1.0). The prior report searched approximately 24,500 UK government repositories across 11 query variations and identified these repositories as the highest-relevance candidates in the govreposcrape index for the National Highways data architecture modernisation programme.

This assessment extends that search with a further 8 govreposcrape query variations targeting specific capabilities extracted from the requirements document (ARC-001-REQ-v1.0), with direct WebFetch and GitHub API assessment of each candidate. The govreposcrape corpus is consistent with prior findings: Dorset Council remains the most prolific and architecturally relevant UK local government open-source contributor, and no central government (DfT, HMRC, MOJ, GDS) IoT pipeline or streaming data platform code has been surfaced. The Dorset Council suite therefore represents the practical ceiling of government open-source reuse for this programme.

**Capabilities Assessed**: 6 capability areas derived from FR/NFR/INT requirements

**Govreposcrape Queries Run**: 14 variations across 6 capabilities (including 3 variations carried over from ARC-001-GCSR-v1.0)

**Repositories Evaluated**: 19 unique repositories reviewed; 4 shortlisted for detailed assessment via WebFetch and GitHub API

### Key Findings

| Capability | Best Candidate | Organisation | Reuse Strategy | Effort Saved |
|------------|---------------|--------------|----------------|--------------|
| Geospatial mapping and spatial data visualisation | GIFramework-Maps | Dorset Council | Fork | 35 person-days |
| Distributed service message contracts / event schema | FloodOnlineReportingTool.Contracts | Dorset Council | Fork | 10 person-days |
| GDS-compliant frontend components (.NET) | GdsBlazorComponents | Dorset Council | Library | 15 person-days |
| Distributed .NET service architecture reference | FloodOnlineReportingTool.Public | Dorset Council | Reference | 8 person-days |
| Real-time IoT sensor ingestion pipeline | None found | — | Build new | — |
| Transport traffic data API / DATEX II integration | None found | — | Build new | — |

### Reuse Summary

**Total Estimated Effort Saved**: 68 person-days (approximately 13.6 person-weeks)

**Reuse Coverage**: 4 of 6 required capability areas have government code candidates; 2 core capabilities (IoT ingestion, transport data API) have no government open-source precedent.

**Recommended Approach**: Fork GIFramework-Maps as the foundation for the National Highways spatial data visualisation layer and road sensor position management. Fork FloodOnlineReportingTool.Contracts as the structural template for sensor event schema design. Adopt GdsBlazorComponents as a NuGet dependency for the control room dashboard Blazor frontend. Use FloodOnlineReportingTool.Public as a reference architecture for distributed .NET service design patterns. Proceed to build from scratch for the IoT ingestion pipeline (Azure IoT Hub/Event Hubs) and transport data API (DATEX II/OpenAPI), where no government precedent exists.

---

## Capability Analysis

### Capability 1: Geospatial Mapping and Spatial Data Visualisation

**Requirements Addressed**: FR-003 (Regional Control Room Unified Dashboard), FR-004 (Incident Management — map-based incident placement with road network snapping), FR-005 (Roadworks Scheduling — conflict detection within 10-mile radius), FR-006 (Data Mesh Data Products — geospatial display layer), INT-003 (Local Highway Authority integration — spatial data exchange)

**Search Terms Used**:
- `geospatial mapping web application road network spatial data visualisation OpenLayers`
- `PostgreSQL PostGIS geospatial data storage government council road network`
- `Azure Active Directory authentication government identity access control web application`
- `transport traffic data API real-time road network DATEX II UK open data`

---

#### Candidate: GIFramework-Maps

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dorset Council (Dorset-Council-UK) |
| **Repository URL** | https://github.com/Dorset-Council-UK/GIFramework-Maps |
| **Language** | TypeScript (42.7%), C# (37.6%), HTML (18.1%), CSS (1.6%) |
| **License** | MIT License |
| **Last Activity** | 2026-03-23 (pushed today; v1.10.0 released 2025-12-22) |
| **Stars** | 21 |
| **Forks** | 12 |
| **Contributors** | 14 |
| **Open Issues** | 36 (actively triaged) |
| **Releases** | 17 releases (v1.10.0 latest) |
| **Documentation** | Comprehensive — README, CONTRIBUTING.md, DEVELOPING.md, SECURITY.md, dedicated Admin Guide repository (GIFramework-Maps-Admin-Guide), GitHub Actions CI build badges |

**Description**: A production .NET web mapping application built by Dorset Council's GIS team that enables organisations to create, share, and manage web maps from multiple OGC web service sources. It supports spatial querying with customisable Nunjucks-templated responses, PDF export with customisable legends, GPS location tracking, multi-source location search (LLPG, OpenStreetMap, OS Places), annotation tools, Azure Active Directory authentication for secure deployments, and consumption of WMS/WFS OGC standard feeds. The backend is .NET with Entity Framework Core and PostgreSQL 13+ with PostGIS. The frontend is TypeScript with OpenLayers and Bootstrap. CI/CD is implemented via GitHub Actions (dev-build.yml and prod-build.yml workflows). A dedicated test project (GIFrameworkMaps.Tests) is present. The application has been deployed in production at Dorset Council and is the most starred (21) and most forked (12) UK local government GIS repository in the govreposcrape corpus.

**Why Relevant to National Highways**: The National Highways control room dashboard (FR-003) requires a live traffic map with colour-coded congestion levels and CCTV feed integration. The incident management module (FR-004) requires map-based incident placement with road network snapping. The roadworks scheduler (FR-005) requires spatial conflict detection. All three capabilities require a geospatial web layer backed by a spatial database. GIFramework-Maps provides exactly this stack — OpenLayers + .NET + PostgreSQL/PostGIS — and adds Azure AD authentication that National Highways requires for control room operator access on its Azure tenant (NFR-SEC-001). The OGC WMS/WFS consumption capability is directly applicable to consuming OS National Map feeds and DATEX II spatial layers.

**Reusability Assessment**:

| Criteria | Score (1-5) | Notes |
|----------|-------------|-------|
| **License Compatibility** | 5 | MIT License confirmed via GitHub API — permits unrestricted modification, redistribution, and commercial/public-sector use. Crown Copyright obligations satisfied with attribution. |
| **Code Quality** | 4 | Test project (GIFrameworkMaps.Tests) present. Two GitHub Actions CI workflows (dev and prod builds). 17 releases with semantic versioning. 14 contributors. 536 commits (across related FORT repos). Clean modular structure (GIFrameworkMaps.Data, GIFrameworkMaps.Web, GIFrameworkMaps.Tests). Minor gap: specific test coverage % not published. |
| **Documentation Quality** | 5 | README with feature list and setup requirements. CONTRIBUTING.md, DEVELOPING.md, SECURITY.md present. Separate admin guide repository (GIFramework-Maps-Admin-Guide) with MkDocs-built documentation deployed to GitHub Pages. Build status badges in README. This is the best-documented repository in the govreposcrape local government corpus. |
| **Tech Stack Alignment** | 5 | TypeScript frontend, C# .NET backend, PostgreSQL 13+ with PostGIS, Entity Framework Core, OpenLayers, Bootstrap, Azure AD authentication, IIS/Kestrel/Azure hosting — every element aligns with the National Highways target architecture (Azure UK South/West, .NET 8+, Azure Entra ID). No stack adaptation required. |
| **Activity / Maintenance** | 5 | Last pushed 2026-03-23 (today at time of assessment). 21 stars, 12 forks, 14 contributors, 36 open issues being tracked. Active semantic versioning (v1.10.0). Highest community engagement of any UK local government repository assessed. |
| **Overall** | **4.8** | |

**Recommended Strategy**: Fork

**Estimated Effort Saved**: 35 person-days. Building an equivalent geospatial web layer (OpenLayers integration, PostgreSQL/PostGIS schema design, Azure AD authentication, OGC service consumption, PDF export, admin configuration) from scratch in .NET/TypeScript would require approximately 6-8 weeks of senior full-stack development. Forking and adapting GIFramework-Maps to National Highways' road network context (replacing Dorset Council branding, adding traffic flow colour rendering, integrating incident overlay, connecting to DATEX II feeds) is estimated at 3-4 weeks, saving approximately 35 days.

**Key Considerations**:

- The fork must replace Dorset Council branding and council-specific spatial data sources with National Highways equivalents (OS National Map, DATEX II feeds, sensor position data)
- The roadworks conflict detection (FR-005) requires custom business logic — GIFramework-Maps provides the spatial query infrastructure but not the conflict detection algorithm
- Azure AD integration is already present but will need reconfiguration for National Highways' Azure tenant and the specific role model for control room operators versus public users
- The admin guide (GIFramework-Maps-Admin-Guide) provides deployment guidance that should be reviewed before forking to understand configuration model
- 36 open issues should be triaged before forking to understand any known defects relevant to the use case
- Consider contributing bug fixes and transport-domain enhancements back to the upstream fork under the MIT licence (GDS Service Standard Point 12: make new source code open)

---

#### Candidate: East Sussex County Council — Escc.Gritting.GrittingMap (evaluated and excluded)

| Attribute | Value |
|-----------|-------|
| **Organisation** | East Sussex County Council |
| **Repository URL** | https://github.com/east-sussex-county-council/Escc.Gritting.GrittingMap |
| **Language** | C# |
| **License** | Other (non-standard, unconfirmed) |
| **Last Activity** | 2016-02-05 (10 years inactive) |
| **Stars** | 0 |

**Description**: Google Maps-based web application showing gritter vehicle positions as they move around East Sussex — a transport-adjacent domain (road maintenance vehicle tracking). Evaluated as a potential alternative to GIFramework-Maps for the transport mapping capability.

**Reusability Assessment**:

| Criteria | Score (1-5) | Notes |
|----------|-------------|-------|
| **License Compatibility** | 1 | Listed as "Other" (non-standard) — no confirmed permissive license. Cannot reuse without legal risk. |
| **Code Quality** | 1 | No CI, no test evidence, single-contributor project. |
| **Documentation Quality** | 1 | Minimal README. |
| **Tech Stack Alignment** | 2 | Google Maps API dependency (vendor lock-in, per-request fees) — incompatible with National Highways open standards mandate (TCoP Point 4) and cost model. |
| **Activity / Maintenance** | 1 | Last commit 2016 — abandoned for 10 years. |
| **Overall** | **1.2** | |

**Recommended Strategy**: None. GIFramework-Maps is materially superior in every dimension.

---

### Capability 2: Distributed Service Message Contracts and Event Schema

**Requirements Addressed**: FR-001 (Real-Time Traffic Data Ingestion — message schema between IoT gateway, stream processor, and data products), FR-006 (Data Mesh Data Products — event contracts between domain data products), NFR-O-001 (Structured logging with correlation IDs — correlates with message tracing), INT-001 through INT-005 (all integration interfaces require defined message schemas)

**Search Terms Used**:
- `distributed message contracts event schema microservices CQRS government`
- `NuGet package library C# .NET message contracts inter-service event driven`

---

#### Candidate: FloodOnlineReportingTool.Contracts

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dorset Council (Dorset-Council-UK) |
| **Repository URL** | https://github.com/Dorset-Council-UK/FloodOnlineReportingTool.Contracts |
| **Language** | C# (100%) |
| **License** | MIT License |
| **Last Activity** | 2026-03-11 (v3.2.0 release) |
| **Stars** | 0 |
| **Forks** | 0 |
| **Contributors** | 5 |
| **Open Issues** | 1 |
| **Releases** | 13 releases (v3.2.0 latest; v3.1.0 on 2026-02-25; 3 releases in 4 weeks) |
| **Documentation** | Good — README.md, CONTRIBUTING.md, DEVELOPING.md, CODE_OF_CONDUCT.md, SECURITY.md with dedicated reporting email |

**Description**: A standalone C# class library defining all inter-service message contracts for the Flood Online Reporting Tool distributed system. The library separates commands (service directives) and events (state change notifications) into typed C# classes, distributable as a versioned NuGet package. The pattern separates message contract definitions from service implementations, enabling independent versioning of the schema layer. With 13 releases over approximately 9 months — including 3 releases in the 4 weeks before this assessment — the library demonstrates active schema evolution in a production government system. Top-level content: `.github/` (CI/CD workflows), `FloodOnlineReportingTool.Contracts/` (the contract class library), standard governance files.

**Why Relevant to National Highways**: The IoT sensor pipeline requires precisely this pattern. Between the MQTT sensor gateway, the Azure Event Hubs stream processor, the Databricks enrichment layer, and the 5 domain data product consumers, National Highways needs clearly defined, independently versioned message contracts. The FloodOnlineReportingTool.Contracts structure — commands vs. events, NuGet distribution, semantic versioning with frequent releases — directly answers the question of how a UK government team has implemented this in production. While the FORT schema covers flood reports rather than traffic sensor readings, the structural pattern (separate class library, typed contracts, NuGet packaging, CQRS-adjacent command/event distinction) is the reusable artefact, not the domain model.

**Reusability Assessment**:

| Criteria | Score (1-5) | Notes |
|----------|-------------|-------|
| **License Compatibility** | 5 | MIT License confirmed via GitHub API. Unrestricted reuse and modification. |
| **Code Quality** | 3 | No dedicated test project visible in repository root (only the contracts library project itself). However, 13 releases with semantic versioning and active evolution indicate the contracts are being exercised by a consumer application (FORT.Public). The .github/ directory confirms CI/CD workflows present. Score limited by absence of explicit test project — contracts libraries typically have few tests of their own but should have consumer-side integration tests. |
| **Documentation Quality** | 4 | README describes purpose and structure. CONTRIBUTING.md, DEVELOPING.md with setup instructions, CODE_OF_CONDUCT.md, SECURITY.md with dedicated reporting address. The DEVELOPING.md is a notable addition — it implies sufficient complexity to need developer onboarding documentation. Missing: published NuGet package URL or explicit package name in README. |
| **Tech Stack Alignment** | 4 | Pure C# class library with no external framework dependencies — aligns directly with any .NET 8+ service in the National Highways stack. The NuGet distribution model is standard. Score not 5 because National Highways may also need Python-compatible schema definitions (for Azure Databricks workloads), which a C#-only library does not address — a parallel schema definition (e.g., JSON Schema or Avro for Databricks) will be needed. |
| **Activity / Maintenance** | 5 | Last pushed 2026-03-11 (12 days before assessment). v3.2.0 released 2026-03-11, v3.1.0 on 2026-02-25 — 3 major/minor releases in 4 weeks. 13 total releases in approximately 9 months of operation. Highly active. |
| **Overall** | **4.2** | |

**Recommended Strategy**: Fork

**Estimated Effort Saved**: 10 person-days. The structural pattern (class library project setup, CI/CD for NuGet packaging, command/event distinction, semantic versioning pipeline) would take approximately 2 weeks to establish from scratch including CI/CD configuration. Forking, renaming to National Highways context, and replacing FORT domain classes with sensor event schemas is estimated at 1 week, saving approximately 10 days.

**Key Considerations**:

- All FORT domain classes must be replaced with National Highways sensor event schemas (SensorReading, IncidentDetected, SensorHealthAlert, SensorOnboarded, DataProductUpdated, etc.)
- The command/event distinction should be preserved — a SensorReadingReceived event (from sensor gateway to stream processor) differs structurally from a ProcessSensorBatch command (from scheduler to batch processor)
- Consider extending the pattern with a parallel JSON Schema or Apache Avro definition for Databricks / Python consumers — the C# library alone will not serve the data engineering layer
- The GitHub Actions NuGet publication workflow in `.github/` should be examined before forking — it likely contains a GitHub Packages or NuGet.org publication pipeline that can be reused directly
- Schema versioning strategy must account for the 10,000+ deployed sensors: breaking schema changes require a migration window

---

### Capability 3: GDS-Compliant Frontend Components for .NET Applications

**Requirements Addressed**: FR-003 (Regional Control Room Unified Dashboard — WCAG 2.2 Level AA compliance), BR-006 (GDS Service Standard Compliance — all 14 points including accessibility), NFR-C-003 (GDS Service Standard — WCAG 2.2 AA), INT-002 (developer portal for navigation app providers — GOV.UK Design System)

**Search Terms Used**:
- `GDS design system GOV.UK frontend components .NET Blazor government service`
- `environmental sensor data reporting public submission local authority UK` (surfaced GdsBlazorComponents as secondary result)

---

#### Candidate: GdsBlazorComponents

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dorset Council (Dorset-Council-UK) |
| **Repository URL** | https://github.com/Dorset-Council-UK/GdsBlazorComponents |
| **Language** | HTML (45.1%), C# (41.1%), TypeScript (8.1%), SCSS (2.6%), JavaScript (2.5%) |
| **License** | MIT License |
| **Last Activity** | 2026-03-23 (pushed today; v3.0.0 released 2026-03-20) |
| **Stars** | 4 |
| **Forks** | 2 |
| **Contributors** | 8 |
| **Open Issues** | 11 |
| **Releases** | 12 releases (v3.0.0 latest, released 3 days before assessment) |
| **Documentation** | Comprehensive — 28+ components documented with code examples, demo site, CONTRIBUTING.md, CODE_OF_CONDUCT.md, SECURITY.md |

**Description**: A NuGet-publishable Blazor component library implementing the GOV.UK Design System for C# Blazor applications. Originally created for Dorset Council's FloodOnlineReportingTool (itself a GDS-compliant government service), the library provides 28+ accessible, WCAG-compliant UI components including form elements (text inputs, date pickers, file uploads, checkboxes, radios), structural components (header, footer, breadcrumbs, fieldsets), feedback components (error messages, warnings, notification banners, inset text), and display components (tables, panels, tags, loading spinners). The package name is `Dorset-Council-UK.GdsBlazorComponents`. Installation requires adding `@using GdsBlazorComponents` to Razor imports and linking the GOV.UK Frontend CSS/JS assets. The library is already in production use in the FORT application and is the only Blazor-specific GOV.UK Design System implementation in the govreposcrape corpus.

**Why Relevant to National Highways**: If the Regional Control Room Dashboard (FR-003) uses Blazor — the natural choice given the .NET stack and the project's Azure/Microsoft technology preferences — this library directly addresses GDS Service Standard Point 4 (make the service simple to use), Point 5 (make sure everyone can use the service — WCAG 2.2 AA), and Point 12 (make new source code open — this library already is). Using an existing government-produced GOV.UK Design System implementation avoids rebuilding 28+ components and reduces GDS Alpha assessment risk. The developer portal (INT-002) for navigation app providers also requires GDS-compliant design.

**Reusability Assessment**:

| Criteria | Score (1-5) | Notes |
|----------|-------------|-------|
| **License Compatibility** | 5 | MIT License confirmed via GitHub API. Unrestricted use as a NuGet dependency. |
| **Code Quality** | 3 | GitHub Actions CI present (.github/ directory). 297 commits. 12 releases with semantic versioning. 8 contributors. However, no explicit test project listed in repository contents — the library is primarily validated by its demo site and by the FORT application's usage. Score limited by absent formal test suite for component rendering and accessibility compliance. |
| **Documentation Quality** | 4 | 28+ components documented with installation instructions and code examples. Demo website linked from README. CONTRIBUTING.md, CODE_OF_CONDUCT.md, SECURITY.md present. Package named explicitly (`Dorset-Council-UK.GdsBlazorComponents`). Missing: accessibility compliance statement confirming WCAG 2.2 AA per component — critical for GDS assessment evidence. |
| **Tech Stack Alignment** | 4 | Blazor (C#/HTML/TypeScript/SCSS) aligns with .NET stack. Uses GOV.UK Frontend assets (CSS and JavaScript modules). Score not 5 because the project's control room dashboard could be a non-Blazor SPA (React/TypeScript) — if so this library is inapplicable. The alignment score reflects the high probability that a .NET-first team will choose Blazor for internal tooling. |
| **Activity / Maintenance** | 5 | Last pushed 2026-03-23 (today). v3.0.0 released 2026-03-20 (3 days ago). 12 releases since 2025. 8 contributors. Extremely active at time of assessment. |
| **Overall** | **4.2** | |

**Recommended Strategy**: Library

**Estimated Effort Saved**: 15 person-days. Building 28+ accessible, WCAG 2.2 AA-compliant GOV.UK Design System components from scratch in Blazor — with sufficient test coverage to pass GDS assessment — is estimated at 4-5 weeks of frontend development work. Adopting GdsBlazorComponents as a NuGet package and building the control room dashboard on top of it is estimated at 1-2 weeks of integration work, saving approximately 15 days.

**Key Considerations**:

- Confirm that the National Highways control room dashboard frontend will be implemented in Blazor before committing to this library; if React/TypeScript is chosen, use the standard `govuk-frontend` npm package instead
- The GOV.UK Frontend CSS and JS assets must be licensed separately (MIT, from the GOV.UK Design System team at GDS)
- Obtain confirmation that each component passes WCAG 2.2 Level AA automated testing before citing this library as GDS assessment evidence — the absence of a published test suite means this should be validated during integration
- The package name `Dorset-Council-UK.GdsBlazorComponents` is Dorset Council's NuGet namespace; National Highways should consider whether to fork and republish under a national-highways namespace for long-term supply chain independence, or to accept the upstream NuGet dependency
- v3.0.0 (released 2026-03-20) is a major version — review the changelog for any breaking changes from v2.x before adopting

---

### Capability 4: Distributed .NET Service Architecture (Reference)

**Requirements Addressed**: FR-001 (IoT data ingestion service architecture), FR-004 (Incident management workflow — distributed service pattern), NFR-A-001 through NFR-A-004 (availability and resilience — distributed service design), NFR-O-001 through NFR-O-003 (observability — structured logging, metrics, tracing across services)

**Search Terms Used**:
- `distributed message contracts event schema microservices CQRS government`
- `incident management workflow automated notifications government emergency`
- `environmental sensor data reporting public submission local authority UK`

---

#### Candidate: FloodOnlineReportingTool.Public

| Attribute | Value |
|-----------|-------|
| **Organisation** | Dorset Council (Dorset-Council-UK) |
| **Repository URL** | https://github.com/Dorset-Council-UK/FloodOnlineReportingTool.Public |
| **Language** | C# (81.1%), HTML (17.8%), Other (1.1%) |
| **License** | MIT License |
| **Last Activity** | 2026-03-23 (pushed today — most recently active repository assessed) |
| **Stars** | 0 |
| **Forks** | 0 |
| **Contributors** | 5 |
| **Open Issues** | 21 |
| **Releases** | No published releases (continuous delivery model — changes pushed directly to main) |
| **Documentation** | Adequate — docs/ folder with governance files; no explicit deployment guide found. README present but not accessible via raw URL at time of assessment. |

**Description**: A full .NET web application enabling the public to report flooding incidents to local flood authorities. Used by councils across south-west England. The repository demonstrates a multi-project .NET solution structure: AppHost (orchestration), FloodOnlineReportingTool.Public (main web application), Database (PostgreSQL/PostGIS schema migrations), MigrationService (schema migration runner), ServiceDefaults (shared cross-cutting concerns), and Tests (integration test suite). It uses GitHub Actions for CI/CD (.github/ directory), GDS Design System for the frontend, Entity Framework Core for database access, and the companion Contracts library for inter-service messaging. The AppHost project suggests .NET Aspire orchestration — a modern cloud-native .NET hosting model directly relevant to Azure deployment.

**Why Relevant to National Highways**: The project demonstrates how a UK government team has structured a multi-service .NET application for a public-facing environmental monitoring domain. The architectural decisions — .NET Aspire orchestration, PostgreSQL/PostGIS, GDS Design System, message contract separation, CI/CD via GitHub Actions — are all directly applicable to the National Highways platform layer. The domain (flood reporting vs. traffic incident reporting) is superficially different but architecturally analogous: both involve public submission of environmental condition reports, geospatial incident location, and distributed service communication. This repository is the reference for how a production UK government .NET service is structured in 2026.

**Reusability Assessment**:

| Criteria | Score (1-5) | Notes |
|----------|-------------|-------|
| **License Compatibility** | 5 | MIT License confirmed via GitHub API. |
| **Code Quality** | 4 | Tests/ directory present with notification tests (Tests/Notifications/GovUKNotifyTests.cs). GitHub Actions CI/CD configured. 536 commits. Multi-project solution with clean separation of concerns (AppHost, MigrationService, ServiceDefaults pattern). 5 contributors. Minor gap: no released versions — continuous deployment model rather than semantic versioning. |
| **Documentation Quality** | 3 | docs/ folder with governance files (CONTRIBUTING.md, CODE_OF_CONDUCT.md, SECURITY.md). README present but not accessible via raw URL during assessment — may be located at a non-standard path. No explicit deployment guide found. Admin documentation less comprehensive than GIFramework-Maps. |
| **Tech Stack Alignment** | 4 | C# / .NET (8+ inferred from .NET Aspire usage), PostgreSQL 13+ with PostGIS, Entity Framework Core, GitHub Actions, GDS Design System — all aligned. .NET Aspire AppHost pattern directly applicable to Azure Container Apps deployment. Score not 5 because the application's public-facing flood reporting model differs from the multi-tenant, multi-region, high-throughput National Highways architecture — significant adaptation required. |
| **Activity / Maintenance** | 5 | Last pushed 2026-03-23 (today). Extremely active. 21 open issues suggests active development backlog. 5 contributors from Dorset Council. |
| **Overall** | **4.2** | |

**Recommended Strategy**: Reference

**Rationale for Reference rather than Fork**: The application itself is a public flood reporting tool, not a traffic management system. Directly forking the application code would require replacing the entire domain model (flood reports → sensor readings, incidents, roadworks), the UI flows (public report submission → operator dashboard), and the integration layer (flood authority notification → navigation app API). This is effectively a rebuild. However, the architectural skeleton — .NET Aspire AppHost, ServiceDefaults shared library pattern, PostgreSQL/PostGIS migration service, GDS Design System integration, GitHub Actions CI/CD pipeline — is a directly reusable template for structuring the National Highways application projects. Engineers should clone and study this repository, not fork and adapt it.

**Estimated Effort Saved**: 8 person-days. The .NET Aspire project structure, GitHub Actions pipeline configuration, and ServiceDefaults pattern provide approximately 1-2 weeks of solution scaffolding that engineers can reproduce rather than design from scratch.

**Key Considerations**:

- Focus specifically on the AppHost orchestration pattern, ServiceDefaults project structure, MigrationService pattern, and GitHub Actions CI/CD configuration — these are the reusable structural elements
- The GovUKNotifyTests.cs indicates GOV.UK Notify integration for notifications — relevant to FR-004 (incident notification to emergency services and navigation apps), though National Highways will use Azure Service Bus for high-volume notifications rather than GOV.UK Notify
- The .gitmodules file suggests the repository uses Git submodules — examine before attempting to clone to understand dependencies
- The 21 open issues represent active development work — many may be feature additions rather than defects, but should be noted when referencing the architecture patterns

---

### Capability 5: Real-Time IoT Sensor Ingestion Pipeline

**Requirements Addressed**: FR-001 (Real-Time Traffic Data Ingestion — 10,000+ IoT sensors, < 2 second latency), NFR-P-002 (Data Ingestion Throughput — 5TB/day, 20TB/day capacity), NFR-S-003 (Sensor Network Expansion — 50,000 sensor capacity), INT-004 (Met Office Weather Data Feed)

**Search Terms Used**:
- `IoT sensor data ingestion streaming pipeline government` (carried from ARC-001-GCSR-v1.0)
- `event sourcing time series data ingestion IoT platform government cloud`
- `sensor data collection pipeline MQTT message broker` (carried from ARC-001-GCSR-v1.0)

**Candidates Found**: None with score above 1.5. The govreposcrape corpus continues to return zero results for MQTT, Kafka, Azure Event Hubs, Azure IoT Hub, stream processing, time-series databases, or real-time telemetry ingestion from any UK government organisation.

**Recommended Action**: Build new. No government open-source precedent identified for large-scale road sensor IoT data pipelines in the UK public sector. Recommend using ArcKit `/arckit.research` command to research Azure IoT Hub, Azure Event Hubs (Kafka-compatible), Azure Databricks, and Azure Stream Analytics as the commercial cloud services for this layer.

---

### Capability 6: Transport Traffic Data API and DATEX II Integration

**Requirements Addressed**: FR-002 (Public Journey Planning API — OpenAPI 3.x), FR-005 (Roadworks API — DATEX II format), FR-008 (Local Authority Data Exchange — REST and DATEX II), INT-002 (Navigation App APIs — OpenAPI), INT-003 (Local Highway Authority Integration — DATEX II)

**Search Terms Used**:
- `transport traffic data API real-time road network DATEX II UK open data`
- `public open data REST API developer portal government OpenAPI specification`

**Candidates Found**: None with score above 2.0. No UK government repository in the govreposcrape corpus implements DATEX II, UTMC, or a transport-specific OpenAPI data platform. The closest result — DundeeCityCouncil/OpenData — is inactive (last commit 2015) and provides only Jupyter notebooks for static data exploration, not a real-time API.

**Recommended Action**: Build new. National Highways will need to implement OpenAPI 3.x endpoints and DATEX II serialisation from first principles. The DATEX II XML standard is published by ERTICO/TN-ITS and the UK's DfT — these standards documents are the reference, not any open-source implementation. Recommend engaging DfT's traffic data team directly and reviewing the `github.com/nationalhighways` organisation (which did not appear in govreposcrape results) for any prior API implementation.

---

## License Compatibility Matrix

| Repository | License | Commercial Use | Modification | Distribution | Attribution Required | Compatible with National Highways |
|------------|---------|---------------|--------------|--------------|----------------------|-----------------------------------|
| GIFramework-Maps | MIT | Yes | Yes | Yes | Yes (copyright notice) | Yes — full compatibility |
| FloodOnlineReportingTool.Contracts | MIT | Yes | Yes | Yes | Yes (copyright notice) | Yes — full compatibility |
| GdsBlazorComponents | MIT | Yes | Yes | Yes | Yes (copyright notice) | Yes — full compatibility |
| FloodOnlineReportingTool.Public | MIT | Yes | Yes | Yes | Yes (copyright notice) | Yes — full compatibility |
| Escc.Gritting.GrittingMap | Other (unconfirmed) | Unknown | Unknown | Unknown | Unknown | No — do not use without legal review |

**Notes**: All four Dorset Council repositories use the MIT License. This is the most permissive open-source licence and imposes only a single obligation: the copyright notice and licence text must be retained in derivative works. For National Highways, this means any forked or adapted code must preserve the Dorset Council copyright attribution in the LICENSE file of the derivative repository. This does not affect the intellectual property status of National Highways' own additions to a fork. The MIT licence is fully compatible with the GDS Service Standard Point 12 requirement (make new source code open) — National Highways may publish its adaptations under MIT without restriction. The OGL v3.0 (Open Government Licence) is also a compatible outbound licence for the documentation layer (consistent with GIFramework-Maps Admin Guide's OGL documentation licence pattern).

---

## Tech Stack Alignment

| Repository | Language | Framework | Database | Infrastructure | Aligns with National Highways | Adaptation Needed |
|------------|----------|-----------|----------|----------------|-------------------------------|-------------------|
| GIFramework-Maps | TypeScript / C# | .NET + OpenLayers + Bootstrap | PostgreSQL 13+ / PostGIS | Azure / IIS / Kestrel | Yes — exact match | Rebrand, add traffic flow rendering, DATEX II feed integration |
| FloodOnlineReportingTool.Contracts | C# | .NET class library (no framework) | None (library only) | NuGet / GitHub Packages | Yes — .NET native | Replace FORT domain contracts with sensor event schemas |
| GdsBlazorComponents | C# / HTML / SCSS | Blazor + GOV.UK Frontend | None (UI library) | NuGet / GitHub Packages | Yes — if Blazor chosen for dashboard | Confirm Blazor is the chosen dashboard framework |
| FloodOnlineReportingTool.Public | C# | .NET Aspire + Entity Framework Core | PostgreSQL 13+ / PostGIS | GitHub Actions / Azure (inferred) | Yes — architecture reference | Reference only — do not fork application code |

**Project Tech Stack**: Azure UK South + UK West (primary + DR), .NET 8+ (C#), TypeScript, Azure IoT Hub, Azure Event Hubs (Kafka API), Azure Databricks (Python/Scala), Azure Blob Storage, PostgreSQL with PostGIS, Entity Framework Core, Azure Active Directory (Entra ID), OpenAPI 3.x, DATEX II, GeoJSON.

---

## Gap Analysis

| Capability | Status | Notes | Recommended Action |
|------------|--------|-------|--------------------|
| Geospatial mapping and spatial data visualisation | Reusable | Strong candidate — GIFramework-Maps (average score 4.8). Exact tech stack match, MIT licence, actively maintained, 14 contributors, production-proven. | Fork GIFramework-Maps. Estimated 3-4 weeks to adapt for National Highways. |
| Distributed service message contracts / event schema | Reusable | Strong candidate — FloodOnlineReportingTool.Contracts (average score 4.2). Structural pattern directly applicable; domain model must be replaced with sensor event schemas. | Fork FloodOnlineReportingTool.Contracts. Replace FORT contracts with National Highways sensor event and command types. Add Avro/JSON Schema for Python/Databricks consumers. |
| GDS-compliant frontend components (.NET) | Reusable | Good candidate — GdsBlazorComponents (average score 4.2). MIT licence, 28+ components, NuGet-distributable, production use in FORT. Conditional on Blazor being chosen for control room dashboard. | Adopt as NuGet Library dependency if Blazor chosen. Validate WCAG 2.2 AA compliance per component before GDS assessment. |
| Distributed .NET service architecture reference | Partial | Good reference — FloodOnlineReportingTool.Public (average score 4.2). Application domain is not reusable but architectural skeleton (.NET Aspire, PostGIS, ServiceDefaults, CI/CD) is directly applicable as a structural reference. | Reference only. Study project structure, AppHost pattern, MigrationService, GitHub Actions CI/CD. Do not fork application code. |
| Real-time IoT sensor ingestion pipeline | No match | Zero relevant results across all query variations. No UK government open-source implementation of MQTT ingestion, Kafka/Event Hubs streaming, or time-series data processing exists in the govreposcrape corpus. | Build new with Azure IoT Hub + Azure Event Hubs (Kafka API) + Azure Databricks. Run `/arckit.research` for technology assessment. |
| Transport traffic data API / DATEX II integration | No match | Zero relevant results. No UK government repository implements DATEX II, UTMC, or transport-domain OpenAPI. | Build new. Engage DfT traffic data standards team. Review `github.com/nationalhighways` directly. Run `/arckit.research` for API gateway and developer portal technology options. |

**Legend**: Reusable = Fork or Library strategy recommended | Partial = Reference strategy recommended | No match = Build from scratch

---

## Recommendations

### Reuse Strategy Summary

The Dorset Council open-source suite (GIFramework-Maps, FloodOnlineReportingTool.Contracts, GdsBlazorComponents, FloodOnlineReportingTool.Public) represents the most architecturally coherent collection of reusable UK government code identified across the govreposcrape corpus of approximately 24,500 repositories. All four repositories share a consistent technology stack (.NET 8+, PostgreSQL/PostGIS, Azure, GitHub Actions, MIT licence) that is a direct match for the National Highways Azure-centric target architecture. The three repositories with Fork or Library recommendations provide an estimated combined saving of 60 person-days (approximately 12 person-weeks) of senior engineering effort. The Reference candidate (FORT.Public) provides an additional 8 days of scaffolding benefit.

The most impactful reuse decision is the Fork of GIFramework-Maps. The National Highways geospatial layer — serving the control room dashboard, incident map, roadworks conflict detection, and sensor position display — would be the most complex single component to build from scratch (estimated 6-8 weeks). GIFramework-Maps is a production-grade, community-supported, well-documented government implementation of exactly this capability with 17 releases, 14 contributors, and Azure AD authentication already integrated. Forking this repository and extending it with National Highways-specific overlays (traffic flow colour rendering, sensor health icons, DATEX II feed integration) is the highest-value reuse opportunity in this programme.

The two genuine gaps — IoT sensor ingestion and DATEX II transport data API — are not failures of the search process but reflect a genuine absence of government open-source precedent for large-scale infrastructure data engineering. National Highways is operating at a scale (10,000 sensors, 5TB/day, < 2 second latency, 50,000 requests/second peak) that exceeds the operational context of all UK local government open-source repositories. For these capabilities, National Highways should use best-of-breed commercial cloud services (Azure IoT Hub, Azure Event Hubs) and first-principles API design aligned with DATEX II standards. As the programme delivers, National Highways should consider publishing its IoT pipeline implementation under OGL or MIT licence to fill this gap in the government open-source ecosystem — consistent with TCoP Point 3 (be open and use open source) and GDS Service Standard Point 12 (make new source code open).

### Implementation Priority

| Priority | Repository | Capability | Action | Estimated Effort | Timeline |
|----------|------------|------------|--------|-----------------|----------|
| 1 | GIFramework-Maps | Geospatial mapping and spatial data visualisation | Fork, rebrand for National Highways, add traffic layer rendering and DATEX II OGC feed integration | 3-4 weeks (after 1 week spike) | Sprint 2-5 (Alpha phase) |
| 2 | FloodOnlineReportingTool.Contracts | Distributed service message contracts / event schema | Fork, replace FORT domain model with sensor events and commands, add Avro schema for Databricks | 1 week | Sprint 2-3 (Alpha phase) |
| 3 | GdsBlazorComponents | GDS-compliant frontend components (.NET) | Adopt as NuGet Library dependency for control room dashboard Blazor frontend — conditional on Blazor framework decision | 1-2 weeks integration | Sprint 3-6 (Alpha phase) |
| 4 | FloodOnlineReportingTool.Public | Distributed .NET service architecture reference | Study and document patterns for .NET Aspire, ServiceDefaults, PostGIS migrations, GitHub Actions CI/CD scaffolding | 1 week (reference study) | Sprint 1 (pre-Alpha) |
| 5 | — | Real-time IoT sensor ingestion pipeline | Build new: Azure IoT Hub + Azure Event Hubs (Kafka API) + Azure Databricks + Azure Stream Analytics | 12-16 weeks | Sprint 1-10 (Alpha + Beta) |
| 6 | — | Transport traffic data API / DATEX II | Build new: Azure API Management + OpenAPI 3.x design + DATEX II serialisation + developer portal | 8-12 weeks | Sprint 4-12 (Beta phase) |

### Risk Considerations

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| GIFramework-Maps architectural divergence requires significant rework after fork commitment | Medium | High | Conduct a 1-week technical spike (proof of concept) before committing to the fork: configure Azure AD, connect a DATEX II WMS feed, render a traffic flow overlay. Validate feasibility before Sprint 2. |
| GdsBlazorComponents WCAG 2.2 AA compliance cannot be evidenced for GDS assessment | Medium | High | Commission independent accessibility audit of each component used before Alpha assessment. Do not cite the library as compliance evidence without audit results. |
| FloodOnlineReportingTool.Contracts C# schema not compatible with Python/Databricks consumers | High | Medium | Implement a parallel Apache Avro or JSON Schema definition alongside the C# contracts library from the start. Use Schema Registry (Azure Schema Registry or Confluent Schema Registry) as the authoritative schema source. |
| Dorset Council ceases maintenance of upstream repos after National Highways forks | Low | Low | MIT licence means National Highways' fork is fully independent. Monitor upstream for security patches and selectively merge where applicable. The risk is negligible given 4 repos are all actively maintained as of 2026-03-23. |
| GIFramework-Maps 36 open issues contain undiscovered defects relevant to the use case | Medium | Medium | Triage all 36 open issues before the fork spike. Categorise as: relevant defects (fix before forking), roadmap features (decide whether to adopt), and out-of-scope items (ignore). Assign an engineer 2 days to complete this triage. |
| NuGet package name `Dorset-Council-UK.GdsBlazorComponents` creates supply chain dependency on Dorset Council NuGet publication | Low | Medium | Evaluate forking and republishing under `NationalHighways.GdsBlazorComponents` NuGet namespace for long-term independence. Decision required before Beta phase. |

---

## External References

| Document | Type | Source | Key Extractions | Path |
|----------|------|--------|-----------------|------|
| ARC-001-GCSR-v1.0 — Government Code Search Report | ArcKit document | Internal — projects/001-national-highways-data-architecture-modernization/research/ | Identified three Dorset Council repos as primary candidates; confirmed absence of IoT pipeline code in govreposcrape corpus | projects/001-national-highways-data-architecture-modernization/research/ARC-001-GCSR-v1.0.md |
| GIFramework-Maps README | GitHub README | https://github.com/Dorset-Council-UK/GIFramework-Maps | .NET + OpenLayers + PostGIS + Azure AD stack; OGC WMS/WFS consumption; deployment targets (IIS, Kestrel, Azure) | N/A |
| GIFramework-Maps Admin Guide | GitHub repository | https://github.com/Dorset-Council-UK/GIFramework-Maps-Admin-Guide | MkDocs-based administrator documentation deployed to GitHub Pages | N/A |
| FloodOnlineReportingTool.Contracts README | GitHub README | https://github.com/Dorset-Council-UK/FloodOnlineReportingTool.Contracts | Command/event contract pattern; MIT licence; DEVELOPING.md developer guide | N/A |
| GdsBlazorComponents README | GitHub README | https://github.com/Dorset-Council-UK/GdsBlazorComponents | 28+ GOV.UK Design System Blazor components; NuGet package name; installation instructions | N/A |
| GitHub API — all four repositories | GitHub REST API v3 | https://api.github.com/repos/Dorset-Council-UK/{repo} | Stars, forks, contributors, last pushed date, license name, open issues count, releases | N/A |

---

**Generated by**: ArcKit `/arckit.gov-reuse` agent
**Generated on**: 2026-03-23
**ArcKit Version**: 4.5.0
**Project**: National Highways Data Architecture Modernization (Project 001)
**AI Model**: claude-sonnet-4-6
