---
title: 漏斗分析
sidebar_position: 5
---

## 一、引入案例

在[埋点设计指南](/sdk/tapdb/features/customEvent/dataModel.md)里，我们基于「用户从打开 App 到真正创建角色」的转化过程进行了埋点设计，在这里我们用「漏斗分析」功能对这个转化过程来进行分析。

**1、设置步骤**：将用户从打开 App 到真正创建角色的全过程创建事件，并按照用户操作顺序设置为漏斗步骤；
![](/img/customEvent/funnel/案例-1.png)

**2、设置维度**：不同系统类型可能会对转化情况有影响，所以在维度里选择「设备系统类型」；

![](/img/customEvent/funnel/案例-2.png)

**3、设置漏斗周期**：我们将漏斗窗口期设置为 7 天；

![](/img/customEvent/funnel/案例-3.png)

**4、设置展示结果**：设置时间段和其他参数，并点击查询查看分析结果；

![](/img/customEvent/funnel/案例-4.6.png)

**5、保存报表**：将查询结果保存为报表。再将报表转变为看板，就可以每天方便快捷的看漏斗分析。

![](/img/customEvent/funnel/案例-5.2.png)

## 二、什么是漏斗分析

漏斗分析是分析从起点到终点各阶段用户的转化率情况的分析模型，可以衡量每个节点的转化效果。在理想情况下，用户会沿着产品设计的路径到达最终目标事件，但实际情况是用户的行为路径是多种多样。通过埋点事件配置关键业务路径，可以分析多种业务场景下转化和流失的情况，不仅找出产品潜在问题的位置，还可以定位每个环节流失用户，通过产品手段或营销手段促进转化。

## 三、漏斗分析的支持场景

漏斗分析支持的场景很多，比较典型的场景如下：

- 游戏流量很大，但注册用户很少，是过程中哪个环节除了问题？
- 用户从「注册 – 创建角色 - 体验游戏 - 付费」 总体转化率如何？
- 不同地区的用户支付转化率有什么差异？
- 两个推广渠道带来不同的用户，哪个渠道的注册转化率高？

## 四、如何做漏斗分析

如案例所述，漏斗分析可以分为 5 个步骤：

**1、设置步骤；**

**2、设置维度；**

**3、设置漏斗周期；**

**4、设置展示结果；**

**5、保存报表；**

### 4.1 设置漏斗

在漏斗分析页面，点击「设置步骤」，可以看到「添加漏斗步骤」界面。

![](/img/customEvent/funnel/exp/1-漏斗分析-设置漏斗.png)

在「添加漏斗步骤」界面，可以选择漏斗步骤和添加漏斗步骤：

1、步骤：由一个事件（可添加一个或者多个筛选条件）组成，表示一个转化流程中的一个关键性的步骤。

一个漏斗中至少包含 2 个步骤，每个步骤对应一个事件。可增加更多步骤，拖动步骤前的序号可以改变步骤顺序。

同样可对步骤设置筛选条件。也可在漏斗分析主界面设置全局筛选。

2、添加步骤：给要分析的漏斗增加更多步骤。

![](/img/customEvent/funnel/exp/2-漏斗分析-设置漏斗.png)

### 4.2 设置维度

在维度下拉框，展示的内容包括事件属性（步骤 1）、用户属性和用户分群。

![](/img/customEvent/funnel/exp/3-漏斗分析-选择维度.png)

### 4.3 设置漏斗周期

**漏斗周期**：用户触发步骤 1 起，在窗口期内完成后续步骤，算作后续步骤的转化。

![](/img/customEvent/funnel/exp/4-漏斗分析-漏斗窗口期.png)

**限制窗口期在时间区间内**：表示只有在这个时间范围内，用户从第一个步骤，行进到最后一个步骤，才被视为一次完整的漏斗转化。

### 4.4 设置展示结果

可选择进行分析的步骤范围，并根据「对比 / 趋势」、「转化 / 流失」设置，能够得到 4 类报表：转化对比表、流失对比表、转化趋势表、流失趋势表。

![展示结果](/img/customEvent/funnel_analyse_result_type.png)

转化对比表：用以分析从步骤一到后续步骤的累计的转化率

![转化对比表](/img/customEvent/funnel_analyse_table_1.png)

流失对比表：用以分析每个步骤之间的流失率

![流失对比表](/img/customEvent/funnel_analyse_table_2.png)

转化趋势表：用以分析不同日期的转化率变化趋势

![转化趋势表](/img/customEvent/funnel_analyse_table_3.png)

流失趋势表：用以分析不同日期的流失率变化趋势

![流失趋势表](/img/customEvent/funnel_analyse_table_4.png)

### 4.5 保存到看板

将设置好的查询结果保存为报表，再基于报表创建看板，漏斗分析结果一触即达。

![](/img/customEvent/funnel/exp/5-漏斗分析-保存报表.png)

## 五. 漏斗分析原理

接下来将会描述漏斗分析原理，尤其是有分组和筛选情况时，计算原理就会显得较为复杂，此处将详细说明。

### 5.1. 基本计算原理

假设一个由步骤 1、2、3、4、5 构成的漏斗，选择的时间范围为 2021 年 3 月 1 日到 2021 年 3 月 7 日，窗口期是 3 天，如果用户在 2021 年 3 月 1 日到 2021 年 3 月 7 日触发了步骤 1，并且在步骤 1 发生的 3 天内，依顺序依次触发了步骤 2、3、4、5，则认为该用户完成了一次完整的漏斗转化，若依次触发了步骤 1 > 2 > 4 > 5，则该用户仅完成了步骤 1 > 2 的转化。

如果步骤中间夹杂了一些其它的步骤，如用户的行为顺序是 1 > X > 2 > X > 3 > 4 > X > 5（其中 X 代表其他事件），则依然认为该用户完成了一次完整的漏斗转化。

当一个用户在所选时段内有多个事件都符合某个转化步骤的定义，则会优先选择更靠近最终转化目标的事件作为转化事件，并在第一次达到最终转化目标时停止转化计算。

假设一个漏斗的步骤定义为：浏览商城、选择道具、生成订单、支付成功，那么不同用户的行为序列及实际转化步骤（加粗部分）如下：

例 1：**浏览商城** > 选择道具（道具 B ） > **选择道具（道具 A ）** > **生成订单** > 支付成功

例 2：浏览商城 > 选择道具（道具 B ） > **浏览商城** > **选择道具（道具 A ）** > **生成订单** > **支付成功**

例 3：浏览商城 > 选择道具（道具 B ） > **浏览商城** > **选择道具（道具 A ）** > **生成订单** > **支付成功** > 选择道具（道具 A ） > 生成订单 > 支付成功

漏斗分析中展示的数字代表转化 / 流失的独立用户数，而非触发的事件次数。在该时间范围内，即使一个用户多次完成漏斗，也仅计数一次。

### 5.2 分组与筛选

漏斗分析的分组与筛选，均基于完成转化 / 流失的用户。  
基于用户属性、用户分群的分组与筛选：在完成转化 / 流失的用户的基础上，根据用户属性、用户分群进行分组与筛选。  
基于事件属性的分组与筛选：在完成转化 / 流失的用户的基础上，以该用户在步骤 1 的事件属性进行分组与筛选。