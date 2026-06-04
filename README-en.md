# AEV Safety

Autonomous Engineering Vehicle Safety

[中文](README.md) | English

AEV Safety is an open research and standardization project for autonomous engineering vehicles and mobile working-machine systems. The project does not ask only whether a vehicle can drive without a human driver. It asks how wheel loaders, excavators, autonomous haulage trucks, trenching and piling machines, solar-construction robots and future planetary-resource machines can produce reviewable safety evidence under explicitly defined worksite, task, material, tool, human-machine interaction and remote-supervision conditions.

Website:

https://aev-safety.autozyx.com/

GitHub:

https://github.com/AutoZYX-Labs/AEV-Safety

## Positioning

Road-vehicle automation safety has a relatively mature methodological base: ISO 26262 functional safety, ISO 21448 SOTIF, ISO 34502 scenario-based testing, ISO/SAE 21434 cybersecurity engineering, ISO/PAS 8800 AI safety and safety-case argumentation. Autonomous engineering vehicles are moving into mines, ports, batching plants, construction sites, solar-construction sites and extreme environments. Their safety evidence, however, remains fragmented across machinery safety, functional safety of control systems, autonomous mining guidance, public company pages, construction automation research and site-specific operational rules.

The central claim of AEV Safety is:

The safety problem is not to copy automated-driving standards into construction machinery. The useful transfer is at the level of problem structure: system boundary, scenario, trigger condition, functional insufficiency, testing evidence, operational monitoring and safety argumentation.

## Three Core Concepts

| Abbreviation | Chinese | English | Role |
|---|---|---|---|
| MWMS | 移动作业机器系统 | Mobile Working Machine System | Treats the vehicle, work equipment, attachment, material, site infrastructure, supervision system and operational organization as one assurance object |
| WTDC | 作业场地与任务设计条件 | Worksite and Task Design Conditions | Extends road-vehicle ODD to terrain, material, loading and unloading points, exclusion zones, communication, supervision, weather and production constraints |
| DMWT | 动态移动与作业任务 | Dynamic Moving and Working Task | Extends road-vehicle DDT to movement, localization, digging, loading, unloading, compacting, piling, trenching, hauling and recovery actions |

## Why This Project Is Open

AEV Safety is published to attract broader attention and deeper work, not to treat publication as the only destination. Papers are one output. The more important goal is to move the problem into research programs, standardization discussions, testing and evaluation systems, and real engineering products.

AEV Safety is designed for four output tracks:

1. Review and methodology papers that can be peer reviewed.
2. Conference and teaching material that gives researchers, engineers and standardization experts a shared vocabulary.
3. Standardization proposals for engineering-vehicle SOTIF, scenario testing, safety cases and operational monitoring.
4. Engineering practice that converts loader, excavator, haulage and construction-robot experience into reviewable safety evidence.

## Source Absorption

The project has absorbed the following technical strands:

- Li Xuefei's autonomous construction-machinery materials: autonomous digging, autonomous unloading, material-pile perception, bucket fill-rate measurement, V-shaped work-cycle path planning, tracking control, indoor/outdoor vehicle tests and front-fit/retrofit productization.
- The `Move the Earth and Beyond` material: terrestrial construction and mining automation, lunar and Mars resource-operation test-site design, safety system engineering for unmanned earthwork tasks, Built Robotics safety mechanisms and NASA/DLR resource-operation references.
- Construction and mining autonomy literature: unmanned ground/surface/underwater vehicles in construction, safety assurance of cooperating construction equipment, system-of-systems safety analysis, STPA and Petri-net extensions.
- General mobile physical AI safety material: robot SOTIF, physical interaction safety, VLA/LLM decision safety, runtime safety monitoring and SOTIF transfer.

Public papers, official standards pages and public company pages can support public evidence claims. Internal business-plan slides, project decks and unpublished collaboration material are used only as background inputs unless independently verified.

## Repository Structure

```text
AEV-Safety/
├── README.md
├── README-en.md
├── CONTRIBUTING.md
├── CONTRIBUTING-en.md
├── taxonomy/
├── architecture/
├── benchmarks/
├── standards/
├── paper/
├── docs/
├── figures/
└── references/
```

## Reading Path

1. [Source synthesis and evidence boundaries](docs/source-synthesis-en.md)
2. [Literature review and research landscape](docs/literature-review-en.md)
3. [Worksite and task taxonomy](taxonomy/worksite-task-taxonomy-v1.0-en.md)
4. [Reference architecture](architecture/reference-architecture-en.md)
5. [Evaluation matrix](benchmarks/evaluation-matrix-en.md)
6. [Standards landscape](standards/landscape-en.md)
7. [Standardization roadmap](standards/standardization-roadmap-en.md)
8. [Chinese manuscript draft](paper/manuscript-zh.md)
9. [English manuscript draft](paper/manuscript-en.md)

## Authors

- Zhang Yuxin
- Li Xuefei
- Yao Zongwei

Author order, affiliations, corresponding author, ORCID, funding, competing-interest statement and contribution statement will be finalized before formal submission.

## License

Open research materials in this repository are released under Apache License 2.0 unless otherwise stated. Third-party standards, papers, company pages, videos, internal business plans and project decks remain under their original rights and are not relicensed by this project.

## Citation

The formal citation will be updated after the manuscript version and author information are finalized.

```bibtex
@misc{AEVSafety2026,
  title = {AEV Safety: Autonomous Engineering Vehicle Safety},
  author = {Zhang, Yuxin and Li, Xuefei and Yao, Zongwei},
  year = {2026},
  note = {Open research framework and draft manuscript},
  url = {https://github.com/AutoZYX-Labs/AEV-Safety}
}
```
