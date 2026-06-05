# AEV Safety Repository Quality Audit

[中文](repository-quality-audit.md)

Information status: 2026-06-05.

This file records the quality-control status of the public AEV Safety repository and website. It is not a one-off note. It should be maintained whenever the public repository is updated.

## Audit Goals

This audit focuses on six requirements:

1. Chinese and English public documents must be highly aligned; Chinese must not be a simplified version of English.
2. AEV Safety must provide both the English full name and the Chinese full name: Autonomous Engineering Vehicle Safety / 自主工程车辆安全.
3. The public introduction must emphasize safety assurance, testing, evaluation and standardization, not use the older safety-weak positioning.
4. SOTIF must use Safety of the Intended Functionality / 预期功能安全, with no incorrect English translation.
5. The repository and website must show a ROAM-like output route: papers, standardization, technical work packages and engineering implementation.
6. Process matters, internal coordination, deployment settings and unpublished collaboration details must not enter the public reading path.

## Current Public File Pairing

| Chinese file | English file | Current status |
|---|---|---|
| `README.md` | `README-en.md` | Paired, with aligned structure and line count |
| `CONTRIBUTING.md` | `CONTRIBUTING-en.md` | Paired, with aligned structure and line count |
| `docs/source-synthesis.md` | `docs/source-synthesis-en.md` | Paired, with aligned structure and line count |
| `docs/literature-review.md` | `docs/literature-review-en.md` | Paired, with aligned structure and line count |
| `docs/technical-work-packages.md` | `docs/technical-work-packages-en.md` | Paired, with aligned structure and line count |
| `taxonomy/worksite-task-taxonomy-v1.0.md` | `taxonomy/worksite-task-taxonomy-v1.0-en.md` | Paired, with aligned structure and line count |
| `architecture/reference-architecture.md` | `architecture/reference-architecture-en.md` | Paired, with aligned structure and line count |
| `benchmarks/evaluation-matrix.md` | `benchmarks/evaluation-matrix-en.md` | Paired, with aligned structure and line count |
| `standards/landscape.md` | `standards/landscape-en.md` | Paired, with aligned structure and line count |
| `standards/standardization-roadmap.md` | `standards/standardization-roadmap-en.md` | Paired, with aligned structure and line count |
| `standards/standardization-opportunities.md` | `standards/standardization-opportunities-en.md` | Paired, with aligned structure and line count |
| `paper/README.md` | `paper/README-en.md` | Paired, with aligned structure and line count |
| `paper/manuscript-zh.md` | `paper/manuscript-en.md` | Paired, with aligned structure and line count |
| `paper/publication-plan.md` | `paper/publication-plan-en.md` | Paired, with aligned structure and line count |
| `figures/README.md` | `figures/README-en.md` | Paired, with aligned structure and line count |
| `references/README.md` | `references/README-en.md` | Paired, with aligned structure and line count |

## Line-Count Audit

Key paired public documents currently have the following line counts:

| Module | Chinese lines | English lines | Status |
|---|---:|---:|---|
| README | 167 | 167 | Pass |
| Source synthesis | 116 | 116 | Pass |
| Literature review | 121 | 121 | Pass |
| Technical work packages | 252 | 252 | Pass |
| Taxonomy | 124 | 124 | Pass |
| Architecture | 113 | 113 | Pass |
| Evaluation matrix | 75 | 75 | Pass |
| Standards landscape | 73 | 73 | Pass |
| Standardization roadmap | 96 | 96 | Pass |
| Standardization opportunities | 188 | 188 | Pass |
| Manuscript | 666 | 666 | Pass |
| Publication plan | 211 | 211 | Pass |

Line-count alignment is not sufficient proof of quality, but it prevents the Chinese version from degrading into an English-version summary. Future updates should also check structure, headings, tables, key terms and reference numbering.

## Public Positioning Audit

The current public positioning is:

AEV Safety, or Autonomous Engineering Vehicle Safety / 自主工程车辆安全, is an open safety-assurance, testing, evaluation and standardization framework for wheel loaders, excavators, autonomous haulage trucks, construction robots, solar-construction machines and future planetary-resource systems.

This positioning meets three requirements:

1. It explicitly provides the Chinese full name.
2. It puts safety assurance at the center.
3. It avoids presenting the project as bilingual for its own sake.

## SOTIF and Terminology Audit

Current terminology rules:

| Term | Usage |
|---|---|
| SOTIF | Keep the acronym and explain it as Safety of the Intended Functionality / 预期功能安全 at first use where needed |
| MWMS | Mobile Working Machine System / 移动作业机器系统 |
| WTDC | Worksite and Task Design Conditions / 作业场地与任务设计条件 |
| DMWT | Dynamic Moving and Working Task / 动态移动与作业任务 |
| HMRM | Human-like Mobility Reference Model / 类人移动参考模型 |
| HLMB | Human-like Mobility Behaviour / 类人移动行为 |

Public scans performed:

1. No incorrect SOTIF translation found.
2. No older safety-weak positioning found.
3. No expression that reduces research questions into paper-writing goals found.
4. No deployment-setting, outreach, coordination or unpublished collaboration process matter found.
5. No Chinese Markdown inline bold marker found.

## Website Audit

Website entry:

https://aev-safety.autozyx.com/

The current website satisfies:

1. Page title is AEV Safety — 自主工程车辆安全.
2. The hero provides both the Chinese full name and the English full name.
3. The introduction emphasizes open safety assurance, testing, evaluation, standardization, autonomy and autonomous-driving capability.
4. The page includes five navigation groups: framework, taxonomy, standards, outputs and documents.
5. The output route names safety-development practice, engineering product deployment, paper/review outputs and standardization pre-research.
6. The public document library links to paired Chinese and English files.
7. Desktop and 390px mobile screenshots have been checked.

## Output Route Audit

The current output route includes:

1. Safety-development practice: MWMS, WTDC, DMWT, SOTIF-oriented risk chains, test records, operational monitoring and safety cases are turned into an engineering workflow.
2. Engineering product deployment: loader, excavator, haulage, piling/trenching and construction-robot pilots are supported with operating boundaries, task-quality criteria, recovery logic and product evidence.
3. Paper and review outputs: Chinese review and English methodology papers build shared language and invite peer review.
4. Standardization pre-research package: priority topic is testing, evaluation and operational monitoring requirements, while also covering a SOTIF implementation guide, WTDC, DMWT and a safety-case guide.
5. Technical work packages: sources, technical objects, verification methods, evidence boundaries and next work are decomposed into WP0-WP6.

## Evidence Boundary Audit

The public material follows four evidence classes:

| Class | Usage |
|---|---|
| A-FULL | Authorized standards, regulations and full peer-reviewed papers can support clause-level or research conclusions |
| B-OFFICIAL | Official standards status pages, official project pages and company pages can support status and scope |
| C-PUBLIC | Press releases, videos, public demos and job posts are scenario anchors only |
| D-INTERNAL | Business plans, project decks, internal discussion and unpublished interviews are background inputs only |

The public repository must not use D-INTERNAL material as evidence for certification, safety maturity, business scale or market share.

## Future Quality Gates

Every future update should complete:

1. Paired Chinese and English file update.
2. Key-document line count, heading hierarchy, table count and reference-numbering check.
3. SOTIF mistranslation and old-positioning scan.
4. Internal-material public-boundary check.
5. HTML parser check and desktop/mobile screenshot check.
6. GitHub Pages online-content verification.

## Current Remaining Work

1. Complete formal author information, affiliations, corresponding author, ORCID, funding, competing-interest statement and author-contribution statement.
2. Continue checking standard text versions, DOI, official project status and Special Issue pages.
3. Add at least three worked examples for the RESS English methodology paper.
4. Convert test-record fields into machine-readable templates.
5. Prepare the group-standard pre-research material and expert-discussion version.
