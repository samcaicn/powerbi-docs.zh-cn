---
title: "基本分区图（教程）"
description: "教程：基本分区图。"
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
ms.openlocfilehash: 42e068b11c22c32f1a6736a6ca8f9020594fb40a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="basic-area-chart-tutorial"></a>基本分区图（教程）
基本面积图（又称为分层分区图）基于折线图。 轴和行之间的区域使用颜色进行填充以指示量。 

分区图强调变化随时间推移的度量值，可以用于吸引人们关注某个趋势间的总值。 例如，可以在分区图中绘制表示随时间推移的利润的数据以强调总利润。

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>何时使用基本面积图
基本分区图适用情况：

* 查看并比较各个时序间的量趋势 
* 对于表示可以物理方式计数的集合的各个序列

## <a name="create-a-basic-area-chart"></a>创建基本面积图
要遵循示例执行操作，请登录到 Power BI，然后选择**获取数据 \> 示例 \> 零售分析示例** 。 

1. 从“零售分析示例”仪表板中，选择**总商店数**磁贴以打开“零售分析示例”报表。
2. 选择**编辑报表**在编辑视图中打开报表。
3. 添加新报表页。
4. 创建按月显示本年度销售额和去年销售额的面积图。
   
   a.  从“**字段**”窗格，选择“**销售额 \> 去年销售额**”，以及“**本年度销售额 > 值**”。
   
   b.  将图表转换为基本面积图。    
   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  选择“时间”\>“月份”以将其添加到“轴”框。   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  若要按月显示图表，请选择“省略号”（视觉对象的右上角）并选择“按月排序”。

## <a name="highlighting-and-cross-filtering"></a>突出显示和交叉筛选
有关使用筛选器窗格的信息，请参阅[向报表添加筛选器](power-bi-report-add-filter.md)。

若要选择某个区域，请在该区域内或沿顶部行单击。  基本面积图不对报表页上的其他可视化效果进行交叉筛选。 但是，面积图是报表页上其他可视化效果触发的交叉筛选的目标。

## <a name="considerations-and-troubleshooting"></a>注意事项和疑难解答
* 基本面积图对于比较值无效，因为分层区域上是封闭的。 Power BI 使用透明度指示区域的重叠。 但是，它只适用于两个或三个不同区域。 需要将趋势与三个以上的度量值进行比较时，请尝试使用折线图。 需要将量与三个以上的度量值进行比较时，请尝试使用树状图。

## <a name="next-steps"></a>后续步骤
[Power BI 中的报表](service-reports.md)  
[Power BI 报表中的可视化效果](power-bi-report-visualizations.md)  
[Power BI - 基本概念](service-basic-concepts.md)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

