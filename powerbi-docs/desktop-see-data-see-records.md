---
title: "在 Power BI Desktop 中查看视觉对象的数据和记录"
description: "使用 Power BI Desktop 的“查看数据”和“查看记录”功能深入了解详细信息"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 02/22/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: c44a5140fe40217aac170abb0b351197803b6299
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>使用 Power BI Desktop 的“查看数据”和“查看记录”功能
在 **Power BI Desktop** 中，可以深入了解任意视觉对象的详细信息，并能查看选定视觉对象的数据文本或单个数据元素文本。 这些功能有时亦称为“单击后了解详细信息”、“深入了解”或“深入了解详细信息”。

可以使用“**查看记录**”功能查看视觉对象中某个选定数据元素的基础行，也可以使用“**查看数据**”功能查看视觉对象中使用的值文本。 使用“**查看数据**”和“**查看记录**”功能时需要遵循一些限制，本文结尾处将予以介绍。

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>使用 Power BI Desktop 中的“查看数据”功能
“**查看数据**”按钮位于功能区的“**可视化工具**”部分中的“**数据/钻取**”选项卡内。

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

也可以右键单击视觉对象，然后从随即显示的菜单中选择“**查看数据**”，从而使用“**查看数据**”功能。

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> 必须将鼠标悬停在视觉对象中的数据点上方，才能在右键单击后看到菜单。
> 
> 

在你选择“**查看数据**”后，**Power BI Desktop** 会重点关注你选择的视觉对象和数据，并在画布空间内专门显示视觉对象和数据文本。 视觉对象显示在画布的上半部分，数据显示在下半部分，如下图所示。 这是水平视图。

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

还可以选择右上角的图标，切换到垂直视图（或返回水平视图）。

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

若要返回报表，请选择画布左上角的“**< 返回报表**”。

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>使用 Power BI Desktop 中的“查看记录”功能
还可以重点关注视觉对象中的一个数据元素，然后深入了解此元素的数据。 选择视觉对象后，使用“**查看记录**”功能的方式有两种：可以启用“**数据/钻取**”功能区中的“**查看记录**”切换按钮，然后单击数据元素；也可以右键单击数据元素，然后从随即显示的菜单中选择“**查看记录**”。

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> 如果选定的视觉对象不支持“查看记录”，功能区上的按钮会灰显。
> 
> 

在你选择“**查看记录**”后，**Power BI Desktop** 会重点关注单个数据元素，并在画布空间内专门显示该元素的数据，如下图所示。

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

> [!NOTE]
> 无法将“查看记录”视图中查看的（或用户修改的）数据更改保存到报表。

若要返回报表，请选择画布左上角的“**返回报表**”按钮。

## <a name="limitations"></a>限制
使用“**查看数据**”或“**查看记录**”功能时，需要遵循几个限制：

* 仅支持以下类型的视觉对象：
  * **条形图**
  * **列**
  * **地图图表**
  * **树形图**
  * **着色地图**
  * **饼图**
  * **环形图**
  * **漏斗图**
* 如果视觉对象使用计算度量值，则不能使用**查看记录**
* 连接到实时多维 (MD) 模型时无法使用**查看记录**

## <a name="next-steps"></a>后续步骤
**Power BI Desktop** 提供各种报表格式和数据管理功能。 请参阅下列资源，其中列举了部分示例：

* [在 Power BI Desktop 中使用分组和装箱](desktop-grouping-and-binning.md)
* [在 Power BI Desktop 报表中使用网格线、与网格对齐、z 顺序、对齐和分布](desktop-gridlines-snap-to-grid.md)

