---
title: "Power BI 问答入门（教程）"
description: "教程：通过零售分析示例使用 Power BI 服务问答入门"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 2038fb5bd4a21235c3026c8506ae30b8c3e287e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="get-started-with-power-bi-qa-tutorial"></a>Power BI 问答入门（教程）
## <a name="tutorial-use-power-bi-qa-with-the-retail-analysis-sample"></a>教程：通过零售分析示例使用 Power BI 问答
有时从你的数据中获得答案的最快方法是使用自然语言提问。  在本教程中我们将考察创建相同的可视化效果的 2 种不同方法：在报表中构建和使用问答提问。  

## <a name="method-1-using-the-report-editor"></a>方法 1：使用报表编辑器
1. 在 Power BI 工作区中，选择“获取数据” \>“示例”\>“零售分析示例” > “连接”。
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)
2. 仪表板包含“上年度销售额和本年度销售额”的面积图磁贴。  选择此磁贴。 
   
   * 如果此磁贴是使用问答创建的，选择该磁贴将打开 Q&A。 
   * 但是，此磁贴是在报表中创建的，因此将在包含此可视化效果的页中打开报表。
3. 在编辑视图中打开报表，方法是选择**编辑报表**。  如果你不是报表的所有者，则无法在编辑视图中打开报表。
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. 选择此面积图，然后在**字段**窗格中检查设置。  报表创建者通过选择这 3 个值（“时间”>“会计月份”、“销售额”>“本年度销售额”、“销售额”>“上年度销售额”>“值”），并且在“坐标轴”和“值”框中组织它们来生成此图表。
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="method-2-using-qa"></a>方法 2：使用问题解答
我们将如何使用问答着手创建相同的折线图？

![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. 重新导航到“零售分析示例”仪表板。
2. 使用自然语言，在问题框中键入类似如下内容：
   
   **本年度销售额和上一年度销售额按月以分区图显示是什么**
   
   当你键入问题时，Q&A 选择最佳的可视化效果显示你的回答；并且可视化效果会随着问题的修改而动态更改。 此外，Q&A 还会通过建议、自动完成和拼写更正等功能来帮助你设置问题的格式。
   
   键入你的问题之后，所得到的图表正是我们在报表中看到的同一图表。  但是使用该方式创建要快得多！
   
   ![](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. 类似于使用报表，在问答中你有权访问“可视化效果”、“筛选器”和“字段”窗格。  打开这些窗格以进一步浏览和修改你的视觉对象。
4. 要将图表固定到仪表板中，请选择固定图标 ![](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png)。

## <a name="next-steps"></a>后续步骤
[我可以询问“问答”哪种类型的问题？](service-q-and-a.md)

[Power BI 中的“问答”](service-q-and-a.md)

[让你的数据在 Power BI 中很好地与“问答”协作](service-prepare-data-for-q-and-a.md)

[准备“问答”的工作簿](service-prepare-data-for-q-and-a.md)

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

