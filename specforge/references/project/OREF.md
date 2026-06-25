# OREF

## 项目定位

OREF 是对外平台，主要面向上海交大等外部用户，提供数据集、模型相关能力。

## 业务范围

- 对外数据集使用
- 对外模型使用
- 登录与外部用户访问
- 和 openxhub 相关的外部访问链路

## 技术栈

| 项 | 内容 |
| --- | --- |
| 前端 | Vue3 + Vite + ElementPlus + TypeScript |
| Node | >=18 |
| 包管理 | pnpm |
| 主要环境 | test/prod |

## 环境与地址

| 环境 | 地址 |
| --- | --- |
| prod | https://open.bigdata.duiopen.com/openxhub/#/login |

## 仓库与部署

| 项 | 内容 |
| --- | --- |
| Git | https://git.aispeech.com.cn/analytics/dataset-management-web-external |
| 分支 | test |
| 世界之树 | bdp-openxhub-web |

## 运行命令

```bash
pnpm install
pnpm dev
```

## 账号与权限

- 账号：jingjing.lu@aispeech.com
- 密码：见密码管理器/联系负责人

## 常见研发规则

- 方案要考虑外部用户访问体验和权限边界。
- 对外环境的异常提示要清晰，避免暴露内部系统细节。
- 涉及数据集或模型时，需要确认外部用户的数据范围、资源权限和下载/使用限制。

## 常见风险

- 外部用户权限和内部用户权限混淆。
- 对外地址和内部环境能力不一致。
- 需求如果复用数据集项目能力，需要确认接口、路由和权限是否一致。

## 数字人生成方案时要特别关注

- 外部用户角色
- 对外访问权限
- 页面空状态和错误提示
- 数据范围隔离
- 与数据集/模型平台能力的复用关系
