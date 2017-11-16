---
title: "Power BI 中的圆环图（教程）"
description: "教程：Power BI 中的圆环图"
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
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Power BI 中的圆环图（教程）
圆环图类似于饼图，因为它显示部分与整体的关系。 唯一的区别是中心为空，因而有空间可用于标签或图标。

## <a name="create-a-doughnut-chart"></a>创建圆环图
若要继续，请登录 Power BI，然后依次选择“**获取数据**”\>“**示例**”\>“**零售分析示例**”\>“**连接**”。 

1. 选择仪表板中的“**总商店数**”磁贴，打开“零售分析示例”报表。
2. 选择**编辑报表**在编辑视图中打开报表。
3. [添加新报表页](power-bi-report-add-page.md)。
4. 创建按类别显示本年度销售额的圆环图。
   
   * 从**字段**窗格，选择**销售额** \> **去年销售额**。
   * 转换为圆环图。 如果“去年销售额”不在**值**区域中，请将它拖动到其中。
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * 依次选择“**项**”\>“**类别**”，将其添加到**图例**区域中。 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

## <a name="considerations-and-troubleshooting"></a>注意事项和疑难解答
* 圆环图值的总和相加必须达到 100%。
* 类别太多会难以查看和解释。
* 圆环图最适用于将特定部分与整体进行比较，而不是将各个部分相互比较。 

## <a name="next-steps"></a>后续步骤
[Power BI 中的报表](service-reports.md)

[Power BI 中的可视化效果类型](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI 报表中的可视化效果](power-bi-report-visualizations.md)

[Power BI - 基本概念](service-basic-concepts.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

