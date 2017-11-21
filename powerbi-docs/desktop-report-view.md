---
title: "Power BI Desktop 中的报表视图"
description: "Power BI Desktop 中的报表视图"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 3715f2b877073357975af76495f955ff204cbc73
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="report-view-in-power-bi-desktop"></a>Power BI Desktop 中的报表视图
如果你一直在使用 Power BI，就知道它非常便于创建可为数据提供动态透视和深入见解的报表。 在 Power BI Desktop 中，Power BI 还具有更高级的功能。 通过 Power BI Desktop，可创建高级查询、混合多个源中的数据和创建表格之间的关系等。

Power BI Desktop 提供**报表视图**，可在其中创建任何数量具有可视化内容的报表页。 此处报表视图所提供的设计体验与 Power BI 中报表的编辑视图所提供的几乎相同。 可四处移动可视化内容，进行复制粘贴、合并等。

两者的区别在于当使用 Power BI Desktop 时，可运用查询并对数据建模以确保数据支持报表中的最佳见解。 无论在本地驱动器还是云中，都可在任何位置保存 Power BI Desktop 文件。

## <a name="lets-take-a-look"></a>我们来看一下吧！
首次在 Power BI Desktop 中加载数据时，将显示具有空白画布的**报表视图**。

![](media/desktop-report-view/pbi_reportviewinpbidesigner_reportview.png)

通过选择左侧导航栏中的图标，可在**报表视图**、**数据视图**和**关系视图**之间进行切换：

![](media/desktop-report-view/pbi_reportviewinpbidesigner_changeview.png)

添加一些数据后，可在画布中新的可视化对象内添加字段。

![](media/desktop-report-view/pbid_reportview_addvis.gif)

若要更改可视化对象的类型，可在功能区的**可视化**组中将其选中，或者右键单击并从**更改可视化类型**图标中另选一种。

![](media/desktop-report-view/pbid_reportview_changevis.gif)

> [!TIP]
> 请务必试用不同的可视化类型。 可视化对象可清楚传达数据中的信息，这一点非常重要。
> 
> 

报表将至少具有一个可供使用的空白页。 页面将显示在画布左侧的浏览器窗格中。 可向页面添加各种类型的可视化效果，但请不要过度编写。 如果页面上的可视化效果太多，将使其看起来杂乱，很难找到正确信息。 可向报表添加新页面，只需单击功能区上的**新建页面**即可。

![](media/desktop-report-view/pbidesignerreportviewnewpage.png)

若要删除页面，请单击报表视图底部页面的选项卡上的 **X**。

![](media/desktop-report-view/pbi_reportviewinpbidesigner_deletepage.png)

> [!NOTE]
> 报表和可视化对象均不可固定到 Power BI Desktop 中的仪表板上。 为此，需要[从 Power BI Desktop 发布](desktop-upload-desktop-files.md)到 Power BI 站点。
> 
> 

