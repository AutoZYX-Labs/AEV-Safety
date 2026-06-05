# AEV Safety

Autonomous Engineering Vehicle Safety / 自主工程车辆安全

[中文](README.md) | English

AEV Safety, or Autonomous Engineering Vehicle Safety, is an open safety-research, testing, evaluation and standardization project for autonomous engineering vehicles and mobile working-machine systems. The project does not ask only whether a vehicle can drive without a human driver. It asks how wheel loaders, excavators, autonomous haulage trucks, trenching and piling machines, solar-construction robots and future planetary-resource machines can produce reviewable safety evidence under explicitly defined worksite, task, material, tool, human-machine interaction and remote-supervision conditions.

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

## Output Roadmap

AEV Safety follows ROAM's portfolio logic, but the output object is different. The current plan has three mutually reinforcing tracks:

| Track | Goal | Current public material |
|---|---|---|
| Chinese review paper | Build a shared language for Chinese engineering-machinery, automated-driving safety, testing and standardization experts | [Chinese manuscript draft](paper/manuscript-zh.md), [literature review](docs/literature-review.md) |
| High-level English methodology paper | Address international reliability, system safety, automation, robotics and construction-automation readers with MWMS/WTDC/DMWT and SOTIF risk-chain methods | [English manuscript draft](paper/manuscript-en.md), [publication plan](paper/publication-plan-en.md) |
| Standardization pre-research package | Turn the paper framework into terms, scenarios, testing, operational monitoring and safety-case clause skeletons | [standardization opportunities](standards/standardization-opportunities-en.md), [standardization roadmap](standards/standardization-roadmap-en.md) |

## Who This Is For

| Audience | Directly useful material |
|---|---|
| Engineering-vehicle, mining, construction-robot and solar-construction teams | MWMS, WTDC, DMWT, evaluation matrix and safety-case evidence structure |
| Testing and evaluation organizations | Scenario taxonomy, consequence classes, test-record fields, near misses and operational-monitoring metrics |
| Standardization experts | Road-vehicle safety methods, machinery standards, robot SOTIF signals and candidate clause modules |
| Researchers | Literature review, method-transfer framework, system-of-systems safety, runtime assurance and manuscript drafts |
| Enterprise engineering teams | Safety requirements, degradation and recovery logic, and productization evidence checklist for loaders, excavators, haulage trucks and construction robots |

## Source Absorption

The project has absorbed the following technical strands:

- Li Xuefei's autonomous construction-machinery materials: autonomous digging, autonomous unloading, material-pile perception, bucket fill-rate measurement, V-shaped work-cycle path planning, tracking control, indoor/outdoor vehicle tests and front-fit/retrofit productization.
- The `Move the Earth and Beyond` material: terrestrial construction and mining automation, lunar and Mars resource-operation test-site design, safety system engineering for unmanned earthwork tasks, Built Robotics safety mechanisms and NASA/DLR resource-operation references.
- Construction and mining autonomy literature: unmanned ground/surface/underwater vehicles in construction, safety assurance of cooperating construction equipment, system-of-systems safety analysis, STPA and Petri-net extensions.
- General mobile physical AI safety material: robot SOTIF, physical interaction safety, VLA/LLM decision safety, runtime safety monitoring and SOTIF transfer.
- Recent mobile physical AI evaluation-platform material: five-source data, cross-embodiment evaluation, Human-like Mobility Reference Model (HMRM) and Human-like Mobility Behaviour (HLMB) methodology. These strands inform safety, smoothness, efficiency and cross-embodiment comparability for engineering-vehicle evaluation.

Public papers, official standards pages and public company pages can support public evidence claims. Internal business-plan slides, project decks and unpublished collaboration material are used only as background inputs unless independently verified.

## Repository Structure

```text
AEV-Safety/
├── README.md
├── README-en.md
├── CONTRIBUTING.md
├── CONTRIBUTING-en.md
├── taxonomy/
│   ├── worksite-task-taxonomy-v1.0.md
│   └── worksite-task-taxonomy-v1.0-en.md
├── architecture/
│   ├── reference-architecture.md
│   └── reference-architecture-en.md
├── benchmarks/
│   ├── evaluation-matrix.md
│   └── evaluation-matrix-en.md
├── standards/
│   ├── landscape.md
│   ├── landscape-en.md
│   ├── standardization-opportunities.md
│   ├── standardization-opportunities-en.md
│   ├── standardization-roadmap.md
│   └── standardization-roadmap-en.md
├── paper/
│   ├── manuscript-zh.md
│   ├── manuscript-en.md
│   ├── manuscript-zh.docx
│   ├── manuscript-en.docx
│   ├── publication-plan.md
│   └── publication-plan-en.md
├── docs/
│   ├── index.html
│   ├── literature-review.md
│   ├── literature-review-en.md
│   ├── source-synthesis.md
│   ├── source-synthesis-en.md
│   ├── technical-work-packages.md
│   └── technical-work-packages-en.md
├── figures/
│   ├── AEV-Safety-review-workflow.png
│   ├── AEV-Safety-review-workflow.svg
│   └── AEV-Safety-review-workflow.pdf
└── references/
    ├── AEV-Safety-main-references.bib
    ├── README.md
    └── README-en.md
```

## Reading Path

1. [Source synthesis and evidence boundaries](docs/source-synthesis-en.md)
2. [Technical work packages and evidence traceability](docs/technical-work-packages-en.md)
3. [Literature review and research landscape](docs/literature-review-en.md)
4. [Worksite and task taxonomy](taxonomy/worksite-task-taxonomy-v1.0-en.md)
5. [Reference architecture](architecture/reference-architecture-en.md)
6. [Evaluation matrix](benchmarks/evaluation-matrix-en.md)
7. [Standards landscape](standards/landscape-en.md)
8. [Standardization opportunities](standards/standardization-opportunities-en.md)
9. [Standardization roadmap](standards/standardization-roadmap-en.md)
10. [Publication and writing plan](paper/publication-plan-en.md)
11. [Chinese manuscript draft](paper/manuscript-zh.md)
12. [English manuscript draft](paper/manuscript-en.md)

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
  note = {Open safety-assurance framework and draft manuscript},
  url = {https://github.com/AutoZYX-Labs/AEV-Safety}
}
```
