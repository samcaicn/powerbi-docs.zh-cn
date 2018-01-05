---
title: "更改 Power BI 报表中的图表排序方式"
description: "更改 Power BI 报表中的图表排序方式"
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
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 13da4602306b1218baee81909d37897524f6dfc9
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>更改 Power BI 报表中的图表排序方式
在 Power BI 报表中，可以按图表中类别名称的字母顺序，或者每个类别的数值对大多数可视化对象排序。 例如，下图按商店名称排序。

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

可以轻松地将排序依据从类别（商店名称）更改为值（每平方英尺销售额）。

1. 选择省略号 (…)，然后选择**按每平方英尺销售额进行排序**。
2. 如有需要，可选择排序图标 ![](media/power-bi-report-change-sort/sorticon.png) 更改为**降序**。
   
   ![](media/power-bi-report-change-sort/sortby.gif)
   
   **注意**：并非所有视觉对象都可以排序。  例如，以下视觉对象无法排序：树状图、地图、着色地图、散点图、仪表图、卡片图、多行卡片图、瀑布图。

## <a name="sorting-using-other-criteria"></a>使用其他条件排序
有时候，你想使用不同的字段或其他条件对视觉对象排序。  例如，你可能想按月份（而不是字母顺序）排序，或者按整个数值而不是数字排序（例如 0、1、9、20，而不是 0、1、20、9）。  

在某些情况下，你可以按照你想要的方式对视觉对象进行排序，例如按月。  但如果不是，可能是因为报表背后的数据集需要一些调整。 下面提供了几种解决方案：

* 在 Power BI Desktop 中，[可以使用“Data Tools 模型”选项卡按不同的列进行排序](desktop-sort-by-column.md)。
* 在 Excel 中，如果你是数据集的所有者，则可以添加连接月份名称和数字的新列。 然后刷新或重新导入数据集，确保新列位于“字段”区域中。
* 在 Excel 中，确保将数值列标记为“整数”或“小数”，而不是“文本”。

## <a name="next-steps"></a>后续步骤
[Power BI 报表中的可视化对象](power-bi-report-visualizations.md)的详细信息。

[Power BI - 基本概念](service-basic-concepts.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

