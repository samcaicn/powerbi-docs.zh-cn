---
title: "Power BI 支持的 Quick Insights 类型"
description: "Power BI 中的 Quick Insights。"
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
ms.date: 09/03/2017
ms.author: mihart
ms.openlocfilehash: 13f5614cf121b17d8ae4dff9653f5789372f7f49
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="types-of-quick-insights-supported-by-power-bi"></a>Power BI 支持的 Quick Insights 类型
## <a name="how-does-quick-insights-work"></a>Quick Insights 的工作原理
Power BI 可快速搜索数据集的不同子集，同时应用一组复杂的算法来发现潜在相关的见解。 Power BI 会在预定时间内扫描数据集中尽可能多的内容。

可以对数据集或磁贴运行快速数据分析（相关数据分析）。   

## <a name="what-types-of-quick-insights-can-we-find"></a>我们可以找到哪些类型的快速见解？
以下是我们所使用的一些算法：

## <a name="category-outliers-topbottom"></a>类别离群值（上/下）
针对模型中的度量值，突出显示维度的一或两个成员值远大于维度的其他成员值的情况。  

![](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>更改时序中的点
突出显示数据时序中的趋势明显变化的情况。

![](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>关联
检测当根据数据集中的某个维度绘制多个度量值时，多个度量值彼此之间显示关联的情况。

![](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>低方差
检测数据点不偏离平均值的情况。

![](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>多数（主要因素）
查找当总值由另一个维度分解时，其多数可能归因于单一因素的情况。  

![](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>时序中的整体趋势
检测时序数据中的向上或向下趋势。

![](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>时序中的季节性
查找时序数据中的周期模式，例如每周、每月或每年的季节性。

![](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>稳定份额
突出显示子值的份额相对于跨连续变量的整体父值有父子关联的情况。

![](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>时序离群值
针对跨时序的数据，检测特定日期或时间值明显不同于其他日期/时间值的情况。

![](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>后续步骤
[Power BI 快速见解](service-insights.md)

如果你拥有一个数据集，请[对其进行优化以用于 Quick Insights](service-insights-optimize.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

