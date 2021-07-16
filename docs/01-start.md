---
title: 现在开始
hide_title: false
---

## 第一步：注册账号

### 注册：

如果您还没有 TapDB 账号，请先前往 [首页](/index.html "_tapdb") 申请

### 验证邮箱：

您必须在验证邮箱后才能使用 TapDB。邮件的有效期为 7 天。
如果收不到邮件，您可以尝试重新发送邮件或者换一个邮箱。

## 第二步：创建企业和项目

### 创建企业：

首次进入 TapDB，会要求您创建企业，您需要提供企业名称和企业 LOGO（非必须）。

### 创建项目：

企业创建成功后，您可以在「游戏」界面下创建您的游戏项目。
创建项目需要提供项目名称和项目 icon（非必须），如果您的游戏支持多个平台，也只需要创建一个项目即可。
创建完成后会分配一个 APPID，使用该 ID 来进行 SDK 集成步骤。
<Red>注意：iOS 和 Android 共用此 APPID。</Red>

## 第三步：SDK 集成

### 下载 SDK：

目前 TapDB 支持 iOS 与 Andriod 平台的游戏。

[下载 SDK](download "_blank")

### 集成 SDK：

iOS、Android 共用一个 APPID。

[iOS 接入指南](sdk/iOS "_blank")

[Android 接入指南](sdk/Android "_blank")

## 第四步：调试

### 调试数据：

游戏安装包集成完 TapDB 后，需要一台联网设备下载并打开游戏，如果后台接收到了激活数据，那么就可以把项目转为正式游戏，转为正式游戏后，测试数据将被删除，不影响正式数据。

如果后台接收不到数据，您可以：

- 检查测试设备是否联网
- 检查 APPID 是否输入正确
- 重新打开游戏客户端，查看数据是否接收到
- 如果上述办法都无效，请通过 [工单](/dm/m/workOrder "_tapdb") 和我们联系