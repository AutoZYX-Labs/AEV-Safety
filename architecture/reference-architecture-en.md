# AEV Safety Reference Architecture v1.0

[中文](reference-architecture.md)

## Positioning

This reference architecture describes the safety assurance object for autonomous engineering vehicles and mobile working-machine systems. It is not a product architecture and not a mandatory standard. It provides a layered framework that can be shared by papers, testing organizations, standardization proposals and engineering practice.

Principles:

1. Shift from single-vehicle safety to work-system safety.
2. Shift from driving behavior to a closed loop of movement and work.
3. Shift from collision avoidance to combined consequences: people, assets, task quality, production continuity, environment and recovery.
4. Shift from one-time testing to an evidence chain across design boundaries, simulation, vehicle tests, operational monitoring and safety cases.

## Five-Layer Architecture

```text
Layer 4  Safety Case and Standards Evidence
         claims, arguments, evidence, assumptions, limitations

Layer 3  Site Supervision and Operational Control
         dispatch, geofence, remote supervision, authority transfer, recovery

Layer 2  Task Autonomy and Runtime Safety Monitoring
         perception, planning, tool control, task-quality monitor, guardian

Layer 1  Machine Safety and Work-Equipment Control
         functional safety, emergency stop, safe stop, hydraulics, actuators

Layer 0  Worksite and Task Boundary
         WTDC, DMWT, material, terrain, people, assets, infrastructure
```

## Layer 0: Worksite and Task Boundary

Layer 0 defines the conditions under which the system is allowed to make safety claims. A worksite boundary is not only a geographic region. It should include:

- Site type: mine, batching plant, port, construction site, solar site, hold-cleaning site, lunar/Mars analogue site.
- Terrain: slope, trench, bearing capacity, low adhesion, loose material, gravel, low visibility.
- Material: sand, coal, ore, soil, concrete feedstock, lunar regolith simulant.
- Attachment: bucket, breaker, trencher, piling tool, sweeper, conveyor tool.
- Work object: stockpile, truck body, hopper, trench, pile location, hold-cleaning area, refining equipment.
- People and assets: workers, drivers, maintenance staff, bystanders, human-operated equipment and fixed infrastructure.
- Infrastructure: localization, communication, dispatch, charging, barriers, emergency stop and warning system.

Layer 0 outputs WTDC and DMWT statements. Without them, test results should not be generalized.

## Layer 1: Machine Safety and Work-Equipment Control

Layer 1 handles basic machine and work-equipment safety:

- Failure handling for braking, steering, propulsion, hydraulics, sensors, controllers and actuators.
- Safety limits for work equipment: speed, pressure, torque, motion envelope and emergency stop.
- Diagnosis, degradation and minimum-risk conditions for safety-related control systems.
- Interlocks for remote operation, manual takeover and maintenance.

Relevant methods include machinery safety, functional safety of control systems, ISO 19014-type frameworks and remote-control standards for earth-moving machinery.

## Layer 2: Task Autonomy and Runtime Safety Monitoring

Layer 2 is where AEV Safety differs most from conventional machinery safety. It addresses AI, perception, planning, control and task quality:

- Recognition of stockpiles, truck bodies, trenches, people and cooperating equipment.
- V-shaped path planning, reversing, articulated steering and narrow-site tracking.
- Digging-point selection, bucket trajectory, unloading-point selection and attachment pose control.
- Monitoring of fill rate, spillage, trench depth, pile position, compaction, hold-cleaning residue and other task-quality outputs.
- Runtime guardian for OOD, low confidence, trigger conditions, abnormal states and unsafe actions.

The purpose is not to make AI appear intelligent. The purpose is to make functional insufficiencies, trigger conditions and consequences recordable, reproducible and mitigable.

## Layer 3: Site Supervision and Operational Control

Layer 3 connects machines, people, dispatch systems and site management:

- Task assignment, route dispatch, production rhythm and cooperating-equipment state synchronization.
- Geofence, electronic boundary, warning lights, audible warning, signage, safety barrier and emergency stop.
- Remote supervision, remote confirmation, remote driving, on-site takeover and maintenance mode.
- Recovery after communication loss, localization degradation, low energy, tool anomaly, person entry or task failure.

Built Robotics' public safety mechanisms, safety-assurance research for cooperating construction equipment and Volvo Electric Site/HX-type System of Systems (SoS) cases all show that Layer 3 is central to engineering-vehicle safety.

## Layer 4: Safety Case and Standards Evidence

Layer 4 organizes lower-layer evidence into safety argumentation:

- Claims: the system is acceptably safe within specific WTDC and DMWT.
- Arguments: why testing, monitoring, degradation, supervision and recovery support those claims.
- Evidence: simulation, bench tests, closed-course tests, vehicle tests, operational logs, fault injection and human review.
- Assumptions: personnel separation, communication availability, material range, weather, supervisor capacity.
- Limitations: no generalization to untested sites, undeclared materials, unauthorized attachments or unverified mixed-traffic conditions.

Layer 4 also places ISO 26262, ISO 21448, ISO 34502, ISO/PAS 8800, ISO 17757, ISO 19014, ISO 15817, ISO 21815, ISO 18497-1 and robot SOTIF signals in the correct roles.

## Three Evidence Flows

| Evidence flow | Description | Typical output |
|---|---|---|
| Design evidence | Defines system boundary, hazards, insufficiencies and mitigations | HARA/STPA/SOTIF analysis, interface definition, WTDC/DMWT statement |
| Test evidence | Verifies scenario coverage through simulation, closed-course and vehicle tests | Scenario matrix, pass criteria, failure samples, regression tests |
| Operational evidence | Records deployed behavior and anomalies | Operational logs, near misses, takeover records, recovery records, quality deviation |

## Relation to Planetary Resource Work

Planetary resource work is not direct evidence for current engineering-vehicle standards, but it stress-tests the architecture. Lunar and Mars resource work amplifies:

- Communication delay and non-instant remote supervision.
- Limited energy and maintenance resources.
- Highly uncertain terrain, material and environmental states.
- Longer multi-machine task chains.
- Much higher recovery cost after failure.

AEV Safety therefore uses planetary resource work as an extreme extrapolation to test whether MWMS, WTDC, DMWT and safety-case structures are sufficiently general.
