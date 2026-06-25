# 日志查询 log-query

## 项目定位

log-query 是对内日志查询平台。

## 业务范围

- 对内日志查询
- DUI 日志查询
- 海外分支日志查询
- 日志筛选、检索和结果展示

## 技术栈

| 项 | 内容 |
| --- | --- |
| 前端 | Vue2 + Webpack |
| Node | 14/16 |
| 包管理 | yarn |
| 主要环境 | test/prod |

## 环境与地址

| 环境 | 地址 |
| --- | --- |
| test | https://bigdata-t.duiopen.com/logquery/#/DUI |
| prod | https://bigdata.aispeech.com.cn/logquery/#/DUI |

## 仓库与部署

| 项 | 内容 |
| --- | --- |
| Git | https://git.aispeech.com.cn/analytics/log-query-platform-lt |
| 分支 | test: 主开发；ex_overseas: 海外分支 |
| 世界之树 | bdp-log-query-platform-lt |

## 运行命令

```bash
yarn install
yarn dev
```

## 账号与权限

- 账号：jingjing.lu
- 密码：见密码管理器/联系负责人。

## 常见研发规则

- Vue2 + Webpack 项目，修改方案要避免引入 Vue3 写法。
- Node 版本需注意 14/16 兼容，node-sass 可能需要额外处理。
- 涉及海外分支时，要确认分支 `ex_overseas` 与主分支差异。
- 日志查询需求必须关注时间范围、分页、结果导出、字段权限和查询性能。

## 常见风险

- node-sass 版本兼容问题。
- 海外分支与主分支代码差异导致方案不能直接复用。
- 大范围查询导致接口慢、超时或页面渲染卡顿。

## 数字人生成方案时要特别关注

- 对内用户角色
- 主分支/海外分支差异
- 查询性能和超时
- 字段权限和敏感字段
- Vue2 项目限制
