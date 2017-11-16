---
title: "面向 Power BI Quick Insights 优化数据"
description: "面向 Power BI Quick Insights 优化数据。 如果 Power BI 针对你的数据未提供任何见解，你可以执行以下操作"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/02/2017
ms.author: mihart
ms.openlocfilehash: 61901d0055c22540ec2f10bedbbb8cf641d606e9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="optimize-your-data-for-power-bi-quick-insights"></a>面向 Power BI Quick Insights 优化数据
想要改善 Quick Insights 结果吗？  如果你是数据集所有者，请尝试：

* 隐藏或取消隐藏数据集中的列。 Power BI 快速见解不会搜索隐藏的列。  因此，请隐藏重复或不必要的列，并取消隐藏相关列。
* 使用混合的数据类型，例如名称、时间、日期和数字。
* 避免使用（或隐藏）包含重复信息的列。  这会浪费搜索有意义模式的宝贵时间。  例如，一个列包含省/市/自治区名称的完整拼法，而另一个列包含省/市/自治区名称的缩写。
* 你是否收到一条错误消息，说数据不具有统计意义？  这可能发生在非常简单的、没有太多数据的模型中，或者没有日期或数字列的模型中。 若要生成见解，数据集需要具有至少一个维度和一个度量值。

### <a name="next-steps"></a>后续步骤
[Power BI 快速见解](service-insights.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

