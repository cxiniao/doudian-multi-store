# 店阵 ShopMatrix — 抖店多店铺管理系统

> 一套桌面端的抖店（抖音小店）多账号聚合管理工具：一个窗口管理所有店铺的商品、违规、财务、发票与营销任务。
> Doudian (Douyin Shop) multi-store management desktop app — one window for all your shops.

![Python](https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-latest-009688?logo=fastapi&logoColor=white)
![Vue](https://img.shields.io/badge/Vue-3-4FC08D?logo=vuedotjs&logoColor=white)
![Naive UI](https://img.shields.io/badge/Naive%20UI-latest-4FC08D)
![License](https://img.shields.io/badge/License-Commercial-lightgrey)

<img width="2880" height="1620" alt="控制台" src="https://github.com/user-attachments/assets/83c60a16-234e-43c0-9fb5-bafaec55764b" />


## 为什么需要它

运营多个抖店时，你是否每天都在：

- 在多个浏览器、多个登录态之间反复切换，逐店查看数据；
- 手动逐店统计商品、销量、体验分、可提现余额，再汇总到 Excel；
- 错过违规罚单的申诉/整改窗口，保证金白白被扣；
- 发票、对账、涉税报送逐店核对，耗时且容易出错。

**店阵把这一切收进一个本地窗口：所有店铺一屏总览，批量任务一键执行，数据实时同步。**

## 功能一览

### 🏪 多店铺管理

批量添加店铺、独立浏览器配置（防关联）、授权到期提醒、卡密续费、Cookie 失效一键重新登录。

<img width="2880" height="1620" alt="店铺管理" src="https://github.com/user-attachments/assets/3331a29f-a05c-4a3f-af05-9d7d7392cd5a" />


### 📊 经营控制台

健康度、成交金额/订单/客单价、流量漏斗、体验分预警、授权到期预警——9 类店铺状态一屏掌握。

### ⚠️ 违规管理

批量拉取各店铺违规罚单，情节等级、处罚方式、申诉/整改/考试状态一目了然，点击即看违规详情与规则解读，不再错过处理时限。

<img width="2880" height="1620" alt="违规管理" src="https://github.com/user-attachments/assets/cce422d7-fe8a-4f86-85f0-f8e7ffbb7c16" />

### 📦 商品管理

跨店铺商品聚合查询（86+ 商品秒级加载），支持批量上下架、批量改库存、发货时效修改、回收站管理，多关键词多店铺并发查询。

<img width="2880" height="1620" alt="商品管理" src="https://github.com/user-attachments/assets/05d15bdf-9e10-4d1c-af19-3c6375a204ab" />


### 🔍 鉴图排查

批量扫描商品标题、主图、SKU 图、详情图中的违禁词与联系方式（手机号），发现违规自动下架，防患于未然。

<img width="2880" height="1620" alt="鉴图排查" src="https://github.com/user-attachments/assets/7d904ca1-f576-4edf-84eb-5bba90db0d98" />



### ⚡ 限量抢购助手

批量创建限时/限量抢购活动：按百分比或固定库存设置活动库存、折扣、每人限购、预热时间、自动取消时间，支持活动批量管理与作废。

<img width="2880" height="1620" alt="限量抢购" src="https://github.com/user-attachments/assets/583bf4c3-b142-4c66-af11-a5e614e45097" />


### 💡 商机提报与商机收藏

拉取全网商机热词（热度、成交金额、增速、供需比、在线商品数），一键筛选蓝海词并批量提报，支持商机收藏管理。

<img width="2880" height="1620" alt="商机收藏" src="https://github.com/user-attachments/assets/24597265-2ff7-493d-8dbc-69cec4e8d7c7" />


### 💰 财务管理

资金流水明细、赔付账单、千川消耗、涉税信息报送四大报表，按店铺/时间聚合查询，一键导出 Excel 对账。

<img width="2880" height="1620" alt="财务管理" src="https://github.com/user-attachments/assets/417c255f-91d2-487a-806d-f64ed889a7f2" />


### 🧾 发票管理

跨店铺发票状态聚合：待开票/已开票/已作废、开票超时提醒、买家催开票标记，批量开票不错单。

<img width="2880" height="1620" alt="发票管理" src="https://github.com/user-attachments/assets/aa3a4f70-9edd-48c2-836c-f684cca70b2e" />


### 🗂 任务中心

所有批量任务实时进度、日志与失败明细集中管理，关页不丢任务。

<img width="2880" height="1620" alt="任务中心" src="https://github.com/user-attachments/assets/6efca1e3-f6aa-422f-aa76-9ff0042749df" />


### 🧹 缓存管理

可视化各店铺浏览器缓存占用，一键清理，支持每日自动清理。

## 技术架构

| 层 | 技术 |
|---|---|
| 桌面壳 | pywebview（Windows） |
| 后端 | FastAPI + SQLite（本地运行，数据不出本机） |
| 前端 | Vue 3 + Pinia + Naive UI + Vite |
| 自动化 | Playwright 浏览器实例（店铺隔离 profile） |
| 授权/升级 | 卡密授权体系 + 在线增量更新 |

- 本地服务监听 `127.0.0.1`，店铺 Cookie 加密存储，不上传第三方；
- 前后端分离架构（`src/api` → `src/services` → `src/utils/douyin`），模块边界清晰，易于二开。

## 适用对象

- 多抖店商家 / 矩阵店铺运营团队
- 电商代运营公司 / 服务商
- 需要 OEM 贴牌交付客户的软件开发商

## 合作模式

本项目面向商业合作开放以下模式：

| 模式 | 说明 |
|---|---|
| **OEM 贴牌** | 换品牌 LOGO/名称/配色，交付独立安装包，快速形成你自己的产品 |
| **二次开发** | 提供源码与架构文档，支持新增模块、对接你的系统 |
| **功能定制** | 按需求定制专属功能（如类目自动化、数据看板、多平台扩展） |
| **源码授权** | 商业授权买断，含部署指导与技术支持 |

> 联系我们：微信（ReloadingPeacemaker_）/ QQ（467841603），需注明来意。

## 声明

本工具仅用于商家合法管理自有店铺，使用时请遵守抖音电商平台相关协议与规则。页面截图均为演示数据。
