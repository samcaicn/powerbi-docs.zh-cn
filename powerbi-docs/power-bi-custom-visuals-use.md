---
title: "将自定义视觉对象添加到报表中 (Desktop)"
description: "将自定义视觉对象添加到报表中 (Desktop)"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 03/15/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: b3a3e34fac546ee57cd66924e72a2c93aa647850
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="add-a-custom-visual-to-a-report-desktop"></a>将自定义视觉对象添加到报表中 (Desktop)
你已经[下载了自定义视觉对象模板](service-custom-visuals-office-store.md)并将其保存到你的计算机或其他位置。  下一步是将该自定义视觉对象模板导入报表，以便将其作为一个选项添加到“可视化效果”窗格中。

![](media/power-bi-custom-visuals-use/pbi-custom-viz-icon.png)

导入完成后，自定义视觉对象模板就已添加到特定报表。 如果想在另一个报表中使用该视觉对象模板，你也需要将其导入到该报表。 通过使用**另存为**选项保存具有自定义视觉对象的报表时，自定义视觉对象模板的副本将与新的报表一同保存。

1. 打开 Power BI Desktop 并选择你想要添加自定义可视化效果的报表。   
2. 有两个选项可导入自定义视觉对象模板：从**文件**菜单或从**可视化效果**窗格。
   
    **从“桌面文件”菜单**
   
    在报表的**文件**菜单上，选择**导入**&gt;**Power BI 自定义视觉对象**。 必须位于编辑视图。    
   
      ![](media/power-bi-custom-visuals-use/power-bi-import.png)
   
    **从“可视化效果”窗格**
   
    在**可视化效果**窗格中，选择**插入 (…)**。    
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
   
    选择“导出自定义视觉对象”。  
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
3. **查看警告**。
   
    自定义视觉对象有权访问报表中的数据，在共享包含自定义视觉对象的报表时，你的同事可能有权访问同一数据。 查看自定义视觉对象时务必小心，确保其来自可信源。 如果不确定是否使用通过电子邮件从 Office Online 应用商店或从一些其他来源中获得的特定自定义视觉对象，Microsoft 建议你与 IT 部门进行协作。
   
    ![](media/power-bi-custom-visuals-use/caution.png)
4. 导航到保存自定义视觉对象 .pbiviz 文件的位置，并将其打开。
5. 将向你的“可视化效果”窗格添加一个图标（也称为模板）。
   
    ![](media/power-bi-custom-visuals-use/visualuse.png)
6. 选择自定义视觉对象模板，以将其添加至报表中，方式与你对“可视化效果”窗格中的其他任何模板执行的操作相同。 添加字段和筛选器，并创建你的视觉对象。
7. 设置自定义视觉对象的格式，方法与你对其他视觉对象执行的操作相同。  在“可视化效果”窗格中，选择滚动油漆刷图标。 可用的格式设置选项会因视觉对象类型而有所不同。

## <a name="considerations-and-troubleshooting"></a>注意事项和疑难解答
* 若要支持将自定义视觉对象[导出到 PowerPoint](service-publish-to-powerpoint.md)，或[显示在客户订阅报表页后收到的电子邮件中](service-report-subscribe.md)，必须将自定义视觉对象定义为已通过 Microsoft 自定义视觉对象认证过程的“取得认证的自定义视觉对象”。  若要查看“取得认证的自定义视觉对象”列表，并详细了解认证过程，请参阅[取得认证的自定义视觉对象](power-bi-custom-visuals-certified.md)

## <a name="next-steps"></a>后续步骤
[从 Office 应用商店下载和使用自定义视觉对象](service-custom-visuals-office-store.md)  
[将自定义视觉对象添加到 Power BI 服务中的报表](power-bi-report-add-custom-visual.md)  
[将自定义视觉对象发布到 Office 应用商店](developer/office-store.md)  
[Power BI 中的自定义可视化效果](power-bi-custom-visuals.md)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

