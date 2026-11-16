**These rules are provided for personal use only; availability for other users is not guaranteed.**

> 「凡所有相，皆是虛妄。若見諸相非相，則見如來。」
>
> Last updated: **November 16, 2026, 9:28 AM (UTC+8)** Added KirinBeer Release Version

The rules are collected and maintained according to actual usage, personal network conditions, preferred services, proxy nodes, ISP, DNS configuration, and individual requirements.

They are **not intended to be a universal ruleset**, and there is no guarantee that they will work correctly or provide the expected routing behavior in other environments.

Use these rules at your own discretion.

---

# Smart Group Config for OpenClash

一套以 **Smart 智能测速 + 节点质量分级 + 地区分类** 为核心的 OpenClash 配置方案。

本项目通过 **OpenClash Override 节点重命名预处理 + 正则过滤 + Smart 策略组**，将不同机场的节点统一标准化，实现多机场节点的自动分类、自动测速与智能切换。

> **核心理念：**
>
> **统一节点命名 → 按地区 / 等级自动分类 → Smart 自动测速 → 自动选择最优节点**

适合同时使用多个机场，并希望减少手动维护策略组、节点列表的用户。

本目录提供四套 OpenClash 配置，分别针对不同的使用需求。

## 📦 四个版本的区别

| 版本 | 核心策略 | 定位 | 推荐 |
|---|---|---|---|
| **Smart Group Release Version** | Smart + LightGBM | 功能完整版 | ⭐⭐⭐⭐⭐ |
| **Smart Group Release Version lite** | Smart + LightGBM | 轻量化 Smart | ⭐⭐⭐⭐⭐ |
| **Urltest Release Version lite** | URLTEST | 简单自动测速 | ⭐⭐⭐⭐ |
| **KirinBeer Release Version** | Smart + LightGBM | 链式代理 / 住宅节点 / 媒体线路 | ⭐⭐⭐⭐⭐ |

---

### 🧠 Smart Group Release Version

**完整版 Smart 配置。**

保留完整的 Smart 策略、LightGBM、节点分类、地区策略以及较完整的规则体系。

适合希望获得完整功能，并愿意承担更高配置复杂度的用户。

> **关键词：功能完整 / Smart / LightGBM / 高度可定制**

---

### ⚡ Smart Group Release Version lite

**Smart 轻量版。**

保留 Smart + LightGBM 的核心能力，同时精简策略组和部分规则，降低配置复杂度。

适合日常长期使用。

> **关键词：Smart / LightGBM / 轻量 / 日常使用**

---

### 🚀 Urltest Release Version lite

**URLTEST 轻量版。**

不使用 Smart 和 LightGBM，而是使用 Mihomo 原生 `url-test` 策略，根据实时测速结果自动选择节点。

配置更加简单，资源占用和维护成本也更低。

> **关键词：URLTEST / 实时测速 / 简单 / 低维护**

---

### 🍺 KirinBeer Release Version

**面向多机场、链式代理与多类型线路管理的 Smart 配置。**

KirinBeer 在 Smart + LightGBM 智能测速的基础上，加入链式代理、住宅节点以及媒体专用节点组，进一步细分不同类型的节点资源。

主要特点：

* 🧠 **Smart + LightGBM**：自动测速与智能节点选择。
* ⭐ **PRM / BSC 节点分级**：区分优质节点与基础节点，分别建立节点池。
* 🏠 **Residential 住宅节点**：通过 `Resi` / `Native` 等关键词识别住宅线路。
* 🔗 **链式代理**：通过 `RLY-ENTER` 入口策略组与 `LXY-RLY` 链式节点提供商，实现入口与出口节点组合。
* 🌏 **地区策略组**：提供香港、新加坡、日本等地区节点分类。
* 🎬 **媒体专用节点**：提供 `Media HKG`、`Media JPN` 策略组，方便选择适合媒体服务的线路。
* 📥 **独立下载策略**：通过 `Download` 策略组筛选 DL / BT 节点。
* 📚 **细分规则分流**：覆盖 Emby、YouTube、Netflix、TikTok、ChatGPT、Telegram、WhatsApp、Apple、Microsoft、Steam 等常用服务。

**适合希望将普通节点、优质节点、住宅线路、链式代理和媒体线路分开管理的用户。**

> **关键词：Smart / LightGBM / Chain Relay / Residential / Media / 多机场管理**

**使用注意：**

1. 需要使用支持 Smart 功能的 OpenClash / Mihomo 内核。
2. 需要根据自己的机场订阅填写对应的订阅地址。
3. 链式代理需要正确配置入口节点与出口节点，并确保节点名称符合对应 Filter 的匹配条件。
4. 使用前请修改配置中的控制器密钥，并检查监听端口的访问范围。

配置文件：[KirinBeer Release Version.yaml](https://github.com/chungccc/yaml-config/blob/main/openclashYAML/KirinBeer%20Release%20Version.yaml)

---

## 🔍 如何选择？

**想要最完整的功能：**

`Smart Group Release Version.yaml`

**想要 Smart，同时兼顾简洁和性能：**

`Smart Group Release Version lite.yaml`

**只想要简单可靠的自动测速：**

`Urltest Release Version lite.yaml`

**需要链式代理、住宅节点和媒体专用节点组：**

`KirinBeer Release Version.yaml`

---

## 📊 版本功能对比

| 配置 | Smart 完整版 | Smart Lite | URLTEST Lite | KirinBeer |
|---|---|---|---|---|
| 核心策略 | Smart | Smart | URLTEST | Smart |
| LightGBM | ✅ | ✅ | ❌ | ✅ |
| 智能评分 | ✅ | ✅ | ❌ | ✅ |
| 实时测速 | ✅ | ✅ | ✅ | ✅ |
| PRM / BSC | ✅ | ✅ | ✅ | ✅ |
| 地区分类 | ✅ | ✅ | ✅ | ✅ |
| 多机场管理 | ✅ | ✅ | ✅ | ✅ |
| 链式代理 | — | — | — | ✅ |
| Residential | — | — | — | ✅ |
| 媒体专用节点组 | — | — | — | ✅ |
| 规则分流 | 完整 | 精简 | 精简 | 细分 |
| 配置复杂度 | 较高 | 中等 | 较低 | 较高 |

> 注：表格展示的是各版本的主要定位与功能侧重点，具体功能以对应 YAML 文件为准。

---

## 🎯 KirinBeer 主要策略组

| 策略组 | 用途 |
|---|---|
| `SMART` | PRM 优质节点智能选择 |
| `SMART-BSC` | BSC 基础节点智能选择 |
| `Residential` | 住宅 / 原生线路 |
| `HKG` | 香港优质节点 |
| `SGP` | 新加坡优质节点 |
| `JPN` | 日本优质节点 |
| `HK-Basic` | 香港基础节点 |
| `SG-Basic` | 新加坡基础节点 |
| `JP-Basic` | 日本基础节点 |
| `RLY-ENTER` | 链式代理入口节点 |
| `MIX-RLY` | 香港 / 新加坡等链式出口节点 |
| `HKG-RLY` | 香港链式出口 |
| `SGP-RLY` | 新加坡链式出口 |
| `JPN-RLY` | 日本链式出口 |
| `Media HKG` | 香港媒体线路 |
| `Media JPN` | 日本媒体线路 |
| `Manual Choice` | 手动选择节点 |
| `Download` | 下载 / BT 节点 |

---

## ✨ 核心特性

* 🧠 **Smart 智能测速**：自动选择当前延迟和质量更好的节点
* 🌏 **地区自动分类**：HK / JP / SG / US 等地区独立 Smart
* ⭐ **节点质量分级**：通过 `PRM` / `BSC` 区分优质与普通节点
* 🔄 **多机场统一管理**：不同机场的节点统一命名规则
* 🏷️ **机场来源识别**：通过节点前缀快速区分机场来源
* 📡 **自动故障切换**：节点不可用时自动切换其他可用节点
* 🔗 **链式代理**：支持入口与出口节点组合
* 🏠 **住宅线路管理**：独立识别住宅 / 原生节点
* 🎬 **媒体线路管理**：提供独立媒体节点策略组
* 📚 **Rule-Providers**：规则集采用远程引用，方便更新
* 🗺️ **GEO 数据库**：结合 GEOSITE / GEOIP 处理常规国内外分流
* 🎨 **Zashboard UI**：提供配套的策略组图标和界面配置
---

> 「應無所住而生其心」
>
> Last updated: **August 24, 2026**
