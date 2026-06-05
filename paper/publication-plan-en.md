# AEV Safety Publication and Writing Plan

[中文](publication-plan.md)

Information status: 2026-06-05.

This file plans publication and writing work for AEV Safety, or Autonomous Engineering Vehicle Safety. It follows the output logic of ROAM, but it does not copy ROAM's topic. Papers are not the end state. They are a way to organize safety-development practice, engineering deployment, testing/evaluation and standardization discussion into reviewable public knowledge.

AEV Safety publication work should serve four goals:

1. Build a shared language across researchers, testing organizations and enterprise engineering teams.
2. Support safety-development practice, including system boundaries, risk chains, test records, operational monitoring and safety cases.
3. Help autonomous engineering-vehicle safety move into real products, not remain a conceptual discussion.
4. Provide reviewable methods, terms and candidate clause structures for standardization pre-research.

## Output Portfolio

The recommended portfolio contains multiple outputs rather than one paper. Safety-development practice and engineering product deployment come first; papers and standardization are vehicles for synthesis, review and coordination.

| Output | Positioning | Target readers | Current status |
|---|---|---|---|
| Safety-development practice package | Engineering implementation track | Enterprise safety, automation-system, testing and worksite-operation teams | MWMS/WTDC/DMWT, risk chains, evaluation matrix and technical work packages have been drafted |
| Engineering product-deployment package | Real pilots and productization | Loader, excavator, haulage, piling/trenching and construction-robot teams | Task taxonomy, scenario templates and source-synthesis framework have been drafted |
| Chinese review paper | Domestic common-language track | Chinese engineering-machinery, automated-driving safety, testing and standardization experts | Full Chinese draft exists; formal references, tables, authorship data and Chinese-journal format still need work |
| High-level English methodology paper | International method-paper track | International safety science, reliability, automation, robotics and construction-automation readers | Recommended primary target: RESS future risk-assessment methods special issue; second target: RESS multi-hazard resilience special issue |
| Standardization pre-research package | Group-standard and testing-guideline track | Standards bodies, testing organizations and enterprise engineering teams | Standardization opportunities and candidate clause modules drafted |

## Special Issue Search Results

Search scope: global public CFP pages, focusing on high-level journal Special Issues that remain potentially submittable after 2026-06-05 and align with autonomous engineering-vehicle safety, mobile physical AI, complex-system risk assessment, resilience assessment, automation scheduling and the laboratory's research direction. Official journal pages, ScienceDirect, IEEE and IEEE RAS sources are prioritized; all deadlines must be rechecked in the current submission system before submission.

### Strong Recommendation

| Journal / Special Issue | Deadline | Fit | Recommended action | Source |
|---|---|---|---|---|
| Reliability Engineering & System Safety: Methods for risk assessments meeting the challenges of the future | 2026-10-01 | High | Primary target for the English methodology paper | [ScienceDirect](https://www.sciencedirect.com/special-issue/330147/methods-for-risk-assessments-meeting-the-challenges-of-the-future) |
| Reliability Engineering & System Safety: Advanced resilience assessment & enhancement for complex engineering systems exposed to multi-hazards | 2027-02-28 | High | Second target and longer-window option; switch to this route if the paper is strengthened around multi-hazard disturbance, cascading disruption, operational resilience and recovery capability | [ScienceDirect](https://www.sciencedirect.com/special-issue/330906/advanced-resilience-assessment-enhancement-for-complex-engineering-systems-exposed-to-multi-hazards) |

Rationale for the RESS future risk-assessment methods Special Issue:

1. RESS is a high-level journal in reliability, system safety and risk assessment.
2. The special issue explicitly concerns rapid changes, large uncertainties, digitalization, system complexity, big data, autonomous systems and AI.
3. AEV Safety can offer clear methodological advancement: ODD/DDT to WTDC/DMWT, single-vehicle risk to MWMS risk, collision safety to task consequences, and static tests to operational monitoring and safety cases.
4. The special issue requires clear methodological advancement, not a perspective or generic framework. AEV Safety must be written as a risk-assessment method paper, not a project introduction.

Proposed title:

From Safe Driving to Safe Working: A Risk Assessment Method for Autonomous Engineering Vehicles and Mobile Working Machine Systems

Rationale for the RESS multi-hazard resilience Special Issue:

1. The special issue focuses on resilience assessment and enhancement for complex engineering systems exposed to multi-hazard conditions, which aligns with autonomous engineering vehicles operating in mines, construction sites and extreme environments.
2. An accessible CFP relay page reports an open submission window from 2026-02-28 to 2027-02-28, Article Type “VSI: RESS_Multi-hazard Resilience”, and Guest Editors Tao Zeng, Valerio Cozzani, Genserik Reniers and Lijun Wei; the final submission setting should still be checked through ScienceDirect and Editorial Manager.
3. AEV Safety can be reframed as a risk and resilience assessment method for mobile working machine systems under multi-source disturbance: communication degradation, localization abnormality, terrain/material change, worksite-organization failure, task interruption and recovery capability.
4. The longer window is useful for adding worked examples, operational-monitoring fields, recovery metrics and engineering-pilot material in late 2026.

Possible title:

From Safe Working to Resilient Mobile Work: Risk and Resilience Assessment for Autonomous Engineering Vehicles under Worksite and Task Disturbances

### Highly Aligned with the Lab Direction but Better as a Separate Paper

| Journal / Special Issue | Deadline | Fit | Recommended action | Source |
|---|---|---|---|---|
| IEEE Transactions on Automation Science and Engineering: Artificial Intelligence-Driven Scheduling for Manufacturing, Transportation and Logistics | 2026-08-30 | Medium-high | Do not submit the current review draft directly; suitable for a separate paper on safety-constrained multi-machine worksite scheduling, task allocation and recovery scheduling | [IEEE RAS CFP PDF](https://www.ieee-ras.org/wp-content/uploads/2026/03/Special-Issue-CFP-TASE-2026.pdf) |

Judgement on the IEEE T-ASE Special Issue:

1. The official CFP covers AI-driven scheduling, routing optimization, network design, human-machine collaborative scheduling, dynamic and uncertain scheduling, and real-time scheduling in manufacturing, transportation and logistics.
2. The current AEV Safety draft should not be forced into this special issue because its core is safety assurance and risk assessment, not scheduling algorithms.
3. The topic is, however, highly suitable for a later laboratory paper on semi-autonomous worksite Systems of Systems (SoS), safety constraints, multi-machine cooperation, interruption recovery, mixed manual-autonomous operation and remote supervision.

Possible title:

Safety-Constrained AI Scheduling for Autonomous Engineering Vehicles in Semi-Autonomous Worksite Systems

### Not Main Targets

| Journal / Special Issue | Status | Reason | Source |
|---|---|---|---|
| Journal of Safety Research: Injury Prevention Technologies in Construction | 2026-06-15 | Too time-critical now; without field-validated or quasi-field data, the current draft is unlikely to satisfy its construction injury-prevention positioning | [ScienceDirect](https://www.sciencedirect.com/special-issue/328580/injury-prevention-technologies-in-construction-field-validated-human-centered-and-data-driven-approaches) |
| Reliability Engineering & System Safety: Reliability of complex systems with multi-source uncertain information | 2026-07-01 | Relevant to multi-source evidence fusion, but the window is tight and it is less aligned than the 330147 and 330906 RESS calls | [ScienceDirect](https://www.sciencedirect.com/special-issue/322347/reliability-of-complex-systems-with-multi-source-uncertain-information) |
| IEEE Transactions on Robotics: Foundation Models for Robotics | Deadline passed in 2025-12; projected publication 2026-07 | High-level but closed; useful as a future proposal reference | [IEEE RAS](https://www.ieee-ras.org/publications/t-ro/special-issues/foundation-models-for-robotics/) |
| Safety Science: Interdisciplinary Approaches to Electric Micromobility Safety | Official ScienceDirect page shows 2026-02-28 deadline | Topic is electric micromobility, not AEV Safety; third-party pages show inconsistent dates, so the official page governs | [ScienceDirect](https://www.sciencedirect.com/special-issue/324999/interdisciplinary-approaches-to-electric-micromobility-safety) |
| Applied Sciences: Intelligent Autonomous Vehicles | 2026-06-30 | Related but not high-level enough and not focused enough for the main route | [MDPI](https://www.mdpi.com/journal/applsci/special_issues/QRM4N9088O) |
| Automation in Construction: ISARC 2025 selected papers | 2025-12 deadline passed | The journal fits AEV Safety well, but this Special Issue is closed; consider regular submission or a future call | [ScienceDirect](https://www.sciencedirect.com/journal/automation-in-construction/special-issues) |

## Recommended Submission Routes

### Route A: Chinese Review Paper

Recommended target:

A high-quality Chinese journal in engineering machinery, traffic safety, mechanical engineering, intelligent manufacturing, safety science or automated-driving safety.

Positioning:

Use Chinese to clarify the problem landscape of autonomous engineering-vehicle safety for Chinese researchers, standards experts and enterprise engineers.

Suggested title:

从安全行驶到安全作业：自主工程车辆安全保证框架综述

Writing goals:

1. Explain why road-vehicle automated-driving safety methods cannot be directly copied.
2. Introduce MWMS, WTDC and DMWT as three core concepts.
3. Review road-vehicle safety, engineering machinery, autonomous mining systems, robot SOTIF, construction System of Systems (SoS) and mobile physical AI.
4. Propose a SOTIF-oriented risk chain, evaluation matrix and safety-case structure.
5. Provide standardization opportunities and product-deployment recommendations.

Recommended structure:

1. Introduction: from automated driving to autonomous engineering work.
2. Review approach and evidence classification.
3. Road-vehicle safety methods as donors.
4. Engineering-machinery and autonomous-mining standards base.
5. Conceptual transfer: MWMS, WTDC and DMWT.
6. SOTIF-oriented risk chain.
7. Testing, operational monitoring and safety cases.
8. Representative scenarios: loaders, trenching, solar piling, haulage, hold cleaning and planetary-resource work.
9. Standardization recommendations and engineering deployment.
10. Conclusion.

### Route B: RESS English Methodology Paper

Recommended target:

Reliability Engineering & System Safety Special Issue: Methods for risk assessments meeting the challenges of the future.

Positioning:

Not a normal review. This should be a risk-assessment methodology paper.

Suggested title:

From Safe Driving to Safe Working: A Risk Assessment Method for Autonomous Engineering Vehicles and Mobile Working Machine Systems

Core contributions:

1. Propose MWMS, expanding the assurance object from a single vehicle to a vehicle-worksite-task-supervision system.
2. Propose WTDC and DMWT, transferring ODD/DDT methods into engineering work.
3. Propose a SOTIF-oriented risk chain connecting functional insufficiency, triggering condition, hazardous event, task consequence and mitigation.
4. Propose a multi-source evidence classification linking standards, simulation, closed-site tests, field logs, near misses and operational monitoring to safety cases.
5. Demonstrate transferability through loader loading, trenching, solar piling, autonomous haulage and planetary-resource work examples.

Recommended structure:

1. Introduction: why autonomous engineering vehicles create a future-risk-assessment problem.
2. Standards and evidence landscape: what current standards cover and what they cannot prove.
3. Methodological foundation: MWMS, WTDC and DMWT.
4. SOTIF-oriented risk-chain model for mobile working machines.
5. Evidence model: consequence classes, test records, operational monitoring and safety cases.
6. Scenario templates: wheel-loader loading, trenching, solar piling, autonomous haulage and planetary-resource work.
7. Discussion: transferability, non-transferability, standardization and product deployment.
8. Limitations and conclusion.

Methodological additions required:

- A clear figure or table for risk-assessment inputs, process and outputs.
- A reusable test-record schema.
- At least three worked examples, not only conceptual description.
- Each example should include WTDC, DMWT, functional insufficiency, triggering condition, consequence, mitigation and evidence.

### Route C: Standardization Pre-Research Paper or Technical Report

Recommended target:

First build a public white paper or technical report, then submit to Safety Science, Automation in Construction, Journal of Safety Research or a standardization-related conference/journal depending on feedback.

Suggested title:

Standardization Needs for Safety Assurance of Autonomous Engineering Vehicles

Core content:

1. Standards comparison.
2. Gap statement.
3. Candidate terms.
4. Candidate clause modules.
5. Test-record template.
6. Enterprise pilot path.

## Writing Timeline

| Time | Safety development and product deployment | Chinese review | English submission route | Standardization pre-research |
|---|---|---|---|---|
| 2026-06 | Calibrate MWMS, WTDC, DMWT, risk-chain, test-record and operational-monitoring fields | Calibrate Chinese draft structure, references and table replacement | Select the RESS future risk-assessment call as primary target; prepare a one-page fit memo | Complete standardization opportunity document and minimum viable standardization package |
| 2026-07 | Select 2-3 engineering tasks as worked examples and build reusable safety-development templates | Internal review and target-journal selection | Complete detailed outline, method tables, test-record schema and worked examples | Prepare group-standard pre-research outline and expert-discussion version |
| 2026-08 | Convert product-deployment material into safety requirements, degradation/recovery logic and field-evidence checklists | Submit Chinese draft or enter final formatting | Complete RESS full draft v1; if a separate IEEE T-ASE scheduling paper is prepared, submit before 2026-08-30 | Select priority standard topic and sample tasks |
| 2026-09 | Collect enterprise/testing-organization feedback and calibrate test-record and monitoring fields | Revise based on feedback | Internal review, English polishing and reference verification for the RESS future-risk paper | Build proposal package and clause skeletons |
| 2026-10 | Add operational monitoring, near-miss review and recovery capability into the engineering evidence template | Continue revision | Submit to the RESS future risk-assessment methods Special Issue before 2026-10-01; if missed, convert to regular submission or the 330906 multi-hazard resilience route | Update standardization material in parallel with the paper |
| 2026-11 to 2027-02 | Add cases for multi-hazard disturbance, communication degradation, localization abnormality, worksite-organization disruption and recovery capability | Maintain reference and terminology consistency | If switching to the RESS multi-hazard resilience Special Issue, submit before 2027-02-28 | Update testing/evaluation and operational-monitoring clauses from worked examples |

## Materials to Complete

1. Formal authorship data: author order, affiliation, corresponding author and ORCID.
2. References: DOI, official standard version, official status pages and authorized-standard boundaries.
3. Figures: at least three core figures for system boundary, risk chain and safety-case architecture; the review workflow now uses a table, not the previous workflow figure.
4. Tables: review workflow, standards comparison, WTDC/DMWT table, risk-chain examples and test-record schema.
5. Worked examples: at least three among loader, trenching, solar piling, haulage and planetary-resource work.
6. Evidence statement: what is public evidence, what is background input and what needs further verification.

## Recommended Figures and Tables

| Figure/table | Purpose |
|---|---|
| Table 1: Review workflow and evidence classification | Already used in the manuscript to replace the previous workflow figure |
| Core figure A: MWMS boundary model | Vehicle, work equipment, material, worksite, supervision, organization and data loop |
| Core figure B: WTDC-DMWT-SOTIF risk chain | Conditions, insufficiency, triggering conditions, consequences and mitigation |
| Core figure C: Safety-case evidence architecture | Development, testing, operational monitoring, near misses and claims |
| Table 2: Standards comparison | Road-vehicle, machinery, robot and AI safety standards |
| Table 3: WTDC/DMWT taxonomy | Worksite conditions and dynamic working tasks |
| Table 4: Consequence and metric matrix | Six consequence classes and evaluation metrics |
| Table 5: Worked examples | Risk-chain examples for representative tasks |

## Current Conclusion

The most robust output route is:

1. Put safety-development practice and engineering product deployment first, converting MWMS, WTDC, DMWT, SOTIF-oriented risk chains, test records, operational monitoring and safety cases into reusable templates.
2. Use the Chinese review paper as the domestic common-language and standardization base.
3. Target the RESS 2026-10-01 future risk-assessment methods Special Issue with an English methodology paper.
4. If a longer window or stronger resilience/recovery framing is needed, switch to the RESS 2027-02-28 multi-hazard resilience Special Issue.
5. Treat the IEEE T-ASE AI scheduling Special Issue as a separate paper direction on safety-constrained multi-machine worksite scheduling and task recovery, not as a destination for the current review draft.
6. Push the standardization pre-research package in parallel, prioritizing either testing/evaluation and operational monitoring requirements or a SOTIF implementation guide for autonomous engineering vehicles.

If the RESS special-issue window is missed, the English paper can still be converted to a regular submission. Candidate journals include Reliability Engineering & System Safety, Safety Science, Automation in Construction, Robotics and Autonomous Systems or Journal of Field Robotics, but the problem framing must be rewritten for each journal.
