---
title: "Power BI 服务报表中的“阅读视图”和“编辑视图”"
description: "Power BI 服务报表的“阅读视图”与“编辑视图”之间的差异的简要概述"
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
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 6eca438c9e12d99f925aef864ed9b74e16ef30b7
ms.sourcegitcommit: 0a16dc12bb2d39c19e6b0002b673a8c1d81319c9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="reading-view-and-editing-view-in-power-bi-service-reports"></a>Power BI 服务报表中的“阅读视图”和“编辑视图”
Power BI 服务（不是 Power BI Desktop）提供两种模式用于查看报表和与其交互：“阅读视图”和“编辑视图”。 “阅读视图”可供所有用户使用且专为报表使用者设计，而“编辑视图”仅供报表创建者和所有者使用。 

![报表创建者和报表使用者的图稿](media/service-reading-view-and-editing-view/power-bi-creators-consumers.png)

## <a name="report-reading-view"></a>报表阅读视图

 阅读视图是浏览和与报表交互的方式-- 它是一种有趣且安全地使用和了解数据的途径。 阅读视图面向报表使用者 - 通过应用打开报表，或者[与其共享](service-share-dashboards.md)报表的人员。 “阅读视图”可确保特定报表的每个使用者都会看到相同的报表、相同的可视化对象和应用的相同筛选器。  使用者可与报表交互，但不能保存更改。

>**注意**：在某些情况下，由于行级安全性和数据权限方面的原因，报表使用者可能看到不同的数据。 

## <a name="report-editing-view"></a>报表编辑视图

编辑视图仅适用于报表的创建者，或者[作为应用工作区的成员或管理员共同拥有报表](service-create-distribute-apps.md)的人员。

编辑视图专用于报表创建者。 创建者可以从中导入并连接数据集、浏览数据，并生成报表和仪表板。 在“编辑视图”中，创建者可通过在报表中添加和删除字段、更改可视化效果类型、创建新的可视化效果，以及从报表中添加和删除可视化效果与页面，更深入的挖掘数据。 然后，他们可与同事共享其创建的报表。

## <a name="reading-view-versus-editing-view"></a>“阅读视图”和“编辑视图”对比
此图未列出 Power BI 服务的所有报表功能！ 它仅列出了在“阅读视图”和“编辑视图”中不可用的报表任务。 


|任务  | 阅读视图  | 编辑视图 |
|-------------------------|-------|-------|
|**整体报表**  |
||||
| [创建或编辑报表](service-report-create-new.md) | 否  | 是 |
| [共享报表](service-share-reports.md)| 是 | 是，并且还可管理权限，其中包括向其他人提供所有者权限。 |
| [从“筛选器”窗格创建持续（永久）视觉对象级别、drilthrough、页面级和报表级筛选器](power-bi-report-add-filter.md) | 否  | 是 |
| [使用报表“筛选器”窗格](power-bi-how-to-report-filter.md) | 是，可使用现有的筛选器，但更改不会随报表一起保存。 | 是 |
| [使用报表“分析”窗格](service-analytics-pane.md) | 否 | 是 |
| [报表**视图**选项](power-bi-report-display-settings.md) | 是，但存在一些例外情况。 | 是，包括网格线、对齐和锁定在内所有的操作。 |
| [创建刷新计划](refresh-data.md) | 否  | 是 |
| [订阅报表](service-report-subscribe.md) | 是 | 否 |
| [问答 - 在报表中提问](power-bi-q-and-a.md) | 否  | 是 |
| [查看使用情况指标](service-usage-metrics.md) | 是，在报表画布上。 | 是，在报表列表（内容视图）中 |
| [相关视图](service-related-content.md) | 是，在报表画布上。 | 是，在报表列表（内容视图）中 |
| [保存报表](service-report-save.md) | 是，但只能使用“另存为”。 | 是 |
| [删除报表](service-delete.md) | 否  | 是 |
|**报表页** |
||||
| [添加或重命名报表页](power-bi-report-add-page.md)  | 否  | 是  |
| [复制报表页](power-bi-report-copy-paste-page.md) | 否  | 是 |
| [删除报表页](service-delete.md) | 否 | 是 |
|**使用报表可视化效果**|
||||
| [将可视化效果添加到报表](power-bi-report-add-visualizations-i.md) | 否  | 是 |
| [向报表添加文本框和形状](power-bi-reports-add-text-and-shapes.md) | 否  | 是 |
| [使用报表“格式化”窗格](service-the-report-editor-take-a-tour.md) | 否 | 是 |
| [设置视觉对象交互](service-reports-visual-interactions.md) | 否  | 是 |
| [显示用于创建可视化效果的数据](service-reports-show-data.md) | 否  | 是 |
| [配置钻取](power-bi-visualization-drill-down.md) | 否  | 是 |
| [更改在用的可视化效果](power-bi-report-change-visualization-type.md) | 否 | 是|
| [删除可视化效果、文本框或形状](service-delete.md)| 否 | 是 |


## <a name="navigating-between-editing-view-and-reading-view"></a>在“编辑视图”和“阅读视图”之间导航
请记住，仅报表创建者和所有者才能在“编辑视图”中打开报表。

1. 默认情况下，报表通常在“阅读视图”中打开。 如果看到了“编辑报表”选项，则表示目前在“阅读视图”中。 如果“编辑报表”灰显，则你无权在“编辑视图”中打开报表。

   ![编辑灰显报表](media/service-reading-view-and-editing-view/power-bi-edit-report-grey.png)

2. 如果“编辑报表”未灰显，则选择它可在“编辑视图”中打开报表。 
   
   ![编辑报表选项](media/service-reading-view-and-editing-view/power-bi-edit-report.png)
   
   报表现在位于“编辑视图”中，并使用上次在“阅读视图”中所用的相同[显示设置](power-bi-report-display-settings.md)。

2. 若要返回到“阅读视图”，请从顶部导航栏中选择“阅读视图”。
   
    ![“阅读视图”选项](media/service-reading-view-and-editing-view/power-bi-reading-view.png)



### <a name="next-steps"></a>后续步骤
可通过多种方式来与“阅读视图”中的报表交互，交叉分析数据可以发现见解，并获取问题的答案。  下一主题[在阅读视图中与报表交互](service-interact-with-a-report-in-editing-view.md)详细介绍了这些操作。    
返回 [Power BI 中的报表](service-reports.md)    
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/) 

