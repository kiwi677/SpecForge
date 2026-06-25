# AI平台

## 项目定位

AI平台是 MLOps 相关前端 Monorepo，覆盖概览、个人空间、模型服务、数据服务、原子能力、超算平台等系统。

## 业务范围

- 概览
- 个人空间
- 模型服务
- 数据服务
- 原子能力
- 超算平台
- 数据生产
- 模型管理
- 模型测试
- 模型训练
- 用户管理
- 数据采集
- 线上回流

## 技术栈

| 项 | 内容 |
| --- | --- |
| 前端 | Monorepo + Vue3 + Vite |
| Node | >=18 |
| 包管理 | pnpm |
| 主要环境 | master/test |

## 环境与地址

| 环境 | 地址 |
| --- | --- |
| beta | http://mlops.beta.aispeech.com.cn/aipf/#/login |
| prod | https://mlops.aispeech.com.cn/aipf/#/login |

## 仓库与部署

| 项 | 内容 |
| --- | --- |
| Git | https://git.aispeech.com.cn/eztl/ai-platform-front |
| 分支 | master: 稳定；test: 开发；transsion: 传音 |

## 运行命令

| 子项目 | 命令 |
| --- | --- |
| AI 平台 | `pnpm run dev:aipf` |
| AI 前台（数据生产、模型管理、测试、训练） | `pnpm run dev:afpf` |
| AI 中台（原子能力） | `pnpm run dev:ampf` |
| 线上回流 | `pnpm run dev:reflow` |
| 用户管理 | `pnpm run dev:aaf` |
| 数据采集 | `pnpm run dev:admf` |

## 世界之树映射

| 模块 | 世界之树 |
| --- | --- |
| 外框架/登录/概览/个人空间 | mlops-ai-platform-front |
| 用户管理 | mlops-ai-account-front |
| 数据采集 | mlops-ai-data-manage-front |
| 线上回流 | mlops-ai-reflow-platform-front |
| AI 前台 | mlops-ai-platform-front |
| AI 中台 | mlops-ai-middle-platform-front |

## 账号与权限

- 账号：jingjing.lu
- 密码：见密码管理器/联系负责人

## 常见研发规则

- 涉及模型、训练、测试、部署的需求，需要重点拆任务状态、异常状态、权限和日志。
- Monorepo 内需求要先确认所属子项目和运行命令。
- 模型相关流程通常包含上传、校验、异步任务、状态轮询、结果展示和历史记录。
- 方案中前端事项要明确页面模块、组件拆分、状态管理和跨模块跳转。
- 后端事项要明确接口、状态枚举、错误码、任务 ID、权限和数据一致性。

## 常见风险

- 需求所属子项目不明确，导致运行命令、路由和模块归属错误。
- 异步任务状态不完整，导致前端无法恢复刷新后的任务状态。
- 模型/数据文件上传规则不清，导致联调返工。
- 不同环境 beta/prod 能力或数据不一致。

## 数字人生成方案时要特别关注

- 模型服务/模型测试/模型训练属于哪个子项目
- 是否需要异步部署或异步测试
- 任务状态和错误码
- 文件上传限制
- 权限与数据范围
- 运维资源、日志、监控和回滚
