# AEV Safety Standardization Opportunities and Recommendations

[中文](standardization-opportunities.md)

Information status: 2026-06-05.

This file turns the current standards landscape, source synthesis and manuscript draft into standardization recommendations for AEV Safety, or Autonomous Engineering Vehicle Safety. It is not a formal standards proposal and does not represent any standards body. Its purpose is to make autonomous engineering-vehicle safety discussable, modular and pilotable as standardization work packages.

## Core Judgement

The standardization opportunity is not to claim that engineering vehicles have no standards. Earth-moving machinery, mining equipment, robots, road-vehicle automation and AI safety already have many standards and guidance documents.

The real opportunity is:

Connect machine safety, control-system functional safety, road-vehicle SOTIF, scenario-based testing, remote control, autonomous mining systems, robot safety and AI safety into a scenario evidence chain for mobile working machine systems.

This evidence chain should cover:

1. MWMS: Mobile Working Machine System.
2. WTDC: Worksite and Task Design Conditions.
3. DMWT: Dynamic Moving and Working Task.
4. SOTIF risk chain: functional insufficiency, triggering condition, hazardous event, task consequence and mitigation.
5. Testing and evaluation: simulation, closed-site tests, field operation, operational monitoring and near-miss review.
6. Safety case: claims, arguments, evidence, assumptions, limitations and residual risk.

## Gaps from Standards Comparison

| Standards/guidance family | Existing value | Gap for AEV Safety |
|---|---|---|
| ISO 26262 | Road-vehicle functional-safety lifecycle, ASIL, safety goals and hardware/software development process | Road-vehicle E/E scope does not directly cover work equipment, material interaction and construction-site organization |
| ISO 21448 | SOTIF, functional insufficiency, triggering conditions and known/unknown unsafe scenarios | Needs transfer from road ODD/DDT to WTDC/DMWT |
| ISO 34502 | Scenario classification and scenario-based testing language | Needs material, tool, task quality, recoverability and site-organization dimensions |
| ISO/PAS 8800 | Road-vehicle AI safety lifecycle | Inspires AI component safety but does not replace field validation and task-quality evaluation |
| ISO/SAE 21434 | Road-vehicle cybersecurity engineering | Needs linkage to remote supervision, dispatch, site communication, maps and operational logs |
| ISO 17757 | Safety of autonomous and semi-autonomous earth-moving and mining machine systems | Provides a machinery autonomy base but still needs connection with SOTIF, scenario testing and safety cases |
| ISO 19014 | Functional safety of safety-related parts of earth-moving machinery control systems | Supports control-system failure risk but does not cover functional insufficiency and task consequence |
| ISO 15817 | Remote operator control systems for earth-moving machinery | Supports remote control and operator responsibility but needs extension to remote supervision, authority transfer and operational monitoring |
| ISO 21815 | Collision warning and collision avoidance for earth-moving machinery | Supports proximity risk but does not cover material interaction, task quality and production continuity |
| ISO 18497-1:2024 | Design principles and vocabulary for partly automated, semi-autonomous and autonomous functions in agricultural machinery and tractors | Adjacent non-road autonomy signal, not an engineering-vehicle compliance standard |
| Chinese robot SOTIF project | ODD, scenario, triggering condition, functional insufficiency, risk evaluation and mitigation entering robot standardization language | Mobile physical AI standardization signal, not a published engineering-vehicle standard |
| GMG autonomous mining guidance | Autonomous mining, operational readiness, change management and safety-case language | Mining-operations oriented; needs transfer to loading, trenching, piling, hold cleaning and solar-construction tasks |

## Priority Recommendations

### Recommendation 1: SOTIF Implementation Guide for Autonomous Engineering Vehicles

Recommended positioning:

A SOTIF method guide for autonomous engineering vehicles and mobile working machine systems.

Recommended scope:

1. Terms: MWMS, WTDC, DMWT, functional insufficiency, triggering condition, task consequence and minimal-risk state.
2. Scenarios: worksite, material, tool, people, cooperating equipment, remote supervision and recovery conditions.
3. Risk chain: functional insufficiency → triggering condition → hazardous event/task failure → consequence → mitigation.
4. Evidence: simulation, closed-site tests, vehicle tests, operational monitoring, near misses and safety cases.

Why it matters:

The Chinese robot SOTIF project shows that SOTIF methods are moving from road vehicles toward mobile physical AI. Engineering vehicles have clearer industrial scenarios and test objects, making them suitable for a more concrete industry guide or group standard.

### Recommendation 2: Worksite and Task Design Conditions for Autonomous Engineering Vehicles

Recommended positioning:

Define WTDC as the worksite-task counterpart of road-vehicle ODD.

Recommended scope:

1. Site types: mine, port, batching plant, construction site, solar field, vessel hold, testbed and lunar-analogue site.
2. Terrain and material: slope, low adhesion, dust, stockpile, trench, embankment and unknown material.
3. People and assets: workers, bystanders, human-operated equipment, trucks, conveyors, fixed infrastructure and exclusion zones.
4. Operating constraints: communication, localization, map, energy, lighting, weather, dispatch and supervision.
5. Prohibited conditions: outside WTDC, supervision unavailable, localization drift, exclusion-zone failure and unavailable recovery path.

Why it matters:

Without WTDC, testing organizations and enterprises tend to write generic site descriptions that cannot support repeatable scenario libraries or safety evidence.

### Recommendation 3: Dynamic Moving and Working Task Classification

Recommended positioning:

Define DMWT as the engineering-work counterpart of road-vehicle DDT.

Recommended scope:

1. Movement tasks: forward motion, reversing, turning, V-shaped cycle, ramp, obstacle avoidance, following and platooning.
2. Work tasks: digging, loading, dumping, hauling, piling, trenching, compacting, hold cleaning, breaking and material transfer.
3. Task quality: fill rate, dumping deviation, trench depth, pile position, compaction and surface flatness.
4. Recovery tasks: slowdown, stop, emergency stop, remote confirmation, remote driving, on-site takeover, evacuation and retest.

Why it matters:

The distinctive feature of engineering vehicles is work. Without DMWT, standardization can retreat into collision avoidance, emergency stops and remote control, missing real product value.

### Recommendation 4: Testing, Evaluation and Operational Monitoring Requirements

Recommended positioning:

Define test records, operational monitoring, near misses and safety-case evidence fields.

Recommended scope:

1. Six consequence classes: human safety, assets and infrastructure, production continuity, task quality, environment and resources, recoverability.
2. Test record: machine_type, worksite_type, task_type, WTDC, DMWT, trigger_condition, insufficiency, consequence, mitigation and evidence.
3. Operational monitoring: low confidence, OOD, remote-supervision request, human takeover, MRC, task-quality deviation and near miss.
4. Feedback mechanism: operational anomalies should feed back into taxonomy, risk chain and safety case.

Why it matters:

This is closest to testing organizations and enterprise engineering practice. It can become a group standard, testing guideline or public template first.

### Recommendation 5: Safety Case Guide for Autonomous Engineering Vehicles

Recommended positioning:

Define a safety argumentation structure from development and testing to operation.

Recommended scope:

1. Claim: the system is acceptably safe within defined WTDC/DMWT.
2. Argument: combine functional safety, SOTIF, cybersecurity, AI safety, machine safety, operational monitoring and organizational processes.
3. Evidence: standard conformity, simulation, closed-site test, vehicle test, operation log, near miss, fault recovery and human review.
4. Assumption: site boundary, supervision capability, communication quality, maintenance state and personnel responsibility.
5. Limitation: outside WTDC, unverified tasks, unauthorized retrofit and undefined cooperating systems.

Why it matters:

Safety cases connect manuscripts, testing and standardization, and they fit enterprise product safety review and third-party assessment.

## Recommended Roadmap

| Phase | Time | Goal | Output |
|---|---|---|---|
| Phase 0 | 2026-06 to 2026-07 | Complete public white paper and expert-discussion material | Standardization opportunity analysis, glossary and WTDC/DMWT draft |
| Phase 1 | 2026-07 to 2026-09 | Build a group-standard pre-research package | Proposal, scope, standard framework, clause skeletons and sample scenarios |
| Phase 2 | 2026-09 to 2026-12 | Select one minimum deployable standard topic | Recommended first topic: testing/evaluation and operational monitoring requirements, or SOTIF implementation guide |
| Phase 3 | 2027-H1 | Pilot with enterprise cases and testing organizations | Sample test records, near-miss template and safety-case examples |
| Phase 4 | 2027-H2 onward | Transfer to higher-level standardization | Industry standard, national-standard pre-research and ISO/IEC/SAE/IEEE discussion material |

## Minimum Viable Standardization Package

If only one standardization output can be prioritized, the recommended topic is:

Testing, Evaluation and Operational Monitoring Requirements for Autonomous Engineering Vehicles

Reasons:

1. Easier to deploy than a general safety-assurance standard.
2. Easier to connect with testing organizations and enterprise test systems than a broad SOTIF guide.
3. Naturally includes WTDC, DMWT, SOTIF risk chains and safety-case fields.
4. Can grow through sample tasks for loaders, excavators, haulage trucks, solar piling and hold-cleaning robots.

Suggested chapters:

1. Scope.
2. Normative references.
3. Terms and definitions.
4. General principles.
5. Worksite and Task Design Conditions.
6. Dynamic Moving and Working Task.
7. Scenario classification and triggering conditions.
8. Testing and evaluation metrics.
9. Operational monitoring and near-miss records.
10. Safety-case evidence requirements.
11. Annex A: test-record template.
12. Annex B: sample tasks.
13. Annex C: evidence classes and public boundaries.

## Expressions to Avoid

1. Do not claim that engineering vehicles have no standards.
2. Do not claim that road-vehicle standards directly apply to engineering vehicles.
3. Do not describe ISO 18497-1:2024 as an engineering-vehicle compliance basis.
4. Do not describe the robot SOTIF project as a published engineering-vehicle standard.
5. Do not use company public pages or demonstration videos as safety-certification evidence.
6. Do not write thresholds, ratios or KPIs as universal industry requirements without authorized standards, test data or expert consensus.

## Relation to Safety Development, Papers and Website

Standardization is not an appendix after the papers. It is one of the core outputs of AEV Safety. More precisely, standardization should grow out of safety-development practice and product pilots, then be distilled through papers and the website into public technical language.

The recommended output chain has four mutually reinforcing tracks:

1. Safety-development practice: turn MWMS, WTDC, DMWT, SOTIF-oriented risk chains, test records, operational monitoring and safety cases into enterprise engineering workflows.
2. Engineering product deployment: calibrate operating boundaries, task-quality criteria, recovery logic and field evidence in loader, excavator, haulage, piling/trenching and construction-robot pilots.
3. Paper and review outputs: use the Chinese review and English methodology paper to explain the problem landscape, method transfer and risk-assessment framework.
4. Standardization pre-research package: turn the engineering workflow into candidate terms, scenarios, testing, operational monitoring and safety-case clause skeletons.
