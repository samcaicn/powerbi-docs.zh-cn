---
title: "让你的数据与 Power BI 中的问答功能很好地协作"
description: "让你的数据与 Power BI 中的问答功能很好地协作"
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 499c3beca9046af9336de6dfec96994004050986
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="make-your-data-work-well-with-qa-in-power-bi"></a>让你的数据与 Power BI 中的问答功能很好地协作
如果你是创建数据模型或生成用于 Power BI 的 Excel 工作簿的人员，请阅读...

在 Power BI 中，“问答”可以搜索结构化数据，然后针对你的问选择合适的可视化效果 — 这让它成为一种极具吸引力的工具。   

“问答”适用于任何已上传的具有表格、范围或包含 PowerPivot 模型的 Excel 文件，但执行的优化和数据清理越多，“问答”性能就越可靠。 

## <a name="how-qa-works"></a>“问答”的工作原理
“问答”具有一套核心的自然语言理解功能，可以处理你的数据。 它还具有针对 Excel 表、列和计算的字段名称的上下文相关关键字搜索功能。 其次，它还具有如何筛选、排序、聚合、分组和显示数据的内置知识。 

例如，在名为“Sales”的 Excel 表中，其中含有“Product”、“Month”、“Units Sold”、“Gross Sales”和“Profit”列，你可以询问有关这些实体的问题。  你可以要求按月显示销售额和总利润、按销售件数对产品排序等其他功能。 请详细阅读 [kinds of questions you can ask](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx)（你可以提问的问题种类）、[asking questions using a question template](service-q-and-a.md)（使用问题模板提问）以及 [visualization types you can specify in a问答query](power-bi-visualization-types-for-reports-and-q-and-a.md)（在“问答”查询中可以指定的虚拟化效果类型）。

## <a name="prepare-a-workbook-for-qa"></a>准备“问答”的工作簿
“问答”依靠表格、列和计算字段的名称来回答特定于数据的问题，这意味着，实体在工作簿中的命名很重要！

以下是有关充分利用工作簿中的“问答”的一些提示。

* 请确保你的数据在 Excel 表中。 下面是 [how to create an Excel table](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US)（如何创建 Excel 表）。
* 请确保表格、列和计算字段的名称采用表达意义的英文。
  
  例如，如果表格中含有销售数据，请将此表命名为“Sales”。 像“Year”、“Product”、“Sales Rep”和“Amount”等列名称对“问答”也很适用。

> [!NOTE]
> 如果你的工作簿具有 Power Pivot 数据模型，则可以执行更多优化操作。 详细阅读有关我们内部的自然语言专家所提供的 [Demystifying Power BI问答part 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx)（阐述 Power BI 问答（第 2 部））。
> 
> 

## <a name="next-steps"></a>后续步骤
[Power BI 中的“问答”](service-q-and-a.md)  
[教程：Power BI 问答简介](power-bi-visualization-introduction-to-q-and-a.md)  
[获取 Power BI 的数据](service-get-data.md)  
[Power BI - 基本概念](service-basic-concepts.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

