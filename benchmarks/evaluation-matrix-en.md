# AEV Safety Evaluation Matrix v1.0

[中文](evaluation-matrix.md)

## Positioning

This matrix defines metric families that should be recorded for autonomous engineering-vehicle safety evaluation. It is not a fixed threshold table. Thresholds must be calibrated for specific machines, sites, tasks and regulatory environments. This repository provides metric structure, record fields and evidence use.

## Six Consequence Categories

| Consequence category | Description | Typical metrics |
|---|---|---|
| Personnel safety | Exposure of workers, drivers, maintenance staff and bystanders | Minimum distance, intrusion count, emergency-stop trigger, missed person detection |
| Asset and infrastructure | Damage to vehicles, attachments, fixed facilities, trucks, hoppers and conveyors | Collision, contact force, asset damage, exclusion-zone violation |
| Production continuity | Schedule, rhythm, downtime and recovery | MTTR, task interruption, recovery time, manual-intervention rate |
| Task quality | Fill rate, unloading accuracy, trench depth, pile position, flatness | Deviation, rework rate, spillage rate, quality-failure rate |
| Environment and resources | Energy, spillage, dust, replenishment and material waste | Energy per task, material loss, environmental anomaly |
| Recovery capability | Ability to stop, evacuate, recover or repair after faults | MRC success, recovery path, supervisor response, on-site handling time |

## Metric Families

### 1. Worksite-boundary metrics

- WTDC completeness: whether site type, terrain, material, attachment, personnel area, exclusion zone, communication, localization and supervision are declared.
- Map freshness: update frequency for site map, stockpile boundary, unloading point, obstacle and exclusion zone.
- Infrastructure health: communication quality, localization quality, dispatch system, emergency stop, barrier and warning system status.

### 2. Perception and semantic metrics

- Recall and false-positive rate for people, equipment, stockpiles, truck bodies and trenches.
- Trigger-condition logs for low confidence, OOD, occlusion, dust, night, rain/snow and glare.
- Time from perception failure to safe degradation.

### 3. Mobility and path metrics

- Path-tracking error reported by task tolerance, not only road-style lateral deviation.
- Speed, acceleration, articulation angle, turning radius, reversing distance and minimum safety distance.
- V-cycle path length, cycle time and path-conflict count.

### 4. Work-equipment and material metrics

- Bucket/attachment pose error, entry angle, unloading height, tool speed, force/pressure limit.
- Fill rate, spillage rate, dumping deviation, trench-depth deviation, pile-position deviation and compaction quality.
- Tool anomaly, hydraulic shock, slip, blockage, pile collapse and task failure.

### 5. Supervision and recovery metrics

- Remote-supervision request rate, response time, confirmation quality and misconfirmation rate.
- Automated degradation, MRC execution, manual takeover, on-site handling and recovery time.
- Authority-transfer record among autonomous, remote supervision, remote driving, on-site manual and maintenance modes.

### 6. Safety-case metrics

- Whether each claim has evidence, assumptions, limitations and failure samples.
- Whether each pass criterion connects to WTDC, DMWT and consequence categories.
- Whether each operational anomaly can be fed back into scenario taxonomy, trigger condition, functional insufficiency and mitigation.

## Test Record Template

| Field | Description |
|---|---|
| machine_type | Loader, excavator, haulage truck, piling machine, trencher, hold-cleaning robot |
| worksite_type | Mine, batching plant, port, construction site, solar site, test site, lunar analogue |
| task_type | Digging, loading, unloading, hauling, piling, trenching, compacting, cleaning, recovery |
| WTDC | Terrain, material, weather, communication, localization, supervision, personnel area, exclusion zone |
| DMWT | Mobility action, work-equipment action, task-quality action, recovery action |
| trigger_condition | Dust, occlusion, low adhesion, communication degradation, localization drift |
| insufficiency | Material recognition insufficiency, tracking insufficiency, unloading-point insufficiency |
| consequence | One or more of the six consequence categories |
| mitigation | Slowdown, emergency stop, degradation, remote confirmation, replanning, manual takeover |
| evidence | Simulation, closed-course test, vehicle test, operational log, human review |

## Boundary

This matrix does not declare universal safety thresholds. Thresholds must be determined by specific machine, site, task, authorized standard, test data and stakeholder consensus.
