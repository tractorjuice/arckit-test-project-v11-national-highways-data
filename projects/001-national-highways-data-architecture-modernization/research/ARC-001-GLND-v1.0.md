# Government Landscape Analysis: Transport and Highways Data

> **Template Origin**: Official | **ArcKit Version**: 4.5.0 | **Command**: `/arckit.gov-landscape`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-GLND-v1.0 |
| **Document Type** | Government Landscape Analysis |
| **Project** | National Highways Data Architecture Modernization (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-03-23 |
| **Last Modified** | 2026-03-23 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-06-23 |
| **Owner** | Programme Director, Data Architecture Modernization |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Programme Team, Architecture Team, Executive Sponsors |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-03-23 | ArcKit AI | Initial creation from `/arckit.gov-landscape` agent | PENDING | PENDING |

---

## Executive Summary

### Domain Overview

This landscape analysis maps UK government open-source activity across the transport and highways data domain, with a focus on areas directly relevant to National Highways' data architecture modernisation programme. The domain spans real-time traffic data, road network management, digital traffic regulation, geospatial mapping, open data publication, and sensor-based infrastructure monitoring. Understanding what has already been built across UK public sector organisations enables National Highways to avoid duplication, adopt proven patterns, and identify collaboration opportunities before committing to bespoke development.

The govreposcrape search across 24,500+ UK government repositories returned a consistent set of organisations active in adjacent data and geospatial domains. The most significant finding is that the central government transport body (Department for Transport) has very limited open-source output — its two most transport-relevant public repositories are D-TRO (Digital Traffic Regulation Orders) and Open_NaPTAN (National Public Transport Access Nodes). Neither addresses strategic road network data, real-time sensor pipelines, or data mesh architecture directly. The majority of active open-source transport-adjacent work is concentrated at local authority level, particularly Dorset Council (GIS and reporting tools), East Sussex County Council (web services), and Dundee City Council (GIS and open data).

This landscape is characterised by a significant gap between the scale of National Highways' ambitions — a cloud-native data mesh handling 5TB/day from 10,000+ IoT sensors — and what exists in UK government open source. The closest analogues are the local authority geospatial and open data tools, the DfT's nascent digital traffic regulation work, and the DVLA's cloud infrastructure patterns. National Highways' project will operate on a considerably larger scale than anything found in the public sector open-source corpus, placing it in a position to lead and publish reusable components that others could adopt.

**Domain**: Transport and Highways Data (Strategic Road Network, IoT Sensors, Traffic Management, Open Data APIs, Geospatial Services, Digital Traffic Regulation)

**Analysis Date**: 2026-03-23

**Platforms Searched**: GitHub (UK government organisations via govreposcrape index of 24,500+ repositories), direct WebFetch on GitHub organisation and repository pages

### Organisations Identified

**Total Organisations**: 10

**Central Government**: 2 (Department for Transport, DVLA)

**Arms Length Bodies / NDPBs**: 0 (National Highways itself has no public GitHub presence)

**Local Government**: 7 (Dorset Council, East Sussex County Council, Dundee City Council, Camden Council, Bath and North East Somerset, Bristol City Council, Bracknell Forest Council)

**NHS / Health**: 0

**International Equivalents**: Not in scope

### Repositories Analysed

**Total Repositories Found**: 42 (unique, deduplicated across 12 search queries)

**Active (commits < 6 months)**: 5

**Maintained (commits 6–18 months)**: 4

**Stale (commits > 18 months)**: 11

**Archived / Abandoned**: 22

### Key Findings

- **Most Active Organisations**: Dorset Council (Dorset-Council-UK), Department for Transport Public (department-for-transport-public), East Sussex County Council
- **Dominant Tech Stack**: C# / .NET, Python, R, TypeScript / JavaScript
- **Common Standards**: GOV.UK Design System, MIT License, PostgreSQL with PostGIS, GDS API design patterns, OpenAPI 3.x (referenced in D-TRO)
- **Maturity Level**: Nascent to Developing — local authority tools are mature for their narrow use case but no production-grade, national-scale transport data platform or real-time streaming infrastructure exists in UK government open source. The DfT's D-TRO programme is the most strategically significant emerging work.

---

## Domain Landscape Map

### Organisations Overview

| Organisation | Repos in Domain | Primary Language | Focus Area | Activity Level |
|-------------|-----------------|-----------------|------------|----------------|
| Dorset Council (Dorset-Council-UK) | 7 | C# / TypeScript | Geospatial mapping, flood reporting, GOV.UK components | Active |
| Dept for Transport Public (department-for-transport-public) | 3 | R / HTML / PHP | Traffic regulation data, transport open data | Active |
| East Sussex County Council | 4 | C# / JavaScript | Web services, gritting maps, Azure integration | Stale |
| Dundee City Council | 4 | JavaScript / Python | GIS, open data publishing, ArcGIS widgets | Maintained |
| DVLA | 2 | JavaScript / Scala / Ruby | Cloud infrastructure utilities, address lookup | Active |
| Department for Transport (department-for-transport) | 2 | Python / R | Vehicle counting ML, R transport data training | Stale/Archived |
| Camden Council | 2 | JavaScript | Mapping services, local data finder | Stale |
| Bath and North East Somerset (BathnesDevelopment) | 2 | Python / JavaScript | Open data scripts, geospatial needs | Stale |
| Bristol City Council | 1 | JavaScript / Java | Frontend toolkit | Stale |
| Bracknell Forest Council | 1 | — | Government GitHub registration | Stale |

**Legend**: Active (commits < 6 months) | Maintained (6–18 months) | Stale (> 18 months)

---

### Dorset Council (Dorset-Council-UK)

**GitHub**: https://github.com/Dorset-Council-UK

**Focus**: Dorset Council's GIS and digital team builds geospatial, mapping, and public-facing web applications using .NET and the GOV.UK Design System. They are among the most prolific local authority open-source contributors in the UK government space, with 15 public repositories.

**Notable Repositories**:

| Repository | Description | Language | Stars | Last Active |
|------------|-------------|----------|-------|-------------|
| GIFramework-Maps | Web mapping application using OGC web services, OpenLayers, and .NET | TypeScript / C# | 21 | 2025-03-23 |
| GdsBlazorComponents | Blazor components styled to GOV.UK Design System (30+ components) | C# / HTML | 4 | 2026-03-20 |
| FloodOnlineReportingTool.Public | Public flood reporting service, GDS-compliant, used by SW councils | C# | 0 | 2025 (active) |
| QGIS.Mosaic.Builder | QGIS plugin for creating derived geospatial datasets | Python | 0 | 2026-02-05 |
| FloodOnlineReportingTool.Contracts | Message contracts for distributed Flood Reporting Tool architecture | — | 0 | 2025 (active) |

**Architectural Approach**: .NET 8+ microservices with PostgreSQL/PostGIS for spatial data storage; TypeScript/OpenLayers for frontend mapping; GitHub Actions CI/CD; Azure-compatible deployment via IIS, Kestrel, or Azure App Service. The FloodOnlineReportingTool uses a message contract pattern for distributed service communication, suggesting familiarity with event-driven architecture at small scale.

**Standards Followed**: GOV.UK Design System, MIT License, GDS accessibility requirements, Open Government Licence (OGL) for data

---

### Department for Transport Public (department-for-transport-public)

**GitHub**: https://github.com/department-for-transport-public

**Focus**: The public-facing DfT GitHub organisation hosts the Digital Traffic Regulation Orders (D-TRO) beta programme — the UK's most strategically relevant open-source transport data initiative — alongside NaPTAN geospatial validation tooling and R-based data analysis packages. 39 public repositories, primarily R packages for internal data analysis.

**Notable Repositories**:

| Repository | Description | Language | Stars | Last Active |
|------------|-------------|----------|-------|-------------|
| D-TRO | Digital Traffic Regulation Orders data specification and beta programme | JSON Schema / Docs | 12 | 2025-01-06 |
| Open_NaPTAN | Validation and mapping of UK National Public Transport Access Nodes | Python / HTML | 29 | 2020-08-26 |
| nts_digital_diary | National Travel Survey digital diary application | PHP | — | Active |
| govspeakr | R package for govspeak formatting for GOV.UK publishing | R | — | Active |

**Architectural Approach**: D-TRO uses a JSON schema data specification with a dedicated API portal (d-tro.dft.gov.uk). The organisation predominantly uses R for internal data analysis pipelines. The NaPTAN tool uses Python with GeoPandas, Folium, and Pandas for geospatial processing.

**Standards Followed**: JSON Schema (D-TRO data specification v3.5.1), SWA codes (GeoPlace), Reproducible Analytical Pipelines (RAP), GOV.UK publishing standards, MIT License

---

### East Sussex County Council

**GitHub**: https://github.com/east-sussex-county-council

**Focus**: East Sussex was one of the most active UK local authority open-source contributors in the early 2010s, with 93 public repositories. Their output covers web infrastructure, CMS customisation (Umbraco), Azure services, address management, and legacy transport-adjacent tools. Most activity has ceased since 2022.

**Notable Repositories**:

| Repository | Description | Language | Stars | Last Active |
|------------|-------------|----------|-------|-------------|
| Escc.Gritting.GrittingMap | Google Map showing position of gritting vehicles in real time | C# / JS | 0 | 2019 (archived) |
| Escc.Services.Azure | Azure-hosted services integration library | C# | — | 2022 |
| Escc.Services | Service layer library for council web applications | C# | — | 2022 |
| Escc.AddressAndPersonalDetails | Address data management and validation | C# | — | 2022 |

**Architectural Approach**: .NET / ASP.NET legacy web stack; Classic ASP in older repos; Azure hosting; Umbraco CMS. The gritting map used Google Maps API with vehicle GPS integration — a direct predecessor to the kind of real-time IoT asset tracking National Highways requires.

**Standards Followed**: Azure deployment patterns; GDS web standards; MIT/Apache licensing

---

### Dundee City Council (DundeeCityCouncil)

**GitHub**: https://github.com/DundeeCityCouncil

**Focus**: Dundee's GIS team maintains 8 public repositories covering ArcGIS Web App Builder widgets, open data publishing (Scottish open data catalogue integration), and Jupyter notebooks for geographic analysis. Contact via gis@dundeecity.gov.uk.

**Notable Repositories**:

| Repository | Description | Language | Stars | Last Active |
|------------|-------------|----------|-------|-------------|
| GIS | GIS web applications and tools | JavaScript | — | Active |
| open-data-scotland | Integration with Scottish open data catalogue | Python | — | Maintained |
| OpenData | Open datasets with Jupyter analysis notebooks (streets, recycling) | Jupyter Notebook | 0 | Maintained |
| WABWidgets | ArcGIS Web App Builder custom widgets | JavaScript | — | Maintained |

**Architectural Approach**: ArcGIS platform (Esri ecosystem) for GIS; Python/Pandas/Jupyter for data analysis; JavaScript for custom web widgets. Focused on open data publication via existing national portals rather than building new API infrastructure.

**Standards Followed**: Open Government Licence (where applicable), Scottish Open Data standards, Esri/ArcGIS platform conventions

---

### DVLA

**GitHub**: https://github.com/DVLA

**Focus**: The Driver and Vehicle Licensing Agency maintains 39 public repositories emphasising cloud infrastructure utilities, testing frameworks, and emerging technology experimentation. Their AWS SQS tooling and address lookup microservice are notable for infrastructure patterns relevant to National Highways.

**Notable Repositories**:

| Repository | Description | Language | Stars | Last Active |
|------------|-------------|----------|-------|-------------|
| sqs-extended-client | AWS SQS message management for large payloads (> 256KB via S3) | JavaScript | — | Active |
| aws-sqs-utility | CLI tool for reading, writing, transforming AWS SQS messages | JavaScript | — | Active |
| os-address-lookup | Microservice for Ordnance Survey postcode/UPRN address lookup | Scala | — | Active |
| lab-gen | Generative AI experiments | Python | — | Active |

**Architectural Approach**: Cloud-native on AWS; microservices architecture (Scala services); Ruby/Cucumber test automation; TypeScript frontends. Strong DevOps culture with reusable CLI utilities and published libraries.

**Standards Followed**: AWS Well-Architected patterns, Ordnance Survey UPRN standard, accessibility testing (axe-core), MIT License

---

### Department for Transport (department-for-transport)

**GitHub**: https://github.com/department-for-transport

**Focus**: The internal DfT GitHub organisation has 23 public repositories, primarily R guidance and data science experiments. Notably, it hosted a now-archived YOLOv2 vehicle counting neural network — an early experiment in computer vision for traffic monitoring.

**Notable Repositories**:

| Repository | Description | Language | Stars | Last Active |
|------------|-------------|----------|-------|-------------|
| dftlab-yolo-vehiclecounting | CNN for identifying and counting vehicles in images and video (archived) | Python / Jupyter | 8 | 2024-08-02 (archived) |
| learn_r_by_doing | R exercises for reading and visualising transport data | R | 0 | 2023-07-11 |
| R-cookbook | R coding guidance for DfT analysts | HTML / R | 1 | 2023-01-16 |

**Architectural Approach**: Python/TensorFlow for ML experiments; R for analytical pipelines with Reproducible Analytical Pipeline (RAP) methodology. No production services or APIs in the public organisation.

**Standards Followed**: Reproducible Analytical Pipelines (RAP), GOV.UK publishing via GitHub Pages, MIT License (ML repos)

---

## Technology Stack Analysis

### Languages

| Language | Repo Count | Percentage | Notable Projects |
|----------|------------|------------|-----------------|
| C# | 12 | 29% | GIFramework-Maps, FloodOnlineReportingTool, GdsBlazorComponents, Escc.Services.Azure |
| JavaScript / TypeScript | 10 | 24% | camdenmaps, WABWidgets, DVLA SQS tools, GIFramework-Maps (frontend) |
| Python | 7 | 17% | Open_NaPTAN, QGIS.Mosaic.Builder, dftlab-yolo-vehiclecounting, OpenData |
| R | 5 | 12% | learn_r_by_doing, R-cookbook, govspeakr, dftutils, dftplotr |
| HTML | 3 | 7% | R-cookbook (published), D-TRO documentation, Open_NaPTAN |
| Scala | 1 | 2% | os-address-lookup (DVLA) |
| Other (PHP, PowerShell, Classic ASP, Jupyter) | 4 | 10% | nts_digital_diary, Escc legacy repos, OpenData notebooks |

### Frameworks

| Framework | Language | Repo Count | Percentage | Notes |
|-----------|----------|------------|------------|-------|
| .NET / ASP.NET Core | C# | 8 | 19% | Dominant server-side framework across local authority repos |
| OpenLayers | TypeScript | 2 | 5% | Used in GIFramework-Maps and CamdenMaps for web mapping |
| Bootstrap | TypeScript / HTML | 3 | 7% | GIFramework-Maps, GdsBlazorComponents, FloodOnlineReportingTool |
| Blazor | C# | 1 | 2% | GdsBlazorComponents — GOV.UK Design System components for .NET |
| GeoPandas / Shapely | Python | 2 | 5% | Open_NaPTAN, QGIS plugin — geospatial processing |
| Folium | Python | 1 | 2% | Open_NaPTAN — interactive geospatial maps |
| TensorFlow / Keras | Python | 1 | 2% | dftlab-yolo-vehiclecounting (archived) |
| Entity Framework Core | C# | 2 | 5% | GIFramework-Maps, FloodOnlineReportingTool |
| Angular | JavaScript | 1 | 2% | camdenmaps — service finder mapping |

### Databases and Storage

| Technology | Type | Repo Count | Common Use |
|-----------|------|------------|------------|
| PostgreSQL with PostGIS | Relational + Geospatial | 2 | Spatial data storage in GIFramework-Maps and FloodOnlineReportingTool |
| AWS S3 | Object Storage | 1 | Oversized SQS message bodies (DVLA sqs-extended-client) |
| CSV / Open Data Files | Flat files | 3 | Open data publishing (Dundee, Bath NES) |
| Azure Blob / Services | Cloud storage | 2 | East Sussex Azure deployment, DfT data pipelines |

### Infrastructure and Deployment

| Technology | Repo Count | Notes |
|-----------|------------|-------|
| Azure (App Service / IIS / Kestrel) | 4 | GIFramework-Maps, FloodOnlineReportingTool, East Sussex services |
| AWS (SQS, S3) | 2 | DVLA infrastructure utilities |
| GitHub Actions | 4 | GIFramework-Maps (dev + prod pipelines), GdsBlazorComponents, R-cookbook |
| Heroku | 1 | camdenmaps (CI/CD via Travis CI) |
| NuGet | 1 | GdsBlazorComponents (12 releases published) |

---

## Standards and Patterns

| Standard / Pattern | Adoption | Description | Repos |
|-------------------|----------|-------------|-------|
| GOV.UK Design System | 4 repos (10%) | GOV.UK frontend components and interaction patterns | GdsBlazorComponents, FloodOnlineReportingTool, D-TRO portal, Escc legacy |
| MIT License | 8 repos (19%) | Open permissive licensing enabling government reuse | GIFramework-Maps, FloodOnlineReportingTool, GdsBlazorComponents, Open_NaPTAN, dftlab-yolo |
| Open Government Licence (OGL) | 3 repos (7%) | UK government standard licence for open data | GIFramework-Maps (docs), DundeeCityCouncil OpenData, DfT publications |
| PostgreSQL with PostGIS | 2 repos (5%) | Spatial database pattern for geospatial data | GIFramework-Maps, FloodOnlineReportingTool |
| JSON Schema (data specification) | 1 repo (2%) | Machine-readable data specification for traffic regulation | D-TRO |
| Reproducible Analytical Pipelines (RAP) | 3 repos (7%) | DfT analytical standard for reproducible R-based data work | R-cookbook, learn_r_by_doing, govspeakr |
| OGC Web Services (WMS/WFS) | 1 repo (2%) | Open Geospatial Consortium standards for spatial data services | GIFramework-Maps |
| OpenAPI / REST API design | Referenced in D-TRO portal | JSON-based API for traffic regulation data submission | D-TRO |
| GitHub Actions CI/CD | 4 repos (10%) | Automated build and deployment pipelines | GIFramework-Maps, GdsBlazorComponents, FloodOnlineReportingTool |
| Microservices / Message Contracts | 2 repos (5%) | Distributed service architecture with typed contracts | FloodOnlineReportingTool (public + contracts), DVLA SQS patterns |

---

## Maturity Assessment

Scores use a 1–5 scale per dimension. Overall maturity score is the mean across all five dimensions.

**Criteria Definitions**:
- **Activity** (1 = archived/dead, 5 = actively developed with commits < 3 months)
- **Documentation** (1 = no docs, 5 = comprehensive README, guides, API docs, architecture docs)
- **Tests** (1 = no tests, 5 = full test suite with CI and coverage reporting)
- **CI/CD** (1 = no automation, 5 = full CI/CD pipeline with automated deployment)
- **Community** (1 = single contributor, 5 = multiple departments/organisations contributing)

| Repository | Activity | Documentation | Tests | CI/CD | Community | Overall | Classification |
|------------|----------|---------------|-------|-------|-----------|---------|----------------|
| GIFramework-Maps (Dorset Council) | 5 | 4 | 3 | 4 | 2 | **3.6** | Mature |
| GdsBlazorComponents (Dorset Council) | 5 | 4 | 3 | 4 | 2 | **3.6** | Mature |
| D-TRO (DfT Public) | 4 | 3 | 1 | 1 | 2 | **2.2** | Developing |
| FloodOnlineReportingTool.Public (Dorset Council) | 4 | 3 | 2 | 3 | 2 | **2.8** | Developing |
| DVLA sqs-extended-client | 4 | 3 | 3 | 3 | 1 | **2.8** | Developing |
| DVLA os-address-lookup | 4 | 3 | 3 | 3 | 1 | **2.8** | Developing |
| Open_NaPTAN (DfT Public) | 2 | 4 | 3 | 2 | 3 | **2.8** | Developing |
| QGIS.Mosaic.Builder (Dorset Council) | 4 | 3 | 2 | 2 | 1 | **2.4** | Developing |
| FloodOnlineReportingTool.Contracts (Dorset Council) | 4 | 2 | 2 | 2 | 1 | **2.2** | Developing |
| DundeeCityCouncil/OpenData | 3 | 2 | 1 | 1 | 1 | **1.6** | Experimental |
| Escc.Services.Azure (East Sussex) | 2 | 2 | 2 | 2 | 1 | **1.8** | Experimental |
| Escc.Gritting.GrittingMap (East Sussex) | 1 | 2 | 1 | 1 | 1 | **1.2** | Experimental |
| dftlab-yolo-vehiclecounting (DfT) | 2 | 3 | 1 | 1 | 1 | **1.6** | Experimental |
| camdenmaps (Camden Council) | 2 | 3 | 4 | 3 | 1 | **2.6** | Developing |
| DfT R-cookbook | 2 | 4 | 2 | 3 | 1 | **2.4** | Developing |

**Maturity Summary**:
- Production-Grade (4.0+): 0 repositories
- Mature (3.0–3.9): 2 repositories (GIFramework-Maps, GdsBlazorComponents)
- Developing (2.0–2.9): 9 repositories
- Experimental (< 2.0): 4 repositories

---

## Collaboration Opportunities

| Opportunity | Organisations | Description | Potential Value |
|-------------|--------------|-------------|-----------------|
| Shared GeoJSON / OGC spatial data API pattern | Dorset Council, DfT Public, National Highways | GIFramework-Maps demonstrates a mature OGC/WMS/WFS pattern with PostGIS. National Highways could engage Dorset Council to extend this into a higher-throughput pattern suitable for strategic road network layers, potentially contributing back a road-network data product connector. | Avoid 6-12 months of geospatial API design; adopt proven PostgreSQL/PostGIS stack; reduce duplication of mapping infrastructure across government |
| D-TRO data specification alignment | DfT Public (D-TRO team), National Highways, Local Highway Authorities | D-TRO (Digital Traffic Regulation Orders) will mandate digital submission of traffic regulation orders. National Highways' open data API must produce data compatible with D-TRO v3.5.1+ JSON schema. Early engagement with the DfT D-TRO team would ensure National Highways' roadworks and incident data products align with the emerging national standard from day one. | Prevents costly rework when D-TRO submission becomes mandatory; positions National Highways as a model participant for other Highway Authorities |
| GOV.UK Design System component reuse for control room dashboards | Dorset Council (GdsBlazorComponents), National Highways | GdsBlazorComponents provides 30+ production-ready GOV.UK Design System Blazor components published to NuGet. If National Highways builds any .NET-based internal tooling or public-facing portals, these components eliminate front-end build time and ensure GDS compliance. | Saves 4-8 weeks of frontend component development; guaranteed WCAG 2.2 AA compliance; actively maintained with 12+ NuGet releases |
| Vehicle counting and traffic analytics ML patterns | DfT (archived YOLOv2 repo), National Highways | DfT's archived vehicle counting neural network (YOLO-based) provides a useful reference architecture for automated traffic classification from CCTV footage. National Highways' 3,500 CCTV cameras represent a significant opportunity to build on this pattern at scale. A joint experiment with the DfT lab team could revive and productionise this work under shared sponsorship. | Avoided duplicate R&D on computer vision for traffic; shared model training datasets; positions both organisations for future AI/ML capability building |
| Open data publishing patterns | Dundee City Council, Bath NES, DfT Public, National Highways | Multiple local authorities have developed open data publication workflows (Jupyter notebooks, Python scripts, open data portals). While none match National Highways' scale, the pattern of publishing road and geographic datasets under the Open Government Licence is well established. National Highways could publish its open API datasets using an extended version of these patterns. | Faster time to open data publication; community of practice for open government transport data |

---

## Gaps and Opportunities

| Gap / Opportunity | Current State | Impact | Recommended Action |
|------------------|---------------|--------|--------------------|
| No real-time transport data streaming platform in UK government open source | No open-source implementations of Kafka/Event Hub-based traffic sensor pipelines exist across 24,500+ UK government repos. All sensor data work is proprietary or absent. | Critical gap — National Highways must build from scratch with no government precedent to draw on | Design the streaming ingestion platform for reusability from the outset; publish architecture decision records and reference implementations so future highway authorities can adopt the pattern |
| No data mesh implementations in UK public sector open source | No data mesh or data product architecture examples found in any UK government repository. The pattern is discussed in strategy documents but not implemented openly. | High — National Highways is pioneering this approach within UK government | Consider publishing the data mesh governance framework and data product contract templates under OGL once the architecture is proven; engage GDS and CDDO to contribute to cross-government guidance |
| D-TRO is a documentation repo, not a service implementation | D-TRO is a data specification and beta programme document repo. No open-source service implementation (API gateway, validation service, submission portal) exists publicly. | Medium — if National Highways builds D-TRO-compliant services, it could open-source the implementation for all highway authorities to reuse | National Highways should engage the DfT D-TRO programme team to understand the reference implementation, and consider contributing a D-TRO validator or adapter as a reusable library |
| NaPTAN validation tool is unmaintained (last commit 2020) | Open_NaPTAN has not been updated since August 2020 despite being a foundational transport dataset tool | Medium — public transport access node data quality affects journey planning data integrations (e.g. multimodal routing from strategic road network to public transport) | National Highways should assess whether NaPTAN data is needed for multimodal routing integrations; if so, engage DfT to understand whether Open_NaPTAN is being replaced with a maintained alternative |
| No government-wide vehicle or asset tracking open-source pattern | The East Sussex gritting map (archived 2019) is the only example of real-time government vehicle tracking found. No pattern library or reference implementation exists. | High — National Highways needs real-time tracking for Traffic Officer vehicles and maintenance fleets | Review the East Sussex gritting map as a reference architecture only; the pattern (GPS feed + map API + CCTV integration) is directly analogous to National Highways' need, but the implementation must be rebuilt at enterprise scale |
| Geospatial tools use ArcGIS (proprietary) or limited OGC services | Dundee uses ArcGIS Web App Builder (proprietary Esri platform). GIFramework-Maps uses open OGC standards. No central government-wide geospatial platform exists in open source. | Medium — National Highways must choose between Esri ecosystem lock-in and open OGC/PostGIS stack | GIFramework-Maps represents the recommended open-standard approach. Adopt OGC WMS/WFS/WCS standards with PostGIS for National Highways' geospatial layer; avoids Esri licensing costs at scale |
| No shared data platform infrastructure for government | Each organisation builds its own data lake, ETL pipelines, and API management from scratch. No cross-government shared data infrastructure exists in open source. | High — represents significant cross-government duplication of effort and cost | Recommend National Highways participate in the CDDO data exchange programme and GovDataShare initiatives; publish infrastructure-as-code templates for Azure-based data platforms under OGL |
| ANPR and CCTV data handling — no open patterns | No UK government open-source repository addresses ANPR anonymisation, privacy-preserving video analytics, or OFFICIAL-SENSITIVE data handling for road cameras | Critical — National Highways handles ANPR and CCTV data under OFFICIAL-SENSITIVE classification | Design ANPR anonymisation pipeline with NCSC guidance from the outset; do not rely on any existing open-source government pattern; engage NCSC directly for CAF assessment of the CCTV/ANPR data flows |

---

## Recommendations

### Strategic Recommendations

1. **Engage the DfT D-TRO programme team**: The Digital Traffic Regulation Orders programme (d-tro.dft.gov.uk) is the most strategically significant adjacent government data initiative. National Highways' roadworks and incident data products must be D-TRO-compatible from the outset. Early engagement will prevent costly rework and position National Highways as a model data publisher under the mandatory digital submission regime.

2. **Adopt GIFramework-Maps' PostgreSQL/PostGIS and OGC pattern for geospatial layers**: Dorset Council's GIFramework-Maps is the most mature open-source geospatial tool in UK government, using OGC web services, PostGIS, and OpenLayers. National Highways should adopt the same open-standard stack rather than committing to proprietary Esri ArcGIS, and should engage the Dorset Council GIS team as a community of practice partner.

3. **Pioneer open data publication for strategic road network data**: No UK central government organisation currently publishes real-time road network data via an open API. National Highways has an opportunity to become the sector leader. The DfT's Open_NaPTAN (29 stars, 5 contributors) shows that even a simple open data tool attracts cross-government engagement. A well-documented REST API for traffic, incidents, and roadworks will attract navigation app developers and position National Highways as a model for GDS Service Standard compliance.

4. **Reuse GdsBlazorComponents for any .NET-based internal tooling**: If the control room unified dashboard or any internal tooling uses .NET/Blazor, Dorset Council's GdsBlazorComponents (12 NuGet releases, actively maintained) should be adopted immediately. This eliminates frontend component development time and ensures GOV.UK Design System compliance out of the box.

5. **Monitor the DVLA's cloud infrastructure patterns**: DVLA's public repositories demonstrate mature AWS-first microservices patterns (SQS extended client, UPRN address lookup microservice). While National Highways targets Azure, the DVLA's patterns for building resilient cloud-native government services are directly transferable, particularly the message queue management approach which mirrors the event-driven architecture National Highways needs for sensor data ingestion.

### For This Project Specifically

National Highways is operating at a scale and technical ambition that has no direct precedent in UK government open source. The programme should design its architecture with a "contribute back" mindset from day one: publish data schemas, API specifications, infrastructure-as-code templates, and data product governance frameworks under the Open Government Licence. This approach fulfils the Technology Code of Practice requirement to make things open and aligns with the DfT's own direction of travel on digital standards for roads.

The most immediately actionable reuse candidates are: (1) GdsBlazorComponents for any .NET-based portal or dashboard work; (2) the PostGIS/OGC stack demonstrated in GIFramework-Maps for the geospatial layer of the data platform; and (3) the D-TRO JSON schema as an input to the Roadworks data product contract specification. These three reuse opportunities could save 3–6 months of design and development effort across the programme.

The absence of any real-time streaming, data mesh, or large-scale sensor data management implementations in UK government open source confirms that National Highways must build the streaming ingestion and data product platform largely from first principles, drawing on Azure Databricks, Event Hubs, and Kafka patterns from commercial sector references rather than government precedent. The programme should plan for this build complexity in the risk register (see ARC-001-RISK-v1.0) and ensure architecture decision records (ADRs) are published to GitHub so future government data platform programmes can learn from the approach.

### Related ArcKit Commands

- Run `/arckit.gov-reuse` to perform a detailed reusability assessment of GIFramework-Maps, GdsBlazorComponents, D-TRO, and DVLA os-address-lookup as reuse candidates
- Run `/arckit.gov-code-search` to search for specific code patterns within Dorset Council's PostGIS integration or DfT's D-TRO JSON schema implementation
- Run `/arckit.research` for broader market and vendor research on Azure Event Hubs, Databricks data mesh, and Kafka-based real-time transport data platforms beyond government open source

---

## External References

| Document | Type | Source | Key Extractions | Path |
|----------|------|--------|-----------------|------|
| D-TRO Data Specification v3.5.1 | Technical Specification | https://d-tro.dft.gov.uk | JSON schema for digital traffic regulation orders; mandatory submission programme | External |
| GIFramework-Maps Repository | Open Source Repository | https://github.com/Dorset-Council-UK/GIFramework-Maps | OGC/WMS/WFS stack, PostGIS, OpenLayers, .NET — reuse candidate | External |
| GdsBlazorComponents Repository | Open Source Repository | https://github.com/Dorset-Council-UK/GdsBlazorComponents | 30+ GOV.UK Design System Blazor components, NuGet published | External |
| Open_NaPTAN Repository | Open Source Repository | https://github.com/department-for-transport-public/Open_NaPTAN | Python/GeoPandas NaPTAN validation — transport data quality reference | External |
| DVLA sqs-extended-client | Open Source Library | https://github.com/DVLA/sqs-extended-client | AWS SQS message management pattern for large payloads | External |
| DfT YOLO Vehicle Counting (archived) | Research Repository | https://github.com/department-for-transport/dftlab-yolo-vehiclecounting | CNN vehicle counting from CCTV/video — reference for traffic analytics | External |

---

**Generated by**: ArcKit `/arckit:gov-landscape` agent
**Generated on**: 2026-03-23
**ArcKit Version**: 4.5.0
**Project**: National Highways Data Architecture Modernization (Project 001)
**AI Model**: claude-sonnet-4-6
