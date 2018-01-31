---
title: "开始使用 Power BI 报表服务器"
description: "了解如何安装 Power BI 报表服务器。 "
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 61558613b0022f7585b31c3e3d674a64ea009d61
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="get-started-with-power-bi-report-server"></a>开始使用 Power BI 报表服务器
使用 Power BI 报表服务器提供的各种现成工具和服务在本地创建、部署和管理 Power BI 报表、移动报表和分页报表。

## <a name="create-deploy-and-manage-reports"></a>创建、部署和管理报表
Power BI 报表服务器是客户在自己的本地环境中部署的解决方案，用来创建、发布和管理报表，然后以不同的方式将报表传送给适当的用户，无论用户是在 Web 浏览器、移动设备还是在收件箱中以电子邮件的形式查看报表。

Power BI 报表服务器提供了一套产品：

* 可以在任意新式浏览器中查看的新式 Web 门户。 在 Web 门户中，可以整理并显示报表和 KPI。 此外，还可以在门户上存储 Excel 工作簿。
* 使用 Power BI Desktop 创建的 Power BI 报表，可以在你自己环境中的 Web 门户内查看此类报表。
* 分页报表，从而可以使用专门用于创建分页报表的工具来创建新式报表。
* 含响应式布局的移动报表，此类布局可适应不同的设备以及不同的屏幕方向。

有关各个产品的详细信息，请继续阅读下文。

### <a name="whats-new-in-power-bi-report-server"></a>Power BI 报表服务器中的新增功能
通过下面这些源，可以随时了解 Power BI 报表服务器中的新增功能。

* [Power BI 报表服务器中的新增功能](whats-new.md)
* [Microsoft Power BI 博客](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services 团队博客](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Guy in a Cube YouTube 频道](https://aka.ms/guyinacube)

## <a name="web-portal"></a>Web 门户
![](media/get-started/web-portal.png)

对于 Power BI 报表服务器的最终用户，用户界面是可以在任意新式浏览器中查看的新式 Web 门户。 可以在新门户中访问所有报表和 KPI。

可以向 Web 门户应用自己的自定义[品牌](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal)。 此外，还可以直接在 Web 门户中创建 KPI。 借助 KPI，可以在浏览器中一目了然地了解关键业务指标，而无需打开报表。

Web 门户上的内容按以下类型进行分类：Power BI 报表、移动报表、分页报表和 KPI，以及用作报表构建基块的 Excel 工作簿、共享数据集和共享数据源。 可以在门户上用传统的文件夹层次结构安全地存储和管理这些内容。 不仅可以标记收藏项，还可以管理内容（如果拥有相应角色的话）。

此外，还可以安排报表处理、按需访问报表，并订阅新 Web 门户中的已发布报表。

详细了解 [Web 门户](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode)。

## <a name="power-bi-reports"></a>Power BI 报表
![](media/get-started/powerbi-reports.png)

Power BI 报表是对数据集的多角度审视，使用可视化效果来表示数据集呈现的各种见解和数据分析。  报表可包含单个可视化效果，也可包含充满可视化效果的多个页面。 你可能是报表创建者和/或报表使用者，具体视你的作业角色而定。

报表以单个数据集为基础。 报表中的可视化效果分别表示信息的一个功能。 此外，可视化效果不是静态的；你可以添加和删除数据，更改可视化效果类型，并在深入探究数据时应用筛选器和切片器，从而发现见解并寻找答案。 报表类似于仪表板，但它更具有高度互动性和高度可定制性，并且可视化效果随着基础数据的更改而更新。

## <a name="paginated-reports"></a>分页报表
![](media/get-started/paginated-reports.png)

分页报表是分页的文档样式报表，即数据越多，表中的行就越多，报表的页数也就越多。 这非常适合生成更适合打印的布局固定且像素效果完美的文档，如 PDF 和 Word 文件。

可以使用 [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt) 中的[报表生成器](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016)或报表设计器来创建新式报表。

## <a name="report-server-programming-features"></a>报表服务器编程功能
利用 Power BI 报表服务器编程功能，可以使用 API 在自定义应用中集成或扩展数据和报表处理，从而扩展和自定义报表功能。

详细阅读[报表服务器开发者文档](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation)。

## <a name="next-steps"></a>后续步骤
[用户手册](user-handbook-overview.md)  
[管理员手册](admin-handbook-overview.md)  
[快速入门：安装 Power BI 报表服务器](quickstart-install-report-server.md)  
[安装报表生成器](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[下载 SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

