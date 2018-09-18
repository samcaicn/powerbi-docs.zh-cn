---
title: 更改 Power BI 报表中的图表排序方式
description: 更改 Power BI 报表中的图表排序方式
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 89891ead8eda1b8de4c7be943af2a9e9e98314c5
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44726078"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>更改 Power BI 报表中的图表排序方式
在 Power BI 报表中，可以按图表中类别名称的字母顺序，或者每个类别的数值对大多数可视化对象排序。 例如，下图按商店名称排序。

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

可以轻松地将排序依据从类别（商店名称）更改为值（每平方英尺销售额）。

1. 选择省略号 (…)，然后选择**按每平方英尺销售额进行排序**。
2. 如有需要，可选择排序图标 ![](media/power-bi-report-change-sort/sorticon.png) 更改为**降序**。

   ![](media/power-bi-report-change-sort/sortby.gif)

   **注意**：并非所有视觉对象都可以排序。  例如，以下视觉对象无法排序：树状图、地图、着色地图、散点图、仪表图、卡片图、多行卡片图、瀑布图。

## <a name="saving-changes-you-make-to-sort-order"></a>保存对排序顺序的更改
Power BI 报表可保留你对筛选器、切片器、排序和其他数据视图的更改。 因此，如果离开报表并在稍后返回，会保存你的更改。  如果想要将更改还原为报表作者的设置，请选择顶部菜单栏中的“重置为默认值”。 

![持久性排序](media/power-bi-report-change-sort/power-bi-reset-to-default.png)

但是，如果“重置为默认值”按钮灰显，则表示作者已禁用保存（保留）更改的功能。

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>使用其他条件排序
有时候，你想使用不同的字段或其他条件对视觉对象排序。  例如，你可能想按月份（而不是字母顺序）排序，或者按整个数值而不是数字排序（例如 0、1、9、20，而不是 0、1、20、9）。  

在某些情况下，你可以按照你想要的方式对视觉对象进行排序，例如按月。  但如果不是，可能是因为报表背后的数据集需要一些调整。 下面提供了几种解决方案：

* 在 Power BI Desktop 中，[可以使用“Data Tools 模型”选项卡按不同的列进行排序](desktop-sort-by-column.md)。
* 在 Excel 中，如果你是数据集的所有者，则可以添加连接月份名称和数字的新列。 然后刷新或重新导入数据集，确保新列位于“字段”区域中。
* 在 Excel 中，确保将数值列标记为“整数”或“小数”，而不是“文本”。

## <a name="next-steps"></a>后续步骤
[Power BI 报表中的可视化对象](visuals/power-bi-report-visualizations.md)的详细信息。

[Power BI - 基本概念](service-basic-concepts.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)
