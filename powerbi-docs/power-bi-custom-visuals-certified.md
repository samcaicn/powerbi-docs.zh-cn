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
ms.date: 01/24/2018
ms.author: mihart
ms.openlocfilehash: f9824b29515481742c339bc76e766e5e62cf1716
ms.sourcegitcommit: be5223b62e9a5d57c52f8588d4e539d814751dd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
---
# <a name="getting-a-custom-visual-certified"></a>让自定义视觉对象取得认证
## <a name="what-is-meant-by-certified"></a>取得认证是指什么？
取得认证的自定义视觉对象是指已满足一系列代码要求且已通过严格的安全测试。  自定义视觉对象取得认证后，它可以[导出到 PowerPoint 中](service-publish-to-powerpoint.md)，并显示在用户[订阅报表页](service-report-subscribe.md)后收到的电子邮件中。 当然，它还可以用作[标准自定义视觉对象](power-bi-custom-visuals.md)，添加到 Power BI 服务和 Power BI Desktop 报表中，并在 Power BI 移动中查看和嵌入。

你是 Web 开发者吗？对创建自己的可视化效果，并将它们添加到 [Microsoft AppSource](https://appsource.microsoft.com) 感兴趣吗？ 请参阅[开发人员工具入门](service-custom-visuals-getting-started-with-developer-tools.md)，了解具体操作。


## <a name="certification-requirements"></a>认证要求
* Microsoft AppSource 已批准    
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
| AppSource 链接 | 链接到视频 |
| --- | --- |
| [关联规则](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [星状体图](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar（Beyondsoft 日历）](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [MAQ Software 的蝴蝶结图](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[视频](https://youtu.be/So5xKMSpVJI) |
| [框和须线](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [MAQ 软件砖形图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | |
| [Akvelon 气泡图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340?src=office) | |
| [项目符号图表](https://store.office.com/app.aspx?assetid=WA104380755) |[视频 1](https://youtu.be/AOlsFYkfkcw)   [视频 2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[视频](https://youtu.be/mtvUNl9bMjA) |
| [Tallan 的日历](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [OKViz K 线图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | |
| [条切片器](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[视频](https://youtu.be/iYOkJ1APueY) |
| [和弦图](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[视频](https://youtu.be/AQvd2FhRyCI) |
| [MAQ 软件绘制的圆形仪表](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [圆柱仪表](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [度盘式指示表](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[视频](https://youtu.be/AOlsFYkfkcw) |
| [MAQ 软件绘制的环形图（环形图表）](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[视频](https://youtu.be/pDToHDFHnq8) |
| [MAQ 软件点图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381101) | |
| [OKViz 的点阵图](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[视频](https://youtu.be/4lskRgcpFJY) |
| [Microsoft 点图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760?src=office) | |
| [ZoomCharts 向下钻取式环形图](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [向下钻取变形地图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045?src=office) | |
| [向下钻取分级统计图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044?src=office) | |
| [ZoomCharts 向下钻取柱形图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881?src=office) | |
| [ZoomCharts 基于时间的向下钻取柱形图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | |
| [ZoomCharts 向下钻取式环形图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [双 KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[视频](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [增强散点图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | |
| [Enlighten 水族馆](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| [Enlighten 气泡图堆栈](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380868) | |
| [Enlighten 切片器](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960?tab=Overview) | |
| [Enlighten 洗牌排序法](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten 方格百分比图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Enlighten 世界国旗](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380923) | |
| [Force-Directed Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) |[视频](https://youtu.be/YsTa7uyJ4sg) |
| [预测 TBATS](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381326?src=office) | |
| [漏斗图（含源）]() | || [甘特图](https://store.office.com/gantt-WA104380765.aspx) |[视频](https://youtu.be/qJ7s_KrGiUU) |
| [Akvelon 层次机构图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333?src=office) | |
| [直方图](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [水平漏斗图](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[视频](https://youtu.be/SudZei68PPo) |
| [图像时间线](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [信息图设计器](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898?src=office) | |
| [KPI 指示器](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [MAQ 软件 KPI 股票代码](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | |
| [点线图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766?src=office) | |
| [MAQ 软件绘制的线性仪表](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[视频](https://youtu.be/AOlsFYkfkcw) |
| [马赛克图](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [视频](https://youtu.be/90FLCKpgicA)|
| [播放轴（动态切片器）](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[视频](https://youtu.be/IvfIP3E6-1Q) |
| [脉冲图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | |
| [雷达图](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [MAQSoftware 的圆环图（环形图）](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [视频](https://youtu.be/pDToHDFHnq8)|
| [MAQ 软件旋转图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007?src=office) |  |
| [桑基图](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[视频](https://youtu.be/WWP9wVUHGaA) |
| [滚动条](https://store.office.com/scroller-WA104381018.aspx) |[视频](https://youtu.be/uhRFQF2cGSY) |
| [SQLBI 的智能筛选器](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[视频](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[视频](https://youtu.be/0m3Vnvso9tY) |
| [Stream 关系图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772?tab=Overview) |  |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [热度地图表](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [转速计](https://store.office.com/tachometer-WA104380937.aspx?) |[视频](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [文本包装器](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [温度计](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [视频](https://youtu.be/SPX9mgrAdBc)|
| [时序分解](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [时间线切片器](https://store.office.com/timeline-slicer-WA104380786.aspx) |[视频](https://youtu.be/ozMtZ4_NZ10) |
| [飓风图](https://store.office.com/tornado-chart-WA104380768.aspx) |[视频](https://youtu.be/AQvd2FhRyCI) |
| [Klaus Birringer 终极方差图](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140?src=office) | |
| [终极瀑布图（免费）](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | |
| [VitaraCharts - MicroChart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381165) | |
| [Waffle 图](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[视频](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[视频](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>后续步骤
[自定义视觉对象开发者工具（预览版）入门](service-custom-visuals-getting-started-with-developer-tools.md)      
[YouTube 上的 Microsoft 自定义视觉对象播放列表](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI 中的可视化效果](power-bi-report-visualizations.md)  
[Power BI 中的自定义可视化效果](power-bi-custom-visuals.md)  
[将自定义视觉对象发布到 Microsoft AppSource](developer/office-store.md)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

