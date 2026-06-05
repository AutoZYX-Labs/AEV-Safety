# AEV Safety

Autonomous Engineering Vehicle Safety / 自主工程车辆安全

中文 | [English](README-en.md)

AEV Safety（自主工程车辆安全）是一个面向自主工程车辆与移动作业机器系统的开放安全研究、测试评价与标准化项目。项目关注的不是单一车辆能否无人行驶，而是装载机、挖掘机、矿卡、摊铺/打桩/开沟设备、太阳能施工机器人以及未来星球资源作业系统，如何在定义清楚的场地、任务、物料、工具、人机协同和远程监督条件下形成可审查的安全证据链。

项目网址：

https://aev-safety.autozyx.com/

GitHub：

https://github.com/AutoZYX-Labs/AEV-Safety

## 项目定位

道路车辆自动驾驶安全已经形成较成熟的方法体系，包括 ISO 26262 功能安全、ISO 21448 SOTIF、ISO 34502 场景测试、ISO/SAE 21434 网络安全、ISO/PAS 8800 AI 安全和 safety case 论证。工程车辆智能化正在进入矿山、港口、拌合站、施工现场、光伏施工和极端环境作业，但安全证据仍分散在机械安全、控制系统功能安全、矿山无人化指南、企业项目页面、施工自动化研究和现场管理规则之间。

AEV Safety 的核心判断是：

工程车辆智能化安全的主问题，不是把自动驾驶标准直接搬到工程机械上，而是把道路车辆安全方法中的系统边界、场景、触发条件、功能不足、测试证据、运行监控和安全论证结构，迁移到移动作业机器系统。

## 三个核心概念

| 缩写 | 中文 | English | 作用 |
|---|---|---|---|
| MWMS | 移动作业机器系统 | Mobile Working Machine System | 把车辆本体、工作装置、工具、物料、场地基础设施、监督系统和人员组织作为一个安全对象 |
| WTDC | 作业场地与任务设计条件 | Worksite and Task Design Conditions | 扩展道路车辆 ODD，描述地形、物料、装卸点、禁入区、通信、监督、天气和生产约束 |
| DMWT | 动态移动与作业任务 | Dynamic Moving and Working Task | 扩展道路车辆 DDT，覆盖移动、定位、铲掘、装载、卸料、压实、打桩、开沟、运输和恢复动作 |

## 为什么开放这个项目

这个项目开放出来，不是为了把开放问题收束为单一发表目标。论文只是阶段性表达。更重要的目标是让这些问题进入更深的研究、标准化讨论、测试评价体系和真实产品落地。

AEV Safety 面向四类输出：

1. 综述论文与方法论文：形成可被同行审阅的理论框架。
2. 会议报告与教学材料：帮助研究人员、工程师和标准化专家形成共同语言。
3. 标准化建议：为工程车辆 SOTIF、场景测试、安全案例和运行监控提供条款级候选结构。
4. 工程实践落地：把装载机、挖掘机、矿卡和施工机器人项目中的现场经验转化为可审查的安全证据。

## 成果路线

AEV Safety 参考 ROAM 的成果组合方式，但成果对象不同。当前规划形成三条互相支撑的路线：

| 路线 | 目标 | 当前公开材料 |
|---|---|---|
| 中文综述论文 | 为国内工程机械、自动驾驶安全、测试评价和标准化专家建立共同语言 | [中文论文初稿](paper/manuscript-zh.md)、[文献综述](docs/literature-review.md) |
| 英文高水平方法论文 | 面向国际 reliability、system safety、automation、robotics 和 construction automation 读者，提出 MWMS/WTDC/DMWT 与 SOTIF 风险链方法 | [英文论文初稿](paper/manuscript-en.md)、[投稿规划](paper/publication-plan.md) |
| 标准化预研包 | 把论文框架转化为术语、场景、测试、运行监控和 safety case 条款骨架 | [标准化机会](standards/standardization-opportunities.md)、[标准化推进路线](standards/standardization-roadmap.md) |

## 面向谁

| 对象 | 可直接使用的内容 |
|---|---|
| 工程车辆、矿山、施工机器人和光伏施工装备团队 | MWMS、WTDC、DMWT、评价矩阵和 safety case 证据结构 |
| 测试评价机构 | 场景分类、后果类别、测试记录字段、近失事件和运行监控指标 |
| 标准化专家 | 道路车辆安全方法、工程机械标准、机器人 SOTIF 信号和候选条款模块 |
| 研究人员 | 文献综述、方法迁移框架、体系（SoS）安全、运行时安全保证和论文初稿 |
| 企业工程团队 | 装载机、挖掘机、矿卡、施工机器人项目的安全需求、降级恢复和产品化证据清单 |

## 当前材料吸收

本项目已吸收以下材料的技术脉络：

- 李学飞老师关于工程机械自主作业系统的商业计划书和技术材料：自主铲掘、自主卸料、料堆识别、铲斗满载率测量、V 型作业路径规划、路径跟踪控制、室内外实车测试和前装/后装产品化。
- `Move the Earth and Beyond` 项目材料：从地球施工/矿山自动化延伸到月球、火星和未来星球资源作业的沙盘设计、无人土方工程安全系统工程、Built Robotics 安全机制和 NASA/DLR 资源作业资料链。
- 施工与矿山无人系统文献：无人地面/水面/水下设备在施工中的应用、半自动工地协同装备安全、体系（SoS）安全分析、STPA 与 Petri net 扩展。
- 通用移动物理 AI 安全材料：机器人预期功能安全、物理交互安全、VLA/大模型决策安全、运行时安全监控和 SOTIF 方法迁移。
- 近期移动物理 AI 测评平台材料：五源数据、跨本体测评、类人移动参考模型 HMRM（Human-like Mobility Reference Model）和类人移动行为 HLMB（Human-like Mobility Behaviour）评价方法学，为工程车辆安全评价提供“安全性、平顺性、运行效率”和跨本体可比性的启发。

这些材料中，公开论文、标准页面和公开企业页面可作为公开证据；内部商业计划书、项目 PPT 和未公开协作信息只作为背景输入，不直接作为公开事实证明。

## 仓库结构

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
│   ├── repository-quality-audit.md
│   ├── repository-quality-audit-en.md
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

## 快速阅读路径

1. [材料吸收与证据边界](docs/source-synthesis.md)
2. [技术工作包与证据追踪](docs/technical-work-packages.md)
3. [仓库质量审计](docs/repository-quality-audit.md)
4. [文献综述与研究脉络](docs/literature-review.md)
5. [作业场地与任务分类体系](taxonomy/worksite-task-taxonomy-v1.0.md)
6. [参考架构](architecture/reference-architecture.md)
7. [评价矩阵](benchmarks/evaluation-matrix.md)
8. [标准版图](standards/landscape.md)
9. [标准化机会](standards/standardization-opportunities.md)
10. [标准化推进路线](standards/standardization-roadmap.md)
11. [论文投稿与写作规划](paper/publication-plan.md)
12. [中文论文初稿](paper/manuscript-zh.md)
13. [English manuscript draft](paper/manuscript-en.md)

## 作者

- Zhang Yuxin
- Li Xuefei
- Yao Zongwei

作者顺序、单位、通信作者、ORCID、基金、利益冲突和作者贡献声明将在正式投稿前确认。

## 许可证

本项目开放研究材料采用 Apache License 2.0，除非单独注明。第三方标准、论文、企业资料、视频、内部商业计划书和项目材料仍归原权利方所有，本项目不重新授权这些材料。

## 引用

正式引用格式将在论文版本和作者信息确认后更新。当前占位格式：

```bibtex
@misc{AEVSafety2026,
  title = {AEV Safety: Autonomous Engineering Vehicle Safety},
  author = {Zhang, Yuxin and Li, Xuefei and Yao, Zongwei},
  year = {2026},
  note = {Open safety-assurance framework and draft manuscript},
  url = {https://github.com/AutoZYX-Labs/AEV-Safety}
}
```
