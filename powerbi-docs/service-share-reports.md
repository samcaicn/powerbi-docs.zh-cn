---
title: "与同事共享 Power BI 报表"
description: "了解如何与组织中的同事共享 Power BI 报表和筛选的报表。"
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: complete
qualitydate: 06/22/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/05/2017
ms.author: maggies
ms.openlocfilehash: 2a7b4cc652e600b9a368f6f7eda657c06e131da3
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="share-power-bi-reports-with-your-coworkers"></a>与同事共享 Power BI 报表
共享是一种使多人能够访问你的仪表板和报表的有效方式。 Power BI 提供了[多种开展协作和分发报表的方式](service-how-to-collaborate-distribute-dashboards-reports.md)，共享只是其中之一。

要进行共享，你和收件人都需要一个 [Power BI Pro 许可证](service-free-vs-pro.md)，或者内容需要位于[高级容量](service-premium.md)中。 建议？ Power BI 团队始终期待你的反馈，因此，请转到 [Power BI 社区站点](https://community.powerbi.com/)。

可以从“我的工作区”或应用工作区中，与处于同一电子邮件域的同事共享报表。 共享报表时，你与之共享的人员可查看该报表并与其交互，但不能编辑它。 除非应用[行级别安全性 (RLS)](service-admin-rls.md)，否则他们会看到你在报表中看到的相同数据。 

## <a name="share-a-power-bi-report"></a>共享 Power BI 报表
1. 在 Power BI 服务中，[创建一个仪表板](service-dashboard-create.md)，其中至少包含一个可链接到想要共享的报表的磁贴。 
   
    即使只想共享报表，也需要先创建一个链接到该报表的仪表板，然后再将其共享。 

1. 在仪表板的右上角选择“共享”。

     ![选择“共享”](media/service-share-reports/power-bi-share-upper-right.png)
  
2. 向计划的收件人发出关于它的通知。 如果不想向这些收件人发送关于此仪表板的邮件，则清除“向收件人发送电子邮件通知”复选框。

     ![清除“发送电子邮件通知”复选框](media/service-share-reports/power-bi-share-dont-send-mail.png)

4. 选择**共享**。

      你与之共享仪表板的人员现在有权限查看基础报表。 

1. 在 Power BI 服务中打开此报表，复制报表页 URL，然后将其发送给同事。 
   
    当他们选中此链接时，Power BI 将打开该报表的只读版本。

## <a name="share-a-filtered-version-of-a-report"></a>共享筛选的报表版本
如果你想要共享筛选的报表版本，该怎么办？ 也许一个报表仅显示特定城市或销售人员或年份的数据。 可以通过创建自定义 URL 来执行此操作。

1. 打开[编辑视图](service-reading-view-and-editing-view.md)中的报表、应用筛选器并保存报表。
   
   在此示例中，我们正在筛选[零售分析示例](sample-tutorial-connect-to-the-samples.md)，从而仅显示“区域”等于“NC”的值。
   
   ![报表筛选窗格](media/service-share-reports/power-bi-filter-report2.png)
2. 将以下代码添加到以下报表页 URL 的末尾：
   
   ?filter=*tablename*/*fieldname* eq *value*
   
    此字段必须是字符串类型，并且表名或字段名都不可以包含空格。
   
   在本示例中，表的名称是 **Store**，字段的名称是 **Territory**，我们要筛选的依据值是 **NC**：
   
    ?filter=Store/Territory eq 'NC'
   
   ![已筛选的报表 URL](media/service-share-reports/power-bi-filter-url3.png)
   
   浏览器会添加特殊字符来表示斜杠、空格和撇号，因此最终会看到：
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-10a61f70f2f5/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. 将此 URL 发送给同事。 
   
   当他们选中此链接时，Power BI 将打开已筛选报表的只读版本。

## <a name="next-steps"></a>后续步骤
* 想提供反馈？ 请转到 [Power BI 社区站点](https://community.powerbi.com/)提出你的建议。
* [应如何针对仪表板及报表开展协作并进行共享？](service-how-to-collaborate-distribute-dashboards-reports.md)
* [共享仪表板](service-share-dashboards.md)
* 更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)。

