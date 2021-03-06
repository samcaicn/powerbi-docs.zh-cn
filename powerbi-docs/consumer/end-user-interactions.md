---
title: 更改视觉对象在报表中的交互方式
description: 介绍如何在 Microsoft Power BI 服务报表和 Power BI Desktop 报表中设置视觉对象交互的文档。
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: N_xYsCbyHPw
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: a70d5ac5265f88a6e407815ecb0fb6ac23e24416
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565420"
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Power BI 报表中的可视化交互
如果具有编辑报表的权限，则可以使用“视觉对象交互”，更改报表页上的可视化效果相互影响的方式。 

默认情况下，报表页上的可视化组件可用于交叉筛选和交叉突出显示页面上的其他可视化组件。
例如，在地图可视化组件上选择一个州会突出显示柱形图并筛选折线图以便仅显示适用于该州的数据。
请参阅[关于筛选和突出显示](../power-bi-reports-filters-and-highlighting.md)。 如果具有支持[钻取](end-user-drill.md)的可视化效果，在默认情况下，钻取某个可视化效果不会对报表页上的其他可视化效果造成影响。 但可以同时覆盖这两种默认行为，并且可以对每个可视化效果设置交互。

本文演示如何在 Power BI 服务[编辑视图](../service-interact-with-a-report-in-editing-view.md)和 Power BI Desktop 中使用“视觉对象交互”。 如果已与你共享了报表，你将无法更改视觉对象交互设置。

> [!NOTE]
> 词语“ *交叉筛选* ”和“ *交叉突出显示* ”用于区分本文描述的行为与使用“**筛选器**”窗格来筛选和突出显示可视化组件的效果。  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. 选择可视化组件并将其激活。  
2. 显示“视觉对象交互”选项。
    - 在 Power BI 服务中，从报表菜单栏中选择下拉列表。

       ![视觉对象交互下拉列表](./media/end-user-interactions/power-bi-visual-interaction.png)

    - 在 Desktop 中，选择“格式”>“交互”。

        ![依次选择“格式”、“交互”](./media/end-user-interactions/pbi-visual-interaction-desktop.png)

3. 要打开可视化效果交互控件，请选择“编辑交互”。 Power BI 将交叉筛选和交叉突出显示图标添加到报表页上的所有其他可视化效果中。
   
    ![启用视觉对象交互的报表](./media/end-user-interactions/power-bi-icons-on.png)
3. 确定所选的可视化组件需要对其他组件产生的作用。  然后，对报表页上的其他所有可视化效果重复执行此操作（可选）。
   
   * 如果应交叉筛选可视化效果，则选择“筛选”图标 ![筛选图标](./media/end-user-interactions/pbi-filter-icon-outlined.png)。
   * 如果应交叉突出显示该可视化效果，则选择“突出显示”图标 ![突出显示图标](./media/end-user-interactions/pbi-highlight-icon-outlined.png)。
   * 如果其无影响，则选择“无影响”图标 ![无影响图标](./media/end-user-interactions/pbi-noimpact-icon-outlined.png)。

4. 要启用钻取控件，请选择“钻取筛选其他视觉对象”。  现在，在可视化效果中向下钻取（和向上钻取）时，报表页上的其他可视化效果将发生改变，以反映当前的钻取选择。 

   ![启用钻取控件的视频](./media/end-user-interactions/drill2.gif)

### <a name="next-steps"></a>后续步骤
[如何使用报表筛选器](end-user-report-filter.md)

[报表中的筛选器和突出显示](../power-bi-reports-filters-and-highlighting.md)

[Power BI - 基本概念](end-user-basic-concepts.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

