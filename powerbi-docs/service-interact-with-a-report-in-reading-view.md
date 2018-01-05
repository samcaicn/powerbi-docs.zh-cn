---
title: "与 Power BI 中阅读视图中的报表进行交互"
description: "与 Power BI 中阅读视图中的报表进行交互"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/21/2017
ms.author: mihart
ms.openlocfilehash: 1dc6ecab1b3504b658cd41a378a4c0f5e3c65187
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="interact-with-a-report-in-reading-view-in-power-bi"></a>与 Power BI 中阅读视图中的报表进行交互
## <a name="reading-view"></a>阅读视图
阅读视图不像[编辑视图](service-interact-with-a-report-in-editing-view.md)那样可以进行交互，但它仍提供了许多浏览数据的选项。 在查看只能在阅读视图中打开的[与你共享](service-share-dashboards.md)的报表时，使用阅读视图会非常有用。

阅读视图为处理和了解数据提供了一种有趣且安全的方式。 在“阅读视图”中，可以在页面上交叉突出显示和交叉筛选视觉对象。  只要突出显示或在视觉对象中选择一个值，就会立即看到其对其他视觉对象的影响。 使用“筛选器”窗格添加和修改报表页中的筛选器，并更改值在可视化效果中的排序方式。 你所执行的任何筛选和突出显示不随报表一起保存。

## <a name="cross-highlight-the-related-visualizations-on-a-page"></a>交叉突出显示页面上的相关可视化效果
单个报表页上的可视化效果全部都是相互“连接”的。  也就是说，如果你选择一个可视化效果中的一个或多个值，其他使用相同值的可视化效果则会根据你的选择进行变化。

![交叉突出显示](media/service-interact-with-a-report-in-reading-view/pagefilter3b.gif)

> [!NOTE]
> 若要在可视化效果中选择多个元素，请按住 Ctrl 键。
> 
> 

## <a name="hover-over-visual-elements-to-see-the-details"></a>将鼠标悬停在可视化元素，以查看详细信息
![悬停查看详细信息](media/service-interact-with-a-report-in-reading-view/amarillachart.png)

## <a name="sort-the-data-in-a-visualization"></a>对可视化效果中的数据进行排序
选择省略号 (...) 以打开“排序依据”。 选择下拉箭头以选择要作为排序依据的字段或选择 AZ 图标以在升序和降序之间切换。 

![对图表进行排序](media/service-interact-with-a-report-in-reading-view/pbi_changechartsort.gif) 

## <a name="interact-with-filters"></a>与筛选器交互
如果报表作者将筛选器添加到了报表中的某个页面，则可以将它们在阅读视图中进行交互。 所做的更改不会与报表一起保存。

1. 选择右上角的筛选器图标。
   
   ![选择筛选器图标](media/service-interact-with-a-report-in-reading-view/filters.png)  
2. 你将看到筛选器已应用到所选的视觉对象（视觉对象级别筛选器）并跨越整个报表页（页面级别筛选器）和整个报表（报表级别筛选器）。
   
   ![报表筛选器类型](media/service-interact-with-a-report-in-reading-view/power-bi-reading-filters.png)
3. 将鼠标悬停在筛选器上，然后通过选择向下箭头展开它。
   
   ![展开筛选器](media/service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)
4. 对筛选器进行更改，并查看如何影响视觉对象。  
   
   * 在本示例中，我们对“连锁店”提供页面级别筛选器。 将其更改为 Fashions Direct 而非 **Lindseys**，方法是删除后者的复选标记并将其添加到前者）。
     
     ![更改页面级筛选器](media/service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)
   * 或者，选择橡皮图标 ![](media/service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png) 或同时选择两个连锁店可以完全删除连锁店上的筛选器。
   * 选择“**地区**”页面级别筛选器并切换到“**高级筛选**”。 筛选器仅显示以 **FD** 开头的地区且不包含数字 4。
     
     ![高级筛选](media/service-interact-with-a-report-in-reading-view/power-bi-advanced-filter.png)

有关详细信息，请参阅[向报表添加筛选器](power-bi-report-add-filter.md)和[关于报表中的筛选器和突出显示](power-bi-reports-filters-and-highlighting.md)。

## <a name="zoom-in-on-individual-visuals"></a>放大单个视觉对象
将鼠标悬停在视觉对象上并选择“焦点模式”图标![](media/service-interact-with-a-report-in-reading-view/pbi_popouticon.jpg)。 在焦点模式下查看可视化效果时，它将展开以填充整个报表画布，如下所示。

![“焦点”模式](media/service-interact-with-a-report-in-reading-view/powerbi-focus-mode.png)

若要显示相同的可视化效果而不受菜单栏、筛选器窗格和其他部件的干扰，请从顶部菜单栏 ![](media/service-interact-with-a-report-in-reading-view/power-bi-focus-icon.png) 选择“全屏”图标。

![全屏模式](media/service-interact-with-a-report-in-reading-view/power-bi-full-screen.png)

若要了解详细信息，请参阅[报表的焦点模式](service-focus-mode.md)和[报表的全屏模式](service-fullscreen-mode.md)

## <a name="adjust-the-display-dimensions"></a>调整显示尺寸
可以在许多不同的设备上查看报表，这些设备具有不同的屏幕大小和纵横比。  默认的呈现方式可能并不是你想在设备上看到的方式。  若要调整，请选择“视图”，然后选择：

* 适应页面：缩放内容以使其适应页面
* 适应宽度：缩放内容以使其适应页面宽度
* 实际大小：以最大尺寸显示内容  

    ![报表视图菜单](media/service-interact-with-a-report-in-reading-view/power-bi-view.png)

  在“阅读视图”中，选择的显示选项只是暂时的，关闭报表时将不保存。

  有关详细信息，请参阅[教程：在报表中更改显示设置](power-bi-change-report-display-settings.md)。

##  <a name="open-the-selection-pane"></a>打开“选择”窗格
在报表页面上的可视化对象之间轻松导航。 选择“视图”>“选择”窗格 >“开”，打开“选择”窗格。

![报表“选择”窗格](media/service-interact-with-a-report-in-reading-view/power-bi-selection-pane.png)

有关详细信息，请参阅“报表选择窗格”。

##    <a name="miscellaneous-other-interactions"></a>其他交互
可通过多种方法来与阅读视图中的报表交互。 选择下面的链接了解详细信息。

- [查看报表使用情况指标](service-usage-metrics.md)
- [查看相关的仪表板、报表和数据集](service-related-content.md)
- [订阅报表页面](service-report-subscribe.md)
- [在 Excel 中分析](service-analyze-in-excel.md)
- [生成 QR 码](service-create-qr-code-for-report.md)
- [将活动页面固定到仪表板](service-dashboard-pin-live-tile-from-report.md)
- [在通知中心查看消息](service-notification-center.md)
- [将可视化对象固定到仪表板](service-dashboard-pin-tile-from-report.md)

## <a name="next-steps"></a>后续步骤
返回 [Power BI 服务中的“阅读视图”和“编辑视图”](service-reading-view-and-editing-view.md)

[打开编辑视图](service-reading-view-and-editing-view.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

