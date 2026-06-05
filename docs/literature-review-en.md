# AEV Safety Literature Review and Research Landscape

[中文](literature-review.md)

## Purpose

This file is the public literature-review entry point for AEV Safety. It does not replace the manuscript or authorized standards. Its role is to organize the research landscape into actionable directions so researchers, engineers, testing organizations and standardization experts can judge which methods can be transferred, which evidence remains weak and which problems deserve deeper research and engineering validation.

## 1. Road-Vehicle Safety Methods as Donors

Road-vehicle safety methods are useful not because their labels can be reused, but because they provide mature problem structures.

ISO 26262 provides a functional-safety lifecycle, hazard analysis, functional safety concepts, technical safety concepts, verification and validation. ISO 21448 provides the SOTIF vocabulary for unreasonable risk caused by functional insufficiencies, triggering conditions and incomplete scenario coverage in the absence of faults. ISO 34502 provides a scenario-based safety-evaluation framework. ISO/PAS 8800 provides a public entry point for road-vehicle AI safety assurance. ISO/SAE 21434 provides a cybersecurity engineering structure for connected systems, remote operation, cloud platforms and software updates.

For AEV Safety, these methods can be transferred as follows:

| Road-vehicle method | Transferable structure | Required reformulation |
|---|---|---|
| Functional safety | Lifecycle, failure analysis, verification and validation | ASIL cannot be directly mapped to engineering-machinery control-system levels |
| SOTIF | Functional insufficiency, triggering condition, known and unknown unsafe scenarios | ODD and dynamic driving task must be extended into WTDC and DMWT |
| Scenario testing | Functional, logical and concrete scenario layers | Road-traffic ontologies do not describe stockpiles, dumping, trenching or piling |
| AI safety | AI lifecycle, data, model, verification and monitoring | Must be connected to physical work, work equipment and task quality |
| Cybersecurity | Assets, threats, attack paths, software updates and operational monitoring | Must cover remote supervision, dispatch systems and worksite infrastructure |

## 2. Earth-Moving Machinery and Autonomous Mining

The field is not a standards vacuum. ISO 17757, ISO 19014, ISO 15817, ISO 21815 and GMG autonomous-mining guidance already address autonomous and semi-autonomous machine systems, safety-related control systems, remote control, collision warning and avoidance, operational readiness, change management and safety cases.

The main lessons for AEV Safety are:

1. The assurance object should not be a single vehicle only. It should include the machine, operating zone, organization, remote control, supervision and maintenance.
2. Automation capability must be discussed together with site rules, authority transfer, segregation measures and emergency response.
3. Collision risk is only one part of engineering-vehicle risk. Task quality, asset damage, production interruption and recoverability also matter.
4. Public standard status pages and catalogue pages can support status and scope claims, but clause-level mapping requires authorized standard text.

## 3. Wheel Loaders, Excavators and Autonomous Work Loops

Autonomous wheel-loader material is one of the most important engineering backgrounds for this project. It shows that an autonomous loader work loop includes at least:

- Stockpile and work-object perception.
- Digging-point selection and digging strategy.
- Bucket attitude, boom trajectory, entry angle and hydraulic control.
- Bucket fill-rate measurement and task-quality assessment.
- Dumping-object recognition, dumping-point selection and dumping motion control.
- V-shaped work-cycle path planning, reversing, articulated steering and path tracking.
- Indoor/outdoor tests, front-fit or retrofit interfaces and site operations.

These problems show why engineering-vehicle safety evaluation must cover both movement and work equipment. A path-planning algorithm passing a test does not prove that digging, loading, dumping, task quality and recoverability are safe.

## 4. Construction Systems of Systems and Semi-Automated Sites

Construction sites usually operate as a System of Systems (SoS), rather than as single-robot environments. Unmanned ground vehicles, UAVs, automatic haulers, manually operated loaders, remote-control equipment, site servers, fleet-control systems, site operators and remote supervisors may work in the same site.

The key contributions of construction System of Systems (SoS) safety literature are:

- It highlights state consistency, communication delay and dispatch conflicts among cooperating equipment.
- It shows the value of STPA, control structures and state transitions for dynamic system combinations.
- It explains why single-system hazard analysis is often insufficient for remote supervision, multi-machine cooperation and temporary site changes.
- It encourages AEV Safety to treat authority transfer, mixed human-machine operation, remote confirmation and recovery workflows as core evaluation objects.

## 5. Mobile Physical AI and Robot SOTIF

Mobile physical AI safety materials place engineering vehicles in a broader mobile-robot safety context. Robot SOTIF standardization signals show that ODD, scenarios, triggering conditions, functional insufficiencies, risk evaluation and mitigation are becoming shared language for mobile physical AI.

Physical interaction safety materials add speed, distance, force, energy, stability and human-machine shared-space concerns. VLA and LLM decision-safety materials suggest that future engineering vehicles may face semantic task planning, long-horizon decisions, hallucination, OOD behavior, reward shift and runtime Guardian problems.

AEV Safety uses this strand with three boundaries:

1. Robot and foundation-model materials can inspire methods.
2. General robot research cannot be presented as field validation for engineering vehicles.
3. AI behavior risk must be grounded in WTDC, DMWT, triggering conditions, mitigations and evidence records.

## 6. Planetary Resource Operations as Extreme Extrapolation

The `Move the Earth and Beyond` material connects terrestrial construction, mining automation and lunar or Mars resource operations. This direction is not used to claim that space mining is commercially mature. It is used as an extreme stress test for mobile working-machine safety.

Planetary resource operations amplify:

- Communication delay, low bandwidth and non-instant supervision.
- Energy, maintenance and spare-part constraints.
- Uncertain terrain, material, lighting, temperature and radiation conditions.
- Longer multi-machine task chains and higher recovery cost after failure.
- Lower human presence but higher asset, mission and system-recovery risk.

AEV Safety therefore treats planetary resource operations as an extrapolation for framework generality, not as a compliance basis for current terrestrial engineering vehicles.

## 7. From Literature Strands to AEV Safety Modules

The AEV Safety review does not leave each literature strand as generic related work. It converts them into modules that can be discussed, reviewed and advanced collaboratively.

| Literature or material strand | AEV Safety module | Current treatment |
|---|---|---|
| Road-vehicle methods such as ISO 21448, ISO 34502 and ISO/PAS 8800 | SOTIF risk chain, scenario layers, AI safety lifecycle and safety-case argumentation | Used as method donors; road ODD, DDT and ASIL are not copied directly |
| ISO 17757, ISO 19014, ISO 15817, ISO 21815 and GMG guidance | MWMS boundary, remote control, collision warning/avoidance, operational readiness and change management | Used as the machinery and mining autonomy base; clause-level mapping awaits authorized text |
| The SUCCESS semi-automated-site project and System of Systems (SoS) safety literature | SoS hazard analysis, safety arguments, digital twin, dynamic risk management and geofences | Supports the five-layer reference architecture, operational monitoring and dynamic safety-case updates |
| Autonomous loader work-loop materials | Stockpile perception, digging-point selection, bucket fill rate, dumping point, V-shaped path and front-fit/retrofit boundary | Supports DMWT and the task-quality consequence matrix |
| Mobile physical AI evaluation-platform material | Human-like Mobility Reference Model (HMRM), Human-like Mobility Behaviour (HLMB), safety/smoothness/efficiency | Used as cross-embodiment evaluation inspiration, not as a replacement for engineering-vehicle task-quality evaluation |
| Robot SOTIF standardization signal | ODD, scenario, triggering condition, functional insufficiency, risk evaluation and mitigation | Treated as a mobile physical AI safety standardization trend, not as a published engineering-vehicle standard |

This mapping also explains the repository structure: `taxonomy/` handles WTDC and DMWT, `architecture/` handles the assurance object and evidence flows, `benchmarks/` handles consequence classes and evaluation fields, `standards/` handles the standards landscape and candidate roadmap, and `paper/` consolidates the modules into manuscript drafts.

## 8. Research Gaps

The most important gaps to deepen are:

| Gap | Description | Possible direction |
|---|---|---|
| WTDC formalization | Existing ODD formats do not capture material, attachment, site organization and task quality | Build a machine-readable WTDC schema |
| DMWT scenario library | Engineering vehicles lack work-task-level scenario libraries | Start from loading, dumping, trenching, piling and hold-cleaning tasks |
| Task quality as safety evidence | Quality deviation and production interruption are often excluded from safety evaluation | Build a combined safety, quality and recoverability consequence matrix |
| Runtime Guardian | AI decisions and work-equipment control need runtime constraints | Combine OOD detection, low-confidence handling, control barrier functions and minimal-risk states |
| Remote-supervision workload | Multi-machine systems can turn supervisors into safety bottlenecks | Measure request rate, response time and false confirmation |
| Safety-case templates | Engineering vehicles lack WTDC/DMWT-oriented argument templates | Define claims, arguments, evidence and limitations |

## 9. Future Literature Work

Future work should continue along three tracks:

1. Authorized standards review: move from status-level mapping to clause-level mapping.
2. Peer-reviewed literature expansion: systematically search construction robotics, autonomous mining, earth-moving machinery, STPA, System of Systems (SoS) safety and runtime assurance.
3. Anonymized engineering cases: turn real failure samples from loaders, excavators, haulage trucks and construction robots into public, reviewable and discussion-ready safety cases.
