---
title: "Power BI 中的树状图（教程）"
description: "教程：Power BI 中的树状图"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: IkJda4O7oGs
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: 5e5bc8eaa4e710e6564ee6f1d3ea1bfcf7f28127
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="treemaps-in-power-bi-tutorial"></a>Power BI 中的树状图（教程）
树状图将分层数据显示为一组嵌套矩形。  一个有色矩形（通常称为“分支”）代表层次结构中的一个级别，该矩形包含其他矩形（“叶”）。  根据所测量的定量值分配每个矩形的内部空间，从左上方（最大）到右下方（最小）按大小排列矩形。

![](media/power-bi-visualization-treemaps/pbi-nancy_viz_treemap.png)

例如，如果我正在分析销量，我可能会为服装类别设置顶层矩形（分支）：**城市**、**乡村**、**青年**和**混合**。  我的类别矩形将包含代表服装厂商的较小的矩形（叶），这些较小的矩形将根据销量设置大小和明暗度。  在上面提到的**城市**分支中，售出了大量 Maximus 服装，Natura 和 Fama 较少，Leo 则非常少。  因此，我的树状图的**城市**分支将具有代表 Maximus 的最大矩形（位于左上角）、代表 Natura 和 Fama 的稍微小点的矩形、代表所有其他销售的服装的大量其他矩形以及代表 Leo 的一个很小的矩形。  通过比较每个叶节点的大小和明暗度我可以比较其他服装类别销售的服装数量；矩形越大，颜色越深，则值越大。

## <a name="when-to-use-a-treemap"></a>何时使用树状图
当存在以下情况时，树状图是一个不错的选择：

* 要显示大量的分层数据。
* 条形图不能有效地处理大量值。
* 要显示每个部分与整体之间的比例。
* 要显示层次结构中指标在各个类别层次的分布的模式。
* 要使用大小和颜色编码显示属性。
* 要发现模式、离群值、最重要因素和异常。

## <a name="create-a-basic-treemap"></a>创建一个基本的树状图
想要先观看别人创建一个树状图？  跳到此视频的 2:10 处观看 Amanda 创建一个树状图。

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

或者，创建你自己的树状图。 以下说明使用零售分析示例。 若要遵循此示例进行操作，请[下载示例](sample-datasets.md)，登录到 Power BI，然后选择**获取数据 \> Excel 工作簿 \> 连接\>零售分析示例**.**xlsx**

1. 在[编辑视图](service-interact-with-a-report-in-editing-view.md)中开始，选择**销售**  >  **上年度销售额**指标。   
   ![](media/power-bi-visualization-treemaps/treemapfirstvalue_new.png)
2. 将图表转换为树状图。  
   ![](media/power-bi-visualization-treemaps/treemapconvertto_new.png)
3. 将**项目**  >  **类别**拖放到**组**中。 Power BI 将创建一个树状图，其中矩形的大小反映总销售额，颜色代表类别。  实际上你已创建以可视化方式描述按类别的总销售额的相对大小的层次结构。  **男装**类的销售额最高，**袜**类销售额最低。
   ![](media/power-bi-visualization-treemaps/treemapcomplete_new.png)
4. 将“商店”  >  “连锁店”拖放到“详细信息”以完成树状图。 现在你可以按类别和连锁店比较上年度的销售额。   
   ![](media/power-bi-visualization-treemaps/treemap_addgroup_new.png)
   
   > [!NOTE]
   > 不能同时使用色彩饱和度和详细信息。
   > 
   > 
5. 将鼠标悬停在**连锁店**区域上方以显示**类别**中该部分的工具提示。  例如，将鼠标悬停在 **040-Juniors** 矩形中的 **Lindseys** 上方可显示青少年类别的 Lindsey 部分的工具提示。  
   ![](media/power-bi-visualization-treemaps/treemaphoverdetail_new.png)
6. [将树状图添加为仪表板磁贴（固定视觉对象）](service-dashboard-tiles.md)。 
7. [保存报表](service-report-save.md)。

## <a name="highlighting-and-cross-filtering"></a>突出显示和交叉筛选
有关使用筛选器窗格的信息，请参阅[向报表添加筛选器](power-bi-report-add-filter.md)。

突出显示树状图中的一个类别或详细信息可交叉突出显示和交叉筛选报表页上的其他可视化效果…，反之亦然。 若要执行此操作，可将一些视觉对象添加到同一页，或者将树状图复制/粘贴到已有其他视觉对象的报表页面。

1. 在树状图中，选择一个类别或类别中的一个连锁店。  这样可以交叉突出显示页面上的其他可视化效果。 例如，选择 **050-Shoes** 可显示鞋子的上年度销售额为 $3,640,471，其中 $2,174,185 来自 Fashions Direct。  
   ![](media/power-bi-visualization-treemaps/treemaphiliting.png)
2. 在**按连锁店的上年度销售额**饼图中，选择 **Fashions Direct** 切片。  
   ![](media/power-bi-visualization-treemaps/treemapnoowl.gif)
3. 若要管理图表相互交叉突出显示和交叉筛选的方式，请参阅 [Visualization interactions in a Power BI report（Power BI 报表中的可视化效果交互）](service-reports-visual-interactions.md)

## <a name="next-steps"></a>后续步骤
[Power BI 中的报表](service-reports.md)  
[向报表添加可视化效果](power-bi-report-add-visualizations-i.md)  
[Power BI 中的可视化效果类型](power-bi-visualization-types-for-reports-and-q-and-a.md)
[将可视化效果固定到仪表板](service-dashboard-pin-tile-from-report.md)  
[Power BI - 基本概念](service-basic-concepts.md)  
[试用一下 - 完全免费！](https://powerbi.com/)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)  

