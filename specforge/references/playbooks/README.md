# Playbooks

`playbooks/` 用于沉淀不同类型需求的方案生成规则。SpecForge 生成方案时先判断需求类型，再读取对应 playbook，避免每次只套用通用模板。

## 使用顺序

1. 先读取 `SpecForge.md` 和 `📦 项目总览.md`。
2. 识别项目后读取 `project/*.md`。
3. 判断需求类型，读取一个或多个 playbook。
4. 按 `templates/acceptance-checklist.md` 做质量门禁。

## 类型索引

| 需求类型 | 适用场景 | 文件 |
| --- | --- | --- |
| 前端交互类 | 新增入口、页面、编辑态、弹窗、抽屉、表单、图表交互 | `frontend-interaction.md` |
| 后台管理类 | 列表、筛选、权限配置、运营操作、审计记录 | `admin-console.md` |
| 模型/数据/任务流类 | 模型部署、测评、上传、异步任务、数据处理 | `model-data-taskflow.md` |
| 权限审批类 | 用户角色、角色权限、举报、审批、处理流 | `permission-approval.md` |
| 运维部署类 | 部署、资源、监控、日志、告警、回滚、容量 | `ops-deployment.md` |

## 组合规则

- 一个需求可以命中多个 playbook，例如“模型部署后适应测试”应同时读取模型/数据/任务流类和运维部署类。
- 涉及页面变化时，必须同时应用前端交互类的原型规范。
- 涉及角色、权限、审批、举报、处理动作时，必须同时应用权限审批类。
