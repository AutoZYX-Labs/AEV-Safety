# 从安全行驶到安全作业：自主工程车辆的安全保证框架


## 初稿元信息与核验说明

作者：Zhang Yuxin；Li Xuefei；Yao Zongwei

作者顺序、单位和通信作者信息将在正式投稿前确认。

通信作者邮箱：待确认

通信作者通讯地址：待确认

开放研究者与贡献者身份识别码（Open Researcher and Contributor ID, ORCID）：待确认

作者贡献声明：待确认

基金声明：待确认

利益冲突声明：待确认

人工智能（Artificial Intelligence, AI）辅助写作声明：待确认

正式公开引用前仍需核验的内部工程背景输入：

1. 李学飞老师的自主工程机械材料将自主装载机作业界定为由矿山、施工现场和港口智能化需求驱动的工程问题。该材料强调，装载机首先是作业机器，而不仅是移动平台。
2. 商业计划书材料识别了自主铲掘、自主卸料、料堆感知、铲斗满载率测量、路径规划、路径跟踪控制和重复作业循环执行等核心技术问题。这些点支撑本文对移动作业机器系统（Mobile Working Machine System, MWMS）、作业场地与任务设计条件（Worksite and Task Design Conditions, WTDC）和动态移动与作业任务（Dynamic Moving and Working Task, DMWT）的框架化处理；内部材料本身不能作为独立公开证据。
3. `20240514 Move the Earth and Beyond` 材料将地球施工/矿山自动化与月球和火星资源利用、未来探索试验场设计、Built Robotics 安全机制以及美国国家航空航天局（National Aeronautics and Space Administration, NASA）和德国航空航天中心（German Aerospace Center, DLR）的空间资源材料线索连接起来。这些内容在本文中只作为项目背景和问题外延，正式作为外部证据引用前仍需逐项核验来源。

## 摘要

道路车辆自动化安全已经形成了较成熟的方法体系，包括功能安全、预期功能安全（Safety of the Intended Functionality, SOTIF）、网络安全、人工智能（Artificial Intelligence, AI）安全、场景驱动测试和安全案例（safety case）。自主工程车辆正在进入拌合站、矿山、施工现场、光伏场地以及其他受控作业场地，但其安全保证证据仍分散在机械安全、控制系统功能安全、自主矿山指南、碰撞警告标准、相邻非道路机械标准、企业案例和项目特定运行规则之间。本文将自主工程车辆定义为移动作业机器系统，并提出一个面向自主工程车辆的安全保证框架。本文首先将道路车辆安全方法作为方法供体，映射现有土方机械和矿山机械标准，并指出直接迁移会产生误导的位置。随后，本文提出三个核心概念：移动作业机器系统、作业场地与任务设计条件、动态移动与作业任务。该框架连接系统边界、作业场地与任务条件、功能不足、触发条件、任务后果、测试、运行监控和安全案例。装载机、开沟、光伏打桩和自主矿山运输场景在本文中仅作为结构化模板使用，不作为产品成熟度证据。文章最后讨论该框架如何扩展到月球和其他极端环境下的移动作业。

## Highlights

- 道路车辆安全方法可用于组织移动作业机器的安全保证。
- MWMS、WTDC 和 DMWT 将运行设计域（Operational Design Domain, ODD）与动态驾驶任务（Dynamic Driving Task, DDT）扩展到作业场地和作业任务。
- 安全案例必须覆盖工具、物料和远程监督。
- 公开案例可锚定场景，但不能证明现场成熟度。
- 空间采矿为极端移动作业机器安全提供问题框架。

## 关键词

自主工程车辆；移动作业机器；预期功能安全（SOTIF）；功能安全；安全案例；场景驱动测试；自主矿山。

## 1. 引言

### 1.1 从自动驾驶到自主工程作业

道路车辆自动化已经形成相对成熟的安全工程图景。被动安全和主动安全提供了长期的车辆安全基础。功能安全处理电气电子系统故障行为引发的危害。预期功能安全处理系统无故障但预期功能或运行条件不足时可能产生的不合理风险。网络安全工程处理联网和软件密集型车辆系统中恶意或非预期干扰。近年来，人工智能安全、场景驱动测试和安全案例已经成为自动驾驶系统在有边界条件下论证安全性的核心方法 [1, 2, 3, 4, 5, 6]。

自主工程车辆正在进入相似但更异质的阶段。装载机、挖掘机、矿山运输卡车、开沟机、光伏打桩系统以及其他移动作业机器，越来越被期望具备移动、感知、规划、操作工作装置、与物料交互、报告任务进展并在远程监督下运行的能力。它们的运行域通常比开放道路更受控，但任务后果并不一定更低。装载机低速撞击料斗、墙体或其他设备仍可能造成严重后果。挖掘机可能损坏地下管线、过挖沟槽或破坏边坡稳定。打桩机器人如果定位、垂直度或深度控制错误，可能造成系统性质量风险。自主矿山运输系统可能对无线通信、定位、远程控制和运行组织产生安全相关依赖 [7, 8, 9, 10, 11]。

由此，自主工程车辆的安全论证重心由安全行驶扩展至安全作业。道路车辆主要需要在道路交通条件下论证动态驾驶行为的可接受安全；工程车辆则需要在明确定义的作业场地与任务条件下论证作业安全。移动能力仍是必要组成部分，但完整任务还包括工作装置、物料交互、任务质量、现场组织、远程监督和运行监控。

### 1.2 标准版图的碎片化问题

自主工程车辆的标准化基础并非空白。土方机械、矿山机械、机械控制系统、远程操作、碰撞警告和碰撞避免已经有相关标准和指南。ISO 17757 涉及土方机械和矿山自主/半自主机器系统安全。ISO 19014 为土方机械安全相关控制系统提供功能安全框架。ISO 15817 涉及远程操作者控制系统。ISO 21815 涉及碰撞警告和碰撞避免系统。全球采矿指南组织（Global Mining Guidelines Group, GMG）等行业指南讨论自主矿山系统、运营准备、系统安全、变更管理、危险日志（hazard log）和安全案例 [7, 8, 12, 13, 14, 15, 9, 16, 10, 17]。

当前难点在于证据链碎片化。现有标准和指南覆盖了安全保证问题的重要局部，但尚未为 AI 赋能的移动作业形成统一证据链，也尚未系统连接作业场地条件、动态作业任务、功能不足、触发条件、工作装置危害、质量后果、远程监督、测试、运行监控和安全案例。在中国，国家标准、行业标准和团体标准也正在进入自主土方机械、无人驾驶非公路自卸车和露天矿无人运输等方向。相邻非道路机械领域中，ISO 18497-1:2024 涉及农业机械和拖拉机的部分自动、半自主和自主功能设计原则与词汇。该标准并不适用于工程车辆，但说明公共道路之外的自动化移动作业也正在通过机器类型、任务边界、安全作业信息和面向验证的设计原则进行处理 [60]。与此同时，机器人预期功能安全国家标准项目于 2026 年 6 月 2 日进入公开征求意见，征求意见截止日期为 2026 年 7 月 2 日，项目周期标称为 18 个月。其公开范围涉及具有环境感知、信息处理和自主或半自主决策能力的移动机器人系统，包括运行设计域（ODD）声明、场景分类、触发条件、功能不足、危险链构建、风险评价和缓解措施。该项目是移动物理 AI 的相邻标准化信号，尚不构成智能施工或矿山机械的已发布要求。上述来源具有标准化信号价值；在缺少授权文本或确认官方文件时，官方状态页、草案或项目公示信息不宜作为最终技术要求使用 [18, 19, 20, 21, 22, 23]。

基于上述背景，本文提出一个安全保证框架，将道路车辆安全方法、机械安全标准、自主矿山指南、施工自动化研究、公开企业案例和未来现场证据组织到共同结构中。

### 1.3 道路车辆安全方法的迁移边界

道路车辆安全方法提供了成熟的问题结构。这些方法要求工程师定义系统边界、运行条件、危害、功能不足、触发条件、验证证据、剩余风险和运行监控。预期功能安全将注意力集中在预期功能与真实世界条件之间的差距。网络安全工程连接资产、威胁、攻击路径和安全相关后果。场景驱动测试帮助在里程积累之外组织测试覆盖。安全案例显式表达主张（claims）、论证（arguments）、证据（evidence）、假设（assumptions）和限制（limitations）之间的关系 [1, 2, 3, 5, 6]。

直接迁移评级标签和场景假设会导致边界错误。汽车安全完整性等级（Automotive Safety Integrity Level, ASIL）不等同于机械性能等级。SAE 驾驶自动化等级是为道路机动车定义的，难以表达铲斗、动臂、破碎锤、抓斗或打桩机构的自动化水平。道路车辆 ODD 不覆盖物料状态、附件配置、地下管线、任务质量或现场生产约束。道路场景分类也难以直接描述料堆、沟槽、桩位、矿山运输道路、装载区或受控作业区。道路车辆暴露度、可控性和伤害假设不足以覆盖资产损伤、生产延误、返工、质量失效、环境损害和恢复能力 [24, 25]。

因此，本文采用问题结构迁移原则。道路车辆方法被视为方法供体；工程车辆被视为移动作业机器系统，其安全保证需要重新定义系统边界、运行条件、任务结构和主张边界。

### 1.4 范围与贡献

本文覆盖将移动能力与物理作业结合起来的自主和智能工程车辆。主要示例包括装载机、挖掘机、矿山运输卡车、开沟机、光伏打桩系统以及相邻施工机器人。本文还讨论月球资源作业和空间采矿，将其作为移动作业机器安全的极端环境外推；相关材料不作为当前地球标准的证据。

本文作出五项贡献。

第一，将自主工程车辆安全从安全行驶重构为安全作业。第二，映射道路车辆安全方法、土方及矿山机械标准、自主矿山指南、施工自动化研究、公开企业案例和标准化过程之间的关系。第三，提出移动作业机器系统、作业场地与任务设计条件、动态移动与作业任务三个概念。第四，识别道路车辆安全概念的可迁移部分以及评级标签、场景本体和风险假设的重构需求。第五，说明该框架如何应用于装载机、开沟、光伏打桩和自主矿山运输场景，同时保持公开场景锚点与已验证现场证据之间的严格边界。

本文形成结构化综合和面向实践者的问题框架，旨在为研究人员、设备制造商、自动化方案供应商、测试评价机构、施工运营方、矿山运营方和标准化组织提供可进一步深化与实施的安全保证问题结构。

## 2. 综述方法与证据分类

### 2.1 综述类型

本文定位为带概念框架的系统化范围综述，而非完整 PRISMA（Preferred Reporting Items for Systematic Reviews and Meta-Analyses）系统综述。该定位源于当前证据基础的异质性：标准、官方标准状态页、同行评议论文、行业指南、企业公开页面、候选论文、公开通知和未来匿名化现场样本承担不同证据责任，不能作为单一同质文献池计数或解释。

表 1 汇总本文当前使用的系统化范围综述工作流。该工作流从协议定义开始，随后进入来源识别、来源核验、筛选与资格判断、证据分类、框架编码和综合输出。其作用在于明确不同证据类型的使用边界：哪些材料可以支撑条款级判断，哪些只能作为标准化状态、公开场景锚点或未来研究线索。为便于表格阅读，本节使用三个概念缩写：移动作业机器系统（Mobile Working Machine System, MWMS）、作业场地与任务设计条件（Worksite and Task Design Conditions, WTDC）和动态移动与作业任务（Dynamic Moving and Working Task, DMWT）。

表 1. 系统化范围综述的工作流与证据分类。

| 工作阶段 | 主要动作 | 输出与边界 |
| --- | --- | --- |
| 协议定义 | 定义范围、主题、纳入标准和排除标准 | 输出范围综述协议、主题清单和排除规则；边界为非完整 PRISMA 系统综述 |
| 来源识别 | 从标准、数据库、行业指南、企业公开页面、项目通知和本地研究笔记中识别候选来源 | 输出候选来源清单和检索记录；内部材料只作为背景输入，不作为公开事实证明 |
| 来源核验 | 通过官方页面、数字对象标识符（Digital Object Identifier, DOI）、机构页面或来源状态检查进行核验 | 输出来源状态、访问级别和可引用性记录；没有授权全文时，不推导条款级技术要求 |
| 筛选与资格判断 | 按相关性、来源质量、重复性、全文可得性和证据责任进行筛选 | 输出纳入、排除或暂缓决策；草案、立项页和公开通知只用于过程判断 |
| 证据分类 | 区分授权全文、官方状态、同行评议论文、指南、企业公开案例和未验证线索 | 输出证据等级与主张边界；防止把公开页面写成安全认证、客户验收或运行绩效证明 |
| 框架编码 | 按机器类型、场景、MWMS、WTDC、DMWT 和安全案例边界编码 | 输出标准版图、场景模板、风险链字段和证据字段；编码服务于框架综合，不把单一案例推广为行业结论 |
| 综合输出 | 综合 MWMS、WTDC、DMWT、预期功能安全风险链、测试、运行监控和安全案例 | 输出论文框架、测试评价矩阵、标准化机会和工程落地问题清单；不替代授权标准、正式测试报告或企业现场安全案例 |

### 2.2 检索与来源范围

本文覆盖七类证据主题：道路车辆安全方法供体；土方及矿山机械标准；自主装载机和挖掘机；施工机器人和施工现场安全；自主矿山运输；运行监控和安全案例；空间采矿或极端环境移动作业。

来源类型包括国际标准化组织（International Organization for Standardization, ISO）、SAE International（SAE）和 UL Standards（UL）的标准页面或文件，国家标准与数字标准平台，IEEE Xplore、ScienceDirect、SpringerLink、Wiley、ACM Digital Library、arXiv、Google Scholar、Semantic Scholar，政府和行业组织页面，企业官方页面，以及适合公开引用或内部审计的本地研究笔记。中国国家标准、行业标准和团体标准进入标准版图和标准化分析，但其在稿件中的使用受来源状态和访问级别约束。

初始检索执行记录了 16 条查询记录，包括 Crossref 应用程序编程接口（Application Programming Interface, API）检索和 arXiv API 尝试。共提取 16 个候选来源，其中 11 个完成页面核验或元数据复核，11 个获得筛选决策，4 个进入全文预筛选，3 个形成全文摘录卡，3 个迁移进入主参考文献库。当前主 BibTeX 种子在候选迁移后包含 60 个条目。这些计数用于可追踪的范围综述流程草稿，不作为最终 PRISMA 流程图。

### 2.3 纳入与排除标准

来源需满足三个条件才被纳入。第一，直接相关于道路车辆安全方法、工程机械安全、自主工程车辆、施工机器人、自主矿山系统、远程操作、运行监控、安全案例、场景驱动测试或极端环境移动作业机器。第二，能够支撑至少一种功能：标准映射、方法迁移、概念重构、开发与测试应用、运行监控、行业部署分析、标准化过程或空间采矿外推。第三，可追溯到官方标准页面、正式论文、行业组织、政府机构、企业官方页面、正式项目页面或其他公开且可引用来源。

以下来源被排除或暂缓：讨论道路车辆算法但与工程车辆安全保证无可迁移相关性；讨论通用机器人或同步定位与建图（Simultaneous Localization and Mapping, SLAM）但与工程车辆、施工、矿山、工作装置、现场安全或极端环境无关；缺少可追溯来源信息；或仅有强营销主张而无官方或可验证支持。标准草案、公开通知、立项页面、最终国际标准草案（Final Draft International Standard, FDIS）、国际标准草案（Draft International Standard, DIS）和批准后出版准备稿（PRF）材料仅用于标准化过程判断，不作为最终技术要求。

### 2.4 证据类别与主张边界

本文使用证据类别防止过度主张。

表 2. 来源使用的证据类别与主张边界。

| 证据类别 | 来源类型 | 适合用途 | 边界 |
| --- | --- | --- | --- |
| A-FULL | 授权标准全文、法规全文或完整同行评议论文 | 在文本支撑范围内用于条款级或研究结论 | 不得超出来源范围 |
| A-STATUS | 官方标准页面或项目页面 | 名称、版本、状态、阶段、范围摘要 | 不得推导具体技术要求 |
| A-TOC | 官方预览页面、目录或授权目录 | 主题和结构映射 | 不得引用或转述无法访问的条款 |
| A-ACADEMIC | 同行评议期刊或正式会议论文 | 方法、实验、仿真、研究发现 | 不得推断产品成熟度 |
| A-GUIDE | 政府、行业或技术指南 | 行业实践、生命周期概念、安全管理 | 除非法律地位被独立确认，否则按指南处理 |
| B-PREPRINT | 预印本或技术报告 | 研究信号和进一步复核线索 | 不得作为成熟部署证明 |
| B-WORKSHOP | Workshop 论文或 workshop proceedings | 新兴方法或研究方向 | 不得标注为期刊或主会证据 |
| B-CASE | 企业官方页面或公开产品页面 | 场景锚点和公开产品方向 | 不得声称独立安全保证、客户验收或关键绩效指标（Key Performance Indicator, KPI） |
| A2-ANON | 已确认的匿名化访谈或现场样本 | 实践系统边界、WTDC、DMWT 和证据链 | 仅在同意和匿名化后使用 |
| C-LEAD | 口头线索或未验证方向 | 未来研究线索 | 不支撑稿件结论 |

该分类用于约束本文的证据使用。企业页面可以锚定装载机或光伏打桩场景，但不能证明安全认证、客户验收、运行 KPI 或完整安全案例。同行评议的装载机装载论文可以支持任务变量、物料交互和性能指标，但不能证明产品安全成熟度。标准状态页可以确认标准项目或发布状态，但没有授权文本时不能支持条款级解释。行业指南可以支撑运行安全主题，但除非其约束地位被独立确认，否则不应被呈现为强制标准。

## 3. 道路车辆安全方法作为方法供体

### 3.1 被动安全、主动安全与自动驾驶安全

传统车辆安全可通过被动安全和主动安全描述。被动安全降低碰撞后的伤害，主动安全试图在碰撞前避免或缓解碰撞。自动驾驶改变了问题结构，因为系统在定义的运行条件内接管感知、预测、规划和控制。安全问题变为系统是否能在声明边界内表现可接受，并在边界外安全失效或移交。

工程车辆可借鉴这一分层思维，但后果模型需要扩展。人员伤害仍是最高优先级危害。然而，无人工地也使资产损伤、基础设施损伤、地下管线损伤、生产中断、工期延误、任务质量失效、环境损害和恢复能力成为安全论证核心。低速撞击料斗、桩位、沟槽壁或地下管线也可能产生严重运行后果。任务质量错误可能在没有即时碰撞的情况下造成下游危害。

### 3.2 功能安全

功能安全为安全相关电气电子系统故障行为导致的危害提供生命周期框架 [1]。对于工程车辆而言，其可迁移价值主要体现在结构层面：定义相关项（item）或系统，识别危害，评估风险，定义安全目标，分解安全要求，实施技术安全概念，并通过生命周期活动验证证据。

工程机械应在适用时使用机械领域特定的功能安全概念解释。ISO 19014 使用机械控制系统语言，包括机器控制系统安全分析和机器性能等级，并区别于道路车辆 ASIL [8, 12, 13, 14]。该差异直接影响风险参数解释。装载机、挖掘机和自主矿山运输卡车具有转向、制动、液压执行、工作装置、急停、远程操作和控制系统接口，需要功能安全分析，但其严重度、暴露度和可控性假设不同于乘用车在公共交通中的假设。

### 3.3 预期功能安全（SOTIF）

预期功能安全处理在系统无故障情况下，由预期功能不足或可合理预见误用引发的不合理风险 [2]。该方法对工程车辆具有直接价值，但应用对象需要扩展。在道路车辆中，典型预期功能安全问题包括雨、雾、眩光、遮挡、异常物体或施工区下的感知局限。在工程车辆中，类似不足以不同物理形式出现：料堆边界识别、铲斗载荷估计、沟槽几何估计、地下管线地图精度、粉尘和泥污能见度、工具姿态估计、物料状态识别和作业质量判断。

因此，工程车辆的预期功能安全风险链应包括功能意图、功能不足、触发条件、危险事件、任务后果、缓解措施和证据闭环。装载机在部件无故障时仍可能因未知物料、粉尘或料堆演化而出现装载行为不足。挖掘机在执行器无故障时仍可能因地图到现场对齐、土壤条件或地下管线不确定性而形成不充分挖掘计划。打桩机器人即使没有碰撞，也可能通过定位或垂直度误差造成不可接受的下游风险。

### 3.4 网络安全与 AI 安全

网络安全工程对工程车辆越来越具有安全相关性。远程操作、云端调度、无线网络、全球导航卫星系统（Global Navigation Satellite System, GNSS）、实时动态定位（Real-Time Kinematic, RTK）、电子围栏、空中升级（Over-the-Air, OTA）、远程急停、车队协同和现场数据上报都形成网络物理依赖。ISO/SAE 21434 可作为方法供体，因为它组织了资产、威胁、攻击路径、风险处理、网络安全要求、验证和监控 [3]。在自主矿山领域，无线通信、定位、远程控制和网络安全的安全相关性已经在自主运输系统（Autonomous Haulage System, AHS）文献中被讨论 [11]。

AI 安全范围不限于目标检测。自主工程车辆可能将 AI 用于地形可通行性、料堆感知、物料识别、工作装置控制、任务规划、安全监控和报告生成。ISO/PAS 8800 提供了道路车辆 AI 安全参考点，但工程车辆需要额外关注作业场地分布偏移、物料变化、附件状态、工作装置动力学和任务质量验证 [4]。

### 3.5 场景驱动测试与安全案例

场景驱动测试帮助将评价对象从里程或运行小时扩展至覆盖结构 [5]。对于工程车辆，评价问题应关注已覆盖的作业场地条件、任务条件、物料状态、工具状态、监督模式和异常事件。道路车辆场景层级作为结构化思想具有参考价值，但这些层级必须为作业场地与任务设计条件重写 [25]。

工程车辆自主化具有多方系统属性，因此需要安全案例。单个测试结果不能为机器、附件、远程系统、场地基础设施、监督流程、维护流程和运行组织建立安全性。即使本文不声称按 UL 4600 认证，该标准仍可作为“主张-论证-证据”推理的方法供体 [6]。对于自主工程车辆，安全案例应区分产品假设与运行假设，并说明证据如何在场地、物料、软件、传感器配置和监督模式变化期间得到维护。

### 3.6 驾驶自动化等级与场景层级

SAE J3016 为道路机动车驾驶自动化提供了术语体系 [24]。它有参考价值，但不足以描述工程车辆。一台机器可能在现场导航上高度自动化，在工作装置控制上中度自动化，并在异常情况下依赖远程确认。简单称其为 L4 或 L5 会隐藏最重要的安全问题。

因此，本文将自动化视为多维属性。移动自动化、工作装置自动化和监督模式应分别描述。更严格的自主化表述应指明：一个特定移动作业机器系统在特定作业场地与任务设计条件下，以特定监督和后备策略（fallback）假设执行特定动态移动与作业任务。

## 4. 自主工程车辆的现有标准与指南

### 4.1 分层标准与指南版图

现有标准和指南可以组织为七层。

第一层是对象和基础机械安全底座。土方机械类型定义和传统机械安全要求给出机器类型与通用安全基础。这一层必要但不足以覆盖自主作业。

第二层是土方机械控制系统功能安全。ISO 19014 是该领域安全相关控制系统的核心参考 [8, 12, 13, 14]。FDIS 等修订状态记录可支撑标准化过程讨论，但在官方发布被核验前不应替代当前已发布标准 [26, 27, 28, 29]。

第三层是自主和半自主机器系统。ISO 17757 及相关国家或地方标准为土方机械或矿山机械自主系统提供系统安全入口 [7, 19]。其意义在于将自主化处理为系统安全问题，并使分析对象超出单纯车辆控制。本文不将其解释为工程车辆预期功能安全标准。

第四层是远程操作。ISO 15817 与远程操作者控制系统相关 [15]。该标准对远程驾驶和远程监督具有重要价值，但不能单独处理完全自主、AI 功能不足或多方运行责任。

第五层是碰撞警告和碰撞避免。ISO 21815 为土方机械碰撞警告和碰撞避免系统提供重要基础 [9, 16]。草案或批准阶段文件可提示其他运动形式的标准化进展，但没有核验前不能视为最终已发布标准 [30, 31]。

第六层是相邻非道路移动机械，包括地下矿山机器和自主农业机械。ISO 18497-1:2024 特别适合作为比较点，因为它涉及农业机械和拖拉机的部分自动、半自主和自主功能，同时明确排除林业应用和公共道路运行 [60]。这些领域提供相关安全经验，因为它们涉及受控作业场地、非道路移动、远程操作、环境变化和作业功能。其直接适用性仍需按任务逐项评估。

第七层是行业指南以及国家/团体标准动态。GMG 自主矿山系统指南、实施指南、功能安全白皮书、中国自主或无人矿山运输标准、相邻机器人预期功能安全项目信息显示，系统安全、运营准备、变更管理、维护、培训、危险日志、安全案例、ODD 声明、场景分类和风险链推理正在成为 AI 赋能移动作业的核心问题 [10, 17, 32, 18, 20, 21, 22, 23]。

### 4.2 当前标准版图的证据能力与边界

标准版图支持三项判断。

第一，自主工程车辆安全已有标准基础。机械安全、控制系统功能安全、自主机器系统、远程操作、碰撞警告、碰撞避免和自主矿山运行已有相关标准和指南。

第二，现有材料分散在对象定义、控制系统安全、远程操作、碰撞避免、矿山指南、国家标准、团体标准、相邻非道路自动化标准和相邻机器人预期功能安全项目信息之间。机器人预期功能安全项目说明 ODD、场景、触发条件、功能不足、危险链和缓解概念正在进入移动机器人标准化。ISO 18497-1 显示了另一条非道路路径：部分自动、半自主和自主机器功能通过机器设计原则、词汇、安全作业信息和预期用途边界进行处理 [60]。二者均不构成工程车辆的直接合规模板。当前材料仍未为 AI 赋能移动作业提供覆盖机器、工作装置、物料、现场、任务质量、远程监督和运行监控的统一证据链。

第三，道路车辆方法可以帮助组织缺失的证据链，但不能作为直接合规模板。本文的贡献在于方法整合，而非将某个道路车辆标准解释为工程车辆自主化的完整解决方案。

该版图的证据能力也存在明确边界：仅有官方状态页或预览页面（preview）时，不能证明条款级要求；企业公开页面不能证明产品已经完成独立安全保证、运行 KPI、客户验收或完整安全案例；空间采矿或月球资源材料不能作为当前地球工程车辆标准的证据。

### 4.3 安全评价对象从人身伤害扩展到作业后果

人员安全仍是最高优先级问题。受控作业场地仍包括维护人员、监督人员、其他机器操作者、访客以及可能进入限制区域的人员。但自主工程车辆需要更宽的后果模型。资产损伤、基础设施损伤、地下管线损伤、生产中断、工期延误、返工、任务质量失效、环境损害和恢复能力必须纳入考虑。

后果模型扩展改变评价方式。装载机可能在没有碰撞的情况下通过重复误装造成不可接受风险。挖掘机可能通过系统性沟槽深度错误、边坡不稳定或侵入地下管线形成不可接受风险。光伏打桩系统可能通过位置或垂直度错误造成下游结构和施工风险。自主矿山运输可能因通信中断、定位不确定、远程控制失效或人工/自动交通交互不良产生安全相关风险。

因此，安全保证目标应覆盖即时撞击避免、有边界作业任务的安全完成、任务质量维持、假设监控和异常状态恢复。

### 4.4 对后续章节的含义

后续章节将该标准版图发展为安全保证框架。第 5 节将定义 MWMS、WTDC 和 DMWT 三个概念锚点。第 6 节将这些概念连接到预期功能安全导向风险链、场景测试、运行监控和安全案例。第 7 节将代表性场景用作证据收集模板，并将公开企业页面限定为场景锚点。第 8 节讨论迁移边界、标准化缺口以及到月球资源作业和空间采矿的极端环境外推。

核心论点是，自主工程车辆需要一种能够连接道路车辆安全方法、机械标准、现场机器人、作业场地运行和未来物理 AI 部署的安全保证语言。

## 5. 概念迁移：MWMS、WTDC、DMWT 与预期功能安全导向风险链

### 5.1 从车辆相关项到移动作业机器系统

道路车辆安全工程通常从相关项定义（item definition）开始。对于自主工程车辆，相应的安全保证对象应宽于车辆、控制器或自动化软件栈。本文将移动作业机器系统定义为共同支撑一个有边界移动作业任务的机器、工作装置、附件、感知与计算系统、远程操作或监督系统、场地基础设施、数字服务、运行组织、维护组织和运行数据闭环。

该定义反映了自主工程车辆风险来源的分布式特征。装载机系统除移动底盘外，还包括铲斗、动臂、液压执行、物料交互、装载策略、卸料接口、现场交通组织、远程停止能力和生产流程。开沟挖掘机系统除履带车辆外，还包括铲斗或开沟附件、数字施工计划、地下管线假设、禁入区、弃土位置、操作者确认规则和恢复流程。光伏打桩系统除自主移动底盘外，还包括打桩设备、桩料供给或处理、定位基准、垂直度控制、施工质量记录和现场验收流程。

MWMS 概念与现有土方和矿山机械材料方向一致，但并非任何单一标准的复述。ISO 17757 为土方机械和矿山自主/半自主机器系统提供基础 [7]。ISO 19014 为土方机械安全相关控制系统提供功能安全参考 [8]。GMG 指南将自主矿山视为系统安全和运营准备问题，涉及供应商、运营方、控制室、基础设施、培训、维护、变更管理、危险日志和安全案例 [10, 17]。ISO 18497-1 作为相邻非道路提醒，说明自动化机器安全必须与机器设计原则、预期用途、安全作业信息和剩余风险沟通相关联 [60]。MWMS 概念将这些洞见推广到装载机、挖掘机、开沟系统、光伏打桩系统和其他移动作业机器。

MWMS 概念用于避免两类低估。第一，低速并不等同于低风险；即使机器低速移动，工作装置也可能产生高力、高力矩和高后果接触事件。第二，无人操作并不消除运行责任；远程监督、作业许可、现场隔离、维护、校准、急停、后备策略和重启规则仍然是安全论证的一部分。

### 5.2 从道路 ODD 到作业场地与任务设计条件

运行设计域概念对自动驾驶有价值，因为它迫使开发者说明自动驾驶系统意图在何处、何时以及何种条件下运行。对于工程车辆，直接使用道路 ODD 过窄。本文将作业场地与任务设计条件定义为：MWMS 在其下执行特定作业任务的一组场地、物料、工作装置、任务质量、数字和组织条件。

WTDC 至少包括十层。

表 3. 自主工程车辆的作业场地与任务设计条件层级。

| WTDC 层级 | 工程车辆含义 | 示例条件 |
| --- | --- | --- |
| 作业区域与边界 | 任务允许发生的位置 | 拌合站、船舱、矿山运输道路、沟槽走廊、光伏场地、地下矿山、月面施工区 |
| 地形与可通行性 | 机器能否安全移动 | 坡度、车辙、泥地、松土、碎石、台阶边缘、可变形地形、低重力地形 |
| 固定基础设施 | 构成风险结构的现场资产 | 料斗、输送带、管线、公用设施、桩位标记、墙体、通信基站 |
| 临时修改 | 变化中的现场对象和限制 | 临时料堆、临时沟槽、围挡、作业许可边界、临时便道 |
| 动态对象 | 移动人员和机器 | 工人、指挥员、卡车、挖掘机、巡检车、吊装设备、其他机器人 |
| 物料状态 | 作业介质及其变化 | 粒度、含水率、压实度、黏聚性、硬度、破碎度、月壤性质 |
| 工作装置与附件 | 工具配置和能力 | 铲斗、动臂、斗杆、破碎锤、抓斗、打桩装置、开沟附件、钻具、挖掘机构 |
| 环境 | 物理与感知条件 | 粉尘、雾、雨、雪、眩光、低照度、振动、电磁干扰、GNSS 遮挡、极端温度 |
| 数字与连接条件 | 信息基础设施和假设 | 地图、RTK、调度系统、云平台、电子围栏、车联网通信（Vehicle-to-Everything, V2X）或专网、远程视频链路 |
| 组织与监督 | 人员和流程条件 | 车上操作、远程驾驶、远程监督、一对多监督、现场安全员、急停、重启批准 |

该分层 WTDC 结构受场景驱动安全评价和六层场景建模启发，但已面向作业场地任务重新组织 [5, 25]。其实用价值在于测试设计。工程车辆测试应从运行时长进一步扩展到作业区域、地形状态、物料状态、附件状态、任务质量要求、通信状态和监督模式的覆盖情况。

### 5.3 从动态驾驶任务到动态移动与作业任务

道路车辆自动化将动态驾驶任务与后备策略和用户角色区分开。工程车辆需要一个包括物理作业的任务概念。本文将动态移动与作业任务定义为：在 WTDC 内完成特定移动作业任务所需的实时感知、定位、规划、控制、工作装置操作、物料交互、任务质量评估、异常处理和后备策略。

对于拌合站装载机，DMWT 包括从停车点移动到料堆，识别料堆边界和可用铲掘面，设定车辆和铲斗姿态，进入料堆，举升，收斗，估计装载质量，移动到料斗，对齐卸料点，卸料，确认任务完成并返回下一循环。

对于管线开沟，DMWT 包括读取数字施工计划，将计划与现场对齐，确认禁挖区和地下管线，移动到挖掘点，稳定机器，控制铲斗轨迹，保持深度和坡度，检测土壤或岩石变化，更新工作面地图，放置弃土，识别过挖或欠挖，并在假设失效时停止或请求远程确认。

对于光伏打桩，DMWT 包括读取桩位，移动到目标点，局部定位，处理或对齐桩体，打桩，测量深度和垂直度，记录竣工数据，处理异常并移动到下一桩位。

对于自主矿山运输，DMWT 包括路线分配、调度、装载区交互、矿山道路行驶、卸载、与人工交通交互、远程监控、通信故障响应和维护接口。因此，自主矿山运输可以作为生命周期和组织保证的成熟参考，但不能作为装载机、挖掘机或打桩任务已经被解决的通用证明 [10, 17, 33, 34]。

DMWT 概念将中心问题从自主移动能力扩展为有用作业能力：MWMS 能否在声明的 WTDC 下安全、可靠、可验证地完成有用作业。

### 5.4 移动作业的预期功能安全导向风险链

预期功能安全对自主工程车辆有价值，因为许多风险并非由部件故障引起。系统可能按设计运行，但仍不足以应对粉尘、物料变化、地图错配、意外土壤硬度、料堆演化、通信退化、工具姿态不确定或异常现场组织 [2]。

对于移动作业，风险链应包括七个要素。

表 4. 移动作业机器任务的预期功能安全导向风险链要素。

| 风险链要素 | 自主工程车辆含义 | 示例 |
| --- | --- | --- |
| 功能意图 | MWMS 意图完成的任务 | 装载骨料、挖沟、打桩、运输矿石 |
| 功能不足 | 感知、规划、控制、工作装置操作或质量判断不足之处 | 料堆边界错误、铲斗姿态不确定、管线地图错误、桩垂直度错误 |
| 触发条件 | 激活该不足的 WTDC 条件 | 粉尘、未知物料、软土、RTK 丢失、临时人员进入、桩几何变化 |
| 危险事件 | 不足如何变得不安全或不可接受 | 碰撞、过挖、管线击穿、边坡失稳、卸偏、桩位错误 |
| 任务后果 | 随后发生的伤害或损失 | 人员伤害、机器损伤、管线损伤、生产中断、返工、环境损害 |
| 缓解措施 | 如何降低风险 | 限速、停止、远程确认、重新定位、任务重规划、禁入区、质量检查 |
| 证据闭环 | 如何证明并维护风险控制 | 仿真、场景测试、现场试验、事件日志、危险日志、维护记录、重新验证 |

该风险链保留预期功能安全逻辑，同时改变对象。在道路车辆中，触发条件通常是道路、交通或天气条件。在工程车辆中，它们是作业场地和任务条件。在道路车辆中，危险事件通常是驾驶冲突。在工程车辆中，危险事件可能涉及工作装置、物料、基础设施、任务质量或生产连续性。在道路车辆中，证据通常聚焦驾驶场景。在工程车辆中，证据必须包括作业循环场景、工具状态、物料状态、质量记录和运行日志。

### 5.5 三维自动化描述

SAE J3016 是道路机动车驾驶自动化有价值的术语体系，但 L0-L5 不应直接作为工程车辆的完整自动化描述 [24]。一台机器可能在导航上高度自动化，在工作装置控制上中等自动化，并对异常事件依赖远程确认。单一等级会隐藏最安全相关的问题。

因此，本文通过三个维度描述自主化：移动自动化、工作装置自动化和监督模式。表 5 给出了低、中、高自动化解释，以便正文展示项聚焦框架证据链。

表 5. 移动作业机器系统的三维自动化描述。

| 维度 | 低自动化 | 中自动化 | 高自动化 |
| --- | --- | --- | --- |
| 移动自动化 | 远程驾驶或辅助驾驶 | 固定区域自动移动 | WTDC 内自主移动和障碍响应 |
| 工作装置自动化 | 人控制铲斗、动臂、附件或工具 | 自动化子任务或辅助工具动作 | 带任务质量验证的自动作业执行 |
| 监督模式 | 车上操作者或近场遥控 | 远程驾驶员或一对一监督 | 一对多监督、异常确认和运行监控 |

因此，一个精确的自主化声明应写成：特定 MWMS 在特定 WTDC 内，以定义好的移动自动化、工作装置自动化、监督模式和后备策略假设，执行特定 DMWT。该表述虽然不如“L4 工程车辆”简短，但更适合测试、运行和标准化语境。

### 5.6 新兴证据：从自主机器到自主作业系统

来自自主矿山运输的近期作业系统证据强化了扩展安全保证边界的必要性。在对瑞典露天铜矿的探索性案例研究中，Lund 表明，自主运输会重新分配而非消除人的责任：自主区域内的生产仍依赖现场和控制室操作者，组织流程、培训、通信和持续适应也成为安全保证问题的一部分 [58]。对于自主工程车辆，这支持将自主化视为自主作业系统问题，而非仅限于车辆控制问题。

学习型自主挖掘提供了第二个前沿。ExT 表明，transformer 策略可以在多任务仿真示范上预训练，并通过监督学习或强化学习微调适配新任务、土壤条件、地形轮廓和铲斗几何，且在 Menzi Muck M545 上完成了有边界的实机示范 [59]。这支持 DMWT 观点，即机器配置、作业场地状态和任务定义共同塑造已验证运行边界。然而，任务成功、厘米级精度和仿真分布外（Out-of-Distribution, OOD）适配本身并不构成安全保证。

二者共同强化了本文的核心边界转移。安全保证对象从自动化机器扩展为移动作业机器系统，包括机器、工作装置、作业场地、数字上下文、监督模型、组织流程和证据闭环。这也是近期远程操作和 AI 辅助现场巡检来源页面证据需要谨慎处理的原因：两者都与同一作业系统边界相关，但摘要级证据不能被写成全文精读。

## 6. 安全保证证据链：开发、测试、监控与安全案例

### 6.1 从相关项定义到 MWMS 定义的开发过程

道路车辆功能安全、预期功能安全、网络安全、AI 安全和场景驱动测试的可迁移价值是流程纪律。工程车辆可以保留生命周期逻辑，但必须将对象从车辆相关项改为 MWMS [1, 2, 3, 4, 5]。

一个实用开发顺序是：

1. 定义 MWMS，包括机器、工作装置、附件、远程系统、场地基础设施、数字服务、运行组织、维护组织和数据闭环。
2. 定义 WTDC，包括允许场地、地形、物料、附件、环境、数字基础设施和监督条件。
3. 定义 DMWT，包括移动、定位、工作工具操作、物料交互、任务质量判断、异常处理和后备策略。
4. 在适用时使用机械控制系统语言进行功能安全分析，尤其使用 ISO 19014 和机器性能等级，避免直接迁移 ASIL [8, 12, 13, 14]。
5. 通过识别预期功能不足、触发条件、已知不安全场景、未知不安全场景发现方法和验证证据进行预期功能安全分析。
6. 对远程操作、云调度、无线通信、RTK/GNSS、软件更新、远程急停、现场网络和数据接口进行网络安全分析 [3, 11]。
7. 对模型输出局限、分布偏移、数据质量、感知不足、规划不确定性、监控和更新后重新验证进行 AI 安全分析 [4]。
8. 建立场景库、仿真案例、现场测试协议、运行监控和安全案例证据。

该顺序降低“先展示自动化、再补建安全论证”的工程风险。对于移动作业机器，缺少 MWMS 边界、WTDC、DMWT、风险链、测试覆盖和运行监控的演示，不能构成可审查的安全主张。

### 6.2 WTDC-DMWT 测试矩阵

工程车辆的场景驱动测试应通过 WTDC 层级与 DMWT 阶段交叉组织。一个有用测试矩阵包括四个层级。

表 6. WTDC-DMWT 场景测试层级与证据形式。

| 层级 | 问题 | 证据形式 |
| --- | --- | --- |
| 功能场景 | 正在执行什么作业任务？ | 拌合站装载、船舱装载、管线开沟、光伏打桩、自主矿山运输 |
| 逻辑场景 | 哪些参数变化？ | 坡度、粉尘、料堆高度、土壤硬度、管线地图误差、通信延迟、RTK 误差 |
| 具体场景 | 测试或仿真中使用哪些精确参数？ | 测试记录、仿真配置、现场日志、视频和数据轨迹 |
| 运行场景 | 真实运行中出现哪些异常或近失事件？ | 接管、急停、质量缺陷、返工、维护问题、软件或模型变更 |

对于装载机装载，测试除稳定自主行驶外，还应覆盖料堆高度、物料类型、含水率、粉尘、临时障碍、料斗对齐、重复循环、定位漂移、铲斗质量估计、撒料、装载时间、液压响应和远程停止。近期装载机研究通过将未知物料、铲斗物料重量、装载时间、工厂传感器、液压延迟、连续装载、料堆状态演化、质量、时间和功显式化，支撑了 DMWT 视角 [35, 36]。

对于开沟，测试应覆盖数字计划对齐、土壤硬度、地下管线不确定性、沟槽深度偏差、边坡稳定性、弃土位置、铲斗姿态误差、机器支撑状态、回转区域、远程确认和中断后重启。自主挖掘研究支持机器人挖掘的技术可行性，但本身不能关闭管线开沟或管线保护安全案例 [37]。

对于光伏打桩，测试应覆盖桩位误差、垂直度、地面坡度、RTK 丢失、风、振动、桩体处理、人员进入禁入区、深度异常、竣工数据记录和恢复流程。公开产品页面可以锚定场景，但不能替代现场验收、任务质量记录或安全案例证据 [38]。

对于自主矿山运输，测试和仿真应覆盖路线分配、装载和卸载区交互、交通隔离、调度、通信退化、定位异常、人工/自动混行和维护接口。MineSim、OpenMines 和 FusionPlanner 支撑仿真、调度和规划研究，但不能验证装载机铲斗控制、沟槽质量控制或光伏桩质量 [33, 34, 39]。

地形导航、场景工程、虚拟施工和施工 AI 论文也支撑证据链的部分环节。它们对 WTDC 地形层、数字孪生场景、现场监控和危害推理有用，但本身不能构成车辆级安全保证 [40, 41, 42, 43, 44]。

### 6.3 验收准则：从伤害风险到作业后果

人员安全仍是第一优先级。受控作业场地并非空场。维护人员、现场监督员、卡车驾驶员、访客、其他机器操作者和进入限制区域的人仍可能暴露于伤害。然而，工程车辆需要比道路车辆更宽的后果模型。

安全与验收模型至少应包括六类后果：人员安全、资产与基础设施损伤、生产连续性、任务质量、环境与资源影响、恢复能力。类别和示例如表 7 所示。

表 7. 自主工程车辆运行的安全与验收后果类别。

| 类别 | 示例 |
| --- | --- |
| 人员安全 | 现场工人、维护人员、监督员、远程操作者或其他机器操作者受伤 |
| 资产与基础设施损伤 | 机器损伤、工作工具损伤、撞击料斗、墙体损伤、管线击穿、管道损伤、桩损伤 |
| 生产连续性 | 停机、任务延误、场地阻塞、重复停顿、调度中断 |
| 任务质量 | 沟槽深度、沟槽坡度、桩位、桩垂直度、铲斗质量、卸料位置、竣工数据完整性 |
| 环境与资源影响 | 粉尘、撒漏、污染、不必要挖掘、物料浪费、地面扰动 |
| 恢复能力 | 急停、远程确认、诊断、安全重启、人工恢复、变更后重新验证 |

该模型改变证据解释方式。铲斗物料重量、装载时间、质量、时间和功对 DMWT 测试和任务质量具有重要意义，但不会自动成为安全指标 [35, 36]。系统可以高效但不安全；也可以在受限模式下足够安全但商业上不可行。因此，安全验收应区分伤害预防、任务质量保证、生产连续性和运行恢复能力。

### 6.4 运行监控与实时危险日志

工程车辆 WTDC 在运行中会变化。料堆会演化，沟槽会改变形状，土壤会变湿，临时对象会出现，通信质量会波动，传感器会变脏，软件会更新，监督实践会漂移。因此，运行监控构成安全证据链的必要组成部分。

MWMS 至少应记录八类证据：

1. 接管、急停、远程确认、降级模式进入和重启。
2. 感知错误、定位异常和地图到现场不一致。
3. 工作装置异常、任务失败和质量偏差。
4. 返工、生产中断和任务验收失败。
5. 近失事件、禁入区违规和未授权人员进入。
6. 通信中断、RTK/GNSS 异常、云平台故障和远程视频退化。
7. 软件更新、模型更新、校准变更和配置变更。
8. 维护、传感器污染、检查和维修。

这些记录应进入实时危险日志。GMG 系统安全指南在这里有用，因为它强调自主矿山系统的危险管理（hazard management）、运营准备、变更管理、投运调试（commissioning）、维护、培训和安全案例思维 [10, 17]。对于装载机、开沟系统和光伏打桩系统，同一原则适用，即使具体危害和运行不同。

施工危害识别和现场巡检 AI 研究可支撑外部监控和报告生成，但不能默认视为安全监控器 [43, 44]。如果使用这类工具，安全案例必须定义数据来源、检测局限、误报和漏报处理、规则来源、人工复核、响应责任和更新后验证。

### 6.5 安全案例结构

自主工程车辆安全案例应连接主张、论证、证据、假设和限制。除监管展示外，安全案例也为产品团队、现场运营方、维护团队、测试机构和标准化组织提供共同证据语言 [6, 10, 32]。

至少，安全案例应包含六组主张。

表 8. 自主工程车辆最低安全案例主张组。

| 主张组 | 所需证据 | 边界 |
| --- | --- | --- |
| MWMS 边界已定义 | 系统架构、接口清单、配置管理、角色与责任分配 | 本身不证明风险受控 |
| WTDC 已定义并执行 | 作业区域、地理围栏、现场假设、物料条件、附件限制、监督模式和禁止条件 | 必须连接监控和停止规则 |
| DMWT 已定义并分解 | 任务阶段、控制模式、工作装置动作、质量检查、异常处理和后备策略 | 必须包括作业任务并超出导航 |
| 风险已识别并缓解 | 功能安全、预期功能安全、网络安全、AI 安全分析、危险日志和缓解证据 | 必须区分故障、不足、威胁和模型局限 |
| 测试覆盖足以支撑主张 | 场景库、仿真、封闭场地测试、现场试验、验收记录和限制声明 | 覆盖仅适用于声明的 WTDC 和 DMWT |
| 运行保持受控 | 事件日志、维护、变更管理、软件/模型更新、近失复盘和重新验证 | 需要持续流程，不能止于一次性批准 |

供应商产品安全案例与运营方运行安全案例应分离。供应商可以论证产品在声明假设和配置下是安全的。运营方必须论证产品、场地、基础设施、人员、维护和运行流程对于特定部署是安全的。对于自主矿山运输，这一区分尤其重要，因为通信、定位、调度、远程操作和网络安全都可能直接影响安全运行 [11]。

## 7. 代表性场景与框架应用模板

### 7.1 证据原则

本节场景用于展示框架应用方式，并不作为验证样本。企业公开页面、产品页面和年报可以显示产品方向、场景或功能存在。它们不能证明独立安全认证、完整安全案例、现场成熟度、客户验收、运行 KPI、事故率或长期可靠性。同行评议论文可以支撑算法、实验和研究发现。除非证据直接存在，否则不能证明商业部署成熟度。行业指南可以支撑安全保证主题，但不能替代现场特定运行证据。

该证据原则用于约束公开案例的解释范围。综述论文可使用公开案例锚定场景，同时说明形成可辩护安全主张所需的补充证据。

### 7.2 拌合站和船舱中的装载机装载

装载机装载是高频移动作业任务。中国制造商公开案例可以锚定拌合站或类似无人装载机场景，学术装载机研究则支撑物料变化、装载循环性能和工作装置控制等任务变量 [45, 46, 35, 36]。

MWMS 包括装载机、铲斗、液压系统、感知传感器、定位系统、控制软件、远程监督系统、料堆、料斗或卸料点、交通通道、禁入区、现场人员规则、维护流程和运行数据系统。

WTDC 应包括料堆几何、物料类型、含水率、粉尘、能见度、路径宽度、坡度、临时障碍、料斗位置、其他车辆运动、通信质量、照明和监督模式。船舱装载还增加受限空间、舱壁、GNSS 受限、逃生路线受限、粉尘和恢复困难。

DMWT 包括重复循环：接近、选择料堆工作面、铲斗插入、举升、收斗、载荷估计、行驶、对齐、卸料、完成确认和返回。安全相关不足包括料堆边界识别错误、物料状态识别不足、铲斗载荷估计错误、粉尘下感知退化、重复循环定位漂移以及未检测临时障碍。

安全案例应要求人员隔离、料斗和墙体保护、铲斗路径限制、急停、远程确认、任务质量监控、重复循环测试、传感器污染处理、维护和变更后重新验证的证据。公开页面可锚定场景，但实际安全主张需要现场测试记录、事件日志、现场流程和匿名化运行证据。

### 7.3 管线与线性施工中的自主开沟

自主开沟是高价值场景，因为它结合移动、挖掘、地下资产风险和强任务质量要求。公开开沟产品材料可以锚定场景，自主挖掘机研究则支撑机器人挖掘作为技术研究方向 [47, 37]。

MWMS 包括挖掘机或开沟机、铲斗或开沟附件、数字施工模型、定位系统、管线地图、禁入区管理、远程操作者或监督员、现场安全员、弃土区、检查流程、维护流程和数据日志。

WTDC 应包括沟槽路线、允许深度和宽度、土壤类型、坡度、水、岩石、地下管线、禁挖区、附近设备、人员进入、GNSS/RTK 质量、地图精度、通信质量和天气。DMWT 包括与设计模型对齐、沿路线移动、稳定机器定位、铲斗轨迹控制、沟槽深度控制、弃土放置、工作面更新、检查、异常处理和安全重启。

最重要的预期功能安全触发条件包括管线地图错误、土壤硬度超出训练或规划假设、意外岩石、不稳定沟壁、铲斗姿态估计错误、定位漂移、人员进入和通信退化。危险事件包括管线击穿、过挖、欠挖、边坡失稳、机器碰撞、弃土错放和中断后不安全重启。

因此，安全案例应要求管线核验、设计模型对齐、深度和坡度容差、铲斗与回转包络限制、远程确认规则、禁入区监控、急停、地图错配后恢复和任务质量记录的证据。最强现场证据会是匿名化沟槽片段，包含 WTDC、DMWT 阶段、偏差、停止、远程确认、质量检查和经验教训。

### 7.4 光伏打桩系统

光伏打桩是窄但有价值的案例，因为任务重复、有边界且质量敏感。公开光伏打桩产品材料可以锚定任务方向，但本身不能建立安全保证或现场表现 [38]。

MWMS 包括移动底盘、打桩设备、桩体处理或供给流程、RTK 或局部定位基准、数字桩位布置、禁入区管理、远程监督、维护、质量检查和竣工数据管理。

WTDC 应包括现场边界、桩距、地面坡度、土壤条件、桩型、桩位容差、垂直度容差、RTK/GNSS 质量、风、能见度、作业区人员、其他车辆、桩体供给和通信。DMWT 包括移动到桩位、局部对齐、处理桩体、打入、深度和垂直度测量、异常处理、质量记录和移动到下一位置。

安全相关不足包括位置误差、垂直度控制误差、地面条件识别不足、桩处理错误、人员进入检测失败、RTK 丢失以及未识别异常振动或打桩失败。后果包括工人伤害、机器损伤、桩损伤、位置返工、结构质量争议和工期延误。

安全案例应要求地理围栏、远程停止、人员禁入流程、定位验证、桩质量测量、异常打桩检测、竣工记录、重启规则、维护和配置管理证据。光伏打桩适合作为早期安全案例模板，因为任务足够窄，能够精确定义 WTDC 和 DMWT。

### 7.5 自主矿山运输的参考价值与适用边界

在工程车辆自主化领域，自主矿山运输是最成熟的公开参考。相比许多装载机或挖掘机场景，它拥有更强的指南、运行组织、仿真研究和网络安全-安全耦合讨论 [10, 17, 33, 34, 11]。

其可迁移价值是系统保证。自主矿山运输说明，安全对象应包括控制室、调度、通信、维护、培训、道路设计、人工/自动隔离、投运调试、变更管理、危险日志和安全案例。它还说明，当通信、定位、远程控制或调度影响车辆行为时，网络安全具有安全相关性。

其不可迁移边界是任务特异性。矿山运输不能解决铲斗装载、沟槽深度控制、桩垂直度、物料状态识别或工作装置质量保证。其价值主要体现在安全保证参考，而非通用验证样本。

瑞典自动运输系统（Autonomous Haulage System, AHS）实施的近期作业系统证据进一步支撑这一边界：运输卡车可以无人化，但生产系统仍通过现场操作者、控制室操作者、正式流程和组织学习保持有人参与 [58]。

### 7.6 从公开场景到匿名化现场样本

后续证据建设的重点是将选定公开场景转化为匿名化、可审查的现场样本，而非继续堆叠公开案例。每个现场样本应记录：

1. MWMS 边界，包括机器、附件、远程系统、现场基础设施和组织角色。
2. WTDC，包括场地、地形、物料、环境、数字和监督条件。
3. DMWT，包括任务阶段、工作装置动作、质量检查和后备策略。
4. 预期功能安全风险链，包括不足、触发、危险事件、后果和缓解。
5. 测试和运行证据，包括场景测试、事件日志、急停、远程确认、质量记录和变更。
6. 主张边界，包括可以得出的结论和仍未验证的内容。

跨装载机、开沟、打桩和运输形成三到五个匿名样本，将显著提高稿件质量。没有这些样本，框架仍可作为有用的综述和概念贡献，但强实践主张应保持有限。

## 8. 极端环境外推：月球资源作业与空间采矿

### 8.1 纳入空间采矿的研究理由

月球资源作业和空间采矿不构成当前地球工程车辆标准的证据。本文纳入该主题，是因为其能够对同一概念结构进行压力测试。空间资源作业要求移动机器在不确定地形、有限人类在场和强远程监督约束下移动、挖掘、收集、运输、堆放、施工、检查和维护 [48, 49, 50, 51, 52, 53]。

结构相似性很清楚。地球工程车辆自主化和月球资源自主化都涉及移动作业、物料交互、工作装置控制、不确定地形、远程监督、任务质量要求和运行监控。区别在于，空间作业会把每个假设推到更极端：通信延迟、缺乏即时救援、维护受限、极端温度、粉尘附着、光照变化、能源约束、无地球基础设施定位以及高失败成本。

### 8.2 极端条件下的 WTDC 与 DMWT

在月球或星球语境中，WTDC 层级会变化，但不会消失。作业区域变为着陆点、施工区或资源勘探区。地形包括陨石坑、坡面、风化层、岩石和可变形表面。固定基础设施可能包括着陆器、电力系统、通信中继和储存单元。临时变化包括挖出的堆体、车辙、挡土堤、沟槽和构造表面。动态对象包括其他机器人以及有人或无人车辆。物料状态包括风化层分布、颗粒特性、含冰材料和巨石。环境包括真空、辐射、低重力、粉尘和极端温度。数字条件包括延迟通信、自主模式、建图和任务规划。组织条件包括地面控制、监督式自主、中止规则和健康管理。

DMWT 也仍然可识别。月球挖掘可能包括移动到目标、局部建图、地形准备、切削、铲取、运输、卸载、压实或整平，以及验证任务完成。月球施工仿真、CraterGrader 和相关空间机器人工作表明，地形操作、场地准备、可变形地形、自主施工、挖掘和多机协同都是活跃研究方向 [54, 55, 56, 57]。

### 8.3 安全含义

空间外推强化了地球工程车辆的三个结论。

第一，移动和作业不能分离。空间挖掘机到达资源点但不能安全处理物料，就没有完成安全相关任务。地球上的装载机、开沟机和打桩系统同理。

第二，任务质量具有安全相关性。不正确挖掘、不稳定地形准备或低质量施工会产生下游任务风险。地球上的类似风险包括沟槽坍塌、管线损伤、桩返工、料斗损伤和生产停机。

第三，运行监控和变更管理不可避免。在极端环境中，假设会失效。因此，证据必须包括健康监测、异常检测、恢复、远程监督规则以及软件或配置变更后的重新验证。

因此，空间采矿外推应作为概念地平线使用。它强化“安全作业”命题，但不能被用于声称当前地球标准已经覆盖空间采矿，或空间机器人原型验证了地球产品安全。

## 9. 讨论与结论

### 9.1 道路车辆安全中的可迁移要素

道路车辆安全提供强方法供体。功能安全贡献生命周期思维、危害分析、安全目标、要求分解和验证纪律。预期功能安全贡献故障与预期功能不足之间的区分，并提供识别触发条件和未知不安全场景的结构。网络安全贡献联网和远程监督系统中的资产、威胁和风险处理思维。AI 安全贡献对模型局限、数据质量、分布偏移和更新后验证的关注。场景驱动测试贡献按功能、逻辑和具体场景组织覆盖的方法。安全案例贡献“主张-论证-证据”纪律。

这些要素有价值，是因为它们是问题结构。它们迫使工程车辆领域说明系统边界、运行边界、任务定义、假设、限制、证据和剩余风险。

### 9.2 不可迁移要素与必要改造

若干道路车辆要素不应复制。ASIL 不应机械映射为机械机器性能等级。SAE 驾驶自动化等级不应作为工作装置自动化或监督模式的完整描述。道路 ODD 不应在缺少物料、工作装置、任务质量、数字和组织层的情况下使用。道路场景层级不应被视为最终作业场地本体。道路交通暴露度、可控性和伤害假设不应被假定能覆盖资产损伤、管线损伤、生产中断、返工、环境影响和恢复能力。

该领域因此需要适配后的语言。MWMS 替代狭窄车辆相关项。WTDC 替代道路 ODD 的直接迁移。DMWT 在涉及物理作业时替代动态驾驶任务。预期功能安全导向风险链必须包括任务后果和证据闭环。自动化应通过移动自动化、工作装置自动化和监督模式描述。

### 9.3 对研究、标准化和产品部署的含义

对于研究人员，后续工作需要在导航和操作算法之外，建立 WTDC 和 DMWT 模型、场景库、仿真基准、任务质量指标、触发条件发现方法和运行数据反馈闭环。装载机、开沟、打桩和运输任务应作为不同基准，因为其风险链本质不同。

近期挖掘预训练工作也说明，研究基准不应只记录任务成功，还应记录地形、土壤、附件、机器配置、后备策略和更新后验证边界 [59]。

对于标准化组织和测试评价机构，更具可操作性的起点是任务特定测试与评价指南，例如拌合站或船舱无人装载机作业、管线施工自主开沟、自主光伏打桩和自主矿山运输。这些指南可以定义 WTDC 层级、DMWT 阶段、场景参数、触发条件、证据记录和安全案例期望。

对于制造商、自动化供应商和运营方，产品部署应从一开始围绕证据设计。系统应能说明它能做什么、在哪里做、何时必须停止、谁监督、记录什么数据、变更如何验证以及每个安全主张由什么证据支撑。在实践上，这意味着将场景库、测试记录、事件日志、危险日志和运行安全案例与自主化开发同步构建。

对于空间资源和极端环境领域，地球工程车辆安全为安全移动作业提供近期实验室。装载机、挖掘机、开沟机、打桩系统和运输卡车提供真实任务，能够在将同一逻辑推向月球或星球作业前，研究移动、工作装置控制、物料交互、监督和监控。

### 9.4 局限性

本文有五项局限。

第一，若干标准通过官方状态页、公开预览页面或映射性二手材料使用。条款级主张需要授权全文访问和最终核验。相邻标准如 ISO 18497-1:2024 也一样：其公开页面可支撑发布状态、范围摘要和边界讨论，但不能支撑详细条款解释。

第二，公开企业案例仅作为场景锚点。它们不能作为独立安全保证、客户验收、运行 KPI 或长期安全表现证据。

第三，当前框架需要匿名化现场样本。没有现场样本时，它仍是结构化综述和概念框架，尚不构成已验证部署方法。

第四，本文聚焦选定高需求场景：装载机装载、开沟、光伏打桩和自主矿山运输。其他工程车辆，包括起重机、平地机、推土机、压路机、地下矿山机器和农业相邻移动机器，仍需进一步适配。

第五，空间采矿被作为极端环境外推。它对概念压力测试有用，但不提供当前地球标准的直接证据。

### 9.5 结论

自主工程车辆应被理解为移动作业机器系统，而非低速自动驾驶汽车。其安全保证必须覆盖移动、工作装置、物料交互、任务质量、远程监督、现场组织、运行监控和变更管理。

道路车辆安全方法在作为问题结构迁移时仍极具价值。功能安全、预期功能安全、网络安全、AI 安全、场景驱动测试和安全案例可以组织证据链。但评级标签、道路场景假设和道路交通后果模型必须重写。

本文提出的 MWMS、WTDC 和 DMWT 概念，为从安全行驶走向安全作业提供了实用桥梁。它们帮助研究人员深化问题，帮助标准化组织定义任务特定评价指南，也帮助企业建立超越演示的部署证据。核心安全问题在于系统能否安全完成有边界作业、保持假设可见，并随着作业场地变化更新证据。

## 参考文献

[1] International Organization for Standardization. ISO 26262-1:2018 Road vehicles - Functional safety - Part 1: Vocabulary. International Organization for Standardization, Geneva, 2018. https://www.iso.org/standard/68383.html (accessed 2026-06-04).

[2] International Organization for Standardization. ISO 21448:2022 Road vehicles - Safety of the intended functionality. International Organization for Standardization, Geneva, 2022. https://www.iso.org/standard/77490.html (accessed 2026-06-04).

[3] International Organization for Standardization; SAE International. ISO/SAE 21434:2021 Road vehicles - Cybersecurity engineering. International Organization for Standardization, Geneva, 2021. https://www.iso.org/standard/70918.html (accessed 2026-06-04).

[4] International Organization for Standardization. ISO/PAS 8800:2024 Road vehicles - Safety and artificial intelligence. International Organization for Standardization, Geneva, 2024. https://www.iso.org/standard/83303.html (accessed 2026-06-04).

[5] International Organization for Standardization. ISO 34502:2022 Road vehicles - Test scenarios for automated driving systems - Scenario based safety evaluation framework. International Organization for Standardization, Geneva, 2022. https://www.iso.org/standard/78951.html (accessed 2026-06-04).

[6] UL Standards. UL 4600 Standard for Safety for the Evaluation of Autonomous Products. Edition 3. UL Standards, Northbrook, IL, 2023. https://www.shopulstandards.com/ProductDetail.aspx?productId=UL4600_3_S_20230317 (accessed 2026-06-04).

[7] International Organization for Standardization. ISO 17757:2019 Earth-moving machinery and mining - Autonomous and semi-autonomous machine system safety. International Organization for Standardization, Geneva, 2019. https://www.iso.org/standard/76126.html (accessed 2026-06-04).

[8] International Organization for Standardization. ISO 19014-1:2018 Earth-moving machinery - Functional safety - Part 1: Methodology to determine safety-related parts of the control system and performance requirements. International Organization for Standardization, Geneva, 2018. https://www.iso.org/standard/70715.html (accessed 2026-06-04).

[9] International Organization for Standardization. ISO 21815-1:2022 Earth-moving machinery - Collision warning and avoidance - Part 1: General requirements. International Organization for Standardization, Geneva, 2022. https://www.iso.org/standard/77302.html (accessed 2026-06-04).

[10] Global Mining Guidelines Group. System Safety for Autonomous Mining Guideline. Global Mining Guidelines Group, 2024. https://gmggroup.org/guideline/ (accessed 2026-06-04).

[11] Gaber, Tarek; El Jazouli, Yassine; Eldesouky, Esraa; Ali, Ahmed. Autonomous Haulage Systems in the Mining Industry: Cybersecurity, Communication and Safety Issues and Challenges. Electronics 10(11): 1357, 2021. doi: 10.3390/electronics10111357. https://www.mdpi.com/2079-9292/10/11/1357 (accessed 2026-06-04).

[12] International Organization for Standardization. ISO 19014-2:2022 Earth-moving machinery - Functional safety - Part 2: Design and evaluation of safety-related parts of the control system. International Organization for Standardization, Geneva, 2022. https://www.iso.org/standard/73568.html (accessed 2026-06-04).

[13] International Organization for Standardization. ISO 19014-3:2018 Earth-moving machinery - Functional safety - Part 3: Environmental performance and test requirements of electronic and electrical components used in safety-related parts of the control system. International Organization for Standardization, Geneva, 2018. https://www.iso.org/standard/70717.html (accessed 2026-06-04).

[14] International Organization for Standardization. ISO 19014-4:2020 Earth-moving machinery - Functional safety - Part 4: Design and evaluation of software and data transmission for safety-related parts of the control system. International Organization for Standardization, Geneva, 2020. https://www.iso.org/standard/70718.html (accessed 2026-06-04).

[15] International Organization for Standardization. ISO 15817:2012 Earth-moving machinery - Safety requirements for remote operator control systems. International Organization for Standardization, Geneva, 2012. https://www.iso.org/standard/46237.html (accessed 2026-06-04).

[16] International Organization for Standardization. ISO 21815-3:2023 Earth-moving machinery - Collision warning and avoidance - Part 3: Risk area and risk level for forward/reverse motion. International Organization for Standardization, Geneva, 2023. https://www.iso.org/standard/77266.html (accessed 2026-06-04).

[17] Global Mining Guidelines Group. Guideline for the Implementation of Autonomous Systems in Mining. Global Mining Guidelines Group, 2024. https://gmggroup.org/guideline/ (accessed 2026-06-04).

[18] 全国标准信息公共服务平台. 国家标准项目《机器人预期功能安全实施指南》. 全国标准信息公共服务平台, 2026. https://std.samr.gov.cn/gb/search/gbDetailed?id=4DFF96682B58A46FE06397BE0A0AC19F (accessed 2026-06-04).

[19] 全国标准信息公共服务平台. GB/T 41862-2022 土方及矿山机械 自主和半自主机器系统安全. 全国标准信息公共服务平台, 2022. https://openstd.samr.gov.cn/bzgk/std/newGbInfo?hcno=841EF14018DC4A78DB015274FFA9DFE3 (accessed 2026-06-04).

[20] 全国标准信息公共服务平台. JB/T 15173-2025 土方机械 无人驾驶非公路自卸车. 全国标准信息公共服务平台, 2025. https://std.samr.gov.cn/hb/search/stdHBDetailedCNF?id=4142E4E8EEA3AA5CE06397BE0A0AAFF7 (accessed 2026-06-04).

[21] 国家标准馆. T/CNCA 116.1-2025 露天矿卡车无人驾驶运输技术要求 第1部分: 总则. 国家标准馆, 2025. https://www.ndls.org.cn/standard/detail/0e25833dc009d87dd580fe4ea8ff2af1 (accessed 2026-06-04).

[22] 国家标准馆. T/ZGCMCA 016-2025 无人驾驶矿用卡车系统安全技术要求. 国家标准馆, 2025. https://www.ndls.org.cn/standard/detail/9312eb254fdc56744719b66bc6e9a80d (accessed 2026-06-04).

[23] 国家标准馆. T/ZGCMCA 023-2024 基于 C-V2X 的无人驾驶矿用卡车运输系统 协同作业技术要求. 国家标准馆, 2024. https://www.ndls.org.cn/standard/detail/90cc2e574ff68fd5c2049e6c95c7312a (accessed 2026-06-04).

[24] SAE International. SAE J3016_202104 Taxonomy and Definitions for Terms Related to Driving Automation Systems for On-Road Motor Vehicles. SAE International, Warrendale, PA, 2021. doi: 10.4271/J3016_202104. https://doi.org/10.4271/J3016_202104 (accessed 2026-06-04).

[25] Scholtes, Maike; Westhofen, Lukas; Turner, Liam R.; Lotto, Katrin; Schuldes, Markus; Weber, Hendrik; Wagener, Nils; Neurohr, Christian; Bollmann, Marcel H.; Körtke, Fabian; Hiller, Jens; Hoss, Michael; Bock, Julian; Eckstein, Lutz. 6-Layer Model for a Structured Description and Categorization of Urban Traffic and Environment. IEEE Access 9: 59131-59147, 2021. doi: 10.1109/ACCESS.2021.3072739. https://doi.org/10.1109/ACCESS.2021.3072739 (accessed 2026-06-04).

[26] International Organization for Standardization. ISO/FDIS 19014-1 Earth-moving machinery - Functional safety - Part 1: Methodology to determine safety-related parts of the control system and performance requirements. International Organization for Standardization, Geneva, n.d. https://www.iso.org/standard/87988.html (accessed 2026-06-04).

[27] International Organization for Standardization. ISO/FDIS 19014-2 Earth-moving machinery - Functional safety - Part 2: Design and evaluation of hardware and architecture requirements for safety-related parts of the control system. International Organization for Standardization, Geneva, n.d. https://www.iso.org/standard/87718.html (accessed 2026-06-04).

[28] International Organization for Standardization. ISO/FDIS 19014-3 Earth-moving machinery - Functional safety - Part 3: Environmental performance and test requirements of electronic and electrical components used in safety-related parts of the control system. International Organization for Standardization, Geneva, n.d. https://www.iso.org/standard/88622.html (accessed 2026-06-04).

[29] International Organization for Standardization. ISO/FDIS 19014-4 Earth-moving machinery - Functional safety - Part 4: Design and evaluation of software and data transmission for safety-related parts of the control system. International Organization for Standardization, Geneva, n.d. https://www.iso.org/standard/87720.html (accessed 2026-06-04).

[30] International Organization for Standardization. ISO/PRF 21815-4 Earth-moving machinery - Collision warning and avoidance - Part 4: Risk area and risk level for swing/rotation motion. International Organization for Standardization, Geneva, n.d. https://www.iso.org/standard/81597.html (accessed 2026-06-04).

[31] International Organization for Standardization. ISO/DIS 21815-5 Earth-moving machinery - Collision warning and avoidance - Part 5: Risk area and risk level for other forms of motion. International Organization for Standardization, Geneva, n.d. https://www.iso.org/standard/89934.html (accessed 2026-06-04).

[32] Construction and Mining Equipment Industry Group; Earthmoving Equipment Safety Round Table; International Council on Mining and Metals. White Paper and Guiding Principles: Functional Safety for Earthmoving Machinery. Version 0.5. Construction and Mining Equipment Industry Group, 2020. https://www.cmeig.com.au/wp-content/uploads/CMEIG-EMESRT-ICMM-White-Paper-and-Guiding-Principles-for-Functional-Safety-on-Earthmoving-Machinery-Ver.-0.5-March-2020.pdf (accessed 2026-06-04).

[33] Chen, Zhi; Yu, Guang; Chen, Peng; Cao, Guang; Li, Zhen; Zhang, Yi; Ni, Hao; Zhou, Baichuan; Sun, Jian; Ban, Heng. MineSim: A scenario-based simulation test system and benchmark for autonomous trucks in open-pit mines. Accident Analysis & Prevention 213: 107938, 2025. doi: 10.1016/j.aap.2025.107938. https://doi.org/10.1016/j.aap.2025.107938 (accessed 2026-06-04).

[34] Meng, Shi; Tian, Bin; Zhang, Xiaotong; Qi, Shuangying; Zhang, Caiji; Zhang, Qiang. OpenMines: A Light and Comprehensive Mining Simulation Environment for Truck Dispatching. In: 2024 IEEE Intelligent Vehicles Symposium (IV), pp. 3043-3049, 2024. doi: 10.1109/IV55156.2024.10588764. https://doi.org/10.1109/IV55156.2024.10588764 (accessed 2026-06-04).

[35] Eriksson, Daniel; Ghabcheloo, Reza; Geimer, Marcus. Automatic Loading of Unknown Material with a Wheel Loader Using Reinforcement Learning. In: 2024 IEEE International Conference on Robotics and Automation (ICRA), 2024. IEEE. doi: 10.1109/ICRA57147.2024.10610221. https://researchportal.tuni.fi/files/126570241/icra2024.pdf (accessed 2026-06-04).

[36] Aoshima, Koji; Wadbro, Eddie; Servin, Martin. Optimizing Autonomous Wheel Loader Performance - An End-to-End Approach. Automation 6(3): 31, 2025. doi: 10.3390/automation6030031. https://www.mdpi.com/2673-4052/6/3/31 (accessed 2026-06-04).

[37] Zhang, Liangjun; Zhao, Jizhong; Long, Pengfei; Wang, Liang; Qian, Li; Lu, Fang; Song, Xiaodong; Manocha, Dinesh. An autonomous excavator system for material loading tasks. Science Robotics 6(55): eabc3164, 2021. doi: 10.1126/scirobotics.abc3164. https://pubmed.ncbi.nlm.nih.gov/34193561/ (accessed 2026-06-04).

[38] Built Robotics. RPD 35 and RPS 25 Solar Piling. Built Robotics, n.d. https://www.builtrobotics.com/solutions/solar-piling (accessed 2026-06-04).

[39] Teng, Shuo; Li, Lin; Li, Yihang; Hu, Xiaosong; Li, Li; Ai, Yutong; Chen, Long. FusionPlanner: A Multi-task Motion Planner for Mining Trucks via Multi-sensor Fusion. Mechanical Systems and Signal Processing 208: 111051, 2024. doi: 10.1016/j.ymssp.2023.111051. https://doi.org/10.1016/j.ymssp.2023.111051 (accessed 2026-06-04).

[40] Guan, Tianyi; He, Ziyang; Song, Ruihua; Manocha, Dinesh; Zhang, Liangjun. TNS: Terrain Traversability Mapping and Navigation System for Autonomous Excavators. In: Robotics: Science and Systems XVIII, 2022. doi: 10.15607/RSS.2022.XVIII.049. https://www.roboticsproceedings.org/rss18/p049.pdf (accessed 2026-06-04).

[41] Teng, Shuo; Li, Xiaowei; Li, Yihang; Li, Lin; Ai, Yutong; Chen, Long. Scenarios Engineering driven Autonomous Transportation in Open-Pit Mines. In: 2023 IEEE 3rd International Conference on Digital Twins and Parallel Intelligence (DTPI), pp. 1-6, 2023. doi: 10.1109/DTPI59677.2023.10365481. https://doi.org/10.1109/DTPI59677.2023.10365481 (accessed 2026-06-04).

[42] Ding, Yize; Luo, Xiaowei. A virtual construction vehicles and workers dataset with three-dimensional annotations. Engineering Applications of Artificial Intelligence 133: 107964, 2024. doi: 10.1016/j.engappai.2024.107964. https://doi.org/10.1016/j.engappai.2024.107964 (accessed 2026-06-04).

[43] Chen, D.; Yin, X. ChatCH: A tailored vision-language framework for automated hazard identification and report generation in construction sites. Advanced Engineering Informatics 66: 103478, 2025. doi: 10.1016/j.aei.2025.103478. https://www.sciencedirect.com/science/article/pii/S1474034625003714 (accessed 2026-06-04).

[44] Naderi, H.; Shojaei, Ali; Agee, Philip; Afsari, Kereshmeh; Akanmu, Abiola. Autonomous Construction-Site Safety Inspection Using Mobile Robots: A Multilayer VLM-LLM Pipeline. arXiv, 2025. doi: 10.48550/arXiv.2512.13974. https://arxiv.org/abs/2512.13974 (accessed 2026-06-04).

[45] 广西柳工机械股份有限公司. 柳工无人驾驶装载机官方页面. 广西柳工机械股份有限公司, n.d. https://www.liugong.com/industry/intelligent/driverless/wheelloader/index.html (accessed 2026-06-04).

[46] 徐工集团. 徐工装载机领跑智能新赛道. 徐工集团, 2024. https://www.xcmg.com/aboutus/news-detail-1128183.htm (accessed 2026-06-04).

[47] Built Robotics. Exosystem and autonomous trenching materials. Built Robotics, n.d. https://www.builtrobotics.com/solutions/trenching (accessed 2026-06-04).

[48] National Aeronautics and Space Administration. Lunar Surface Technology. National Aeronautics and Space Administration, 2026. https://www.nasa.gov/lunar-surface-technology/ (accessed 2026-06-04).

[49] National Aeronautics and Space Administration. Infrastructure Pilot Excavator. National Aeronautics and Space Administration, 2020. https://www.nasa.gov/infrastructure-pilot-excavator/ (accessed 2026-06-04).

[50] National Aeronautics and Space Administration. Regolith Advanced Surface Systems Operations Robot technical materials. NASA Technical Reports Server, 2015. https://ntrs.nasa.gov/citations/20150022134 (accessed 2026-06-04).

[51] National Aeronautics and Space Administration. Lunabotics Challenge. National Aeronautics and Space Administration, 2026. https://www.nasa.gov/learning-resources/lunabotics-challenge (accessed 2026-06-04).

[52] European Space Agency. Second Space Resources Challenge from concept to reality at LUNA. European Space Agency, 2025. https://www.esa.int/Science_Exploration/Human_and_Robotic_Exploration/Second_Space_Resources_Challenge_from_concept_to_reality_at_LUNA (accessed 2026-06-04).

[53] European Space Agency; European Space Resources Innovation Centre. Space Resources Challenge materials. European Space Agency and European Space Resources Innovation Centre, n.d. https://src.esa.int/ (accessed 2026-06-04).

[54] van der Meer, Dennis; Chovet, Loic P.; Garcia, Gabriel M.; Bera, Aniket; Olivares-Mendez, Miguel. REALMS2 - Resilient Exploration And Lunar Mapping System 2 - A Comprehensive Approach. In: 2025 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), 2025. doi: 10.1109/IROS60139.2025.11246516. https://hdl.handle.net/10993/66190 (accessed 2026-06-04).

[55] Lee, Ryan; Younes, Benjamin; Pletta, Alexander; Harrington, John; Wong, Russell Q.; Whittaker, William. CraterGrader: Autonomous Robotic Terrain Manipulation for Lunar Site Preparation and Earthmoving. In: Robotics: Science and Systems XX, 2024. doi: 10.15607/RSS.2024.XX.018. https://www.roboticsproceedings.org/rss20/p018.html (accessed 2026-06-04).

[56] Linde, Mattias; Lindmark, Daniel; Ålstig, Sandra; Servin, Martin. A simulation framework for autonomous lunar construction work. In: Proceedings of the 55th Conference of the International Society for Terrain-Vehicle Systems, pp. 212-222, 2025. International Society for Terrain-Vehicle Systems. https://umu.diva-portal.org/smash/record.jsf?pid=diva2%3A1985377 (accessed 2026-06-04).

[57] Gruetter, Jonas; Terenzi, Luca; Egli, Pascal; Hutter, Marco. Towards Learning Boulder Excavation with Hydraulic Excavators. arXiv, 2025. doi: 10.48550/arXiv.2509.17683. https://arxiv.org/abs/2509.17683 (accessed 2026-06-04).

[58] Lund, Erik. Autonomy for whom? implications of cyber-physical mining systems for operator work and organisation. Applied Ergonomics 132: 104684, 2026. doi: 10.1016/j.apergo.2025.104684. https://pubmed.ncbi.nlm.nih.gov/41289639/ (accessed 2026-06-04).

[59] Zhai, Yifan; Terenzi, Lorenzo; Frey, Patrick; Garcia Soto, Diego; Egli, Pascal; Hutter, Marco. ExT: Towards Scalable Autonomous Excavation via Large-Scale Multi-Task Pretraining and Fine-Tuning. arXiv, 2025. doi: 10.48550/arXiv.2509.14992. https://arxiv.org/abs/2509.14992 (accessed 2026-06-04).

[60] International Organization for Standardization. ISO 18497-1:2024 Agricultural machinery and tractors - Safety of partially automated, semi-autonomous and autonomous machinery - Part 1: Machine design principles and vocabulary. International Organization for Standardization, Geneva, 2024. https://www.iso.org/standard/82684.html (accessed 2026-06-04).
