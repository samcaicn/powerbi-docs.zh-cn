---
title: 开发人员可以使用 Power BI 做什么？
description: Power BI 为开发人员提供了大量选项。 此范围涉及从嵌入到自定义视觉对象到流式处理数据集。
services: powerbi
author: markingmyname
ms.author: maghan
ms.date: 05/03/2018
ms.topic: overview
ms.service: powerbi
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 473052ee652c1fd6e68294efdbd7334cbb2df714
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810957"
---
# <a name="what-can-developers-do-with-power-bi"></a>开发人员可以使用 Power BI 做什么？

开发人员有不同选项来尝试将 Power BI 内容包含在应用程序中。 这些选项包括“使用 Power BI 嵌入”、“自定义视觉对象”和“将数据推送到 Power BI”。

## <a name="embedding"></a>嵌入
Azure (PaaS) 中的 Power BI 服务 (SaaS) 和 Power BI 嵌入式服务具有用于嵌入仪表板和报表的 API。 这意味着，在嵌入内容时，将拥有一组功能以及对最新 Power BI 功能（如仪表板、网关和应用工作区）的访问权限。

![PBIE 示例](media/what-can-you-do/what-can-you-do-01.png)

## <a name="develop-custom-visuals"></a>开发自定义视觉对象
可以通过自定义视觉对象创建自己的视觉对象，以便在 Power BI 报表中使用。 自定义视觉对象将写入 TypeScript（即 JavaScript 的超集）。 TypeScript 支持某些高级功能并提前获取 ES6/ES7 功能。 视觉对象样式使用层叠样式表 (css) 进行处理。 为方便起见，我们使用 Less 预编译器，该编译器支持某些高级功能，例如嵌套、变量、条件、循环等。如果不想使用其中任何一种功能，可以只在 less 文件中编写普通 css。

![CV 示例](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>将数据推送到 Power BI
可以使用 Power BI API 将数据推送到数据集。 这样可以将行添加到数据集内的表。 新数据随后可以在仪表板的磁贴中以及报表中的视觉对象内反映出来。

![推送数据示例](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>后续步骤
[使用 Power BI 嵌入](embedding.md)  
[将自定义视觉对象发布到 Office 应用商店](office-store.md)  
[将数据推送到仪表板](walkthrough-push-data.md)
