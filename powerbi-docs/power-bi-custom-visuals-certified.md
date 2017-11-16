---
title: "认证的 Power BI 自定义可视化效果"
description: "提交自定义视觉对象以供认证的要求和过程。 已认证的自定义视觉对象的列表。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: 27af387a6d789b00837e6bbf8c6be9aa219c7198
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="getting-a-custom-visual-certified"></a>让自定义视觉对象取得认证
## <a name="what-is-meant-by-certified"></a>取得认证是指什么？
取得认证的自定义视觉对象是指已满足一系列代码要求且已通过严格的安全测试。  自定义视觉对象取得认证后，它可以[导出到 PowerPoint 中](service-publish-to-powerpoint.md)，并显示在用户[订阅报表页](service-report-subscribe.md)后收到的电子邮件中。

* 你是 Web 开发人员吗？对创建自己的可视化效果，并将其添加到应用商店感兴趣吗？ 请参阅[开发人员工具入门](service-custom-visuals-getting-started-with-developer-tools.md)，并访问 [Office 应用商店](service-custom-visuals-office-store.md)，了解具体的操作方法。
* 是否有定期使用的 Office 应用商店视觉对象？ 询问视觉对象开发人员以验证 Microsoft 的视觉对象。  开发者的联系信息位于视觉对象的“了解详细信息”页中，作为“提供商”列出。

## <a name="certification-requirements"></a>认证要求
* 经 Office 应用商店批准    
* 自定义视觉对象是使用经版本控制的 API 1.2 或更高版本进行编写    
* 代码存储库可供审核（例如，可通过 GitHub 审核视觉对象代码）    
* 仅使用可审核的公共 OSS 组件    
* 不访问外部服务或资源    

> 提示：建议结合使用 EsLint 与默认安全规则集，以便在提交之前预先验证代码。
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>提交自定义视觉对象以供认证的过程
提交自定义视觉对象以供认证：

1. 向 Power BI 自定义视觉对象支持人员 (pbicvsupport@microsoft.com) 发送电子邮件。 在电子邮件中，添加以下信息：    
   
   * 标题：视觉对象认证申请    
   * 指向托管视觉对象源代码的 GitHub 存储库的链接    
   * 符合要求（见上文）    
   * 通过代码和安全审核    
2. Microsoft 自定义视觉对象团队会通知你自定义视觉对象已取得认证并添加到“取得认证”列表（见下文）中，或自定义视觉对象已遭拒，并随附一份报告，在其中列出需要解决的问题。 开发者负责维护与 Microsoft 建立开放式沟通渠道，并根据需要更新取得认证的视觉对象。

## <a name="removal-of-power-bi-certified-custom-visuals"></a>删除 Power BI 认证的自定义视觉对象
Microsoft 可能会自行从“取得认证”列表中删除视觉对象。  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>取得认证的自定义视觉对象的列表
| 链接到 Office 应用商店 | 链接到视频 |
| --- | --- |
| [关联规则](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [星状体图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar] 即将推出 | |
| [框和须线](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [项目符号图表](https://store.office.com/en-us/app.aspx?assetid=WA104380755) |[视频 1](https://youtu.be/AOlsFYkfkcw)   [视频 2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[视频](https://youtu.be/mtvUNl9bMjA) |
| [Card with States by OKViz](https://store.office.com/card-with-states-by-okviz-WA104380967.aspx) |[视频 1](https://youtu.be/myiX0BmZd8U) [视频 2](https://youtu.be/AOlsFYkfkcw) |
| [条切片器](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[视频](https://youtu.be/iYOkJ1APueY) |
| [MAQ 软件绘制的圆形仪表](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [圆柱仪表](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | |
| [度盘式指示表](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) |[视频](https://youtu.be/AOlsFYkfkcw) |
| [MAQ 软件绘制的环形图（环形图表）](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[视频](https://youtu.be/pDToHDFHnq8) |
| [深化环形图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [双 KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[视频](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| 飞轮 - 即将推出 | |
| [甘特图](https://store.office.com/gantt-WA104380765.aspx) |[视频](https://youtu.be/qJ7s_KrGiUU) |
| [直方图](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [水平漏斗图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) |[视频](https://youtu.be/SudZei68PPo) |
| [图像时间线](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [KPI 指示器](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| Liquid Fill Gauge - 即将推出 |[视频](https://youtu.be/wQ51TTqIZc4) |
| [MAQ 软件绘制的线性仪表](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[视频](https://youtu.be/AOlsFYkfkcw) |
| 长文本查看器 - 即将推出 | |
| [播放轴（动态切片器）](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[视频](https://youtu.be/IvfIP3E6-1Q) |
| [脉冲图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006?src=office&tab=Overview) |[视频](https://www.youtube.com/watch?v=DQWdcQtjDVw) |
| [雷达图](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [桑基图](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[视频](https://youtu.be/WWP9wVUHGaA) |
| [MAQ Software 绘制的环形图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) |[视频](https://youtu.be/pDToHDFHnq8) |
| [滚动条](https://store.office.com/scroller-WA104381018.aspx) |[视频](https://youtu.be/uhRFQF2cGSY) |
| [Smart Filter by OKViz](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[视频](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[视频](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [转速计](https://store.office.com/tachometer-WA104380937.aspx?) |[视频](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [时序分解](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380897) | |
| [热度地图表](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [文本包装器](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [时间线切片器](https://store.office.com/timeline-slicer-WA104380786.aspx) |[视频](https://youtu.be/ozMtZ4_NZ10) |
| [飓风图](https://store.office.com/tornado-chart-WA104380768.aspx) |[视频](https://youtu.be/AQvd2FhRyCI) |
| [Visio 视觉对象（预览版）](https://store.office.com/visio-visual-preview-WA104381132.aspx) |[视频](https://www.youtube.com/watch?v=dCcd7rftjZA&list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x&index=2) |
| [Waffle 图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[视频](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[视频](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>后续步骤
[从 Office 应用商店下载和使用自定义视觉对象](service-custom-visuals-office-store.md)  
[自定义视觉对象开发者工具（预览版）入门](service-custom-visuals-getting-started-with-developer-tools.md)      
[YouTube 上的 Microsoft 自定义视觉对象播放列表](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI 中的可视化效果](power-bi-report-visualizations.md)  
[Power BI 中的自定义可视化效果](power-bi-custom-visuals.md)  
[在 Power BI Desktop 中使用自定义可视化效果](power-bi-custom-visuals-use.md)  
[将自定义视觉对象发布到 Office 应用商店](developer/office-store.md)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

