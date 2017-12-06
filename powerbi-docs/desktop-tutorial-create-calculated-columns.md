---
title: "教程：创建 Power BI Desktop 中的计算列"
description: "教程：创建 Power BI Desktop 中的计算列"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 9ea93980a095ca4e626b6f8071d044448af59635
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>教程：创建 Power BI Desktop 中的计算列
有时，当前分析的数据不包含获取所期望结果时所需的特定字段。 这就是计算列的有用之处。 计算列使用数据分析表达式 (DAX) 公式来定义列的值。 这些值可以是几乎任何内容，无论它是将来自其他位置的几个不同列的组合中的文本值都放到模型中，或是计算来自其他值的数字值。 例如，假设你的数据中含有“城市”和“州”两个列（作为字段列表中的字段），但你想要使同时含有这两个列的单一“位置”字段成为一个单值，如“迈阿密，佛罗里达州”。 这正是计算列的作用。

计算列类似于度量值，因为二者都基于 DAX 公式，但它们的区别在于如何使用。 度量值最常用于可视化的“值”区域，用来计算基于你在表中有行的其他字段的结果，或用于可视化的“轴”、“图例”或“组”区域中。 另一方面，计算列用于当你希望列的结果在此表的某一行中，或在“轴”、“图例”或“组”区域中。

本教程将指导你了解并在 Power BI Desktop 中创建一些你自己的计算列。 教程面向已熟悉使用 Power BI Desktop 创建更高级的模型的 Power BI 用户。 你应该已经熟悉使用“查询”来导出数据、使用多个相关表和向报表画布添加字段。 如果刚开始使用 Power BI Desktop，请务必查看 [Power BI Desktop 入门](desktop-getting-started.md)。

若要完成本教程中的步骤，你需要下载 [Power BI Desktop 的 Contoso 销售示例](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip)文件。 这是在[《在 Power BI Desktop 中创建自己的度量值》](desktop-tutorial-create-measures.md)教程中所用的相同示例文件。 它已包含来自虚构公司 Contoso,inc. 的销售数据。因为文件中的数据已从数据库导入，因此你将无法连接到数据源或在查询编辑器中查看。 当你自己的计算机上有此文件时，请直接在 Power BI Desktop 中将它打开。

## <a name="lets-create-a-calculated-column"></a>让我们来创建一个计算列
假设我们想要在行中的一个单值内同时展示产品类别和产品子类别，如手机 – 附件，手机 – 智能手机和 PDA，等等。 在报表视图或数据视图中（此处我们使用报表视图），如果我们看一下字段列表中的产品表，就会发现给出的结果中没有我们想要的任何字段。 然而，我们有 ProductCategory 字段和 ProductSubcategory 字段，二者分别在其各自的表中。

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

我们将创建新的计算列，用来将这两个列中的值合并到新列中的新值内。 有趣的是，我们需要将两个不同表中的数据组合到一个单列内。 由于要使用 DAX 来创建新列，因而我们可以利用已有模型的完整功能，包括不同的表之间已存在的关系。

### <a name="to-create-a-productfullcategory-column"></a>创建 ProductFullCategory 列
1.  右键单击或单击字段列表中的 **ProductSubcategory** 表上的向下箭头，然后单击**新建列**。 这会确保新列被添加到 ProductSubcategory 表中。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)
    
    公式栏将在报表画布或数据网格的顶部出现。 我们可以在此处重命名列并输入 DAX 公式。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)
    
    默认情况下新计算列简单地命名为列。 如果我们不进行重命名，当我们创建其他度量值时，便会命名为列 2、列 3，依此类推。 我们希望列更易于识别，因此我们为这个新列提供新名称。
    
2.  由于**列**名已在公式栏中突出显示，因此只需键入“ProductFullCategory”即可。
    
    现在我们可以开始输入公式。 我们希望新列中的值以 ProductCategory 表中的 ProductCategory 名称开始。 因为此列在不同但相关的表中，我们将使用 [RELATED](https://msdn.microsoft.com/library/ee634202.aspx) 函数来帮助获得它。
    
3.  在等号后键入 **R**。你将看到显示出来一个下拉建议列表，其中有以字母 R 开头的所有的 DAX 函数。我们键入的字母越多，建议列表就更能调整至接近我们所需的函数。 在函数周围，你将看到该函数的说明。 通过向下滚动选择 **RELATED**，然后按 Enter。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)
    
    出现一个左括号和另一个建议清单，其中包括我们可以传递到 RELATED 函数的所有可用的列。 此外还会显示参数所预期的说明和详细信息。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)
    
    表达式将始终出现在左括号和右括号之间。 在这种情况下，我们的表达式将包含已传递到 RELATED 函数的单个参数；也就是要作为返回值来源的相关列。 列的列表会自动缩小以仅显示相关的列。 在这种情况下，我们想要 ProductCategory 表中的 ProductCategory 列。
    
    选择 **ProductCategory [ProductCategory]**，然后键入右括号。
    
    > [!TIP]
    > 语法错误通常由缺少或错放右括号导致。 但如果你忘记了，Power BI Desktop 通常会添加上。
    > 
    > 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)
    
4. 我们想要添加短划线符号来分隔各个值，因此在第一个表达式的右括号后面，键入空格、& 号、左引号、空格、短划线 (-)、又一空格、右引号和又一 & 号。 该公式现在应如下所示：
    
    **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & " - " &**
    
    > [!TIP]
    > 单击公式栏右侧的向下 V 形图标，展开公式编辑器。 按 Alt 和 Enter 键，向下移动一行，并按 Tab 键来移动内容。
    > 
    > 
    
5.  最后，输入又一左括号，然后选择“[ProductSubcategory]”列，从而完成公式。 该公式应如下所示：
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)
    
    你会注意到我们没有使用调用 ProductSubcategory 列的第二个表达式中的另一个 RELATED 函数。 这是因为此列已在创建新列所在的同一个表中。 我们可以输入带表名（完全限定的）或不带表名（非限定的）的 [ProductCategory]。
    
6.  按 Enter 键或单击在公式栏中的选中标记以完成该公式。 该公式将经过验证并添加到 **ProductSubcategory** 表中的字段列表。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)
    
    你将注意到，计算列在字段列表中有一个特殊图标。 这显示它们包含一个公式。 且仅在 Power BI Desktop 中才会如此显示。 在 PowerBI 服务（Power BI 网站）中，绝对无法更改公式，所以计算列字段不会附带图标。
    
## <a name="lets-add-our-new-column-to-a-report"></a>让我们将新列添加到报表中
现可将新的 ProductFullCategory 列添加到报表画布。 我们来看一下按 ProductFullCategory 排列的 SalesAmount。

将 **ProductSubcategory** 表中 **ProductFullCategory** 列拖到报表画布上，然后将**销售**表的 **SalesAmount** 字段拖到图表中。

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>再来创建一个列
现在了解了如何创建计算列，我们再来创建一列。

Power BI Desktop 模型的 Contoso 销售示例包括针对活跃商店和非活跃商店的销售数据。 我们希望针对非活跃商店显示的数据清楚标识为此状态。 事实上，我们想有一个名为 Active StoreName 的字段。 为此，将再创建一个列。 在本例中，当商店不活跃时，我们希望 Active StoreName 列（作为字段）将此商店的名称显示“非活动”，而在商店活跃时显示此商店的实际名称。

幸运的是，销售表中有一个名为“状态”的列，其针对活跃商店具有值“开”且针对非活跃商店具有值“关”。 我们可在“状态”列中测试每行的值，以在新列中创建新值。

### <a name="to-create-an-active-storename-column"></a>若要创建 Active StoreNam 列
1.  在**销售**表中新建名为 **Active StoreName** 的计算列。
    
    对于此列，DAX 公式将检查每个商店的状态。 如果商店状态为“开”，则公式将返回商店名称。 如果其为“关”，则将具有“非活动”这一名称。 为此，将使用逻辑 [IF](https://msdn.microsoft.com/library/ee634824.aspx) 函数来测试商店状态，并在结果为 true 或 false 时返回特定值。
    
2.  开始键入 **IF**。 建议列表将显示我们可以添加的内容。 选择 **IF**。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)
    
    IF 的第一个参数是逻辑测试。 我们想要测试商店是否具有状态“开”。
    
3.  键入一个左方括号 **[**，它可用于从商店表中选择列。 选择 **[Status]**。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)
    
4.  紧跟 **[Status]** 键入 **="On"**，然后输入逗号 (**,**) 以便输入第二个参数。 工具提示建议我们在结果为 true 时添加一个值。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)
    
5.  如果商店处于“开”的状态，则需要显示商店的名称。 键入一个左方括号 **[**，选择 **[StoreName]** 列，然后再键入一个逗号，以便可输入第 3 个参数。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)
    
6.  当结果为 false 时，需要添加一个值，在本例中我们希望值为**“非活动”**。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)
    
7.  按 Enter 键或单击在公式栏中的选中标记以完成该公式。 该公式将经过验证并添加到销售表中的字段列表。
    
    如其他任何字段一样，能够在可视化对象中使用新的 Active StoreName 列。 在此图中，状态为“开”的商店按名称单独显示，但状态为“关”的商店将组合在一起并显示为“非活动”。 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)
    
## <a name="what-weve-learned"></a>所学内容
计算列可丰富数据，提供更方便的见解。 我们学习了如何使用公式栏来创建计算列、如何使用建议列表，以及如何以最佳方式设置新列的名称。

## <a name="next-steps"></a>后续步骤
如果想要更深入了解 DAX 公式，并使用更高级的 DAX 公式来创建计算列，请参阅 [Power BI Desktop 中的 DAX 基本概念](desktop-quickstart-learn-dax-basics.md)。 本文重点在于介绍 DAX 中的基本概念，如语法、函数和对上下文的透彻理解。

请务必将[数据分析表达式 (DAX) 参考](https://msdn.microsoft.com/library/gg413422.aspx)添加到收藏夹。 你可以在这里找到有关 DAX 语法、运算符和 200 多个 DAX 函数的详细信息。

