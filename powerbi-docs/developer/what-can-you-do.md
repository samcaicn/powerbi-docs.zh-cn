---
title: "开发人员可以使用 Power BI 做什么？"
description: "Power BI 为开发人员提供了大量选项。 此范围涉及从嵌入到自定义视觉对象到流式处理数据集。"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 07/20/2017
ms.author: maghan
ms.openlocfilehash: b310562ac31694f398a659018743b8fa7aa46e35
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="what-can-developers-do-with-power-bi"></a>开发人员可以使用 Power BI 做什么？
Power BI 为开发人员提供了大量选项。 此范围涉及从嵌入到自定义视觉对象到流式处理数据集。

## <a name="embedding"></a>嵌入
Azure 中的 Power BI 服务和 Power BI Embedded 一起提供单个 API，用于嵌入仪表板和报表。 这意味着，在嵌入内容时，将拥有一个 API 外围、一组一致的功能以及对最新 Power BI 功能（如仪表板、网关和应用工作区）的访问权限。 有关详细信息，请参阅[使用 Power BI 嵌入](embedding.md)。

![](media/what-can-you-do/powerbi-embed-sample.png)

## <a name="custom-visuals"></a>自定义视觉对象
可以通过自定义视觉对象创建自己的视觉对象，以便在 Power BI 报表中使用。 使用 TypeScript 编写自定义视觉对象，TypeScript 是 JavaScript 的超集，支持某些高级功能和提前访问 ES6/ES7 功能。 视觉对象样式使用层叠样式表 (css) 进行处理。 为方便起见，我们使用 Less 预编译器，该编译器支持某些高级功能，例如嵌套、变量、mixins、条件、循环等。如果不想使用其中任何一种功能，可以只在 less 文件中编写普通 css。

有关如何开发和发布自定义视觉对象的详细信息，请参阅[将自定义视觉对象发布到 Office 应用商店](office-store.md)。

![](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>将数据推送到 Power BI
可以使用 Power BI API 将数据推送到数据集。 这样可以将行添加到数据集内的表。 新数据随后可以在仪表板的磁贴中以及报表中的视觉对象内反映出来。

有关详细信息，请参阅[将数据推送到仪表板](walkthrough-push-data.md)

## <a name="next-steps"></a>后续步骤
[使用 Power BI 嵌入](embedding.md)  
[如何将 Power BI Embedded 工作区集合内容迁移到 Power BI](migrate-from-powerbi-embedded.md)  
[JavaScript API Git 存储库](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git 存储库](https://github.com/Microsoft/PowerBI-CSharp)  
[将自定义视觉对象发布到 Office 应用商店](office-store.md)  
[Power BI 视觉对象 Git 存储库](https://github.com/Microsoft/PowerBI-visuals)  
[JavaScript 嵌入示例](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Power BI Premium 白皮书](https://aka.ms/pbipremiumwhitepaper)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

