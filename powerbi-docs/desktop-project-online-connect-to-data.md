---
title: Project Online：通过 Power BI Desktop 连接到数据
description: Project Online：通过 Power BI Desktop 连接到数据
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c8293499059b66879b7e52fba579fd0ae15aba3d
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online：通过 Power BI Desktop 连接到数据
可以通过 Power BI Desktop 连接到 Project Online 中的数据。

### <a name="step-1-download-power-bi-desktop"></a>步骤 1：下载 Power BI Desktop
1. [下载 Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521662)，然后运行安装程序，以在计算机上安装 **Power BI Desktop**。

### <a name="step-2-connect-to-project-online-with-odata"></a>步骤 2：通过 OData 连接到 Project Online
1. 打开 **Power BI Desktop**。
2. 在“ *欢迎* ”屏幕上，选择“**获取数据**”。
3. 依次选择“**OData 数据源**”和“**连接**”。
4. 在 URL 框中输入 OData 数据源的地址，然后单击确定。
   
   如果你的 Project Web App 站点的地址类似于 https://\<tenantname\>.sharepoint.com/sites/pwa，那么你将输入的 OData 数据源的地址则为 https:// \<tenantname\>.sharepoint.com/sites/pwa/\_api/Projectdata。
   
   在此示例中，我们使用 https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop 将提示你使用 Office 365 帐户进行身份验证。 请选择组织帐户，然后输入你的凭据。
   
   ![](media/desktop-project-online-connect-to-data/image.png)

请注意，用于连接到 OData 源的帐户必须对 Project Web App 站点至少具有项目组合查看者访问权限。 

从此处你可以选择想要连接到的表并生成查询。  想了解如何开始？  下面的博客文章将演示如何从你的 Project Online 数据生成燃尽图。  博客文章中使用了 Power Query 连接到 Project Online，Power BI Desktop 也同样适用。

[使用 Power Pivot 和 Power Query 为项目创建燃尽图](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

