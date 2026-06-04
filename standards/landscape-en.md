# AEV Safety Standards Landscape v1.0

[中文](landscape.md)

## Positioning

This file maps standards relevant to AEV Safety. It is not authorized standards text and does not provide clause-level interpretation. Without authorized text, official status pages, catalogue pages and public descriptions can support status and scope only; they do not replace standard requirements.

Information status: standard names, versions and project status in this file are calibrated against public pages and the project BibTeX seed as of 2026-06-04. Before formal submission, standardization proposals or enterprise review, ISO, SAE, UL, Chinese national-standard public service pages, industry organizations and authorized standard texts should be rechecked.

## Road-Vehicle Method Donors

| Standard/document | Role | Transferable content | Not directly transferable |
|---|---|---|---|
| ISO 26262 | Road-vehicle functional safety | Safety lifecycle, hazard analysis, functional safety concept, V&V | ASIL labels should not be directly applied to machinery |
| ISO 21448 | SOTIF | Functional insufficiency, trigger condition, known/unknown unsafe scenarios, verification strategy | Road ODD and driving tasks do not cover work tasks |
| ISO 34502 | ADS scenario-based testing | Functional, logical and concrete scenario layers | Road scenario ontology does not directly describe stockpiles, dumping or trenching |
| ISO/SAE 21434 | Cybersecurity engineering | Assets, threats, attack paths, safety impact | Does not replace functional safety or SOTIF |
| ISO/PAS 8800 | Road-vehicle AI safety | AI component lifecycle, safety argumentation and verification thinking | Does not replace engineering-vehicle field validation |

## Engineering and Mining Machinery Base

| Standard/guidance | Relevance | Use in AEV Safety |
|---|---|---|
| ISO 17757 | Safety of autonomous and semi-autonomous earth-moving and mining machine systems | Supports discussion of autonomous machine systems, supervision, operating areas and organizational measures |
| ISO 19014 | Functional safety of safety-related parts of control systems on earth-moving machinery | Supports machine-control system safety, failure handling and performance levels |
| ISO 15817 | Remote operator control systems for earth-moving machinery | Supports remote control, authority, human role and communication boundary |
| ISO 21815 | Collision warning and collision avoidance for earth-moving machinery | Supports proximity risk, warning and avoidance functions |
| GMG autonomous mining guidance | Autonomous mining systems, operational readiness, safety case, change management | Supports system-level evidence and operational readiness for mining autonomy |

## Adjacent Non-Road and Robot Standardization Signals

| Signal | Relevance | Boundary |
|---|---|---|
| ISO 18497-1:2024 | Design principles and vocabulary for partially automated, semi-autonomous and autonomous agricultural machinery and tractors | Adjacent non-road mobile-work evidence, not an engineering-vehicle compliance standard |
| Chinese national-standard project on robot SOTIF | Entered public consultation on 2026-06-02; public scope includes ODD, scenario, trigger condition, functional insufficiency, risk evaluation and mitigation | Mobile physical AI standardization signal, not a published engineering-vehicle standard |
| ISO 10218 / ISO/TS 15066 | Industrial robot and collaborative-application safety | Supports physical interaction, speed and separation, power/force limitation thinking |
| EU AI Act and AI risk-management frameworks | High-risk AI governance | Supports AI risk-management perspective, not machine field safety assurance |

## AEV Safety Gap Statement

AEV Safety does not claim that engineering vehicles have no standards. The more precise gap is:

Existing standards and guidance have not yet formed a unified evidence chain connecting MWMS, WTDC, DMWT, functional insufficiency, trigger condition, task consequence, operational monitoring and safety case.

## Candidate Standardization Modules

Future engineering-vehicle SOTIF or autonomous-work safety guidance may include:

1. Scope and object: mobile working-machine system, not a single vehicle.
2. Terms: MWMS, WTDC, DMWT, task consequence, supervision mode, recovery capability.
3. Worksite and task declaration: terrain, material, attachment, personnel area, exclusion zone, communication, localization, supervision.
4. SOTIF risk chain: insufficiency, trigger condition, hazardous event, task consequence, mitigation.
5. Testing matrix: simulation, closed-course, vehicle test, fault injection, mixed human-machine work.
6. Operational monitoring: anomaly, near miss, takeover, degradation, recovery, task-quality deviation.
7. Safety case: claims, arguments, evidence, assumptions, limitations.

## Status-Check List

Before using this landscape formally, at least the following checks are required:

1. Current versions, revision status and citation boundaries for ISO 21448, ISO/PAS 8800, ISO 34502 and ISO/SAE 21434.
2. Current versions, replacement relationships and authorized clause content for ISO 17757, ISO 19014, ISO 15817 and ISO 21815.
3. The adjacent relationship between ISO 18497-1:2024 and engineering vehicles, avoiding any claim that an agricultural-machinery standard is an engineering-vehicle compliance standard.
4. Project status, consultation period, publication status and scope of the Chinese robot SOTIF national-standard project.
5. Evidence classes for GMG guidance, company official pages and public demonstrations, avoiding the use of scenario anchors as certification evidence.

## Do Not Do

- Do not describe the robot SOTIF project as a published standard.
- Do not treat company case pages as certification evidence.
- Do not treat internal project material as public validation.
- Do not copy ASIL, ODD, DDT or SAE automation levels into engineering vehicles without adaptation.
