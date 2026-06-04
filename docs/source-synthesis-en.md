# Source Synthesis and Evidence Boundaries

[中文](source-synthesis.md)

## Purpose

This file records the key materials absorbed by AEV Safety, the technical strands that can be used publicly, and the evidence boundaries that must be maintained. It is not a substitute for full references and does not publish internal materials. Its role is to convert scattered inputs into structured questions for the manuscript, website, standards proposals and engineering practice.

## 1. Li Xuefei's Autonomous Construction-Machinery Materials

Li Xuefei's materials provide a clear engineering starting point: a wheel loader is not merely a vehicle that moves. It is a mobile working machine with work equipment, material interaction and cyclic task objectives.

| Technical strand | Relevance to AEV Safety |
|---|---|
| Autonomous digging-point selection | The perception object includes material-pile shape, digging position, material state and task quality, not only obstacles |
| Autonomous digging strategy | Work-equipment trajectory, bucket pose, entry angle, energy consumption and fill rate become coupled safety and productivity constraints |
| Bucket fill-rate measurement | Supports task-quality consequences; safety and acceptance cannot be reduced to collision avoidance |
| Autonomous unloading-point selection | Unloading safety depends on truck body, hopper, container edge, bucket pose and dumping action |
| V-shaped work-cycle path planning | Loader planning is not lane keeping; it is a cyclic dig-haul-dump task |
| Path tracking control | Supports DMWT constraints such as articulated pose, turning radius and tracking error |
| Indoor and outdoor vehicle tests | WTDC must distinguish indoor, outdoor, stockyard, batching plant, mine and port conditions |
| Front-fit and retrofit productization | Safety cases must separate complete-machine development, retrofit integration, low-level controller interface and third-party responsibility |

Public-use boundary:

- It is appropriate to state that internal technical materials indicate a closed loop involving perception, planning, work-equipment control, material-state estimation and task-quality assessment.
- Do not publish unverified commercial forecasts, costs, customer lists, financing plans, team photos or commercially sensitive details.
- Do not use internal materials as proof of certification, product maturity, safety performance or market share.

## 2. Move the Earth and Beyond

The `Move the Earth and Beyond` material extends AEV Safety from terrestrial construction machinery to planetary resource operations. Its value is not to claim that space mining is mature, but to stress-test the safety framework under extreme mobile-work conditions.

Absorbed strands:

1. Terrestrial autonomous construction and mining work: loaders, excavators, haulage vehicles, unmanned earthwork tasks, worksite planning and dispatch.
2. Safety system engineering: task definition, system architecture, safety system, operational safety, risk management and standard/patent planning.
3. Built Robotics safety mechanisms: geofence, safety barriers, audible warnings, high-visibility lights, wireless and hardwired emergency stops, bystander awareness and cloud monitoring.
4. 5 x 8 test-site design: hold cleaning, material transfer and future exploration scenarios involving excavation/blasting, loading, transport, refining, rovers, robot dogs, UAVs, solar power and 3D printing.
5. NASA/DLR/space-resource reference chain: lunar and Mars resource operations involve extreme terrain, low gravity, vacuum, temperature, radiation, energy limits, communication limits and remote supervision.

How this enters AEV Safety:

- The architecture includes an Earth-to-extreme-environment-to-planetary-resource transfer path.
- The taxonomy includes energy/communication limitation, remote-supervision delay, unknown terrain, unknown material and multi-machine cooperation.
- The evaluation matrix includes task quality, recovery capability, remote-supervision load and environmental/resource consequences.

## 3. Construction and Mining Autonomy Literature

The reviewed materials show that construction autonomy is not single-vehicle automation. Unmanned ground, surface and underwater vehicles, UAVs, automated transporters, remote-controlled equipment and human-operated machines may operate in the same work system.

Core synthesis:

- The 2018 construction unmanned-vehicle review shows that UAVs have broad construction use, while UGV/USV/UUV potential remains underdeveloped.
- The SUCCESS report emphasizes safety assurance of cooperating construction equipment in semi-automated sites.
- System-of-systems safety analysis materials show that conventional hazard analysis is strained by dynamic system composition, remote control, communication delay and state inconsistency.
- STPA and Petri-net extensions indicate that engineering-vehicle safety analysis should model control structure, state transition, timing constraints and inter-system inconsistency.
- Volvo Electric Site/HX-type cases illustrate a safety object consisting of autonomous transporters, human-operated loaders, site servers, fleet control, remote operators and site operators.

Direct contribution:

- The assurance object is MWMS, not a single vehicle.
- WTDC must include communication, dispatch, remote control, site personnel, mixed human/automated work and infrastructure status.
- The safety case must argue not only vehicle safety, but also interface safety, authority transfer, degradation and recovery in the work system.

## 4. General Mobile Physical AI Safety

Embodied AI safety, physical interaction safety and LLM/VLA decision safety broaden the AEV Safety problem into mobile physical AI.

| Material strand | Transfer to AEV Safety |
|---|---|
| Robot SOTIF | Aligns with the SOTIF chain: ODD/scenario, trigger condition, functional insufficiency, hazard, risk evaluation and mitigation |
| Physical interaction safety | Adds force, energy, distance, speed and stability considerations for contact with humans, materials, tools and infrastructure |
| LLM/VLA decision safety | Supports task planning, semantic understanding, long-horizon decision risk, hallucination, OOD, runtime guardian and fallback |
| ISO/PAS 8800 transfer | Supports AI component lifecycle thinking, but does not replace field validation for engineering vehicles |

## 5. Evidence Classes

| Class | Supports | Limitation |
|---|---|---|
| A-FULL | Authorized standards, regulations and full peer-reviewed papers | Clause-level or research conclusions within source scope |
| B-OFFICIAL | Official status pages, official project pages and company pages | Status, scope and public project description only |
| C-PUBLIC | Press releases, videos, public demos and job posts | Scenario anchors, not safety-performance evidence |
| D-INTERNAL | Business plans, project decks, internal discussion and unpublished interviews | Background inputs only unless independently verified |

## 6. AEV Safety Synthesis

AEV Safety should be organized around six questions:

1. Machine-system boundary: how vehicle, work equipment, attachment, material, site and supervision system are defined together.
2. Worksite-task boundary: how WTDC replaces a simple road-vehicle ODD.
3. Dynamic working task: how DMWT represents movement, work and recovery.
4. SOTIF risk chain: how insufficiency, trigger condition, hazardous event and task consequence connect.
5. Evaluation evidence: how testing matrix, operational monitoring, task-quality consequence and recovery capability are recorded.
6. Standardization path: how road-vehicle safety methods transfer to engineering vehicles, robots and planetary resource work.
