---
title: "教程︰使用 Power BI Desktop 进行 Facebook 分析"
description: "教程︰使用 Power BI Desktop 进行 Facebook 分析"
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
LocalizationGroup: Learn more
ms.openlocfilehash: e0bdec7d2774fd5c6641041af14b2170d7223151
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="tutorial-facebook-analytics-using-power-bi-desktop"></a>教程︰使用 Power BI Desktop 进行 Facebook 分析
在本教程中，你将学习如何导入和可视化来自 **Facebook** 的数据。 在本教程中，你将了解如何连接到特定 Facebook 页面（Power BI 页面）、应用数据转换步骤以及创建某些可视化效果。

将执行下列步骤：

* **任务 1：**连接到 Facebook 页面
* **任务 2**︰使用“报表”视图创建可视化效果
  
  * **步骤 1**︰创建树状图可视化效果
* **任务 3**︰在“查询”视图中调整数据
  
  * **步骤 1**︰将“日期-时间”列拆分为两列
  * **步骤 2**︰从相关表中添加聚合值
* **任务 4**︰使用“报表”视图创建其他可视化效果
  
  * **步骤 1**︰将查询加载到报表
  * **步骤 2**︰创建折线图和条形图

## <a name="task-1-connect-to-a-facebook-page"></a>**任务 1：连接到 Facebook 页面**
在此任务中，你将从 [Microsoft Power BI Facebook](https://www.facebook.com/microsoftbi) 站点中导入数据（在此处为 URL︰*https://www.facebook.com/microsoftbi）*。

任何人都可以连接到该页面并执行下列步骤，而不需要提供任何特殊凭据（但你需在此步骤中使用自己的 Facebook 帐户）。

![](media/desktop-tutorial-facebook-analytics/1.png)

1. 在**入门**对话框中或**主页功能区选项卡**中选择**获取数据**。
2. **获取数据**对话框将打开，并允许你从各种数据源进行选择。 从**其他**组中选择 **Facebook**。
   
   ![](media/desktop-tutorial-facebook-analytics/t_fb_getdataother.png)
   
   当选择**连接**时，出现一个对话框，提醒你如果使用第三方服务将产生风险。
   
   ![](media/desktop-tutorial-facebook-analytics/t_fb_connectingtotps.png)
3. 当你选择“继续”时，将显示 **Facebook** 对话框，你可以将页名称 (**microsoftbi**) 粘贴到**用户名** 文本框中。 从**连接**下拉列表中选择**文章**。
   
   ![](media/desktop-tutorial-facebook-analytics/2.png)
4. 单击**确定**。
5. 在系统提示你输入凭据时，使用你的 Facebook 帐户进行登录，并允许通过你的帐户进行 Power BI 访问。
   
   ![](media/desktop-tutorial-facebook-analytics/facebookcredentials.png)

建立与页面的连接后，你将看到在模型中加载的数据。 

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadpreview.png)

**查询编辑器**将在此处显示数据。 **查询编辑器**是 Power BI Desktop 的一部分，但会在单独窗口中加载，你可以在数据连接上执行所有转换。

![](media/desktop-tutorial-facebook-analytics/t_fb_1-intoqueryeditor.png)

当数据满足要求时，即可将数据加载到 Power BI Desktop。 从**主页**功能区中选择**加载并关闭**。

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)

你将看到一个对话框，其显示向 Power BI Desktop 数据模型加载数据的进度。

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loading.png)

加载数据后，你将转到**报表**视图，其右侧的**字段**列表中列出了表中的列。

![](media/desktop-tutorial-facebook-analytics/fbdesigner1.png)

## <a name="task-2-create-visualizations-using-the-report-view"></a>**任务 2：使用“报表”视图创建可视化效果**
现在，已从页面加载数据，你可以使用可视化效果快速轻松地深入了解数据。

**步骤 1︰**创建树状图可视化效果

创建可视化效果的过程很简单，只需将字段从**字段列表**拖放到**报表画布即可。**

将**类型**字段拖放到**报表**画布中。 Power BI Desktop 将在**报表画布**中创建新的可视化效果。 然后，将**类型**从**字段**（与你刚拖**报表**画布的字段相同）拖放到**值**区域以创建**条形图**可视化效果。

![](media/desktop-tutorial-facebook-analytics/fbdesigner2.png)

可通过从**可视化效果**窗格中选择不同图标来方便地更改可视化效果类型。 我们通过从**可视化效果**中选择相应图标将类型更改为**树状图**，如下图中所示。

![](media/desktop-tutorial-facebook-analytics/fbdesigner3.png)

然后，添加图例，并更改数据点的颜色。 在**可视化效果**窗格中选择**格式**图标；**格式**图标显示为画笔形状。

![](media/desktop-tutorial-facebook-analytics/fbdesigner3a.png)

当你选择**图例**旁边的向下箭头时，此部分将展开以显示如何为所选可视化效果自定义图例。 在此示例中，我们进行以下选择 ︰

* 将**图例**滑块移到**打开**以显示图例
* 从**图例位置**下拉列表中选择**右侧**
* 将**标题**滑块移到**打开**以显示图例的标题
* 键入图例标题的**类型**

在下图中，这些设置已执行并反映在可视化效果中。

![](media/desktop-tutorial-facebook-analytics/fbdesigner3b.png)

然后，我们更改其中一个数据点的颜色。 链接数据点应为蓝色，以便其更接近于常用的超链接颜色。

选择**数据颜色**旁边的箭头以展开该部分。 将显示数据点，并在每种颜色旁边显示一个选择箭头，用于为每个数据点选择不同的颜色。

![](media/desktop-tutorial-facebook-analytics/fbdesigner3c.png)

单击任何数据点旁边的颜色框向下箭头时，会显示颜色选择对话框，提示你选择颜色。 在此示例中，我们将选择浅蓝色。

![](media/desktop-tutorial-facebook-analytics/fbdesigner3d.png)

这样效果会更好一些。 在下图中，你可以看到如何将颜色应用于该可视化对象中的数据点，并且图例也将自动更新，因为其颜色位于**数据颜色**部分中。

![](media/desktop-tutorial-facebook-analytics/fbdesigner3e.png)

## <a name="task-3-shape-data-in-the-table"></a>**任务 3：在表中调整数据**
现在你已导入所选表并开始进行可视化，你可能会发现你需要执行各种数据调整和清理步骤，以便最充分地利用数据。

**步骤 1**︰将“日期时间”列拆分为两列

在此步骤中，你将拆分**创建\_时间**列以获取日期和时间值。 每当你需要在 Power BI Desktop 中修改现有查询时，都必须启动 **查询编辑器**。 为此，请从**主页**选项卡中选择**编辑查询**。

![](media/desktop-tutorial-facebook-analytics/t_fb_editquery.png)

1. 在**查询编辑器**网格中，滚动到右侧，直到你找到**创建\_时间**列
2. 右键单击**查询预览**网格中的列标题，然后单击**拆分列\>，按分隔符**拆分这些列。 在分隔符下拉列表中选择**自定义**，输入**“T”** 请注意，也可在**主页**功能区选项卡上的**管理列**组中执行此操作。
   
   ![](media/desktop-tutorial-facebook-analytics/9.png)
   
   ![](media/desktop-tutorial-facebook-analytics/10.png)
3. 将创建的列分别重命名为**创建\_日期**和**创建\_时间**。
4. 选择新列，**创建\_时间**，****并在**查询视图**功能区中导航到**添加列**选项卡，然后在**从日期和时间**组下选择**时间\>小时**。 将添加一个新列，其中只包含时间数据的小时数部分。
   
   ![](media/desktop-tutorial-facebook-analytics/11.png)
5. 将此新**小时**列的类型更改为**整数**，方法是导航到**主页**选项卡并选择**数据类型**下拉菜单，或者右键单击列并选择**转换\>整数**。
   
   ![](media/desktop-tutorial-facebook-analytics/12.png)

**步骤 2**︰从相关表中添加聚合值

在此步骤中，你将从嵌套值添加共享计数，以便在可视化效果中使用它。

1. 继续向右滚动，直到你看到**共享**列。 嵌套值指示我们需要执行另一个转换以获得实际值。
2. 在列标题的右上角，选择 ![](media/desktop-tutorial-facebook-analytics/14.png) 图标以打开**展开/聚合**生成器。 选择**计数**并单击**确定**。 将在表格中添加每一行的共享的计数。
   
   ![](media/desktop-tutorial-facebook-analytics/15.png)
   
   加载数据后，将列重命名为**共享**，方法是双击列名称并右键单击列，或在**查询视图**功能区中的**重命名**和**任何列**组下选择**转换**选项卡。
3. 最后，将新**共享**列更改为**整数**。 可在选中列的情况下更改类型，方法是选择**转换\>整数**，或****导航到**主页**选项卡并选择**数据类型**下拉列表，或者。

### <a name="query-steps-created"></a>已创建查询步骤
在“查询”视图中执行转换时，将创建查询步骤并将其列在**查询设置**窗格的**应用的步骤**列表中。 每个查询步骤都具有对应的查询公式，也称为“M”语言。

![](media/desktop-tutorial-facebook-analytics/16.png)

| 任务 | 查询步骤 | 公式 |
| --- | --- | --- |
| 连接到 Facebook 源 |源 |Facebook.Graph (&quot;https://graph.facebook.com/microsoftbi/posts&quot;) |
| **拆分列**以获取所需的值 |按分隔符拆分列 |Table.SplitColumn  (Source,&quot;created_time&quot;,Splitter.SplitTextByDelimiter(&quot;T&quot;),{&quot;created_time.1&quot;, &quot;created_time.2&quot;}) |
| 新列的**更改类型**（自动步骤） |已更改类型 |Table.TransformColumnTypes  (#&quot;Split Column by Delimiter&quot;,{{&quot;created_time.1&quot;, type date}, {&quot;created_time.2&quot;, type time}}) |
| **重命名**列**** |已重命名列 |Table.RenameColumns  (#&quot;Changed Type&quot;,{{&quot;created_time.1&quot;, &quot;created_date&quot;}, {&quot;created_time.2&quot;, &quot;created_time&quot;}}) |
| **插入**列**** |已插入小时 |Table.AddColumn  (#&quot;Renamed Columns&quot;, &quot;Hour&quot;, each Time.Hour([created_time]), type number) |
| **更改类型** |已更改类型 1 |Table.TransformColumnTypes  (#&quot;Inserted Hour&quot;,{{&quot;Hour&quot;, type text}}) |
| **展开**嵌套表中的值**** |展开共享 |Table.ExpandRecordColumn  (#&quot;Changed Type1&quot;, &quot;shares&quot;, {&quot;count&quot;}, {&quot;shares.count&quot;}) |
| **重命名**列**** |已重命名列 1 |Table.RenameColumns  (#&quot; Expand shares&quot;,{{&quot;shares.count&quot;, &quot;shares&quot;}}) |
| **更改类型** |已更改类型 2 |Table.TransformColumnTypes  (#&quot;Renamed Columns1&quot;,{{&quot;shares&quot;, Int64.Type}}) |

## <a name="task-4-create-additional-visualizations-using-the-report-view"></a>**任务 4：使用“报表”视图创建其他可视化效果**
现在我们已将数据转换成所需形式以用于执行其余分析，我们可以将生成的表加载到报表，并创建其他可视化效果。

**步骤 1**︰将查询加载到你的报表

为了将查询结果加载到报表，我们需要从**查询编辑器**中选择**加载并关闭**。 这会将所做的更改加载到 Power BI Desktop，并关闭**查询编辑器**。

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)

在 Power BI Desktop 中，需确保我们位于**报表**视图中。 从 Power BI Desktop 的左侧栏中选择顶部的图标。

![](media/desktop-tutorial-facebook-analytics/17.png)

**步骤 2：**创建折线图和条形图

要创建可视化，可以将字段从**字段列表**拖放到**报表画布**中。

1. 将**共享**字段拖放到**报表**画布，这将创建一个条形图。 然后将创建的\_日期拖放到图表中。Power BI Desktop 会将可视化效果更改为**折线图**。
   
   ![](media/desktop-tutorial-facebook-analytics/19.png)
2. 然后，将**共享**字段拖放到**报表画布**。 现在，将**小时**字段拖放到**轴**部分的**字段列表**下。
   
   ![](media/desktop-tutorial-facebook-analytics/20.png)
3. 可以通过在**可视化**窗格中选择不同图标来方便地更改可视化效果类型。 下面的图中箭头指向**条形图**图标。
   
   ![](media/desktop-tutorial-facebook-analytics/21.png)
4. 将可视化类型更改为**条形图**。
5. 将创建**条形图**，但轴并非我们希望的。我们想要按另一个方向（从高到低）对其排序。 选择 **Y 轴**旁边的向下箭头以展开该部分。 我们需要将轴类型从**连续**更改为**分类**从而按所需方式排序（下图显示了执行选择之前的轴；请从后续图像了解我们希望的轴显示形式）。

![](media/desktop-tutorial-facebook-analytics/22.png)

这样效果会更好一些。 现在我们在此页面上具有三种可视化效果，我们可以调整其大小以填满报表页。

![](media/desktop-tutorial-facebook-analytics/23.png)

如你所见，可以方便地在报表中自定义可视化效果以便你按所需方式呈现数据。 Power BI Desktop 提供无缝的端到端体验（从各种数据源获取数据到拆分以满足你的分析需求再到以丰富的交互式方式可视化这些数据）。 在报表准备就绪后，你可[将其上载到 Power BI](desktop-upload-desktop-files.md) 并基于它创建仪表板与其以他 Power BI 用户共享。

可以在[此处](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/FacebookAnalytics.pbix)下载本教程的最终结果

### <a name="where-else-can-i-get-more-information"></a>我还可以在哪些位置获取详细信息？
* [阅读其他 Power BI Desktop 教程](http://go.microsoft.com/fwlink/?LinkID=521937)
* [观看 Power BI Desktop 视频](http://go.microsoft.com/fwlink/?LinkID=519322)
* [访问 Power BI 论坛](http://go.microsoft.com/fwlink/?LinkID=519326)
* [阅读 Power BI 博客](http://go.microsoft.com/fwlink/?LinkID=519327)



