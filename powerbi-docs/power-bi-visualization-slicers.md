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
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="slicers-in-power-bi-tutorial"></a>Power BI 中的切片器（教程）
销售副总裁希望能够看一下针对整个部门和每个区域经理的多项指标。 她可以为每位经理创建单独的报表，也可使用切片器。 切片器用于限制在报表的其他可视化效果中显示的部分数据集。 切片器是筛选的一种替代方法。

本教程通过免费的[零售分析示例](sample-retail-analysis.md)，演示如何创建和格式化切片器以及如何使用它来筛选报表。 通过有趣的新方法使用切片器并进行格式化。 

![切片器](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>何时使用切片器
在要完成以下操作时，切片器非常有用：

* 在报表画布上显示常用或重要的筛选器，用以简化访问。
* 更轻松地查看当前筛选的状态，而无需打开下拉列表。 
* 按数据表中不需要的和隐藏的列进行筛选。
* 通过将切片器放置在重要的视觉对象旁边来创建更多报表。

Power BI 切片器存在以下限制：

- 切片器不支持输入字段。
- 切片器不能固定到仪表板。
- 切片器不支持明细。
- 切片器不支持视觉对象级别的筛选器。

## <a name="create-a-slicer"></a>创建切片器

本教程使用切片器列表。 数字和日期/时间数据类型可使用范围切片器。 若要深入了解如何创建和使用范围切片器，请参阅[在 Power BI Desktop 中使用数值范围切片器](desktop-slicer-numeric-range.md)或观看以下视频。
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. 在 Power BI Desktop 或 Power BI 服务中，打开[编辑视图](service-interact-with-a-report-in-editing-view.md)中的[零售分析示例](sample-retail-analysis.md)，然后 [添加一个新的报表页](power-bi-report-add-page.md)。
2. 在“字段”窗格的“地区”下，选择“区域经理”创建新的可视化效果。
    
    ![新图表](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. 在“可视化效果”窗格中选择切片器图标![切片器图标](media/power-bi-visualization-slicers/slicer-icon.png)，将新的可视化效果转换为切片器。 
    
    ![转换为切片器](media/power-bi-visualization-slicers/2-slicer.png)

还可选择切片器图标来创建新的切片器，然后选择数据字段或将其拖动到字段框进行填充。

>[!TIP]
>可通过数据值对切片器列表项进行排序。 若要按反向字母顺序对切片器项进行排序，请选择切片器右上角的省略号 (...)，然后选择“按区域经理进行排序”。 该设置默认为按字母升序排序，但可在升序和降序之间切换。 

## <a name="format-the-slicer"></a>设置切片器格式
将视觉对象格式应用到区域经理切片器。
1. 选择切片器后，在“可视化效果”窗格中选择格式图标 ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) 以显示格式设置控件。 
    
    ![格式设置](media/power-bi-visualization-slicers/3-format.png)
    
2. 单击每个类别旁边的下拉列表箭头，显示和编辑选项。 

### <a name="general-options"></a>常规选项
1. 选择“边框颜色”中的红色，并将“边框粗细”更改为“2”。 启用时，将设置标头和项目外虚线框或实线框的颜色/粗细。 
2. 默认为垂直方向，这会在项的前面创建一个带选择框的垂直切片器列表。 选择“水平”，生成带水平排列项的切片器。 水平方向可生成各种排列方式的文本、按钮或磁贴，具体取决于切片器大小形状和项格式设置。 
    
    ![水平](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. 启用响应式布局，这将更改水平切片器项的大小和排列方式，进而匹配切片器的大小和形状。 如果尺寸非常小，切片器会变成筛选器图标。 
    
    ![响应式](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >更改响应式布局后，可能会覆盖所设置的特定标题和项格式。 
    
4. 在“X 位置”、“Y 位置”、“宽度”和“高度”中使用数值精度设置切片器位置和大小，或者直接在画布上移动切片器或调整其大小，生成不同的项大小和排列方式（如水平的按钮行）。 

    ![水平按钮](media/power-bi-visualization-slicers/6-buttons.png)

若要深入了解水平方向和响应式格式设置，请参阅[在 Power BI 中创建可调整大小的响应式切片器](power-bi-slicer-filter-responsive.md)。

### <a name="selection-controls-options"></a>选择控件选项
1. 默认关闭“显示全选”。 将其打开，将“选择所有项目”添加到切换器，使其在切换时可选择或取消选择所有项。 选择所有项时，单击某项即取消选择它，这可实现“非”类型筛选器。 
    
    ![全选](media/power-bi-visualization-slicers/7-select-all.png)
    
2. 默认启用“单项选择”。 单击每个项即将其选中，按住 Ctrl 并同时单击多个项可选择多个项。 关闭“单项选择”后，无需按 Ctrl 即可选择多个项。 再次单击每个项即取消选择。 

### <a name="header-options"></a>标头选项
“标头”默认开启，它可在切片器顶部显示数据字段名称。 
1. 设置标头文本格式：将字体颜色设为红色、文本大小为为 14 pt、字体系列为 Arial Black。 
2. 在“边框”中，选择“仅下框线”，生成带有在“常规”选项下设置的大小和颜色的下框线。 

### <a name="item-options"></a>项选项
1. 设置项文本和背景的格式：字体颜色设为黑色、背景为浅红色、文本大小为为 10 pt、字体系列为 Arial。 
2. 在“边框”中，选择“框架”，在每个项周围添加带有在常规选项下设置的大小和颜色的边框线。 
    
    ![格式设置](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- 设置为水平方向时，取消选择的项显示已选文本和背景颜色，而所选项使用系统默认设置，通常是黑色背景和白色文本。 
    >- 设置为垂直方向时，项始终显示设置的颜色，选择项时选择框始终为黑色。 

### <a name="other-formatting-options"></a>其他格式设置选项
其他格式设置选项默认关闭。 当启用时： 
- **标题：**在切片器顶部添加标题并设置其格式（附加在标头上且与标头无关）。 
- **背景：**将背景颜色添加到整个切片器并设置其透明度。
- **锁定纵横比：**重新调整大小后，切片器的形状保持不变。
- **边框：**在切片器周围添加 1 像素的边框并设置其颜色。 （此切片器边框是单独的，不受常规边框设置影响。） 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>同步切片器并在其他页面上使用
自 Power BI 2018 年 2 月更新起，可同步切片器并在报表的任意页面上使用。 
1. 选择“区域经理”切片器后，在 Power BI Desktop 中的“视图”菜单上 选择“同步切片器”，或在 Power BI 服务中启用“同步切片器”窗格。 随即显示“同步切片器”窗格。 
    
    ![同步切片器](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. 在第一列中选择“概述”页面以及要向其同步切片器的任何其他页面，或者单击“添加到所有”，让切片器同步到所有报告页。  
3. 在下一列中选择“概述”页面以及要将切片器设置为“可见”的任何其他页面。 
4. 切换到“概述”页面，此时请注意切片器及其对其他页面视觉对象的影响。 
    - 选择并删除不同项选项，此时请注意其他页面视觉对象如何出现相应变化。 任何页面上的项选择将在所有同步的页面上反映出来。
    - 在“概述”页面上更改切片器的大小、形状、位置和/或格式。 其他同步页上的切片器格式保持不变。 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>控制要受切片器影响的页面视觉对象
默认情况下，报表页上的切片器会影响该页上的其他所有可视化效果。 请使用“视觉对象交互”防止某些页面视觉化效果受到影响。

1. 在“概述”页面上，当选中切片器时：
    - 在 Power BI Desktop 中，单击可视化工具下的“格式”菜单并选择“编辑交互”。
    - 在 Power BI 服务中，沿着菜单栏向下浏览“视觉对象交互”下拉列表，并启用“编辑交互”。 
    
    页面上所有其他视觉对象上方随即显示筛选器控件。 ![筛选器控件](media/power-bi-visualization-slicers/filter-controls.png)
    
2. 选择视觉对象上方的“无”图标，使切片器不筛选它。 选择“筛选器”图标，使切片器再次开始筛选视觉对象。 

有关编辑交互的详细信息，请参阅 [Power BI 报表中的视觉对象交互](service-reports-visual-interactions.md)。

## <a name="next-steps"></a>后续步骤
[试用一下 - 完全免费！](https://powerbi.com/)

你有关于如何改进 Power BI 的想法吗？ [提交想法](https://ideas.powerbi.com/forums/265200-power-bi-ideas)。

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

[向报表添加可视化效果](power-bi-report-add-visualizations-i.md)

[Power BI 中的可视化效果类型](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI - 基本概念](service-basic-concepts.md)

