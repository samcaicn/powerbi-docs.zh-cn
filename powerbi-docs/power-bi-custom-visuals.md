---
title: "Power BI 中的自定义可视化效果"
description: "Power BI 中的自定义可视化效果"
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
ms.date: 11/20/2017
ms.author: mihart
ms.openlocfilehash: c50b984cd8babc845dbe0223613e463a7a8ee76d
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="custom-visuals-in-power-bi"></a>在 Power BI 中自定义视觉对象
创建或编辑 Power BI 报表时，可以使用多种不同类型的视觉对象。 这些视觉对象显示在“可视化效果”窗格中。 下载 Power BI Desktop 或打开 Power BI 服务 (app.powerbi.com) 时，这组视觉对象都已“预打包”。 

![](media/power-bi-custom-visuals/power-bi-visualizations.png)

不过，并不是只能使用这组视觉对象，选择省略号可以打开其他报表视觉对象源，即自定义视觉对象。

自定义视觉对象由社区成员和 Microsoft 创建，托管在 [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) 上。 可以下载这些视觉对象，并将它们添加到 Power BI 报表。 所有这些自定义视觉对象均已获得 Microsoft 批准。它们的行为与 Power BI 随附的预打包可视化效果相似，不同之处在于，它们可以进行筛选、突出显示、编辑、共享等。 

什么是 AppSource？ 简而言之，可以在其中查找 Microsoft 软件的应用、加载项和扩展。 [AppSource](https://appsource.microsoft.com) 为 Office 365、Azure、Dynamics 365、Cortana 和 Power BI 等产品的数百万用户提供解决方案，帮助他们更高效、更有见地或更为完美地完成工作。

## <a name="two-types-of-custom-visuals"></a>两种类型的自定义视觉对象

可以从 AppSource 获取的 Power BI 自定义视觉对象分为两类：已获准和已获认证。 AppSource 批准的视觉对象可以在浏览器、报表和仪表板中运行。  Power BI 取得认证的视觉对象已通过严格的测试，支持用于其他情形，如[电子邮件订阅](service-report-subscribe.md)和[导出到 PowerPoint](service-publish-to-powerpoint.md)。

若要查看已认证的自定义视觉对象列表或提交你自己的自定义视觉对象，请参阅[已认证的自定义视觉对象](power-bi-custom-visuals-certified.md)。

你是 Web 开发者吗？对创建自己的可视化效果，并将它们添加到 AppSource 感兴趣吗？  请参阅[开发人员工具入门](service-custom-visuals-getting-started-with-developer-tools.md)，了解如何[将自定义视觉对象发布到 AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)。

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>从 Microsoft AppSource 下载或导入自定义视觉对象
下载和导入自定义视觉对象的方法有两种，可以在 Power BI 中获取，也可以从 AppSource 网站获取。 

###    <a name="import-custom-visuals-from-within-power-bi"></a>在 Power BI 中导入自定义视觉对象
1. 选择“可视化效果”窗格底部的省略号。 

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. 在下拉列表中，选择“从存储导入”。

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-import.png)

3. 滚动浏览列表，找到要导入的视觉对象。 

    ![](media/power-bi-custom-visuals/power-bi-import-visual.png)

4.  若要详细了解视觉对象之一，请选中它。

    ![](media/power-bi-custom-visuals/power-bi-select.png)

5.  在详细信息页中，可以查看屏幕截图、视频、详细说明等内容。 

    ![](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. 滚动到底部可以查看评论。

    ![](media/power-bi-custom-visuals/power-bi-reviews.png)

7.    选择“添加”，导入自定义视觉对象。 现在，自定义视觉对象图标添加到“可视化效果”窗格底部，可供在报表中使用。

       ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)


###    <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>从 Microsoft AppSource 下载和导入自定义视觉对象

1. 首先，访问 [Microsoft AppSource](https://appsource.microsoft.com)，并选择“应用”选项卡。 

    ![](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. 此时，将会转到[“应用结果”页](https://appsource.microsoft.com/en-us/marketplace/apps)。在此页中，可以查看每种类别的热门应用，包括 Power BI 应用。 不过，由于要找的是自定义视觉对象，因此现在选择左侧导航列表中的“Power BI 视觉对象”，从而缩小结果范围。

    ![](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource 显示每个自定义视觉对象的磁贴。  每个磁贴均有自定义视觉对象的快照、简短说明和下载链接。 如需了解更多详情，请选择磁贴。 

    ![](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. 在详细信息页中，可以查看屏幕截图、视频、详细说明等内容。 选择“立即获取”，并同意接受使用条款，下载自定义视觉对象。 

    ![](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. 单击自定义视觉对象下载链接。

    ![](media/power-bi-custom-visuals/powerbi-custom-download.png)

    下载页还介绍了如何将自定义视觉对象导入 Power BI Desktop 和 Power BI 服务。

    还可以下载包含自定义视觉对象并展示其功能的示例报表。

    ![](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. 保存 .pbiviz 文件，再打开 Power BI。    
7. 打开要将自定义视觉对象添加到的报表，在“可视化效果”窗格底部依次选择省略号和“从文件导入”。  

      ![](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

8. 选择自定义视觉对象文件，将此自定义视觉对象的图标添加到“可视化效果”窗格底部。 现在，自定义视觉对象可供在报表中使用。

    ![](media/power-bi-custom-visuals/power-bi-chord.png)
    
##    <a name="considerations-and-troubleshooting"></a>注意事项和疑难解答


- 导入完成后，自定义视觉对象就已添加到特定报表。 若要在其他报表中使用此视觉对象，还需要将它导入相应报表。 使用“另存为”选项保存包含自定义视觉对象的报表时，自定义视觉对象的副本与新报表一同保存。

- 如果看不到“可视化效果”窗格，表示无权编辑报表。  只能将自定义视觉对象添加到有权编辑的报表，不能添加到与自己共享的报表。


更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

