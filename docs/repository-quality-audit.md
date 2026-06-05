# AEV Safety 仓库质量审计

[English](repository-quality-audit-en.md)

信息状态：2026-06-05。

本文件记录 AEV Safety（自主工程车辆安全）公开仓库和网页的质量控制状态。它不是一次性说明，而是后续每次公开更新都应维护的审计清单。

## 审计目标

本轮审计围绕六个要求：

1. 中文和英文公开文档必须高度一致，中文不是英文简化版。
2. AEV Safety 必须同时给出英文全称和中文全称：Autonomous Engineering Vehicle Safety / 自主工程车辆安全。
3. 公开简介必须突出安全保证、测试评价和标准化，不使用旧的弱化安全定位。
4. SOTIF 必须使用预期功能安全（Safety of the Intended Functionality, SOTIF），不出现错误英译。
5. 仓库和网页必须体现 ROAM 式成果路线：论文、标准化、技术工作包和工程落地。
6. 过程事项、内部协调、部署配置和未公开协作细节不得进入公开阅读路径。

## 当前公开文件配对

| 中文文件 | 英文文件 | 当前状态 |
|---|---|---|
| `README.md` | `README-en.md` | 已配对，结构和行数一致 |
| `CONTRIBUTING.md` | `CONTRIBUTING-en.md` | 已配对，结构和行数一致 |
| `docs/source-synthesis.md` | `docs/source-synthesis-en.md` | 已配对，结构和行数一致 |
| `docs/literature-review.md` | `docs/literature-review-en.md` | 已配对，结构和行数一致 |
| `docs/technical-work-packages.md` | `docs/technical-work-packages-en.md` | 已配对，结构和行数一致 |
| `taxonomy/worksite-task-taxonomy-v1.0.md` | `taxonomy/worksite-task-taxonomy-v1.0-en.md` | 已配对，结构和行数一致 |
| `architecture/reference-architecture.md` | `architecture/reference-architecture-en.md` | 已配对，结构和行数一致 |
| `benchmarks/evaluation-matrix.md` | `benchmarks/evaluation-matrix-en.md` | 已配对，结构和行数一致 |
| `standards/landscape.md` | `standards/landscape-en.md` | 已配对，结构和行数一致 |
| `standards/standardization-roadmap.md` | `standards/standardization-roadmap-en.md` | 已配对，结构和行数一致 |
| `standards/standardization-opportunities.md` | `standards/standardization-opportunities-en.md` | 已配对，结构和行数一致 |
| `paper/README.md` | `paper/README-en.md` | 已配对，结构和行数一致 |
| `paper/manuscript-zh.md` | `paper/manuscript-en.md` | 已配对，结构和行数一致 |
| `paper/publication-plan.md` | `paper/publication-plan-en.md` | 已配对，结构和行数一致 |
| `figures/README.md` | `figures/README-en.md` | 已配对，结构和行数一致 |
| `references/README.md` | `references/README-en.md` | 已配对，结构和行数一致 |

## 行数审计

当前公开文档的关键配对行数如下：

| 模块 | 中文行数 | 英文行数 | 状态 |
|---|---:|---:|---|
| README | 167 | 167 | 通过 |
| Source synthesis | 116 | 116 | 通过 |
| Literature review | 121 | 121 | 通过 |
| Technical work packages | 252 | 252 | 通过 |
| Taxonomy | 124 | 124 | 通过 |
| Architecture | 113 | 113 | 通过 |
| Evaluation matrix | 75 | 75 | 通过 |
| Standards landscape | 73 | 73 | 通过 |
| Standardization roadmap | 96 | 96 | 通过 |
| Standardization opportunities | 188 | 188 | 通过 |
| Manuscript | 666 | 666 | 通过 |
| Publication plan | 211 | 211 | 通过 |

行数一致不是质量的充分条件，但它可以防止中文稿退化为英文稿的摘要版。后续更新时，应同时检查结构、标题、表格、关键术语和引用编号。

## 公开定位审计

当前公开定位为：

AEV Safety（自主工程车辆安全）是面向装载机、挖掘机、矿卡、施工机器人、光伏施工设备和未来星球资源作业系统的开放安全保证、测试评价与标准化框架。

该定位满足三个要求：

1. 明确项目中文全称。
2. 把安全保证放在中心位置。
3. 避免把项目表述为“为了双语而双语”的研究框架。

## SOTIF 与术语审计

当前术语规则：

| 术语 | 使用方式 |
|---|---|
| SOTIF | 保留英文缩写，首次出现时按语境说明为预期功能安全（Safety of the Intended Functionality, SOTIF） |
| MWMS | Mobile Working Machine System / 移动作业机器系统 |
| WTDC | Worksite and Task Design Conditions / 作业场地与任务设计条件 |
| DMWT | Dynamic Moving and Working Task / 动态移动与作业任务 |
| HMRM | Human-like Mobility Reference Model / 类人移动参考模型 |
| HLMB | Human-like Mobility Behaviour / 类人移动行为 |

已执行公开扫描：

1. 未检出 SOTIF 错误英译。
2. 未检出旧的弱化安全定位。
3. 未检出把开放问题收束为单一发表目标的表达。
4. 未检出部署配置、外联沟通、内部协调或未公开协作安排等过程事项。
5. 未检出中文 Markdown inline bold 标记。

## 网页审计

网页入口：

https://aev-safety.autozyx.com/

当前网页满足：

1. 标题为 AEV Safety — 自主工程车辆安全。
2. Hero 中给出中文全称和英文全称。
3. 简介突出开放安全保证、测试评价和标准化。
4. 页面包含框架、场景、标准、成果和文档五类导航。
5. 成果路线明确中文综述论文、英文高水平方法论文和标准化预研包。
6. 公开文档库链接到中英文配对文件。
7. 桌面端和 390px 移动端截图检查通过。

## 成果路线审计

当前成果路线包括：

1. 中文综述论文：面向国内工程机械、自动驾驶安全、测试评价和标准化专家。
2. 英文高水平方法论文：主目标为 Reliability Engineering & System Safety 的未来风险评估方法 Special Issue。
3. 标准化预研包：优先形成测试评价与运行监控要求，兼顾预期功能安全实施指南、WTDC、DMWT 和安全案例指南。
4. 技术工作包：把来源、技术对象、验证方式、证据边界和后续工作拆为 WP0-WP6。

## 证据边界审计

当前公开材料遵守四级证据规则：

| 等级 | 使用方式 |
|---|---|
| A-FULL | 授权标准全文、法规全文和同行评议论文全文，可支撑条款级或研究结论 |
| B-OFFICIAL | 官方标准状态页、官方项目页和企业官方页面，可支撑状态和范围 |
| C-PUBLIC | 新闻稿、视频、公开演示和招聘页，只作为场景锚点 |
| D-INTERNAL | 商业计划书、项目 PPT、内部讨论和未公开访谈，只作为背景输入 |

公开仓库不得把 D-INTERNAL 材料写成认证、安全成熟度、商业规模或市场份额证据。

## 后续质量门

后续每次更新前应完成：

1. 中英文配对文件同步更新。
2. 关键文档行数、标题层级、表格数量和引用编号检查。
3. SOTIF 错译和旧定位口径扫描。
4. 内部材料公开边界检查。
5. HTML 解析和桌面/移动端截图检查。
6. GitHub Pages 线上内容校验。

## 当前剩余工作

1. 补齐正式作者信息、单位、通信作者、ORCID、基金、利益冲突和作者贡献声明。
2. 继续核验标准全文版本、DOI、官方项目状态和 Special Issue 页面。
3. 为 RESS 英文方法论文补充至少 3 个工作示例。
4. 把测试记录字段逐步转为可机读模板。
5. 准备团体标准预研材料和专家讨论版。
