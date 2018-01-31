---
title: "使用 iFrame 嵌入报表"
description: "Power BI 报表服务器本身安装起来非常快。 从下载到安装和配置，只需几分钟，即可快速上手使用。"
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
ms.date: 11/09/2017
ms.author: maghan
ms.openlocfilehash: 56835bfb25c8c930099fadf710137f69fa89fc2e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>快速入门：使用 iFrame 和 URL 参数嵌入 Power BI 报表

可以通过在应用程序中使用 iFrame 嵌入任何报表。 

## <a name="url-parameter"></a>URL 参数

对于指向报表的任何 URL，可以添加查询字符串参数 `?rs:Embed=true`。

例如：

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

这将适用于 Power BI 报表服务器中的所有报表类型。

## <a name="iframe"></a>iFrame

有了 URL 后，可以在 Web 页面中创建 iFrame 来托管报表。

例如：

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>URL 筛选器

可以将查询字符串参数添加到 URL 来筛选在 Power BI 报表中返回的数据。

语法很简单；从报表 URL 入手，然后依次添加问号和筛选语法。

URL?filter=***表***/***字段*** eq '***值***'

请记住以下注意事项：

- 表和字段名称区分大小写，值不区分大小写。
- 可以筛选字段在报表视图中隐藏的报表。
- 必须用单引号将**值**括起来。
- 字段类型必须是字符串。
- 表和字段名称中不能有任何空格。

###  <a name="example-filter-on-a-field"></a>示例：筛选一个字段

以[零售分析示例](../sample-datasets.md)为例。 假设这是报表服务器上名为“power-bi”的文件夹中的报告的 URL：

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

你会在零售分析示例中看到地图可视化效果，其中显示了北卡罗来纳州和其他州的商店。

![零售分析示例地图可视化效果](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

NC 是存储在“Store”表的“Territory”字段中的北卡罗来纳州值。 因此，要筛选报表以仅显示北卡罗来纳州商店的数据，请将以下内容附加到 URL 中：

?filter=Store/Territory eq 'NC'

现在，报表针对北卡罗来纳州进行了筛选；报表页上的所有可视化效果都只显示北卡罗来纳州的数据。

![零售分析示例筛选可视化效果](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>创建 DAX 公式对多个值进行筛选

对多个字段进行筛选的另一方法是在 Power BI Desktop 中创建一个将两个字段合并成一个值的计算列。 然后，便可以筛选此值。

例如，零售分析示例包含两个字段：Territory 和 Chain。 在 Power BI Desktop 中，可以[创建一个计算列](../desktop-tutorial-create-calculated-columns.md)（字段），并将其命名为“TerritoryChain”。 请注意，“字段”名称中不能有任何空格。 下面是此计算列的 DAX 公式。

TerritoryChain = [Territory] & "-" & [Chain]

将报表发布到 Power BI 报表服务器，然后使用 URL 查询字符串筛选出 NC 中 Lindseys 商店的数据。

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>后续步骤

[快速入门：为 Power BI 报表服务器创建 Power BI 报表](quickstart-create-powerbi-report.md)  
[快速入门：为 Power BI 报表服务器创建分页报表](quickstart-create-paginated-report.md)  

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)