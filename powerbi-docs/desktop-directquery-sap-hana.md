---
title: "在 Power BI 中将 DirectQuery 用于 SAP HANA"
description: "将 DirectQuery 用于 SAP HANA 时的注意事项"
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: d6f863df59d7374c792f1e1ac16db3a04ad99d87
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="directquery-and-sap-hana"></a>DirectQuery 和 SAP HANA
可以使用 DirectQuery 直接连接到 SAP HANA 数据源。

使用 SAP HANA 时，请务必了解如何处理其连接的某些方面，以确保：

* 当 SAP HANA 视图包含非累加性度量值（例如，非重复计数或平均值，而不是简单求和）时，结果与预期一致
* 生成的查询是高效的

当“获取数据”或“查询编辑器”中定义的查询执行聚合时，最好先花点时间来弄清关系源（如 SQL Server）的行为。 在以下示例中，查询编辑器中定义的查询按 ProductID 返回平均价格。

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

如果要将数据导入到 Power BI（而不是使用 DirectQuery），将产生以下结果：

* 数据在查询编辑器中创建的查询所定义的聚合级别导入。 例如，按产品划分的平均价格。 这会导致一个表格具有两列：ProductID 和 AveragePrice，可以在视觉对象中使用它们。
* 在视觉对象中，任何后续聚合（如 Sum、Average、Min 等）都在该导入的数据上执行。  例如，在视觉对象中包含 AveragePrice 将默认使用求和聚合，并将针对每个 ProductID 在 AveragePrice 上返回总和 - 在此情况下为 13.67。 这同样适用于视觉对象中使用的任何替代聚合函数（如 Min、Average 等）。 例如，AveragePrice 的平均值返回 6.66、4 和 3 的平均值，即等于 4.56，而不是基础表中的 6 个记录中的价格的平均值 5.17。

如果使用“DirectQuery”而不是导入，则相同的语义适用并且结果将完全相同：

* 对于相同的查询，逻辑上完全相同的数据会提供给报表层 - 即使没有实际导入数据。
* 在视觉对象中，任何后续聚合（Sum、Average、Min 等）再次通过查询中的逻辑表执行。 同样，一个包含 AveragePrice 的平均值的视觉对象返回相同的 4.56。

现在，我们来看一看 **SAP HANA**。 在 SAP HANA 中，Power BI 可以使用分析视图和计算视图，这两种视图都可以包含度量值。 但是现在，用于 SAP HANA 的方法遵循如上所述的相同原则：“获取数据”或“查询编辑器”中定义的查询将确定可用数据，然后视觉对象中的任何后续聚合都在该数据上执行，这同样适用于导入和 DirectQuery。

但是，鉴于 HANA 的性质，初始“获取数据”对话框或“查询编辑器”中定义的查询始终是聚合查询，并且通常会包括度量值，要使用的实际聚合由 HANA 视图定义。

上面 SQL Server 示例的等效为存在包含 ID、ProductID、DepotID 和度量值（包括 AveragePrice，在视图中定义为“平均价格”）的 HANA 视图。

![](media/desktop-directquery-sap-hana/directquery-sap-hana_02.png)

如果在“获取数据”体验中，所做的选择是针对 ProductID 和 AveragePrice 度量值，那么即是在定义对该视图的查询，请求该聚合数据（在上面的示例中，为简单起见，使用与 HANA SQL 的确切语法不匹配的伪 SQL）。 视觉对象中定义的任何更深入聚合都将进一步聚合此类查询的结果。 如上文针对 SQL Server 所述，这同时适用于导入和 DirectQuery 用例。 请注意，在 DirectQuery 用例中，来自“获取数据”或“查询编辑器”的查询将在发送到 HANA 的单个查询中的嵌套 select 语句中使用，因此实际上并不是在更深入聚合之前读取所有数据。

这导致在对 HANA 使用 DirectQuery 时要考虑以下重要注意事项：

* 每当 HANA 中的度量值为非累加性时（例如，不是简单的 Sum、Min 或 Max），必须注意在视觉对象中执行的任何更深入聚合。
* 在“获取数据”或“查询编辑器”中，仅应包含所需的列以检索所需的数据，这反映了结果将是查询的事实，该查询必须是可以发送到 HANA 的合理查询。 例如，如果选择了多个列，认为在后续视觉对象中可能需要这些列，那么即使是对于 DirectQuery，简单的视觉对象也将意味着嵌套 select 语句中使用的聚合查询将包含这些列，这样通常执行效果将非常差。

我们来看一个示例。 在以下示例中，在“获取数据”对话框中选择五个列（CalendarQuarter、Color、LastName、ProductLine、SalesOrderNumber）以及度量值 OrderQuantity 意味着以后创建包含 Min OrderQuantity 的简单视觉对象会导致将以下 SQL 查询发送到 HANA。 阴影部分是嵌套 select 语句，其中包含“获取数据” / “查询编辑器”中的查询。 如果此嵌套 select 语句提供非常高的基数结果，那么很可能由此产生的 HANA 性能会很差。

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

因此，建议在“获取数据”或“查询编辑器”中选择的项应限于所需的项，同时仍然生成 HANA 的合理查询。

### <a name="next-steps"></a>后续步骤
有关 DirectQuery 的详细信息，请查看以下资源：

* [Power BI 中的 DirectQuery](desktop-directquery-about.md)
* [DirectQuery 支持的数据源](desktop-directquery-data-sources.md)
* [DirectQuery 和 SAP BW](desktop-directquery-sap-bw.md)
* [本地数据网关](service-gateway-onprem.md)

