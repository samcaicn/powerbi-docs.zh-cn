---
title: "Power BI 中的组合图（教程）"
description: "此文档是向你演示为何以及如何在 Power BI 中创建组合图的教程（带有视频）。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: lnv66cTZ5ho
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: c00ba74501a411743036c4514750bccbbae3eb00
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="combo-chart-in-power--tutorial"></a>Power BI 中的组合图（教程）
在 Power BI 中，组合图是将折线图和柱形图合并在一起的单个可视化效果。 通过将两个图表合并为一个图表可以进行更快的数据比较。

组合图可以具有一个或两个 Y 轴。

## <a name="when-to-use-a-combo-chart"></a>何时使用组合图
组合图适用情况：

* 具有 X 轴相同的折线图和柱形图时。
* 比较具有不同值范围的多个度量值。
* 在一个可视化效果中说明两个度量值之间的关联。
* 检查一个度量值是否满足另一个度量值定义的目标
* 节省画布空间。

## <a name="create-a-basic-single-axis-combo-chart"></a>创建基本的单轴组合图
观看如何使用销售和市场营销示例创建组合图。

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


要创建自己的组合图，请登录到 Power BI，然后选择“获取数据\> 示例 \> 零售分析示例”。 

1. 从“零售分析示例”仪表板中，选择**总商店数**磁贴以打开“零售分析示例”报表。
2. 选择**编辑报表**在编辑视图中打开报表。
3. [添加新报表页](power-bi-report-add-page.md)。
4. 创建按月显示本年度销售额和毛利的组合图。
   
    a.  从“字段”窗格，选择**销售额** \> **本年度销售额**  >  **值**。
   
    b.  将**销售额** \> **本年度毛利**拖动到**值**框。
   
    c.  选择**时间** \> **会计月份**以将它添加到**轴**框。 
   
    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. 在可视化效果的右上角选择省略号 (...)，然后选择“**按会计月份排序**”。
6. 将柱形图转换为组合图。 在选择了柱形图的情况下，从“可视化效果”窗格中选择“折线和簇状柱形图”。
   
    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. 从**字段**窗格，将**销售额** \> **去年销售额**拖动到**行值**存储段。
   
   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)
   
   组合图应如下所示：
   
   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>创建具有两个轴的组合图
在此任务中，我们会比较毛利和销售额。

1. 按月份创建可跟踪去年毛利率的新折线图。  一月的 GM% 是 35%，在四月达到峰值 45%，在七月下降，在八月再次达到峰值。 去年和本年度的销售额是否会呈现类似模式？
   
   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. 将**本年度销售额 > 值**和**去年销售额**添加到折线图。 **去年 GM%**的规模比**销售额**的规模小得多，这使比较难以进行。      
   
   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. 若要使视觉对象更易于查看和解释，请将折线图转换为折线和堆积柱形图。
   
   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. 将**去年毛利率**从**列值**拖动到**行值**中。 Power BI 会创建两个轴，从而允许数据集以不同方式缩放；左侧度量值是美元，右侧度量值是百分比。
   
   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>向轴添加标题
1. 选择滚动油漆刷图标 ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png)，打开格式窗格。
2. 选择向下箭头以展开 **Y 轴**选项。
3. 对于 **Y 轴（列）**，将“**位置**”设置为“**左**”，将“**标题**”设置为“**打开**”，将“**样式**”设置为“**仅显示标题**”，并将“**显示**”设置为“**百万**”。
   
   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. 在 **Y 轴（列）**下，同时确保将“**显示辅助对象**”设置为“**打开**”。 该操作显示对组合图的折线图部分进行格式化的选项。
   
   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. 对于 **Y 轴（行）**，将“**位置**”保留为“**右**”，将“**标题**”设置为“**打开**”，并将“**样式**”设置为“**仅显示标题**”。
   
   组合图现在显示双轴，它们都具有标题。
   
   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

从这里你可能想要：

* [将组合图添加为仪表板磁贴](service-dashboard-tiles.md)。
* [保存报表](service-report-save.md)。

## <a name="highlighting-and-cross-filtering"></a>突出显示和交叉筛选
有关使用筛选器窗格的信息，请参阅[向报表添加筛选器](power-bi-report-add-filter.md)。

突出显示组合图中的列或行可交叉筛选报表页上的其他可视化效果，反之亦然。

## <a name="next-steps"></a>后续步骤
[向报表添加可视化效果](power-bi-report-add-visualizations-i.md)

[Power BI 报表中的可视化效果](power-bi-report-visualizations.md)

[Power BI 中的可视化效果类型](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI - 基本概念](service-basic-concepts.md)

[试用一下 - 完全免费！](https://powerbi.com/)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

