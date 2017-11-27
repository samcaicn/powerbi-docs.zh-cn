---
title: "教程：在 Power BI Desktop 中创建你自己的度量值"
description: "教程：在 Power BI Desktop 中创建你自己的度量值"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 653895d9cfa64c9029ce9441278adcc94d76a0a8
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>教程：在 Power BI Desktop 中创建你自己的度量值
通过使用度量值，可以在 Power BI Desktop 中创建某些功能强大的数据分析解决方案。 度量值可在我们与报表进行交互时帮助我们对数据执行计算。 本教程将指导你了解并在 Power BI Desktop 中创建一些你自己的基本度量值。

本文面向已熟悉使用 Power BI Desktop 创建更高级的模型的 Power BI 用户。 你应该已经熟悉使用“获取数据”和“查询编辑器”来导出数据、使用多个相关表和向报表画布添加字段。 如果刚开始使用 Power BI Desktop，请务必查看 [Power BI Desktop 入门](desktop-getting-started.md)。

若要完成本教程中的步骤，你需要下载 [Power BI Desktop 的 Contoso 销售示例](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip)文件。 它已包含来自虚构公司 Contoso,inc. 的线上销售数据。因为文件中的数据是从数据库导入的，你将无法连接到数据源或在查询编辑器中查看。 当你自己的计算机上有此文件时，请直接在 Power BI Desktop 中将它打开。

## <a name="what-are-these-measures-all-about"></a>这些度量值有什么用？
度量值往往是自动创建的，如当我们从字段列表中的 **Sales** 表选择 **SalesAmount** 字段旁边的复选框或将 **SalesAmount** 拖动到报表画布时（便会自动创建）。

![](media/desktop-tutorial-create-measures/measurestut_salesamountinfieldlist.png)

将会显示如下的新图表可视化效果：

![](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

我们得到一个在 SalesAmount 字段显示销售总额的柱形图。  SalesAmount 字段实际上只是一个名为 SalesAmount 的列，它位于我们已导入的 Sales 表中。

SalesAmount 列包含超过两百万行的销售值。 你可能想知道为什么看不到具有所有这些值的行的表。 Power BI Desktop 知道 SalesAmount 中的所有值都属于数字数据类型，并且你可能想要以某种方式将它们聚合，可能是求和、求平均值和计数等...

只要你在字段列表中看到拥有 sigma 图标 ![](media/desktop-tutorial-create-measures/meastut_sigma.png) 的字段，就表示此字段是数值并且它的值可以聚合。 在这种情况下，当我们选择 SalesAmount 时，Power BI Desktop 将创建其自己的度量值，并且将在图表中显示计算出的所有销售额的总数。

当我们选择具有数字数据类型的字段时，总和将是默认的聚合方式，但是我们也可以轻易地将其更改为不同的聚合类型。

在 **Value** 区域中，如果我们单击 **SalesAmount** 旁边的向下箭头，就可以选择 **Average**。

![](media/desktop-tutorial-create-measures/meastut_salesamountaverage.png)

SalesAmount 字段中的可视化效果将更改为所有销售值的平均值。

![](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

我们可以根据想要的结果来更改聚合的类型，但并非所有类型的聚合都能应用于任何数字数据类型。 例如，对于 SalesAmount 字段，总和和平均值是有意义的。 最小值和最大值也有它们的意义。 但是，计数对于 SalesAmount 字段则没有太大意义，因为虽然它的值是数值，但它们实际上是货币。

理解聚合是了解度量值的基础，因为每个度量值都将执行某种类型的聚合。 稍后在你创建自己的一些度量值时，我们将看到使用总和聚合的更多示例。

度量值计算的值会随时根据我们与报表的交互而发生变化。 例如，如果我们将 **RegionCountryName** 字段从 **Geography** 表拖动到我们的表格，则会计算每个国家/地区的销售额的平均值并显示出来。

![](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

由于与报表进行交互而导致度量值更改时，也会影响我们度量值的 *上下文* 。 事实上，每当你与报表交互时，都会改变上下文中度量值的计算和其显示的结果。

大多数情况下，Power BI 会执行操作、计算并根据我们已添加的字段和我们选择的聚合类型返回值。 但在其他情况下，你可能需要创建你自己的度量值才能执行更复杂的和独特的计算。

使用 Power BI Desktop，你可以创建你自己的具有数据分析表达式 (DAX) 公式语言的度量值。 DAX 公式非常类似于 Excel 公式。 实际上，DAX 使用许多与 Excel 公式相同的函数、运算符和语法。 但是，DAX 的函数用于在我们与报表进行交互时处理关系数据，并执行更动态的计算。

超过 200 个 DAX 函数可以执行任何计算，从总和和平均值的简单聚合到更复杂的统计和筛选函数。 我们不打算在此处详细探讨 DAX 语言，但仍有许多资源可帮助你了解详细信息。 完成本教程后，请务必参阅 [Power BI Desktop 中的 DAX 基础知识](desktop-quickstart-learn-dax-basics.md)。

当我们创建我们自己的度量值时，它们会添加到我们所需要的表的字段列表中。 我们将此称为 *模型* 度量值，它将作为字段保留在报表中。 模型度量值的几大优势在于，我们可以任意命名模型度量值，使其更容易识别。 我们还可以将它们用作其他 DAX 表达式中的参数，并且可以创建能快速地执行复杂计算的度量值。

## <a name="lets-create-our-own-measure"></a>我们来创建自己的度量值
假设我们要分析净销售额。 如果查看字段列表中的 Sales 表，我们将看到并没有名为 NetSales 的字段。 但是，我们有构建基块，可以用来创建我们自己的度量值以计算净销售额。

我们需要从销售额中减去折扣并返回值的度量值。 因为我们希望度量值能对可视化效果中的任何上下文进行计算，事实上，我们需要从 SalesAmount 的总和中减去 DiscountAmount 和 ReturnAmount 的总和。 现在看起来可能有点令人困惑；别担心，稍后就会更加清楚。

### <a name="net-sales"></a>净销售额
1.  右键单击或单击字段列表中的 **Sales** 表上的向下箭头，然后单击**新建度量值**。 这将确保我们的新建度量值保存在 Sales 表中，以使其更易于查找。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    > [!TIP]
    > 还可以通过单击 Power BI Desktop 开始选项卡上的功能区中的“新建度量值”按钮来创建新的度量值。
    > 
    > ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    > 
    > 从功能区中创建度量值时，可以在其中任何一个表中创建度量值。 虽然度量值不属于任何特定的表，但如果在对你来说最具逻辑关系的表中创建，可能会更容易找到。 如果你希望它位于特定的表中，首先请单击表，以使处于活动状态。 然后单击“新建度量值”。 在本例中，我们将在 Sales 表中创建我们的第一个度量值。
    > 
    > 
    
    编辑栏将出现在报表画布的顶部。 我们可以在此处重命名度量值并输入 DAX 公式。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
    让我们为新度量值指定名称。 默认情况下，新度量值的名称就是“度量值”。 如果我们不进行重命名，当我们创建其他度量值时，便会命名为度量值 2、度量值 3，依此类推。 我们希望我们的度量值更易于识别，因此我们将新度量值命名为 Net Sales。
    
2. 在编辑栏内，选中“Measure”，再键入“Net Sales”。
    
    现在我们可以开始输入公式。
    
3.  在等号后键入 **S**。你将看到显示出来一个下拉建议列表，其中有以字母 S 开头的所有的 DAX 函数。我们键入的字母越多，建议列表就更能调整至接近我们所需的函数。 通过向下滚动选择 **SUM**，然后按 Enter。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    按 Enter 后，将会出现一个左括号和另一个建议清单，其中包括我们可以传递到 SUM 函数的所有可用的列。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    表达式将始终出现在左括号和右括号之间。 在这种情况下，我们的表达式将包含传递到 SUM 函数的单个参数；也就是要计算总和的列。 通过键入我们想要的第一个字母，我们可以缩小列的列表。 在这种情况下，我们需要 SalesAmount 列，以便当我们开始键入 salesam 时，列表范围会变小并显示我们可以选择的两个项。 它们实际上是相同的列。 其中一列只显示 [SalesAmount]，因为我们在 SalesAmount 列所在的相同表中创建度量值。 而另一列，我们将在列名称前看到表名称。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
    一般情况下，最好输入列的完全限定名称。 这将使你的公式更易于阅读。
    
4. 选择“Sales[SalesAmount]”，再键入右括号。
    
    > [!TIP]
    > 语法错误通常由缺少或错放右括号导致。
    > 
    > 
    
    现在，我们想要减去其他两列。
    
5.  在第一个表达式的右括号后依次键入一个空格、减号运算符 (**-**) 和另一个空格。 然后输入另一个将 **Sales [DiscountAmount]** 列用作参数的 SUM 函数。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
    我们已逐渐将公式的空间用完了。 没问题。
    
6.  单击编辑栏右侧的向下 v 形图标。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)
    
    现在我们有了更多的空间。 我们可以按 Alt-Enter 在新行上向我们的公式输入新的部分。 我们还可以使用选项卡移动内容。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)
    
    现在我们可以添加公式的最后一部分。
    
7.  添加另一个减号运算符，并在后面添加另一个 SUM 函数和 **Sales [ReturnAmount]** 列作为其参数。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
    现在，我们的公式已经准备就绪。

8.  按 Enter 或单击编辑栏中的选中标记完成操作。 该公式将经过验证并添加到 Sales 表中的字段列表。

### <a name="lets-add-our-new-measure-to-a-report"></a>让我们将新度量值添加到报表
现在我们可以将 Net Sales 度量值添加到报表画布，之后将对我们添加到报表中的任何字段计算净销售额。 让我们按国家/地区来查看净销售额。

1.  将 **Net Sales** 度量值从 **Sales** 表拖动到报表画布。
    
2. 现在，将“RegionCountryName”字段从“Geography”表拖到图表中。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
    让我们再添加一些数据。
    
3.  将 **SalesAmount** 字段拖动到图表，以查看净销售额和销售额之间的差异。
    
    我们现在在图表中实际上有两个度量值。 自动计算总和的 SalesAmount 和我们创建的 Net Sales 度量值。 在每个案例中，这些结果会依据图表中另一字段的上下文计算，即 RegionCountryName 中的国家/地区。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)
    
    让我们添加一个切片器，以便我们可以按日历年份进一步细分净销售额和销售总额。
    
4.  单击图表旁的空白区域，然后在**可视化效果**中，单击表可视化效果。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktablevisbutton.png)
    
    这会在报表画布中创建一个空白的表可视化效果。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
5.  将 **Year** 字段从 **Calendar** 表拖动到新的空白表。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
    因为 Year 是数值字段，Power BI Desktop 将计算其值的总和并为我们提供一个图表。 但是，与切片器相比，这样做作用不大。
    
6. 在“值”中，依次单击“年份”旁边的向下箭头和“不汇总”。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
    现在，我们可以将表可视化效果中的 Year 字段更改到切片器中。

    7.  在**可视化效果**中单击**切片器**可视化效果。

    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
    现在我们将 Year 字段作为切片器。 我们可以选择任何单独或群组年份，报表的可视化效果将据此进行切分。
    
8. 继续操作并单击“2013 年”。 你将看到图表发生更改。 我们的 Net Sales 和 SalesAmount 度量值将进行重新计算，并仅显示 2013 年的新结果。 再次重申，我们已更改了度量值在其中计算和显示结果的上下文。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

## <a name="lets-create-another-measure"></a>让我们创建另一个度量值
现在你已经知道了如何创建你自己的度量值，让我们再创建一个。

### <a name="net-sales-per-unit"></a>每单位净销售额
如果我们想要了解哪些产品每单位销售的销售额最高要怎么办呢？

我们可以创建另一个度量值。 在本案例中，我们想要用净销售额除以单位销售量。 事实上，我们要用 Net Sales 度量值的结果除以 Sales[SalesQuantity] 的总和。

1.  在 Sales 或 Products 表中创建名为 **Net Sales per Unit** 的新度量值。
    
    在此度量值中，我们将使用我们之前创建的 Net Sales 度量值。 使用 DAX，我们可以在公式中参考其他度量值。
    
2.  开始键入 **Net Sales**。 建议列表将显示我们可以添加的内容。 选择 **[Net Sales]**。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    此外还可以参考其他度量值，通过键入一个左方括号 (**[**) 即可。 建议列表将仅向我们显示能添加到公式的度量值。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  在 **[Net Sales]** 后依次输入一个空格、一个除号运算符 (**/**) 和一个 SUM 函数，然后键入 **Quantity**。 建议列表将显示名称中具有 Quantity 的所有列。 选择 **Sales [SalesQuantity]**。 该公式现在应如下所示：
    
    > **Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])**
    > 
    > 
    
    很酷吧？ 当我们使用 DAX 编辑器的搜索和建议功能时，输入 DAX 公式其实特别简单。 现在，让我们看看新的 Net Sales per Unit 度量值中有什么。
    
4. 将“每单位净销售额”度量值拖到报表画布中的空白区域。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
    不怎么有趣是吗？ 别担心。
    
5.  将图表可视化效果类型更改为**树状图**。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. 现在，将“ProductCategory”字段从“ProductCategory”表向下拖到“组”区域中。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
    这些信息很有用，但如果我们想要按产品查看净销售额呢？
    
7. 删除“ProductCategory”字段，再改为将“ProductName”字段从“Product”表向下拖到“组”区域中。 
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
    好了，我们只是热身而已，但你不得不承认，真的很酷！ 当然，我们可以用多种方法筛选此树状图，但这超出了本教程的范围。

## <a name="what-weve-learned"></a>所学内容
度量值为我们深入了解数据提供了强大的功能。 我们已经学习了如何使用公式栏创建度量值。 我们可以为度量值命名最有意义的名称，并且建议列表使查找并选择正确元素以将它们添加到公式变得更简单。 我们还介绍了上下文，其中度量值中的计算结果会根据其他字段或度量值公式中的其他表达式而发生更改。

## <a name="next-steps"></a>后续步骤
如果你想要深入了解 DAX 公式和创建更高级的度量值，请参阅 [Power BI Desktop 中的 DAX 基础知识](desktop-quickstart-learn-dax-basics.md)。 本文重点在于介绍 DAX 中的基本概念，如语法、函数和对上下文的透彻理解。

请务必将[数据分析表达式 (DAX) 参考](https://msdn.microsoft.com/library/gg413422.aspx)添加到收藏夹。 你可以在这里找到有关 DAX 语法、运算符和 200 多个 DAX 函数的详细信息。

