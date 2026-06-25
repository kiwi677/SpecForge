# DP 数据分析、BI-platform

## 项目定位

DP 数据分析、BI-platform 是数据分析和 BI 看板平台，围绕 model、reporter、dashboard 三类核心对象，支持从数据源建模到图表分析，再到看板组合展示和交互分析。

## 业务范围

- 模型 model：根据数据源等基本信息配置数据源信息，选择主表，配置表关联关系，设置字段等。
- 分析 reporter：关联模型生成图表，支持表格、柱状图、折线图、饼图、地图等常规图像和相关配置。
- 分析 reporter：支持创建条件过滤、filter 设置等分析配置。
- 看板 dashboard：支持添加多个 reporter。
- 看板 dashboard：支持 reporter 联动、下钻、filter 多变量筛选等交互能力。

## 技术栈

| 项 | 内容 |
| --- | --- |
| 前端 | Vue2 + Webpack4 |
| 图表 | ECharts |
| Node | 待补充 |
| 包管理 | 待补充 |
| 主要环境 | prod |

## 环境与地址

| 环境 | 地址 |
| --- | --- |
| prod | https://bigdata.aispeech.com.cn/data-explore/analysis/reporterlist |

## 仓库与部署

| 项 | 内容 |
| --- | --- |
| Git | https://git.aispeech.com.cn/analytics/BI-platform |
| 分支 | 待补充 |
| 部署 | 待补充 |

## 运行命令

```bash
待补充
```

## 账号与权限

- 账号权限说明：待补充。
- 密码、token、SSH 密码：见密码管理器/联系负责人。

## 常见研发规则

- Vue2 + Webpack4 项目，方案和实现需要避免使用 Vue3 写法。
- 图表相关能力基于 ECharts，需要关注图表实例更新、销毁、resize 和配置兼容。
- model、reporter、dashboard 是核心业务对象，需求方案中要明确对象关系和跳转/编辑边界。
- dashboard 中多个 reporter 可能存在联动、下钻、filter 多变量筛选，新增交互不能破坏现有看板交互。
- 涉及编辑能力时，需要明确查看态、编辑态、权限、保存、取消、脏数据提示和返回路径。

## 常见风险

- 看板点击 reporter 的行为可能已被联动、下钻、选中、高亮、tooltip 等交互占用。
- 直接进入编辑可能改变用户当前浏览看板的路径和上下文，需要保留返回看板的能力。
- reporter 可能存在只读、无权限、已删除、模型变更或数据源失效等异常情况。
- Vue2 + Webpack4 老项目可能存在路由、状态管理和依赖兼容问题。
- 图表点击区域与外层容器点击事件可能冲突，需要区分图表内部交互和进入编辑的触发方式。

## 数字人生成方案时要特别关注

- 需求影响的是 dashboard、reporter 还是 model。
- 当前交互是否会与联动、下钻、filter、多变量筛选冲突。
- 点击任意 reporter 进入编辑的触发范围和优先级。
- 编辑页路由、返回路径和上下文参数。
- 用户权限、只读状态、无权限提示和异常 reporter。
- Vue2 + Webpack4 技术约束。
- ECharts 图表事件和外层点击事件的冲突处理。
