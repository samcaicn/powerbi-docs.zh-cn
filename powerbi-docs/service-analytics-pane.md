---
title: "Power BI 服务中的分析窗格"
description: "在 Power BI 服务中创建视觉对象的动态参考行"
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
ms.date: 05/02/2017
ms.author: mihart
ms.openlocfilehash: 30fc0731f819f063aa04e856e8acc75a69f64a59
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="analytics-pane-in-power-bi-service"></a>Power BI 服务中的分析窗格
通过 **Power BI 服务**的“**分析**”窗格，可以向可视化效果添加动态参考行，并重点关注重要趋势或见解。

![](media/service-analytics-pane/power-bi-analytics-pane.png)

> [!NOTE]
> 仅当在报表画布上选择视觉对象时才会显示“分析”窗格。
> 
> 

## <a name="using-the-analytics-pane"></a>使用分析窗格
通过“**分析**”窗格，可以创建以下类型的动态参考行（并非所有的行都适用于所有视觉对象类型）：

* X 轴恒线
* Y 轴恒线
* 最小值线
* 最大值线
* 平均线
* 中线
* 百分位数线

以下各部分介绍如何在可视化效果中使用“**分析**”窗格和动态参考行。

若要查看视觉对象的可用动态参考行，请按照下列步骤操作：

1. 选择或创建视觉对象，然后从“**可视化效果**”窗格选择“**分析**”图标 ![](media/service-analytics-pane/power-bi-analytics-icon.png)。
2. 为想要创建的行类型选择向下箭头以展开其选项。 本示例中将选择“**平均线**”。
   
   ![](media/service-analytics-pane/power-bi-add.png)
3. 若要创建一个新行，请选择“**+ 添加**”。 然后，可以通过双击文本框，键入名称来为行指定名称。
   
   对于行提供了各种选项，例如可以选择其“颜色”、“透明度”、“样式”和“位置”（与视觉对象的数据元素有关），以及是否包括标签。 重要的是，通过选择“**度量值**”下拉列表，可以选择想要行基于视觉对象中的哪个**度量值**，它会自动使用视觉对象中的数据元素予以填充。 本示例中将选择“打开商店数”作为度量值，对其设置“平均# 打开商店”标签，并对其他几个选项进行自定义，如下所示。
   
   ![](media/service-analytics-pane/power-bi-average-line.png)
4. 如果想要显示数据标签，请将“**数据标签**”滑块移至开启状态。 执行此操作可以为数据标签获取大量其他选项。
5. 请注意“**分析**”窗格中的“**平均线**”项旁显示的数目。 它指出目前在视觉对象上所拥有的动态行的数量和类型。 如果添加了“常量行”作为商店数目标 9，则可以看到“分析”窗格显示现在也有适用于此视觉对象的“常量行”参考。
   
   ![](media/service-analytics-pane/power-bi-reference-lines.png)
   
   如果所选择的视觉对象不能具有对其适用的动态参考行（本示例中为**映射**视觉对象），则会在选择“**分析**”窗格时看到以下信息。
   
   ![](media/service-analytics-pane/power-bi-no-lines.png)

通过使用“**分析**”窗格创建动态参考行，可以突出显示各种有趣的见解。

我们正在计划开发更多的特性和功能，其中包括扩展可以具有适用动态参考行的视觉对象，因此请经常查看其新增功能。

## <a name="limitations"></a>限制
是否能使用动态参考行取决于正在使用的视觉对象的类型。 下表显示动态行当前适用的视觉对象：

动态行完全适用于以下视觉对象：

* 分区图
* 折线图
* 散点图
* 簇状柱形图
* 簇状条形图

以下视觉对象仅能使用“**分析**”窗格中的恒线：

* 堆积面积图
* 堆积条形图
* 堆积柱形图
* 百分比堆积条形图
* 百分比堆积柱形图

对于以下视觉对象，趋势线是当前仅有的选项：

* 非堆积折线图
* 簇状柱形图

最后，非笛卡尔视觉对象当前无法应用“**分析**”窗格中的动态行，例如：

* 矩形图
* 饼图
* 圆环图
* 表

## <a name="next-steps"></a>后续步骤
[Power BI Desktop 中的分析窗格](desktop-analytics-pane.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

