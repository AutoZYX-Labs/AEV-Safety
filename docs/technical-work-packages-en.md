# AEV Safety Technical Work Packages and Evidence Traceability

[中文](technical-work-packages.md)

## Purpose

This file turns AEV Safety, or Autonomous Engineering Vehicle Safety, into executable, reviewable and reusable technical work packages. The purpose is not to reduce open problems to a single paper. It is to give researchers, testing organizations, standardization experts and enterprise engineering teams a shared evidence chain for continued work.

The work packages follow one rule:

Every public claim must be traceable to source input, technical object, verification method, evidence boundary and next work.

## Current Public Status

Information status: 2026-06-05.

| Module | Current status | Public output | Next step |
|---|---|---|---|
| Source absorption | Source synthesis and evidence boundary drafted | `docs/source-synthesis-en.md` | Add DOI, official pages and authorized-standard version checks for key public sources |
| Literature review | Chinese and English research landscape drafted | `docs/literature-review.md`, `docs/literature-review-en.md` | Expand search strings, databases, inclusion/exclusion records and PRISMA-style logging |
| Conceptual framework | MWMS, WTDC and DMWT defined | `README-en.md`, `paper/manuscript-en.md` | Test usability in field samples, test records and candidate standard clauses |
| Scenario taxonomy | Seven top-level taxonomy classes drafted | `taxonomy/worksite-task-taxonomy-v1.0-en.md` | Add cross-matrix of machine type, task type, triggering condition and consequence class |
| Reference architecture | Five-layer safety-assurance architecture drafted | `architecture/reference-architecture-en.md` | Add authority transfer, runtime Guardian and remote-supervision interface details |
| Evaluation matrix | Six consequence classes and test-record fields drafted | `benchmarks/evaluation-matrix-en.md` | Convert fields into machine-readable templates and design sample test records |
| Standardization roadmap | Candidate modules and staged plan drafted | `standards/standardization-roadmap-en.md` | Continue calibration against authorized standards, expert review and real engineering evidence |
| Manuscript draft | Full Chinese and English drafts available | `paper/manuscript-zh.md`, `paper/manuscript-en.md` | Complete authorship data, references, submission format and figure-rights status |

## Evidence Traceability Map

| Source strand | Transformed technical object | Public module | Claim it cannot support |
|---|---|---|---|
| Li Xuefei's autonomous construction-machinery material | Loader work loop, stockpile/bucket/dumping/path-control problems | Source synthesis, taxonomy, evaluation matrix, manuscript | Product certification, safety maturity, market share or commercial forecast |
| Move the Earth and Beyond | Extreme-condition extrapolation from terrestrial construction to planetary-resource work | Source synthesis, taxonomy class G, architecture, manuscript Section 8 | Engineering maturity of space mining |
| Construction and mining autonomy literature | Semi-automated sites, cooperating equipment, system-of-systems safety and remote supervision | Literature review, architecture, standards roadmap | Project-specific hazard analysis and field tests |
| Mobile physical AI evaluation-platform material | HMRM/HLMB, five-source data, cross-embodiment behavior evaluation and third-party reviewability | Source synthesis, literature review, evaluation matrix | Direct replacement of engineering-vehicle task-quality evaluation by human-like mobility evaluation |
| Robot SOTIF standardization signal | ODD/scenario, triggering condition, functional insufficiency, risk chain and mitigation | Standards landscape, source synthesis, manuscript | Published engineering-vehicle standard |
| Road-vehicle safety standards | Functional safety, SOTIF, scenario testing, AI safety, cybersecurity and safety-case methods | Standards landscape, manuscript, standardization roadmap | Direct engineering-vehicle compliance conclusion |
| Engineering-machinery and mining standards/guidance | Autonomous machine systems, control-system safety, remote control, collision warning and operational readiness | Standards landscape, architecture, standardization roadmap | Authorized standard text and project-specific conformity judgement |

## WP0: Evidence Governance and Public Boundaries

Goal: prevent internal material, public demonstrations, standards status pages, company pages and peer-reviewed papers from being treated as the same class of evidence.

Core questions:

1. Which sources can support public facts?
2. Which sources are background inputs only?
3. Which conclusions must wait for authorized standard text, formal test reports or field-operation data?

Current outputs:

- Four evidence classes: A-FULL, B-OFFICIAL, C-PUBLIC and D-INTERNAL.
- Evidence-boundary statements in the public website and manuscript.
- Conservative-use rules for unpublished commercial material.

Quality gates:

- Every standard status, project status and date must be traceable to an official page or authorized text.
- Internal material must not be used as evidence for safety performance, certification maturity or market conclusions.
- News, videos and public demos can provide scenario anchors only; they cannot prove safety effectiveness.

## WP1: MWMS System Boundary Definition

Goal: expand the assurance object from a single vehicle to a Mobile Working Machine System.

MWMS includes:

1. Vehicle platform: powertrain, braking, steering, hydraulics, chassis, upper structure and controllers.
2. Work equipment: bucket, boom, stick, piling device, trenching device, compaction device, breaker and other tools.
3. Attachments and material: stockpiles, earthwork, ore, truck beds, hoppers, piles, trenches, solar racks and planetary surface material.
4. Site infrastructure: barriers, geofence, localization, communication, dispatch, maps, energy supply and warning devices.
5. People and organization: site workers, maintainers, remote supervisors, remote drivers, dispatchers and third-party cooperating personnel.
6. External systems: trucks, conveyors, UAVs, robot dogs, site servers and mine/construction-site management systems.

Current outputs:

- Five-layer structure in `architecture/reference-architecture-en.md`.
- Section 5.1 in `paper/manuscript-en.md`.
- MWMS definition in `README-en.md`.

Quality gates:

- Every test record must state the MWMS boundary, not only the machine model.
- Every safety claim must state whether it covers the complete machine, work equipment, site system or organizational process.

## WP2: WTDC and DMWT Taxonomy

Goal: transfer road-vehicle ODD/DDT methods into worksite and task conditions.

WTDC should cover:

1. Site: mine, port, batching plant, construction site, solar field, vessel hold, testbed and lunar-analogue site.
2. Terrain: slope, surface, low adhesion, pothole, embankment, trench, loose material and unknown terrain.
3. Material: sand, gravel, ore, earth, slurry, dust, piles, solar racks and unknown planetary surface material.
4. People and assets: workers, bystanders, human-operated equipment, trucks, conveyors, fixed infrastructure and exclusion zones.
5. Operating conditions: communication, localization, map freshness, energy, weather, lighting, remote supervision and dispatch constraints.

DMWT should cover:

1. Movement: forward motion, reversing, turning, V-shaped cycle, ramp, obstacle avoidance, following and platooning.
2. Work: digging, loading, dumping, hauling, piling, trenching, compacting, hold cleaning, breaking and material transfer.
3. Task quality: fill rate, dumping deviation, trench depth, pile position, compaction, surface flatness and rework.
4. Recovery: slowing down, stopping, emergency stop, remote confirmation, remote driving, on-site takeover, evacuation and retest.

Current outputs:

- `taxonomy/worksite-task-taxonomy-v1.0-en.md`.
- Test-record fields in `benchmarks/evaluation-matrix-en.md`.
- Sections 5.2 and 5.3 in `paper/manuscript-en.md`.

Quality gates:

- A scenario must not be written only as "loader operation"; it must include reviewable WTDC and DMWT fields.
- Passing criteria must connect to task consequences, not only collisions or emergency stops.

## WP3: SOTIF-Oriented Risk Chain

Goal: connect functional insufficiency, triggering condition, hazardous event, task consequence and mitigation.

Typical risk chain:

```text
WTDC/DMWT condition
→ functional insufficiency
→ triggering condition
→ hazardous event or task failure
→ six consequence classes
→ mitigation
→ residual risk and evidence
```

Examples:

| Scenario | Insufficiency | Triggering condition | Consequence | Mitigation |
|---|---|---|---|---|
| Stockpile loading | Insufficient stockpile-shape recognition | Dust, backlight, material collapse | Low fill rate, spillage, hydraulic shock | Slowdown, stockpile re-estimation, remote confirmation |
| Vessel-hold cleaning | Insufficient person/obstacle recognition | Narrow space, occlusion, strong reflection | Human exposure, asset collision, difficult recovery | Exclusion zone, low-speed mode, on-site confirmation |
| Solar piling | Insufficient pile-position and terrain judgement | Uneven ground, GNSS drift, rack occlusion | Pile-position deviation, rework, equipment damage | Localization recheck, task pause, human review |
| Lunar resource work | Unknown terrain/material judgement | Long delay, low energy, communication loss | Machine entrapment, task interruption, non-recoverability | Planned recovery path, local autonomous recovery, energy protection |

Current outputs:

- Section 5.4 in `paper/manuscript-en.md`.
- SOTIF risk-chain clause skeleton in `standards/standardization-roadmap-en.md`.
- `trigger_condition` and `insufficiency` fields in `benchmarks/evaluation-matrix-en.md`.

Quality gates:

- SOTIF must not be reduced to a collision-risk checklist; functional insufficiency and triggering conditions must be explicit.
- Road-vehicle ODD must not be treated as WTDC; material, tool, task quality and recoverability must be included.

## WP4: Testing, Evaluation and Operational Monitoring

Goal: extend safety evidence from one-off tests to a development, closed-site, field-operation and review loop.

Evaluation objects:

1. Human safety.
2. Assets and infrastructure.
3. Production continuity.
4. Task quality.
5. Environment and resources.
6. Recoverability.

Data sources:

1. Simulation scenarios.
2. Closed-site tests.
3. Indoor and outdoor vehicle tests.
4. Field-operation logs.
5. Human review and remote-supervision records.
6. Incidents, near misses and anomaly reviews.

Current outputs:

- `benchmarks/evaluation-matrix-en.md`.
- Sections 6.2, 6.3 and 6.4 in `paper/manuscript-en.md`.

Quality gates:

- Metrics must define unit, sampling frequency, triggering condition, applicable machine and applicable worksite.
- Thresholds must not be written as universal standards without machine, site, task and authorized-standard basis.
- Operational monitoring must feed back into taxonomy, risk chain and safety case.

## WP5: Safety Case and Standardization Modules

Goal: convert the research framework into evidence structures reviewable by standardization experts, testing organizations and enterprise engineering teams.

Candidate standard modules:

1. Scope and terms: MWMS, WTDC, DMWT, functional insufficiency, triggering condition, task consequence and minimal-risk state.
2. System boundary: machine, tool, material, site, people, supervision and external cooperating systems.
3. Scenario classification: functional, logical and concrete scenarios for work tasks.
4. Risk analysis: boundaries among SOTIF risk chain, functional-safety failure, cybersecurity event and AI functional insufficiency.
5. Testing and evaluation: simulation, closed-site tests, field operation, operational monitoring and near-miss review.
6. Safety argumentation: claims, arguments, evidence, assumptions, limitations and residual risk.

Current outputs:

- `standards/landscape-en.md`.
- `standards/standardization-roadmap-en.md`.
- Sections 6.5 and 9.3 in `paper/manuscript-en.md`.

Quality gates:

- Standard names, versions, project status and public-notice periods must be checked against official sources.
- Adjacent standards must not be written as direct compliance bases.
- Candidate clauses must not be described as published or already adopted by industry.

## WP6: Engineering Implementation and Productization Evidence

Goal: make the research framework useful for real products, not only manuscript expression.

Target engineering objects:

1. Autonomous loading and dumping with wheel loaders.
2. Excavators and trenching machines.
3. Autonomous haulage trucks and haulage systems.
4. Solar-construction and piling equipment.
5. Hold-cleaning, breaking, compaction and material-transfer robots.
6. Extreme-environment and future planetary-resource systems.

Productization evidence should include:

1. Requirement decomposition: derive safety requirements from WTDC, DMWT and consequence classes.
2. Interface definition: low-level controller, hydraulic/braking/steering interface, remote-supervision interface and dispatch interface.
3. Degradation and recovery: functional insufficiency, triggering condition, low confidence, communication degradation and on-site takeover process.
4. Field records: test records, operation logs, anomaly samples, near misses and retest results.
5. Responsibility boundary: complete-machine development, front-fit, retrofit, remote operation, site management and third-party cooperation.

Quality gates:

- Product implementation must state specific machine, site, task and operating mode.
- Generic safety slogans must not replace reviewable evidence fields.
- Enterprise data must be anonymized, rights-cleared and evidence-class labeled before public use.

## How to Use This File

| User | Suggested path |
|---|---|
| Researchers | Use WP1-WP3 to formulate research questions, WP4-WP5 to design validation and WP6 to locate engineering relevance |
| Testing organizations | Use WP2-WP4 to design scenario libraries, test records and operational-monitoring fields |
| Standardization experts | Use WP0, WP3 and WP5 to discuss terms, scope, clause skeletons and evidence boundaries |
| Enterprise engineering teams | Use WP1, WP2, WP4 and WP6 to build product safety cases and close field-problem loops |

## Current Non-Goals

1. Do not publish internal business plans, customer information, cost, quotation or unpublished collaboration details.
2. Do not replace authorized standards, formal test reports, enterprise field safety reviews or certification conclusions.
3. Do not directly copy road-vehicle automated-driving safety standards into engineering-vehicle compliance requirements.
4. Do not describe the robot SOTIF project as a published engineering-vehicle standard.
5. Do not treat manuscript publication as the only project objective; real product implementation and standardization consensus are equally important.
