---
title: "从 Power BI 可视化效果导出数据"
description: "从报表可视化效果和仪表板可视化效果导出数据并在 Excel 中查看此数据。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: jtlLGRKBvXY
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/02/2017
ms.author: mihart
ms.openlocfilehash: fb40b2576176b772c841cea3347909aaf34af375
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="export-data-from-visualizations"></a>从可视化效果导出数据
若要查看用于创建可视化效果的数据，可以[在 Power BI 中显示该数据](service-reports-show-data.md)或将这些数据以 .xlsx 或.csv 文件形式导出到 Excel。   

Watch 将从其报表中的其中一个可视化效果导出数据，将其保存为 .xlsx 文件，并在 Excel 中打开它。 然后按照视频下面的分步说明来自己尝试一下。

<iframe width="560" height="315" src="https://www.youtube.com/embed/KjheMTGjDXw" frameborder="0" allowfullscreen></iframe>

## <a name="from-a-visualization-on-a-power-bi-dashboard"></a>Power BI 仪表板上的可视化效果
1. 选择可视化效果右上角的省略号。
   
    ![](media/power-bi-visualization-export-data/pbi-export-tile3.png)
2. 选择导出数据图标。
   
    ![](media/power-bi-visualization-export-data/pbi_export_dash.png)
3. 数据导出到.csv 文件中。 如果筛选了视觉对象，那么下载的数据也将进行筛选。
4. 你的浏览器将提示你保存该文件。  保存后，在 Excel 中打开该 .csv 文件。
   
    ![](media/power-bi-visualization-export-data/pbi-export-to-excel.png)

## <a name="from-a-visualization-in-a-report"></a>从报表中的可视化效果
为此，打开“[编辑视图](service-reading-view-and-editing-view.md)”中的“[采购分析示例报表](sample-procurement.md)”。 [添加新的空白报表页](power-bi-report-add-page.md)。 然后按照以下步骤来添加聚合和可视化效果级别筛选器。

1. 创建一个新的柱形图。  从字段窗格中，选择“位置 > 城市”和“发票 > 折扣百分比”。   
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data3.png)
2. 将折扣百分比的聚合从“计数”更改为“平均”。 在“值”一列中，选择“折扣百分比”右侧的箭头（它可能显示“折扣百分比计数”），然后选择“平均”。
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data6.png)
3. 向“城市”添加筛选器以删除“亚特兰大”。
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data4.png)
   
   现在准备尝试使用两个选项导出数据。
4. 选择可视化效果右上角的省略号。 选择导出数据。
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data2.png)
5. 如果你的可视化效果具有聚合（一个示例是如果将“计数”更改为“平均”、“总和”或“最小”），则具有两个选项：汇总数据和基础数据。 如需有关了解聚合的帮助，请参阅 [Power BI 中的聚合](service-aggregates.md)。
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data5.png)
6. 选择“汇总数据” > “导出”并选择 .xlsx 或 .csv。 Power BI 导出数据。  如果已将筛选器应用到可视化效果，则导出的数据将在筛选后导出。 选择“导出”时，浏览器会提示你保存文件。 保存后，在 Excel 中打开该文件。
   
   汇总数据：如果你没有聚合或者如果有聚合但不想查看完整的细目，请选择此选项。 例如，如果有一个显示 4 条的条形图，则将获得 4 行数据。 汇总数据可作为 .xlsx 和 .csv。
   
   在此示例中，Excel 导出会显示每个城市的总计。 由于已筛选出亚特兰大，因此它并不包含在结果中。  电子表格的第一行显示的是我们在从 Power BI 提取数据时所使用的筛选器。
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data7.png)
7. 现在尝试选择“基础数据” > “导出”并选择 .xlsx。 Power BI 导出数据。 如果已将筛选器应用到可视化效果，则导出的数据将在筛选后导出。 选择“导出”时，浏览器会提示你保存文件。 保存后，在 Excel 中打开该文件。
   
   >[!WARNING]
   >使用导出基础数据功能，用户可以查看所有详细的数据（数据中的每列）。 Power BI 服务管理员可以为其组织关闭此功能。 如果你是数据集的所有者，则可以将专有列设置为“隐藏”，这样它们就不会出现在 Desktop 或 Power BI 服务的“字段”列表中。
   > 
   > 
   
   基础数据：如果你的可视化效果无聚合，并且你想要查看所有基础详细信息，请选择此选项。 基本上，选择“基础数据”会删除聚合。 选择“导出”时，数据将导出到 .xlsx 文件，并且你的浏览器会提示你保存该文件。 保存后，在 Excel 中打开该文件。
   
   在此示例中，Excel 导出显示我们的数据集中每一个城市行的一行，以及该单个条目的折扣百分比。 换言之，数据平展而不聚合。 电子表格的第一行显示的是我们在从 Power BI 提取数据时所使用的筛选器。  
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data8.png)

## <a name="limitations-and-considerations"></a>限制和注意事项
* 最多可将 30,000 行从 Power BI Desktop 导出到 .csv。
* Pro 用户最多可将 150,000 行从 Power BI 服务导出到 .xlsx，免费用户最多可导出 30,000 行。
* 使用 DirectQuery 时，最多可以导出 16MB 数据。 这可能会导致导出的行数少于上限，尤其是当有许多列、难以压缩的数据以及其他增加文件大小但减少导出行数的因素时。
* Power BI 仅支持导出使用基本聚合的视觉对象。 不支持导出使用模型或报表度量值的视觉对象。
* 目前不支持自定义视觉对象和 R 视觉对象。
* 不可以对使用已与其共享的仪表板的组织外用户导出数据。 
* 如果 .csv 文件中存在 unicode 字符，那么 Excel 中的文本可能不会正常显示。 不过，在记事本中打开它则会正常显示。 Unicode 字符的示例是货币符号和外语单词。 对此的解决方法是将 csv 文件导入到 Excel 中，而不是直接打开 csv 文件。 如何执行此操作：
  
  1. 打开 Excel
  2. 从“数据”选项卡上，选择“获取外部数据” > “从文本”。
* Power BI 管理员可以禁用数据导出功能。

## <a name="next-steps"></a>后续步骤
[Power BI 中的仪表板](service-dashboards.md)  
[Power BI 中的报表](service-reports.md)  
[Power BI - 基本概念](service-basic-concepts.md)

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

