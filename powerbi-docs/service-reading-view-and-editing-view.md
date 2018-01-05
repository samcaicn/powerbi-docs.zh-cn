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
ms.date: 12/21/2017
ms.author: mihart
ms.openlocfilehash: 7c0c09bd04eac31bac00e4562853c99befe9715f
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="reading-view-and-editing-view-in-power-bi-service-reports"></a>Power BI 服务报表中的“阅读视图”和“编辑视图”
Power BI 服务（不是 Power BI Desktop）提供两种模式用于查看报表和与其交互：“阅读视图”和“编辑视图”。  

“阅读视图”可供所有用户使用，而“编辑视图”仅供报表创建者和所有者使用。 “阅读视图”面向报表使用者：通过应用打开报表，或者与其共享了报表的同事。 “阅读视图”可确保特定报表的每个使用者都会看到相同的报表、相同的可视化对象和应用的相同筛选器。  使用者可与报表交互，但不能保存更改。

>**注意**：在某些情况下，由于行级安全性和数据权限方面的原因，报表使用者可能看到不同的数据。 

“编辑视图”仅适用于报表的创建者，或者作为应用工作区的成员或管理员共同拥有报表的人员。

## <a name="reading-view"></a>阅读视图

“阅读视图”为处理和了解数据提供了一种有趣且安全的方式。 阅读视图不像[编辑视图](service-interact-with-a-report-in-editing-view.md)那样可以进行交互，但它仍提供了许多浏览数据的选项。 例如，在查看只能在阅读视图中打开的[与你共享](service-share-dashboards.md)的报表时，使用阅读视图会非常有用。

有关详细信息，请参阅 [Power BI 报表的阅读视图](service-interact-with-a-report-in-reading-view.md)。

## <a name="editing-view"></a>编辑视图
在 Power BI 的编辑视图中（对比[阅读视图](service-interact-with-a-report-in-reading-view.md)），你可以通过在报表中添加和删除字段、更改可视化类型、创建新可视化效果以及添加和删除可视化效果与页面，更深入地了解数据。

有关详细信息，请参阅 [Power BI 报表的编辑视图](service-interact-with-a-report-in-editing-view.md)。

## <a name="navigating-between-editing-view-and-reading-view"></a>在“编辑视图”和“阅读视图”之间导航
请记住，只有报表创建者和所有者才能在“编辑视图”中打开报表。

1. 默认情况下，报表通常在“阅读视图”中打开。 如果看到了“编辑报表”选项，则表示目前在“阅读视图”中。 如果“编辑报表”灰显，则你无权在“编辑视图”中打开报表。

   ![](media/service-reading-view-and-editing-view/power-bi-edit-report-grey.png)

2. 如果“编辑报表”未灰显，则选择它可在“编辑视图”中打开报表。 
   
   ![](media/service-reading-view-and-editing-view/power-bi-edit-report.png)
   
   报表现在位于“编辑视图”中，并使用上次你在“阅读视图”中使用的相同[显示设置](power-bi-report-display-settings.md)。

2. 若要返回到“阅读视图”，请从顶部导航栏中选择“阅读视图”。
   
    ![](media/service-reading-view-and-editing-view/power-bi-reading-view.png)

可通过多种方式来与“阅读视图”中的报表交互，交叉分析数据可以发现见解，并获取问题的答案。  下一主题[与编辑视图中的报表交互](service-interact-with-a-report-in-editing-view.md)列出并详细介绍了这些操作。

### <a name="next-steps"></a>后续步骤
[与阅读视图中的报表交互](service-interact-with-a-report-in-editing-view.md)    
返回 [Power BI 中的报表](service-reports.md)    
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/) 

