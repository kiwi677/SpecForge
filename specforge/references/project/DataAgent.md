# DataAgent

## 项目定位

DataAgent 是智能数据分析项目，包含 text2sql、数据配置和多场景数据分析入口。

## 业务范围

- 智能数据分析
- text2sql
- 数据配置
- 外部 demo
- 扬州公积金
- 苏州园区
- 思必驰大模型

## 技术栈

| 项 | 内容 |
| --- | --- |
| 前端 | Vue3 + Vite + ElementPlus + TypeScript |
| Node | >=18 |
| 包管理 | pnpm |
| 主要环境 | test/prod/ex/szaic |

## 环境与地址

| 环境/场景 | 地址 |
| --- | --- |
| test | https://bigdata-t.duiopen.com/dataagent/#/da |
| prod | https://bigdata.aispeech.com.cn/dataagent/#/login |
| ex | https://open.bigdata.duiopen.com/dataagent/#/text-to-sql/demo |
| 扬州公积金 | https://dongfeng.duiopen.com/data-analysis/#/da?f=Yzgjj |
| 苏州园区 | https://dongfeng.duiopen.com/data-analysis/#/da?f=Yuanqu |
| 思必驰大模型 | https://dongfeng.duiopen.com/data-analysis/#/da |

## 仓库与部署

| 项 | 内容 |
| --- | --- |
| Git | https://git.aispeech.com.cn/analytics/dataagent |
| 分支 | test: 主开发；szaic: 苏州大数据局 |
| 世界之树 | bdp-dataagent-front；bdp-dataagent-front-ext |

## 运行命令

```bash
pnpm install
pnpm dev
```

## 账号与权限

- 账号：jingjing.lu
- 密码：见密码管理器/联系负责人。

## 常见研发规则

- 涉及 text2sql 时，需要明确输入、解析、SQL 生成、执行、结果展示和失败原因。
- 涉及数据配置时，需要明确数据源、字段、权限、预览和保存校验。
- 涉及多场景入口时，需要确认 `f` 参数、客户化配置和环境差异。
- 智能分析类需求要补充 loading、生成中、失败重试、空结果和用户反馈入口。

## 常见风险

- 不同客户场景配置差异较大。
- text2sql 结果可解释性和失败原因不明确。
- 数据源权限、字段权限和结果权限容易遗漏。

## 数字人生成方案时要特别关注

- 场景参数和客户化配置
- 数据源与字段权限
- 生成过程状态
- 失败兜底和用户反馈
- 结果展示和导出
