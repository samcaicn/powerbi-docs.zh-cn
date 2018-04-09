---
title: 教程：在 Power BI Desktop 中分析 Excel 和 OData 源中的销售数据
description: 教程：分析来自 Excel 和 OData 源的销售数据
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: aad93a6c636fb0d75ad89f9e3d9eb70ec203cc88
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>教程：分析来自 Excel 和 OData 源的销售数据
使用 **Power BI Desktop**，你可以连接到各种类型的不同数据源，然后以形成有趣和令人信服的数据分析和可视化效果的方式对它们进行合并和调整。 在本教程中，你将了解如何合并来自两个数据源的数据。 

数据遍布于多个数据源是很常见的，例如产品信息可能位于某个数据库，而销售信息则位于另一个数据库。 你将在本文档中了解的技术包括 Excel 工作簿和 OData 源，但这些技术也可以应用于其他数据源，如 SQL Server 查询、CSV 文件或 Power BI Desktop 中的任何数据源。

在本教程中，你将从 Excel（包含产品信息）和 OData 源（包含订单数据）导入数据。 你将执行转换和聚合步骤，以及合并来自这两个源的数据以生成呈现交互式可视化效果的 **Total Sales per Product and Year** 报表。 

下面是最终报表的外观：

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

若要安装本教程中的步骤，需要 Products 工作簿，可以通过以下方式下载：[单击此处下载 Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)

在**另存为**对话框中，将文件命名为**Products.xlsx**。

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>任务 1：从 Excel 工作簿获取产品数据
在此任务中，需要将 Products.xlsx 文件内的产品导入 Power BI Desktop 中。

### <a name="step-1-connect-to-an-excel-workbook"></a>步骤 1：连接到 Excel 工作簿
1. 启动 Power BI Desktop。
2. 从“开始”功能区选择**获取数据**。 Excel 是**最常用**的数据连接之一，因此你可以直接从**获取数据**菜单中选择。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. 如果直接选择“获取数据”按钮，你还可以选择**文件\> Excel**，然后选择**连接。**
4. 在**打开文件**对话框中，选择 **Products.xlsx** 文件。
5. 在**导航器**窗格中，选择 **Products** 表，然后选择**编辑**。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>步骤 2：删除其他列，只显示感兴趣的列
在此步骤中，需要删除除**ProductID**、**ProductName**、**UnitsInStock** 和 **QuantityPerUnit** 之外的所有列。 在 Power BI Desktop 中，完成相同的任务往往有几种方法。 例如，通过在列或单元格上右键单击菜单也能获取位于功能区中的许多按钮。

Power BI Desktop 中包括查询编辑器，你可以在此处对数据连接进行调整和转换。 从**导航器**选择**编辑**时，查询编辑器会自动打开。 还可以通过从 Power BI Desktop 中的**开始**功能区选择**编辑查询**来打开查询编辑器。 在查询编辑器中执行以下步骤。

1. 在查询编辑器中，选择 **ProductID**、**ProductName**、**QuantityPerUnit** 和 **UnitsInStock** 列（通过按住 **Ctrl 并单击**来选择多个列，或按住 **Shift 并单击**来选择相邻的列）。
2. 从功能区选择**删除列** \> **删除其他列**，或右键单击某个列标题，然后单击**删除其他列**。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>步骤 3：更改 UnitsInStock 列的数据类型
当查询编辑器连接到数据时，它会检查每个字段，并确定最佳的数据类型。 对于 Excel 工作簿，库存产品将始终为整数，因此在此步骤中需要确认 **UnitsInStock** 列的数据类型为整数。

1. 选择 **UnitsInStock** 列。
2. 选择**开始**功能区中的**数据类型**下拉列表按钮。
3. 如果没有整数，请从下拉列表中选择**整数**数据类型（**数据类型：**按钮也会显示当前所选的数据类型）。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>创建的 Power BI Desktop 步骤
在查询编辑器中执行查询活动时，将创建查询步骤并在**应用步骤**列表中的**查询设置**窗格中列出。 每个查询的步骤都有相应的公式，也称为“M”语言。 有关“M”公式语言的详细信息，请参阅[了解 Power BI 公式](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f)。

| 任务 | 查询步骤 | 公式 |
| --- | --- | --- |
| 连接到 Excel 工作簿 |源 |Source{[Name="Products"]}[Data] |
| 将第一行提升至表格列标题 |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> （产品） |
| 删除其他列，只显示感兴趣的列 |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| 更改数据类型 |更改的类型 |Table.TransformColumnTypes(\#"Removed Other Columns",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>任务 2：从 OData 源导入订单数据
在此任务中，你需要导入订单数据。 此步骤中表示连接到销售系统。 将位于下面的 URL 的示例 Northwind OData 的数据导入 Power BI Desktop，你可以从下面的步骤复制（并粘贴）：<http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>步骤 1：连接到 OData 源
1. 从查询编辑器中的**开始**功能区选项卡中选择**获取数据。**
2. 浏览到 **OData 源**数据源。
3. 在 **OData 源**对话框中，粘贴 Northwind OData 源的 **URL**。
4. 选择**确定**。
5. 在**导航器**窗格中，选择 **Orders** 表，然后选择**编辑**。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>单击表名即可查看预览，而不必选择复选框。

### <a name="step-2-expand-the-orderdetails-table"></a>步骤 2：展开 Order\_Details 表
**Orders** 表包含对 **Details** 表的引用，其中包含每个订单中的各个产品。 当你连接到多个表的数据源（如关系数据库）时，可以使用这些引用来构建你的查询。 

在此步骤中，展开与 **Orders** 表相关的**Order\_Details** 表，以将**Order\_Details** 中的 **ProductID**、**UnitPrice** 和 **Quantity** 列合并到 **Orders** 表。 这是数据在这些表中的表示形式：

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

**展开**操作会将相关表中的列合并到主体表。 当查询运行时，相关表 (**Order\_Details**) 中的行将合并到主体表 (**Orders**) 中的行。

展开 **Order\_Details** 表后，将会有三个新列和其他行添加到 **Orders** 表中，分别用于嵌套或相关表中的每一行。

1. 在**查询视图**中，滚动到 **Order\_Details** 列。
2. 在 **Order\_Details** 列中，选择展开图标 (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png))。
3. 在**展开**下拉列表中：
   1. 选择**（选择所有列）**以清除所有列。
   2. 选择 **ProductID**、**UnitPrice** 和 **Quantity**。
   3. 单击**确定**。
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>步骤 3：删除其他列，只显示感兴趣的列
在此步骤中，将删除 **OrderDate、ShipCity**、**ShipCountry**、**Order\_Details.ProductID**、**Order\_Details.UnitPrice** 和 **Order\_Details.Quantity** 以外的所有列。 在上一任务中，你使用了**删除其他列**。 对于此任务中，你需要删除所选的列。

1. 在**查询视图**中选择所有列，方法是完成a. 和 b：
   1. 单击第一列 (**OrderID**)。
   2. 按住 Shift 并单击最后一列 (**Shipper**)。
   3. 现在已选中了所有列，按住 Ctrl 并单击来取消选择以下列：**OrderDate**、**ShipCity**、**ShipCountry**、**Order\_Details.ProductID**、**Order\_Details.UnitPrice** 以及 **Order\_Details.Quantity**。
2. 现在只选中了我们要删除的列，右键单击任何所选列的标题并单击**删除列**。

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>步骤 4：计算每个 Order\_Details 行的项目总计
Power BI Desktop 可让你创建针对正在导入的列的计算，因此你可以加强连接到的数据。 在此步骤中，你需要创建**自定义列**来计算每个 **Order\_Details** 行的项目总计。

计算每个 **Order\_Details** 行的项目总计：

1. 在**添加列**功能区选项卡上，单击**添加** **自定义列**。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. 在“添加自定义列”对话框的“自定义列公式”文本框中，输入“[Order\_Details.UnitPrice] \* [Order\_Details.Quantity]”
3. 在**新的列名称**文本框中输入 **LineTotal**。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. 单击**确定**。

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>步骤 5：设置 LineTotal 字段的数据类型
1. 右键单击 **LineTotal** 列。
2. 选择“更改类型”，然后选择“十进制数”。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>步骤 6：对查询中的列进行重命名和重新排序
在此步骤中，你需要对最后的列进行重命名和改变顺序，从而在完成时使模板在创建报表时更易于使用。

1. 在**查询编辑器**中，将 **LineTotal** 向左拖动到 **ShipCountry** 之后。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. 通过双击每个列标题，并从列名称中删除文本，删除以下列的 *Order\_Details.* 前缀：**Order\_Details.ProductID**、**Order\_Details.UnitPrice** 和 **Order\_Details.Quantity**。

### <a name="power-bi-desktop-steps-created"></a>创建的 Power BI Desktop 步骤
在查询编辑器中执行查询活动时，将创建查询步骤并在**应用步骤**列表中的**查询设置**窗格中列出。 每个查询的步骤都有对应的 Power Query 公式，也称为“M”语言。 有关此公式语言的详细信息，请参阅[了解 Power BI 公式](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "了解 Power Query 公式")。

| 任务 | 查询步骤 | 公式 |
| --- | --- | --- |
| 连接到 OData 源 |源 |Source{[Name="Orders"]}[Data] |
| 展开 Order\_Details 表 |展开 Order\_Details |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| 删除其他列，只显示感兴趣的列 |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| 计算每个 Order\_Details 行的项目总计： |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>任务 3：合并 Products 和 Total Sales 查询
Power BI Desktop 不需要合并查询来建立报表。 相反，你可以创建数据集之间的**关系**。 这些关系可以在数据集通用的任何列上创建。 有关详细信息，请参阅[创建和管理关系](desktop-create-and-manage-relationships.md)。

在本教程中，有共用通用“ProductID”字段的 Orders 和 Products 数据，因此我们需要确保它们在搭配 Power BI Desktop 使用的模型中具有某种关系。 只需在 Power BI Desktop 中指定这两个表中的列相关（即这些列具有相同的值）即可。 Power BI Desktop 会为你找出关系的的方向和基数。 在某些情况下，它甚至会自动检测关系。

在此任务中，你将确认 **Products** 和 **Total Sales** 查询在 Power BI Desktop 中建立了关系。

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>步骤 1：确认 Products 和 Total Sales 之间的关系
1. 首先，我们需要将在查询编辑器中创建的模型加载到 Power BI Desktop。 从查询编辑器中的**开始**功能区选择**关闭并加载**。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop 将从这两个查询加载数据。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. 加载数据后，选择**开始**功能区中的**管理关系**按钮。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. 选择**新建...** 按钮
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. 当我们尝试创建关系时，我们看到已经存在一个关系！ 如**创建关系**对话框（阴影列）中所示，每个查询中的 **ProductsID** 字段都有一个已建立的关系。
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. 选择**取消**，然后选择 Power BI Desktop 中的**关系**视图。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. 如下图所示，查询之间的关系将以视觉化方式显示。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. 当双击连接到查询的线条上的箭头时，将会显示**编辑关系**对话框。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. 由于无需进行任何更改，因此我们只需选择**取消**来关闭**编辑关系**对话框。

## <a name="task-4-build-visuals-using-your-data"></a>任务 4：使用数据生成视觉效果
Power BI Desktop 使你可以创建多种可视化效果来深入探索你的数据。 你可以生成多页报表，而且每页可以有多个视觉效果。 你可以与可视化效果进行交互，以帮助分析和了解你的数据。 有关编辑报表的详细信息，请参阅[编辑报表](service-interact-with-a-report-in-editing-view.md)。

在本任务中，你将基于以前加载的数据创建报表。 使用字段窗格选择要从中创建可视化效果的列。

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>步骤 1：创建显示产品的库存单位数量和年度总销售额的图表
将 **UnitsInStock** 从字段窗格（字段窗格位于屏幕最右侧）拖到画布上的空白区域。 这样便创建了表可视化效果。 接下来，将 ProductName 拖动到可视化效果窗格下半部分的“轴”框中。 然后使用可视化效果右上角的图示来选择**排序依据 \>UnitsInStock**。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

将 **OrderDate** 拖动到第一个图表下方的画布上，然后将 LineTotal（再次从字段窗格）拖动到视觉效果，然后选择折线图。 这样便创建了如下所示的可视化效果。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 接下来，将 **ShipCountry** 拖动到右上角画布上的空白处。 由于你已经选择了地理字段，因此会自动创建地图。 现在，将 **LineTotal** 拖动到**值**字段；地图上代表每个国家/地区的圆圈将会根据运送至该国家/地区的订单的 **LineTotal** 呈现出相对应的大小。

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>步骤 2：与报表视觉效果进行交互以进一步分析
Power BI Desktop 使你可以与相互突出显示和筛选的视觉效果进行交互，从而发觉进一步的趋势。 有关详细信息，请参阅[在报表中进行筛选和突出显示](power-bi-reports-filters-and-highlighting.md)

1. 单击位于**加拿大**中心的浅蓝色圆形。 请注意如何筛选其他视觉效果，才能只显示加拿大的库存 (**ShipCountry**) 和总订单数 (**LineTotal**)。
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>完成销售分析报表
执行所有这些步骤后，你将拥有一个合并了来自 Products.xlsx 文件和 Northwind OData 源的数据的销售报表。 此报表显示帮助分析来自不同国家/地区的销售信息的视觉效果。 你可以在[此处](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix)下载本教程的完整 Power BI Desktop 文件。

## <a name="next-steps"></a>后续步骤
* [阅读其他 Power BI Desktop 教程](http://go.microsoft.com/fwlink/?LinkID=521937)
* [观看 Power BI Desktop 视频](http://go.microsoft.com/fwlink/?LinkID=519322)
* [访问 Power BI 论坛](http://go.microsoft.com/fwlink/?LinkID=519326)
* [阅读 Power BI 博客](http://go.microsoft.com/fwlink/?LinkID=519327)


