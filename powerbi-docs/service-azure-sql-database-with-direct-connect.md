---
title: "具有 DirectQuery 的 Azure SQL 数据库"
description: "具有 DirectQuery 的 Azure SQL 数据库"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 83613f0ed915a03b65b90d4bf61e37568b922182
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="azure-sql-database-with-directquery"></a>具有 DirectQuery 的 Azure SQL 数据库
了解如何直接连接到 Azure SQL 数据库并使用实时数据创建报表。 你可以在源中（不是在 Power BI 中）保存数据。

借助 DirectQuery，查询会在你浏览报表视图中的数据时发送回 Azure SQL 数据库。 对于熟悉数据库以及它们连接到的实体的用户，建议使用此体验。

**注意：**

* 在连接时指定完全限定的服务器名称（请参阅下文以了解详细信息）
* 确保数据库的防火墙规则配置为[允许访问 Azure 服务](https://msdn.microsoft.com/library/azure/ee621782.aspx)。
* 每个操作（例如选择列或添加筛选器）都会将查询发送回数据库
* 磁贴大约每 15 分钟刷新一次（刷新不需要进行计划）。 连接时可以在“高级设置”中对此进行调整。
* 问答不可用于 DirectQuery 数据集
* 不会自动选取架构更改

随着我们继续改进体验，这些限制和说明可能会发生变化。 下面详细介绍了用于连接的步骤。 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop 和 DirectQuery
若要使用 DirectQuery 连接到 Azure SQL 数据库，则必须使用 Power BI Desktop。 这种方法提供了更多灵活性和功能。 使用 Power BI Desktop 创建的报表随后可以发布到 Power BI 服务。 可了解如何在 Power BI Desktop 内[使用 DirectQuery 连接到 Azure SQL 数据库](desktop-use-directquery.md)的详细信息。 

## <a name="connecting-through-power-bi"></a>通过 Power BI 连接
你不能再直接通过 Power BI 服务连接到 Azure SQL 数据库。 在你选择“[Azure SQL 数据库连接器](https://app.powerbi.com/getdata/bigdata/azure-sql-database-with-live-connect)”后，系统将要求你在 Power BI Desktop 内进行连接。 然后你可将 Power BI Desktop 报表发布到 Power BI 服务。 

![](media/service-azure-sql-database-with-direct-connect/azure-sql-database-in-power-bi.png)

### <a name="finding-parameter-values"></a>查找参数值
可以在 Azure 门户中找到你的完全限定的服务器名称和数据库名称。

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>后续步骤
[在 Power BI Desktop 中使用 DirectQuery](desktop-use-directquery.md)  
[Power BI 入门](service-get-started.md)  
[获取 Power BI 的数据](service-get-data.md)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

