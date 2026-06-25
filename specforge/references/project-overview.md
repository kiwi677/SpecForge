# 项目总览

本文件作为数字人的项目索引页，用于帮助数字人快速判断需求属于哪个项目，并按需读取 `project/` 目录下的单项目知识库。

## 项目速查

| 项目 | 一句话定位 | 技术栈 | Node | 包管理 | 环境 | 知识库 |
| --- | --- | --- | --- | --- | --- | --- |
| OREF | 对外提供数据集、模型相关能力，主要面向上海交大等外部用户 | Vue3 + Vite + ElementPlus + TS | >=18 | pnpm | test/prod | [OREF](project/OREF.md) |
| AI平台 | 覆盖概览、个人空间、模型服务、数据服务、原子能力、超算平台等能力 | Monorepo + Vue3 + Vite | >=18 | pnpm | master/test | [AI平台](project/AI平台.md) |
| 数据集 | 管理物理、逻辑、众标数据集，包含任务管理、后台管理、数据预览、上传规范 | Vue3 + Vite + ElementPlus + TS | >=18 | pnpm | test/beta/prod | [数据集](project/数据集.md) |
| 苏州大数据局 | 对接苏州大数据局，包含模型训练和管理后台 | Vue3 + Vite + ElementPlus + TS | >=18 | pnpm | test/beta/prod | [苏州大数据局](project/苏州大数据局.md) |
| 日志查询 log-search | 对外日志查询平台 | Vue2 + Webpack + TS | 14/16 | yarn | test/prod | [日志查询-log-search](project/日志查询-log-search.md) |
| 日志查询 log-query | 对内日志查询平台 | Vue2 + Webpack | 14/16 | yarn | test/prod | [日志查询-log-query](project/日志查询-log-query.md) |
| DataAgent | 智能数据分析、text2sql、数据配置 | Vue3 + Vite + ElementPlus + TS | >=18 | pnpm | test/prod/ex/szaic | [DataAgent](project/DataAgent.md) |
| DP 数据分析、BI-platform | 数据分析和 BI 看板平台，覆盖 model、reporter、dashboard | Vue2 + Webpack4 + ECharts | 待补充 | 待补充 | prod | [dp](project/dp.md) |

## 数字人读取规则

当用户输入需求时，数字人应先判断需求所属项目，再读取对应项目知识库：

- 出现“模型、训练、测试、模型服务、数据服务、原子能力、超算平台、AI平台、MLOps”时，优先读取 `project/AI平台.md`。
- 出现“数据集、物理数据集、逻辑数据集、众标、数据预览、上传规范、任务管理”时，优先读取 `project/数据集.md`。
- 出现“OREF、openxhub、上海交大、对外数据集、对外模型”时，优先读取 `project/OREF.md`。
- 出现“苏州大数据局、szaic、模型训练、管理后台、mp-beta、szsuanli”时，优先读取 `project/苏州大数据局.md`。
- 出现“log-search、对外日志、外部日志查询”时，优先读取 `project/日志查询-log-search.md`。
- 出现“log-query、对内日志、DUI 日志查询、海外日志分支”时，优先读取 `project/日志查询-log-query.md`。
- 出现“DataAgent、智能数据分析、text2sql、数据配置、扬州公积金、苏州园区”时，优先读取 `project/DataAgent.md`。
- 出现“DP 数据分析、BI-platform、BI、看板、dashboard、report、reporter、图表、model、数据分析、下钻、联动、多变量筛选”时，优先读取 `project/dp.md`。
- 如果需求无法判断项目，先询问用户项目归属；用户回答后，如果是已有项目则读取对应项目文件，如果是新项目则先引导用户补齐项目信息并创建新的 `project/项目名.md`，再生成方案。

## 项目匹配置信度规则

| 置信度 | 判断标准 | 处理方式 |
| --- | --- | --- |
| 高 | 用户明确说出项目名，或需求关键词只命中一个项目且模块高度吻合 | 直接读取对应 `project/*.md` 并生成方案 |
| 中 | 关键词命中一个主项目，但可能涉及相邻系统或复用能力 | 按最可能项目生成初版，并在“问题”板块确认项目归属或依赖边界 |
| 低 | 关键词命中多个项目，或只描述通用能力，没有项目、模块、技术栈线索 | 先询问用户项目归属，不强行生成方案 |
| 新项目 | 用户明确说明是新项目，或当前速查表没有对应项目 | 先按新项目入库规则创建 `project/项目名.md`，再生成方案 |

当置信度为中或低时，不能假装已经完全确认项目；必须把不确定项写入“问题”或先追问。

## 新项目入库规则

当用户提供的项目不在当前项目速查表中时，数字人需要先补齐项目知识库，再继续生成需求方案。

新项目最小信息：

| 信息 | 说明 |
| --- | --- |
| 项目名称 | 用于生成 `project/项目名.md` |
| 项目定位/业务范围 | 说明项目是做什么的、面向谁 |
| 技术栈 | 前端/后端/组件库/Node/包管理等 |
| 运行环境和地址 | test/beta/prod 等环境 |
| 仓库/分支/运行命令 | Git 地址、主要分支、本地启动方式 |
| 账号权限说明 | 只记录账号和获取方式，不记录明文密码 |
| 生成方案时需要特别关注 | 项目特有风险、模块边界、研发偏好 |

入库要求：

- 新项目文件使用 `project/README.md` 中的单项目模板。
- 信息缺失时允许写“待补充”。
- 新增项目后同步更新本总览的项目速查表和读取规则。
- 不记录明文密码、token、SSH 密码、生产账号密码。

## 通用研发偏好

- 前端方案优先贴合现有技术栈，不引入额外框架。
- Vue3 项目默认按 Vue3 + Vite + ElementPlus + TypeScript 方案拆分页面、组件和状态。
- Vue2 项目默认注意 Webpack、Node 版本、node-sass 兼容和 yarn 依赖。
- 涉及模型、部署、异步处理、文件上传的需求，必须补充任务状态、失败原因、权限边界、日志监控和运维事项。
- 涉及文件上传的需求，必须补充格式、大小、上传进度、失败重试、存储位置和清理策略。
- 涉及后台管理的需求，必须补充角色权限、数据范围、操作审计和异常状态。
- 涉及页面、入口、编辑态、弹窗、抽屉、图表或看板交互的需求，必须提供带业务细节的一张或多张原型图。
- 涉及权限、审批、举报、处理流的需求，必须补充权限粒度、状态枚举、处理动作、并发和审计日志。
- 涉及模型、数据、部署、测评和异步任务的需求，必须补充任务状态、指标口径、错误码、日志监控和资源容量。

## 常用链接

| 类型 | 地址 |
| --- | --- |
| GitLab | https://git.aispeech.com.cn |
| 世界之树 | http://console.talkinggenie.com/portal-devops/#/portal-release/releaseStatus |
| Docker 仓库 | https://daoker.dui.ai/users/login?next=/aibuild/project-node |

## 安全说明

- 项目知识库不建议保存明文密码、SSH 密码、生产账号密码或敏感 token。
- 如确需记录账号信息，只记录账号名、环境和获取方式；密码统一写“见密码管理器/联系负责人”。
- 数字人生成方案时不得主动输出敏感账号、密码、token、SSH 跳板机密码等信息。
