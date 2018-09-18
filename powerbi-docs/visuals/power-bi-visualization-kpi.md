---
title: KPI 视觉对象
description: 在 Power BI 服务和 Power BI Desktop 中创建 KPI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: xmja6EpqaO0
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: bb1ebf08c7ffb7a18cc0dd273c767c082f89f1aa
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44728913"
---
# <a name="kpi-visuals"></a>KPI 视觉对象
关键绩效指标 (KPI) 是一个视觉提示，用于传达针对可度量目标已完成的进度。 有关 KPI 的详细信息，请参阅 [Microsoft Developer Network](https://msdn.microsoft.com/library/hh272050)。

## <a name="when-to-use-a-kpi"></a>何时使用 KPI
当存在以下情况时，KPI 是一个不错的选择：

* 要衡量进度（我是超前了还是落后了？）
* 要衡量与目标的距离（我提前或落后了多少？）   

## <a name="kpi-visual-requirements"></a>KPI 可视化要求
关键绩效指标 (KPI) 基于特定的指标值，旨在帮助你针对定义的目标评估指标的当前值和状态。 因此，KPI 视觉对象需要一个用于计算值的*基础*指标值、一个*目标*指标或指标值，以及一个阈值或目标。

> [!NOTE]
> 目前 KPI 数据集需要包含 KPI 的目标值。 如果数据集不包含目标，则可以通过向数据模型或 PBIX 文件添加带目标的 Excel 工作表来创建目标。
> 
> 

## <a name="how-to-create-a-kpi"></a>如何创建 KPI
若要遵循示例执行操作，请登录到 Power BI 服务，然后选择“获取数据”>“示例”>“零售分析示例”。 我们将创建一个 KPI 来衡量针对销售目标我们已完成的进度。

或观看 Will 介绍如何创建单个指标视觉：仪表、卡片和 KPI。

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. 在[编辑视图](../service-reading-view-and-editing-view.md)中打开报表并[添加新页面](../power-bi-report-add-page.md)。    
2. 选择**销售 > 本年度总单位数**。  这是指标。
3. 添加**时间 > 月份**。  这用于表示趋势。
4. 重要说明：按月对图表进行排序。 在将可视化效果转换为 KPI 后，没有要进行排序的选项。

    ![](media/power-bi-visualization-kpi/power-bi-sort-by-month.png)
5. 在“可视化”窗格中选择 KPI 图标，以便将可视化效果转换为 KPI。
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-icon.png)
6. 添加目标值。 添加上年度销售额作为目标值。 将**上年度总单位数**拖到**目标**字段。
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi.png)
7. 你也可以根据需要选择滚动油漆刷图标打开“格式”窗格来设置 KPI 格式。
   
   * **指标** - 控制指标的显示单位和小数位数。
   * **趋势轴** - 当设置为**开**时，趋势轴显示为 KPI 视觉对象的背景。  
   * **目标值** - 当设置为**开**时，视觉对象将显示目标值和相对于目标的距离百分比。
   * **颜色编码 > 方向** - 一些 KPI 被视为值越高越好，一些则视为值越低越好。 例如，收入与等待时间。 通常更高的收入值好于更高的等待时间值。 选择“越高越好”，并选择性地更改颜色设置。

1. 如果你已经具有所想要的 KPI，[将其固定到仪表板](../service-dashboard-pin-tile-from-report.md)。

KPI 还可用于移动设备 – 让你始终保持与业务中心的联系。

## <a name="considerations-and-troubleshooting"></a>注意事项和疑难解答
* 如果 KPI 并非如上所示，则可能是因为需要按月进行排序。 由于 KPI 没有排序选项，则需要先按月排序，然后将可视化效果转换为 KPI。

## <a name="next-steps"></a>后续步骤

[Power BI 报表中的可视化效果](power-bi-report-visualizations.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

