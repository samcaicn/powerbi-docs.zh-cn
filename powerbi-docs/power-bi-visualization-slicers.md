---
title: "Power BI 中的切片器（教程）"
description: "教程：Power BI 中的切片器"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/30/2017
ms.author: mihart
ms.openlocfilehash: b6ce0c396f4a189489b97fe5cd86ab5cd8dbcc35
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Power BI 服务中的切片器（教程）
销售副总裁希望能够看一下整个部门以及每个单独的地区经理的多个指标。 她可以为每位经理创建单独的报表页，或者可以使用切片器。 切片器用于限制在页面的其他可视化效果中显示的部分数据集。  切片器是筛选的一种替代方法。

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>何时使用切片器
在以下情况下切片器是个不错的选择。

* 要在报表画布上显示常用或重要的筛选器以便访问数据。
* 要更加轻松地查看当前筛选的状态，而无需打开下拉列表来查找筛选详细信息。
* 如果想要隐藏不需要的列，但是仍可以使用它们来筛选 - 这会使表格更小、更简洁。
* 要创建更突出重点的报表 - 由于切片器是浮动对象，因此可将其放在报表中你希望用户关注的感兴趣的内容的旁边。

## <a name="create-a-slicer"></a>创建切片器
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. 在“[编辑视图](service-interact-with-a-report-in-editing-view.md)”中打开 [零售分析示例](sample-retail-analysis.md)，然后 [添加一个新的报表页](power-bi-report-add-page.md)。
2. 从“字段”窗格中，选择**地区 > 地区经理**。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. 将可视化效果转换为切片器。 在“可视化效果”窗格中，选择切片器图标。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>设置切片器格式
1. 选择切片器后，在“可视化效果”窗格中选择滚筒刷图标 ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) 以显示格式选项。
2. 选择**常规 > 边框颜色**，然后选择深蓝色，并且将**线条粗细**更改为**6**。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. 默认情况下，在**选择控制**下方的**全选**为**关闭****选择一个**状态，为**打开**状态。 这意味着我需要使用 CTRL 键来一次选择多个姓名。 将**全选**设为**打开**，**选择一个**设为**关闭**。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * 请注意现在切片器的列表顶部有**全选**选项。 切换**全选**可以选择所有姓名或不选择任何姓名。
   * 现在你无需使用 CTRL 键就可以选择多个姓名。
4. 在**项目**中，将文本大小增加到 14 pt。  我们想要确保同事能注意到此切片器。
5. 最后，将**字体颜色**设置为深红色。  这样可以将切片器中已选定姓名和未选定的姓名区分开来。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. 尽情探索切片器的其他可用选项。

## <a name="use-the-slicer-in-a-report"></a>在报表中使用切片器
1. 将某些其他可视化效果添加到报表页，或打开[零售分析示例报表](sample-retail-analysis.md)，然后选择“**地区每月销售额**”选项卡。
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. 针对 Carlos 划分报表页。 请注意其他可视化效果是如何更新以反映这些选择的。
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. 按地区经理姓氏的字母顺序对切片器进行排序。  选择切片器右上角的省略号 (...)，然后选择**地区经理**。
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>控制切片器对页面上的其他视觉对象有何影响
是否希望切片器仅筛选出报表页上的部分视觉对象？  使用**视觉对象交互**控件来对此进行设置。

**注意**：如果看不到“**视觉对象交互**”，请改为查找其图标 ![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png)。 如果找不到这两者，请确保你处于报表[编辑视图](service-reading-view-and-editing-view.md)中。

1. 选择切片器使其处于活动状态，并从菜单栏中选择“**视觉对象交互**”。
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. 筛选器控件将显示在页面上所有其他视觉对象上方。 如果切片器要筛选一个视觉对象，请选择“筛选器”图标。  如果切片器不对视觉对象产生任何影响，请选择“无”图标。
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

有关详细信息，请参阅 [Visual interactions in a Power BI report（Power BI 报表中的视觉对象交互）](service-reports-visual-interactions.md)。

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Power BI 中有关切片器的注意事项和疑难解答
使用 Power BI 中的切片器存在一些限制，如下所示：

1. 切片器不支持输入字段。
2. 单个切片器不能用于整个报表。 切片器只会影响当前页。
3. 切片器不能固定到仪表板。
4. 切片器不支持明细。    
5. 切片器不支持视觉对象级别的筛选器。

你有关于如何改进 Power BI 的想法吗？ [提交想法](https://ideas.powerbi.com/forums/265200-power-bi-ideas)。

## <a name="next-steps"></a>后续步骤
 [向报表添加可视化效果](power-bi-report-add-visualizations-i.md)

 [Power BI 中的可视化效果类型](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI - 基本概念](service-basic-concepts.md)

[试用一下 - 完全免费！](https://powerbi.com/)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

