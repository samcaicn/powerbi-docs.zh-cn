---
title: "更改报表页的大小（教程）"
description: "教程：在 Power BI 报表中更改页面的显示设置"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/25/2017
ms.author: mihart
ms.openlocfilehash: a5cc05e26012f88e889612788d4479a370063d4f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="change-the-size-of-a-report-page-tutorial"></a>更改报表页的大小（教程）
在[上一篇文章和视频](power-bi-report-display-settings.md)中，你学习了在 Power BI 报表中控制页面显示的两种方法：“视图”和“页面大小”。 现在让我们亲自试试。

## <a name="first-lets-change-the-page-view-setting"></a>首先，让我们更改页面的“视图”设置
1. 在“阅读视图”或“编辑视图”中打开报表。 此示例使用[零售分析示例](sample-retail-analysis.md)的“新建存储”页。  使用“**调整到页面大小**”设置显示此页面。  在这种情况下，“适应页面”将显示不带滚动条的报表，但是其中的一些详细信息和标题因太小而无法阅读。
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_page.png)
2. 请确保在画布上未选择可视化效果。 选择“视图”并查看显示选项。

* 在“阅读”视图中，你可以看到此项。
  
     ![](media/power-bi-change-report-display-settings/power-bi-page-view-menu-new.png)
* 在“编辑”视图中，你可以看到此项。
  
    ![](media/power-bi-change-report-display-settings/power-bi-view-editing-view.png)

1. 让我们看看使用“实际大小”设置后页面看起来怎么样。
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)
   
   不好，仪表板现有两个滚动条。
2. 切换到“适应宽度”。
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_width.png)
   
   看起来好一些了，虽然仍有滚动条，但是可以更轻松地阅读详细信息。

## <a name="change-the-default-view-for-a-report-page"></a>更改报表页的默认视图
所有 Power BI 报表默认使用“适应页面”视图。 但如果希望此报表页始终以“实际大小”视图打开，应该怎么做？

1. 在报表的“新店铺”页上，切换回“实际大小”视图。
   
   ![](media/power-bi-change-report-display-settings/power-bi-actual-size.png)
2. 选择“文件”>“另存为”将报表保存为其他名称。 现有该报表的两个副本；在原始报表中，“新店铺”将继续以默认视图打开；但在新报表中，它将以“实际大小”视图打开。 请看演示。
   
   ![](media/power-bi-change-report-display-settings/power-bi-save-as.png)
3. 从顶部导航栏中选择当前工作区的名称，以返回到该工作区。  
   
   ![](media/power-bi-change-report-display-settings/power-bi-my-workspace.png)
4. 选择“报表”选项卡，然后选择刚刚创建的新报表（它带有一个黄色的星号）。
   
    ![](media/power-bi-change-report-display-settings/power-bi-new-report2.png)
5. 报表以“实际大小”视图打开！
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)

## <a name="now-lets-explore-the-page-size-setting"></a>现在，让我们浏览页面大小设置
只有[编辑视图](service-interact-with-a-report-in-editing-view.md)才提供“页面大小”设置。 若要在“编辑视图”中打开报表，必须具有该报表的所有者权限。 如果你已连接到我们的任意[示例](sample-datasets.md)，则拥有这些报表的所有者权限。

1. 在“编辑视图”中打开[零售分析示例](sample-retail-analysis.md)的“地区每月销售额”页。
2. 请确保在画布上未选择可视化效果。  在“**可视化效果**”窗格中，选择滚动油漆刷图标 ![](media/power-bi-change-report-display-settings/power-bi-paintroller.png)。
3. 选择“页面大小”&gt;“类型”，以显示页面大小选项。
   
   ![](media/power-bi-change-report-display-settings/power-bi-page-size-menu-new.png)
4. 选择“字母”。  在画布上，只有适应 816 x 1056 像素（字母大小）以内的内容才可以保留在画布的空白区域。
   
   ![](media/power-bi-change-report-display-settings/power-bi-letter-new.png)
5. 如果我们将“视图”更改为“适应宽度”，我们的画布将仅显示适应字母大小的页面内容。
   
   ![](media/power-bi-change-report-display-settings/power-bi-fit-to-width-new.png)
6. 选择“页面大小”“16:9”。
   
   ![](media/power-bi-change-report-display-settings/power-bi-16-to-9-new.png)
   
   使用 16:9 的宽高比显示报表页。 若要查看使用的实际像素大小，请查看灰色的宽度和高度字段 (1280 x 720)。 报表画布周围有很多空白部分，这是因为我们之前将“视图”设置为“适应宽度”。
7. 继续探讨“页面大小”选项。

## <a name="using-page-view-and-page-size-together"></a>结合使用页面“视图”和“页面大小”
结合使用页面视图和页面大小创建报表，使其在嵌入另一应用程序时具有其最佳外观。

在本练习中，你将创建一个报表页，它将显示于可容纳宽 500 像素、高 750 像素的应用程序中。

记得在上一步中，报表页当前显示为宽 1280 像素、高 720 像素。 因此我们知道，如果希望所有视觉对象都适应页面，需要进行大量的大小调整和重新排列。

1. 调整并移动视觉对象，使其可放入当前画布区域一半大小以下的空间。
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-view.gif)
2. 选择“页面大小”&gt;“自定义”。
3. 将宽度设置为 500，高度设置为 750。
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-new.png)
4. 调整报表页以使其达到最佳显示效果。 在“视图”>“实际大小”和“视图”>“调整到页面大小”之间切换以便调整。
   
    ![](media/power-bi-change-report-display-settings/power-bi-final-new.png)

## <a name="next-steps"></a>后续步骤
[为 Cortana 创建报表](service-cortana-answer-cards.md)

返回到 [Power BI 报表中的页面显示设置](power-bi-report-display-settings.md)

详细了解 [Power BI 中的报表](service-reports.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

