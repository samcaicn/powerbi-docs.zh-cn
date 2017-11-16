---
title: "如何使用 Power BI 问答"
description: "如何使用 Power BI 问答"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
tags: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: a6736916a4bb2e94c1f5e1e3c3c3e5339cf990ec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-use-power-bi-qa"></a>如何使用 Power BI 问答
## <a name="ask-questions-of-your-data-using-natural-language"></a>使用自然语言对你的数据提题
启动仪表板。 你可以使用自然语言在问答问题框中提问。 “问答”可以组织你键入的词语并指出可以在哪里（哪个数据集）找到答案。 “问答”还有助于你使用自动完成、重述以及其他文本和视觉对象组织你的问题。

![](media/service-how-to-q-and-a/powerbi-qna.png)

问题的答案以交互式可视化效果显示并会在你修改问题时进行更新。

问答是交互式的且十分有趣，而且一个问题会导致许多其他问题以可视化效果显示要查找的有趣路径。 观看 Amanda 使用问答演示创建视觉对象、深入挖掘这些视觉对象并将其固定到仪表板。

> [!NOTE]
> [iPad、iPhone 和 iPod Touch 设备上的 iOS 版 Microsoft Power BI 应用](mobile-apps-ios-qna.md)也支持问答。
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="use-natural-language-to-ask-questions-about-your-data"></a>使用自然语言提出有关数据的问题
1. 将光标放在问题框上。 在开始键入前，“问答”会显示新的屏幕，上面有帮助你提问的一些建议。
   
   ![](media/service-how-to-q-and-a/powerbi-qna-cursor.png)  
   
   此列表包含：  
   a.  用于创建[磁贴](service-dashboard-tiles.md)的问题，该磁贴已固定到仪表板，以及  
   b.  [基础数据集](service-get-data.md)中的表名称。  
   
   你始终可以选择这些问题之一作为起点并继续优化问题，以找出你要查找的特定答案。 或者，使用表名称帮助你组织一个新问题。
2. 从下拉列表中选择或开始键入你自己的问题。  
   
   ![](media/service-how-to-q-and-a/powerbi-qna-list.png)
3. 当你键入问题时，Power BI 问答会选择最佳的[可视化效果](power-bi-visualization-types-for-reports-and-q-and-a.md)显示你的答案；并且可视化效果会在你修改问题时进行动态更改。 “问答”还有助于你使用自动完成、重述问题以及其他文本和视觉对象组织你的问题。  
   ![](media/service-how-to-q-and-a/powerbi-qna-viz.png)
4. 当键入查询时，Power BI 会在所有在该仪表板中具有一个磁贴的数据集中查找答案。  如果所有磁贴都是来自 datasetA，则答案也将来自 datasetA。  如果有的磁贴源自数据集 A，有的磁贴源自数据集 B，那么问答功能将会从这 2 个数据集中搜索最佳答案。
   
   > [!TIP]
   > 请务必谨慎，如果从仪表板中删除唯一一个源自*数据集 A* 的磁贴，那么问答功能将不再有权访问数据集 A。
   > 
   > 
5. 如果对结果满意，则可以通过选择右上角的大头针图标[将可视化效果固定到仪表板](service-dashboard-pin-tile-from-q-and-a.md)。 如果仪表板已与你共享，或者仪表板是应用的一部分，将无法固定。
   
   ![](media/service-how-to-q-and-a/pbi_qna_finish-typing-question.jpg)

### <a name="tell-qa-which-visualization-to-use"></a>告知问答要使用哪个可视化效果。
使用问答，不仅可以让数据自己说话，而且可以使其按你想要的方式显示。 只需将“以<visualization type>显示”添加到问题的末尾即可。  例如，“显示工厂的库存量（以地图形式）”和“显示总库存（以卡片形式）”。  亲自动手。

## <a name="how-does-qa-know-how-to-answer-questions"></a>问答如何知道怎样回答问题？
### <a name="which-datasets-does-qa-use"></a>问答使用哪些数据集？
问答如何知道怎样回答特定于数据的问题？ 它依赖于基础数据集中的表、列和计算字段的名称。 因此你（或数据集所有者）对它们的称谓才最重要！ 

例如，假设你有这样一个 Excel 表，表名称为“销售”，其中列标题有“产品”、“月份”、“销售件数”、“销售总额”和“利润”。 你就可以对任何这些条目提问。  你可以请求提供“显示销售额”、“按月显示总利润”、“按销售件数对产品排序”等。

问答可以根据数据集的整理方式进行回答。 它对 Salesforce 中的数据如何处理？ 当连接到 salesforce.com 帐户时，Power BI 会自动生成一个仪表板。  当你使用问答开始提问时，请同时查看一下在仪表板可视化效果中显示的数据和在问答下拉列表中显示的数据。

* 如果可视化效果的轴标签和值包括“销售额”、“帐户”、“月份”和“商机”，则可以有把握地提出以下问题：“哪个帐户的商机最大”或“以条形图的形式按月显示销售额”。
* 如果下拉列表包括“销售人员”、“省/直辖市/自治区”和“年份”，则可以有把握地提出以下问题：“*2013* 年在美国佛罗里达州，哪个销售人员的销售额最低”。

如果可以通过 Google Analytics（Google 分析）获取网站性能数据，则可以向“问答”提出关于花在网页上的时间、独特网页访问数以及用户参与度方面的问题。 如果你要查询地理数据，则可以按位置就年龄和家庭收入提问。

### <a name="which-visualization-does-qa-use"></a>问答使用哪些可视化效果？
问答会根据要显示的数据选取最佳的可视化效果。 有时，可将基础数据集中的数据定义为特定类型或类别，以帮助问答识别如何显示数据。 例如，如果数据被定义为日期类型，则该数据很有可能显示为线图。 如果将数据分类为城市，则很有可能显示为地图。

通过将可视化效果添加到你的问题，还可以告知“问答”要使用哪个可视化效果。 但请记住，“问答”并非总能显示你请求的可视化效果类型中的数据。

有关“问答”可识别的关键字的信息，请参阅[提问技巧](service-q-and-a-tips.md)。

## <a name="next-steps"></a>后续步骤
返回到 [Power BI 中的问答](service-q-and-a.md)  
[教程：通过零售销售额示例使用问答](power-bi-visualization-introduction-to-q-and-a.md)  
[在问答中提问的提示](service-q-and-a-tips.md)  
[准备问答的工作簿](service-prepare-data-for-q-and-a.md)  
[将磁贴固定到问答中的仪表板](service-dashboard-pin-tile-from-q-and-a.md)  

