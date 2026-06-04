# AEV Safety Worksite and Task Taxonomy v1.0

[中文](worksite-task-taxonomy-v1.0.md)

## Overview

This taxonomy describes safety-relevant scenarios for autonomous engineering vehicles and mobile working-machine systems. It is not a direct rewrite of road-vehicle scenario taxonomies. It is built around MWMS, WTDC and DMWT.

Goals:

1. Support scenario-driven analysis in the manuscript.
2. Help testing organizations design scenario matrices.
3. Help companies convert field problems into recordable, reproducible and reviewable safety evidence.
4. Support standardization discussions about what conditions must be declared and what consequences must be evaluated.

## Top-Level Categories

| Code | Category | Typical issue | Main evidence |
|---|---|---|---|
| A | Worksite and infrastructure | Site boundary, exclusion zone, slope, ground bearing, communication, localization, energy | WTDC statement, site map, communication log, localization quality |
| B | Perception and semantic understanding | Stockpile, truck body, trench, slope, person, vehicle, obstacle, marker | Perception log, labeled data, confidence, failure cases |
| C | Mobility and path control | V-shaped cycle, reversing, articulated steering, narrow encounter, ramp, low adhesion | Tracking error, speed, pose, MRC trigger |
| D | Work equipment and material interaction | Digging, unloading, trenching, piling, compacting, crushing, hold cleaning | Tool pose, force/energy, fill rate, quality deviation |
| E | People, assets and cooperating equipment | Worker entry, bystander, truck, conveyor, lifting equipment, human-operated vehicle | Separation distance, emergency stop, warning, coordination log |
| F | Supervision, dispatch and recovery | Remote supervision, task dispatch, communication loss, authority transfer, fault recovery | Supervision log, takeover log, recovery time, responsibility matrix |
| G | Extreme and planetary resource work | Lunar/Mars terrain, low gravity, energy constraint, long delay, multi-machine work | Simulation, test site, extreme-environment test, task-level safety case |

## A. Worksite and Infrastructure

### A1 Incomplete worksite boundary declaration

The site map, exclusion zones, traversable areas, dumping zones, stockpile boundaries or hazardous areas are incomplete or stale. Consequences include unauthorized entry, entry into personnel areas, infrastructure collision and production disruption.

### A2 Communication or dispatch infrastructure degradation

Wireless network, dispatch server, remote-supervision system, localization base station or edge-computing node degrades. This may not cause an immediate collision, but it affects task allocation, supervision, logging, emergency stop and recovery.

### A3 Localization infrastructure unavailable or drifting

GNSS, RTK, SLAM, UWB, vision localization or site-map matching degrades. Engineering vehicles often operate across indoor/outdoor transitions, occlusion, dust, metallic structures and changing stockpiles. Localization drift affects path tracking and unloading/digging accuracy.

## B. Perception and Semantic Understanding

### B1 Insufficient material-pile state recognition

The system fails to recognize pile height, slope, particle size, moisture, looseness, convexity or diggable location. Consequences include low fill rate, high energy consumption, wheel slip, bucket impact, pile collapse or unstable operation.

### B2 Insufficient unloading-target recognition

The system fails to recognize truck body, hopper, container edge, unloading height, dumping point or obstacle. Consequences include misdumping, spillage, collision, body damage or task interruption.

### B3 Insufficient people and bystander recognition

The system fails to recognize workers, inspectors, drivers, bystanders, reflective-clothing cases or occluded persons. These scenarios must connect to speed and separation monitoring, emergency stop, audible/visual warning and remote supervision.

## C. Mobility and Path Control

### C1 V-shaped work-cycle path planning failure

Loader cycles are not lane following. The dig-reverse-turn-dump-return cycle can fail through excessive path length, insufficient turning radius, high articulation angle, equipment conflict or poor production rhythm.

### C2 Tracking error beyond task tolerance

Tracking error affects not only mobility safety but also digging point, dumping point and tool pose. It should be recorded by task tolerance, not only road-style lateral deviation.

### C3 Stability insufficiency on low-adhesion or complex terrain

Wet surfaces, gravel, slopes, trenches and lunar/Mars-like loose terrain introduce slipping, rollover, bogging, tool loss and recovery difficulty.

## D. Work Equipment and Material Interaction

### D1 Digging-action insufficiency

The bucket entry point, angle, trajectory or speed is insufficient, causing low fill rate, tire slip, hydraulic shock, pile disturbance or equipment damage.

### D2 Unloading-action insufficiency

The dumping point, bucket height, vehicle pose, dumping speed or alignment is insufficient, causing spillage, collision, blockage, truck-body damage or quality deviation.

### D3 Task quality unacceptable

Trench depth, slope, pile position, compaction, flatness, loading amount or hold-cleaning residue fails the task requirement. AEV Safety treats task quality as a safety and acceptance consequence.

## E. People, Assets and Cooperating Equipment

### E1 Person enters machine working area

A worker, driver or bystander enters the working area, triggering stop, speed reduction, warning, remote confirmation or on-site handling.

### E2 Inconsistent cooperating-equipment state

Truck, conveyor, crusher, batching plant, loader, excavator or transporter states are inconsistent, causing dumping failure, dispatch conflict or dangerous proximity.

### E3 Human-operated and autonomous machines mixed

Semi-automated worksites often mix human-operated equipment and autonomous machines. Safety analysis must address authority, predictability, traffic organization and communication conventions.

## F. Supervision, Dispatch and Recovery

### F1 Remote-supervision load exceeds capacity

When multiple machines request confirmation, anomaly handling or task adjustment, supervisors may not respond in time. Evaluation should record request rate, response time, confirmation quality and automated degradation.

### F2 Authority transfer unclear

Unclear authority among autonomous mode, remote supervision, remote driving, on-site takeover and maintenance mode can cause duplicate commands, unclear responsibility or hazardous action.

### F3 Minimum risk condition and recovery path insufficient

For engineering vehicles, MRC is not always simple stopping. It may require lowering the work equipment, leaving a slope edge, releasing hydraulic pressure, preserving access, protecting material and notifying site personnel.

## G. Extreme and Planetary Resource Work

### G1 Energy and communication constrained

Lunar surfaces, Mars analogues, remote mines and large construction sites may have energy supply, bandwidth and latency constraints. The safety case should describe degradation under disconnection, low energy and delayed supervision.

### G2 Unknown terrain and material

Extreme environments involve high uncertainty in terrain, material and obstacles. Tests should cover unknown slopes, loose material, pits, rocks, low gravity or low-gravity-like operation conditions.

### G3 Multi-machine resource operation

Exploration, excavation, loading, hauling, refining, energy supply and fabrication machines work together. The safety object is the resource-operation system, not a single machine.
