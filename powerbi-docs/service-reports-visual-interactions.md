---
title: "更改视觉对象在报表中的交互方式"
description: "介绍如何在 Microsoft Power BI 报表中设置视觉对象的交互的文档。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Power BI 报表中的可视化交互
默认情况下，报表页上的可视化组件可用于交叉筛选和交叉突出显示页面上的其他可视化组件。
例如，在地图可视化组件上选择一个州会突出显示柱形图并筛选折线图以便仅显示适用于该州的数据。
请参阅[关于筛选和突出显示](power-bi-reports-filters-and-highlighting.md)。

若要更改此默认操作，请使用“视觉对象交互”控件。 视觉对象交互仅适用于[编辑视图](service-interact-with-a-report-in-editing-view.md)。 如果已与你共享了报表，你将不具备访问视觉对象交互的权限。

> [!NOTE]
> 词语“ *交叉筛选* ”和“ *交叉突出显示* ”用于区分本文描述的行为与使用“**筛选器**”窗格来筛选和突出显示可视化组件的效果。  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. 选择可视化组件并将其激活。  
2. 通过在顶部菜单栏中选择“视觉对象交互”将其开启。 请注意将鼠标悬停在报表页上的其他可视化组件上方时出现的筛选和突出显示图标。
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. 确定所选的可视化组件需要对其他组件产生的作用。  
   
   * 如果其应交叉筛选其他可视化组件，则选择“筛选”图标 ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png)。
   * 如果其应交叉突出显示该可视化组件，则选择“突出显示”图标 ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png)。
   * 如果其不应产生作用，则选择“不起作用”图标 ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png)。
4. 对报表页上的其他所有可视化组件重复执行此操作（可选）。

### <a name="next-steps"></a>后续步骤
[如何使用报表筛选器](power-bi-how-to-report-filter.md)

[报表中的筛选器和突出显示](power-bi-reports-filters-and-highlighting.md)

[Power BI - 基本概念](service-basic-concepts.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

