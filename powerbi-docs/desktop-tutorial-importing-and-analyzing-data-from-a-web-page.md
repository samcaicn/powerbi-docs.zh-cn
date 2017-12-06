---
title: "教程︰使用 Power BI Desktop 从网页导入和分析数据"
description: "教程︰使用 Power BI Desktop 从网页导入和分析数据"
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
ms.openlocfilehash: c5139c6f9f7b2098b51a608fb7719f371173c291
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="analyzing-web-page-data-using-power-bi-desktop-tutorial"></a>使用 Power BI Desktop 分析网页数据（教程）
在本教程中，您将学习如何从网页导入数据并创建报表以可视化数据。 在此过程中，您将在网页中各个表之间导航，并应用数据转换步骤以调整表。

 本文内容：

* **任务 1︰**连接到 Web 数据源
* **任务 2**︰在“查询”视图中调整数据
  * 步骤 1：删除其他列，只显示所需的列
  * 步骤 2︰替换值以清理所选列中的值
  * 步骤 3 ︰筛选列中的值
  * 步骤 4 ︰重命名列
  * 步骤 5︰筛选列中的 null 值
  * 步骤 6 ︰重命名列
  * 已创建查询步骤
* **任务 3**︰使用“报表”视图创建可视化效果
  * 步骤 1 ︰将查询加载到您的报表
  * 步骤 2 ︰创建地图可视化效果

## <a name="task-1-connect-to-a-web-data-source"></a>任务 1 ︰连接到 Web 数据源
 在任务 1 中，您从 UEFA European Football Championship Wikipedia 页面上的以下位置导入 Tournament Summary 表︰http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

### <a name="add-a-wikipedia-page-data-source"></a>添加 Wikipedia 页面数据源
1. 在**入门**对话框中或**主页功能区选项卡**中，选择**获取数据**。
2. 将显示**获取数据**对话框，您可以在其中选择各种数据源以便向 Power BI Desktop 导入数据。 我们将选择位于**所有**或**其他**组下的 **Web**。
3. 在 **Web 内容**对话框中的 **URL** 文字框中，粘贴 Wikipedia URL (http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship)。
4. 单击**确定**。

建立与网页的连接后，将在**导航器**对话框中显示此 Wikipedia 页面上的可用表的列表。 可以单击其中每个表，以预览数据。

在**导航器**左窗格中，选择**结果 [编辑]** 表了解 Tournament Summary 结果，或选择**结果 [编辑]** 表，然后选择**编辑**。 这将使我们能够在将此表加载到报表前调整此表，因为数据无法满足我们要执行的分析的要求。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)

将在“查询”视图中显示表的预览，并且我们可以在此视图中应用一组转换步骤来清理数据。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)

## <a name="task-2-shape-data-in-the-subject-table"></a>任务 2︰在主题表中调整数据
现在，已为数据查询中选择主题表，您将学习如何执行各种数据调整和清理步骤。

**步骤 1**：删除其他列，只显示所需的列

在此步骤中，除 **Year** 和 **Final Winners** 外的所有列都将删除。

1. 在**查询预览**网格中，选择 **Year** 和 **Final Winners** 列（使用 **CTRL** + **单击**操作执行）。
2. 右键单击**查询预览**网格中的列标题，然后单击**删除其他列**以删除未选定的列。 请注意，也可在**主页**功能区选项卡的**管理列**组中执行此操作。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

**步骤 2**︰替换值以清理所选列中的值

在此步骤中，替换 **Year** 列中的“详细信息”后缀。 请注意，此后缀置于新行中，因此在表预览中不可见。 但是，如果单击 Year 列中含数值的单元格，您将在详细视图中看到完整值。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage5.png)

1. 选择 **Year** 列。
2. 在**查询视图**功能区上，单击**主页**选项卡下的**替换值**，或右键单击 **Year** 列并单击**替换值**，将“详细信息”替换为空文本。
3. 在**替换值**对话框框中，在**要查找的值**文本框中键入详细信息，将**替换为**文本框留空。
4. 单击**确定**。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

 **步骤 3**

在此步骤中，将筛选 **Year** 列以显示不包含“Year”行。

1. 单击 **Year** 列中的筛选器下拉箭头。
2. 在**筛选器**下拉列表中，清除 **Year** 选项。
3. 单击**确定**。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

**步骤 4**︰重命名列

现在，已清理 **Year** 列中的数据，然后我们将处理 **Final Winner** 列。

由于我们只搜索获胜者的列表，因此可以将该列重命名为 **Country**。

1. 在查询预览中选择 **Final Winner** 列。
2. 在**查询视图**功能区的**转换**选项卡和**任何列**组下，会显示**重命名**。
3. 这将使列名称可编辑。 我们将该列重命名为 **Country**。

**步骤 5：**筛选出列中的 null 值

我们还需要筛选出 **Country** 列中的 null 值。 为此，可使用步骤 3 中所示的筛选器菜单，或者可以执行以下操作︰

1. 右键单击 **Country** 列中包含 null 值的一个单元格。
2. 在上下文菜单中选择**文本筛选器 -\> 不等于**。
3. 将创建一个新筛选器步骤以删除 **Country** 列中含 null 值的行。

**步骤 6︰** 命名查询

在此步骤中，将最终查询命名为 **Euro Cup Winners**。

1. 在**查询设置**窗格中的**名称**文字框中，输入 **Euro Cup Winners**。
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

## <a name="task-3-create-visualizations-using-the-report-view"></a>任务 3︰使用“报表”视图创建可视化效果
现在我们已将数据转换成所需形式以用于执行分析，我们可以将所得表加载到报告，并创建几种可视化。

**第 1 步**︰将查询加载到您的报表

为了将查询结果加载到 Power BI Desktop 以及创建报表，我们从**主页**功能区中选择**关闭并加载**。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)

这将导致评估查询以及将表输出内容加载到报表。 在 Power BI Desktop 中，选择**报表**图标可在“报表”视图中查看 Power BI Desktop。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage10.png)

您可以在**报表视图**右侧的**字段窗格**中看到所生成的表字段。

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)

**步骤 2**︰创建地图可视化

要创建可视化，我们可以将字段从**字段列表**拖放到**报表画布**中。

1. 将 **Country** 字段拖放到**报表画布**。 将在**报表画布**中创建新的可视化。 在此示例中，由于我们具有 Country 列表，因此它将创建**地图可视化**。
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage12.png)
2. 可以方便地通过在**可视化效果**窗格中选择不同图标来更改可视化效果类型。
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage13.png)
3. 我们将继续使用**地图**可视化类型。对于地图，还可以调整可视化效果，方法是将可视化效果的一个角拖到所需大小。
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
4. 请注意，地图中的所有当前点具有相同的大小。 我们需要对此进行更改，以便使拥有多个 Euro Cup 大赛冠军的国家/地区由地图中较大的点表示。 为此，我们可以将**字段列表**中的 **Year** 字段拖动到**字段窗格**下半部分的**值**框中。
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)

如您所见，可以非常方便地在报表中自定义可视化效果以便你按所需方式呈现数据。 Power BI Desktop 提供无缝的端到端体验（从各种数据源获取数据到拆分以满足您的分析需求再到以丰富的交互方式可视化这些数据）。 在报表准备就绪后，您可以[将其上载到 Power BI](desktop-upload-desktop-files.md) 并基于它创建仪表板与其他 Power BI 用户共享。

我们的**从 Web 导入数据**教程到此为止。 你可以在[此处](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Data_From_The_Web.pbix)下载完整的 Power BI Desktop 文件。

## <a name="where-else-can-i-get-more-information"></a>我还可以在哪些位置获取详细信息？
* [阅读其他 Power BI Desktop 教程](http://go.microsoft.com/fwlink/?LinkID=521937)
* [观看 Power BI Desktop 视频](http://go.microsoft.com/fwlink/?LinkID=519322)
* [访问 Power BI 论坛](http://go.microsoft.com/fwlink/?LinkID=519326)
* [阅读 Power BI 博客](http://go.microsoft.com/fwlink/?LinkID=519327)

