---
title: 测试设备白名单
hide_title: false
hide_table_of_contents: false
---

## 测试设备白名单

当你需要用旧设备测试分包渠道或广告是否调通时，可以使用测试设备白名单功能来完成这个任务。

**一、确保你的游戏已经接入了最新的 SDK**

白名单功能需要接入最新的 TapDB SDK，具体版本号如下：

iOS：<Data field="sdk.0.version"/>

Android：<Data field="sdk.1.version"/>

Unity 3D：<Data field="sdk.2.version"/>

[下载 SDK](../download "_blank")

**二、添加测试设备**

你可以使用 2 种方法添加测试设备：扫码添加、手动添加
<br/>

**方法一：扫码添加**

1. 下载 TapDB 移动客户端

![图片描述](/img/whiteList/04.png)

2. 打开 App

未登录：在登录界面左上角点击"!"进入添加页面

已登录：点击左上角「设置」-「测试设备」进入添加页面

![图片描述](/img/whiteList/02.png)

3. 点击添加设备，扫描 Web 端「企业设置」-「测试设备」-「+添加设备」中的二维码

![图片描述](/img/whiteList/01.png)

**方法二：手动添加**

1.  用 Web 端点击右上角菜单中的「企业设置」-「测试设备」-「+添加设备」
2.  选择「自定义添加」
3.  选择系统

![图片描述](/img/whiteList/03.png)

4. iOS 填写 IDFA

   > **如何获取 IDFA**
   >
   > 1. 下载 TapDB 客户端，点击测试设备，获取 IDFA

5. Android 填写 Android ID 或 Google ID
   > **如何获取 Android ID 或 Google ID？**
   >
   > 1. 下载 TapDB 客户端，点击测试设备，获取 Android ID 和 Google ID
   > 2. 获取 Android ID：打开手机拨号键，输入\*#\*#8255#\*#\*
   > 3. 获取 Google Advertising ID : <https://support.google.com/googleplay/android-developer/answer/6048248?hl=en>

**注意事项：**

1.  每个企业支持添加 30 个设备
2.  不建议添加模拟器设备，部分品牌的模拟器添加后，会导致所有使用该模拟器的设备都会被加入白名单
3.  设备加入白名单后，将对该企业下的所有项目生效。
4.  设备从白名单内移除后，后续数据将传递在首次激活的设备号上。

如果需要帮助，请联系我们的技术支持
QQ：<Data field="tapdb.support.QQ"/>
邮件：support@tapdb.com