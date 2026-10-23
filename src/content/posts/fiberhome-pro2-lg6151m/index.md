---
title: '烽火Pro2 ( LG6151M )'
published: 2026-10-24
description: '烽火 Pro2（LG6151M）硬件规格与 39Wrt 适配进展，包含蜂窝网络、Wi-Fi 7、短信通话及 LuCI 界面展示。'
tags: [FWA, 5G, CPE]
category: '开发进度记录'
draft: false
---

**烽火 Pro2 是烽火通信推出的旗舰级 5G 移动路由器（插卡上网设备），主打插卡即用、免布线与 Wi-Fi 7 高速体验。**

## 硬件规格

- **处理器与平台**：搭载联发科 T830 平台（Quectel RG620T-EG）。
- **存储规格**：2GB DDR4 内存 + 4GB 闪存。
- **网口配置**：1 个 2.5G 网口（RTL8221B）+ 1 个千兆网口（RTL8211FS）。
- **SIM 卡支持**：单 Nano SIM 卡槽，支持 5G SA/NSA 双模，兼容 n79 等全球主流 5G 频段。
- **Wi-Fi 标准**：支持 **Wi-Fi 7（MT7991AV + MT7976DAN）**，无线规格达到 **BE5000**，支持 **MLO**。

## 适配进展

目前核心功能已完成适配，可以做到**免拆机、无损刷入 39Wrt**。

## 界面展示

### 总览

![总览：系统资源、网络状态与设备信息](./images/01-overview.png)

### 蜂窝网络指标

![蜂窝网络指标：服务小区、邻区、当前状态与接收链路](./images/02-cellular-metrics.png)

![蜂窝网络指标：小区身份、无线传输与 NR 连接统计](./images/03-cellular-metrics-details.png)

### 锁定控制

![锁频点：扫描前](./images/04-frequency-scan-before.png)

![扫描附近小区：确认提示](./images/05-frequency-scan-confirm.png)

![锁频点：扫描完成后的频点列表](./images/06-frequency-scan-results.png)

### Wi-Fi

![Wi-Fi：MLO 模式](./images/07-wifi-mlo.png)

![Wi-Fi：多频合一模式](./images/08-wifi-multiband.png)

### 互联网设置

![互联网设置：蜂窝网络上行与 APN](./images/09-internet-cellular.png)

![互联网设置：以太网上行与动态获取 IP](./images/10-internet-ethernet.png)

### 终端

![终端：已连接设备与接入速率](./images/11-connected-devices.png)

### 短信

![短信：会话列表与短信内容](./images/12-sms.png)

### 通话

![通话：拨号键盘](./images/13-call-dialpad.png)

![通话：通话中状态与通话记录](./images/14-call-active.png)

### 系统偏好设置

![系统偏好设置：辅助按钮、时区与内存压缩](./images/15-system-preferences.png)

### 关于本机

![关于本机：设备信息与存储空间](./images/16-device-information.png)

![关于本机：软件组件与版本信息](./images/17-software-information.png)

### LuCI

![LuCI：系统状态](./images/18-luci.png)
