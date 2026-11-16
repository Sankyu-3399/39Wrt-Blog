---
title: 'SoftBank Air6 ( A775 )'
published: 2026-11-17
description: 'SoftBank Air6（A775）的硬件规格、39Wrt 技术预览版线刷步骤，以及 FWA WebUI 的首次设置。'
tags: [FWA, 5G, CPE]
category: '开发进度记录'
draft: false
---

**SoftBank Air6（A775）是 SoftBank 推出的 5G 家用路由器，支持 Wi-Fi 7。** 这次为 Air6 准备了 39Wrt 技术预览版。下面记录设备的硬件规格、Windows 下的线刷步骤，以及刷机后如何完成首次设置。

## 硬件规格

- **处理器与平台**：搭载联发科 T830 平台（Quectel RG620T-SBK）。
- **存储规格**：2 GB DDR4 内存 + 4 GB 闪存。
- **网口配置**：2 个千兆网口（1 Gbps）。
- **USB 接口**：1 个 USB-A 端口，可在 RC 与 EP 模式之间切换。
- **SIM 卡支持**：单 Nano SIM 卡槽，支持 5G SA/NSA 双模。
- **Wi-Fi 标准**：支持 **Wi-Fi 7（MT7996AV + MT7976GN + MT7977BN + MT7977AN）**，无线硬件规格为 **BE19000**，支持 **MLO** 和 **6 GHz** 频段。

网口、无线频段及 MLO 支持情况可参阅 [SoftBank 官方规格](https://www.softbank.jp/support/faq/view/195409)。

## 刷机前准备

- **电脑**：一台 Windows PC。
- **数据线**：一条 USB-A 转 USB-A 或 USB-A 转 USB-C 数据线，用于连接 Air6 机身电源接口旁的 USB-A 端口与电脑。**只有充电功能的线不能用于刷机。**

先下载并解压 SP Tools 工具包，再安装包内的 `VC_redist.x86`、`VC_redist.x64` 和 `Driver` 驱动。

<a class="no-styling not-prose btn-regular !inline-flex min-h-11 max-w-full rounded-lg px-4 py-2 font-bold" href="http://pan.39network.cc:5212/f/5NWh1/SPFlashTool.zip" aria-label="点我下载 SP Tools 工具包">点我下载</a>

安装完成后，加入下方 QQ 群，从群文件中下载我提供的 **SoftBank Air6（A775）线刷包**，并解压。

<a class="no-styling not-prose btn-regular !inline-flex min-h-11 max-w-full rounded-lg px-4 py-2 font-bold" href="https://qm.qq.com/q/I4tYjKK16S">点击链接加入群聊【softbank air6开源玩机】</a>

## 线刷步骤

### 载入线刷包

1. 打开 **SPFlashToolV6**，勾选左侧的 **自动重启**。
2. 点击 **Download-XML** 右侧的 **选择**，打开线刷包内 `download_agent` 文件夹中的 `flash.xml`。

![SPFlashToolV6 初始界面：左侧勾选「自动重启」，上方为 Download-XML 文件选择栏](./images/01-sp-flash-tool.png)

### 选择固件升级

载入 `flash.xml` 后，在「下载」页的模式下拉框中选择 **固件升级**。位置见下图红框。

:::caution[务必保留原厂校准数据]

**按本文步骤刷机，只选「固件升级」。务必不要选「全部格式化和下载」。** 全盘格式化会清除这台设备的原厂校准数据，可能显著影响无线电性能和相关功能。

除非你明确知道为何需要全盘格式化，并且有办法恢复本机的原厂校准数据，否则不要尝试。**即使他人或 AI 告诉你这个选项是安全的，也不要照做。**

:::

![载入 flash.xml 后的界面：确认红框内的下拉框显示「固件升级」](./images/02-firmware-upgrade.png)

### 写入固件

**写入期间不要拔掉数据线，也不要切断 Air6 或电脑的电源。**

1. 保持 Air6 断电，先点击 SPFlashToolV6 中的 **下载** 按钮。
2. 用数据线将 Air6 的 USB-A 端口连接到 Windows 电脑。
3. 确认已点击 **下载**，且数据线两端都接稳后，再给 Air6 接通电源。工具会自动识别设备，写入 **39Wrt 系统和新版基带固件**。
4. 等待工具提示写入完成，再让设备自动重启并开机。

## 首次开机

刷机后默认使用全新的 **39Wrt FWA WebUI**。这套界面为 FWA 设备设计，首次使用时按向导设置即可。

1. 连接 Air6，在浏览器里打开默认管理地址 `192.168.39.1`。系统默认未设置 `root` 密码。
2. 在 FWA WebUI 中完成设备初始化向导。
3. **完成初始化后，LuCI 才会启动。** LuCI 使用设备的 `81` 和 `444` 端口。

## 版本说明

**当前版本仅为技术预览版。** 部分功能还在开发，一些已实现的功能也还没有接入管理面板，后续会逐步补齐。
