# 日志查询 log-search

## 项目定位

log-search 是对外日志查询平台。

## 业务范围

- 对外日志查询
- 外部用户登录和查询
- 日志筛选、检索和结果展示

## 技术栈

| 项 | 内容 |
| --- | --- |
| 前端 | Vue2 + Webpack + TypeScript |
| Node | 14/16 |
| 包管理 | yarn |
| 主要环境 | test/prod |

## 环境与地址

| 环境 | 地址 |
| --- | --- |
| prod | http://open.bigdata.duiopen.com/logsearch/#/login |

## 仓库与部署

| 项 | 内容 |
| --- | --- |
| Git | https://git.aispeech.com.cn/analytics/external-log-search-platform-frontend |
| 分支 | test |
| 世界之树 | bdp-log-search-front |

## 运行命令

```bash
yarn install
yarn dev
```

## 账号与权限

- 账号：按项目权限获取。
- 密码：见密码管理器/联系负责人。

## 常见研发规则

- Vue2 + Webpack 项目，修改方案要避免引入 Vue3 写法。
- Node 版本需注意 14/16 兼容。
- 涉及日志查询时，需要关注查询条件、时间范围、分页、导出和大数据量性能。
- 对外日志查询要注意权限边界和敏感字段脱敏。

## 常见风险

- node-sass 版本兼容问题。
- 大范围日志查询可能导致接口慢或页面卡顿。
- 对外系统错误信息不能暴露内部细节。

## 数字人生成方案时要特别关注

- Vue2 技术栈限制
- 查询性能
- 时间范围和分页
- 字段脱敏
- 对外用户权限
