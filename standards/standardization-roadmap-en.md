# AEV Safety Standardization Roadmap

[中文](standardization-roadmap.md)

## Purpose

This roadmap is written for standardization discussions on autonomous engineering vehicles, mobile working-machine systems and mobile physical AI. It is not a current standard requirement or a formal proposal to any standards organization. It translates the AEV Safety framework into modules that could enter association standards, industry standards, national standards or enterprise technical specifications.

## Standardization View

The standardization problem is not to build a completely separate system from zero. A more realistic route is to connect existing standards:

- Use engineering-machinery standards for the machine, work equipment and safety-related control systems.
- Use road-vehicle SOTIF and scenario-testing methods for functional insufficiencies, triggering conditions and scenario coverage.
- Use AI safety methods for data, models, AI output insufficiencies and runtime monitoring.
- Use mining and construction safety guidance for operating zones, organizational measures, remote supervision and change management.
- Use robotics and mobile physical AI standardization signals for shared workspaces, physical interaction and autonomous decision-making.

## Candidate Standard Modules

| Module | Recommended content | Main output |
|---|---|---|
| 1. Scope and object | Define the object as MWMS rather than a single vehicle or AI model | Applicable machines, sites, tasks and exclusions |
| 2. Terms | MWMS, WTDC, DMWT, task consequence, supervision mode, recoverability | Bilingual terminology |
| 3. Worksite and task declaration | Terrain, material, attachment, human zone, exclusion zone, communication, localization and supervision | WTDC declaration template |
| 4. Dynamic work task | Movement, work equipment, material interaction, task quality and recovery actions | DMWT task template |
| 5. SOTIF risk chain | Functional insufficiency, triggering condition, hazardous event, task consequence and mitigation | Risk-chain table and scenario library |
| 6. Testing and evaluation | Simulation, closed site, field test, fault injection and mixed human-machine operation | Scenario matrix and pass criteria |
| 7. Operational monitoring | Near misses, takeover, degradation, recovery and task-quality deviation | Runtime data fields and event taxonomy |
| 8. Safety case | Claims, arguments, evidence, assumptions and limitations | Safety-case template |

## Candidate Terms

| Abbreviation | Chinese | English | Meaning |
|---|---|---|---|
| MWMS | 移动作业机器系统 | Mobile Working Machine System | Assurance object composed of vehicle, work equipment, attachment, material, site, supervision and organization |
| WTDC | 作业场地与任务设计条件 | Worksite and Task Design Conditions | Extension of ODD for engineering-work boundaries |
| DMWT | 动态移动与作业任务 | Dynamic Moving and Working Task | Extension of DDT for movement, work and recovery loops |
| Task consequence | 作业后果 | Task consequence | Consequences covering people, assets, quality, production, environment and recovery |
| Runtime Guardian | 运行时安全守护 | Runtime Guardian | Runtime constraints and degradation for AI, control and task quality |

## Clause Skeletons to Prioritize

### 1. WTDC Declaration

Each autonomous engineering-vehicle system should declare before testing and deployment:

- Site type, map boundary, exclusion zones and human activity zones.
- Terrain, slope, load-bearing capacity, low adhesion, dust, occlusion and visibility.
- Material type, particle size, moisture, stockpile shape, diggability or processability.
- Tools, attachments, work equipment and task modes.
- Communication, localization, dispatch, emergency stop, barriers, warnings and remote-supervision conditions.
- Conditions in which operation is not allowed and exit criteria.

### 2. DMWT Decomposition

Each task should be decomposed into movement, work-equipment actions, material interaction, quality judgement and recovery actions. A loader cycle, for example, can be decomposed into approach, stockpile recognition, digging-point selection, digging, fill-rate judgement, reversing and turning, dumping-object alignment, dumping, returning and recovery.

### 3. SOTIF Risk Chain

Each safety-relevant scenario should record:

```text
WTDC / DMWT
  -> functional insufficiency
  -> triggering condition
  -> hazardous event
  -> task consequence
  -> mitigation
  -> evidence
```

### 4. Operational Monitoring

Operational monitoring should record more than collisions and emergency stops:

- Low confidence, OOD, localization degradation and communication degradation.
- Path-tracking error, bucket or tool pose error and task-quality deviation.
- Remote-supervision requests, response time, confirmation result and false confirmation.
- Minimal-risk-state execution, recovery path, site response and retest result.

## Phased Roadmap

| Phase | Goal | Output |
|---|---|---|
| Phase 1 | Align language and scope | Terminology, WTDC/DMWT templates and initial taxonomy |
| Phase 2 | Establish testing structure | Scenario matrix, metric families and failure-sample records |
| Phase 3 | Build standard proposal draft | Standard outline, clause skeleton and reference-standard mapping |
| Phase 4 | Validate with companies and sites | Anonymized cases, runtime log fields and safety-case examples |
| Phase 5 | Public standardization process | Association or industry draft, workshop material and public-comment draft |

## Evidence Boundary

As of 2026-06-05, this public repository uses standard status pages, public catalogues, official project pages and public company pages only as status and scope evidence. Clause-level interpretation, compliance judgement and certification claims must rely on authorized standard text, formal test reports and field-operation evidence.
