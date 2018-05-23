---
title: 使用 Power BI 嵌入
description: Power BI 提供用于将仪表板和报表嵌入应用的 API。
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/30/2017
ms.author: maghan
ms.openlocfilehash: 043bd43ac6d0abcd4cc4bae54f4ee57cc4ef2a41
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="embedding-with-power-bi"></a>使用 Power BI 嵌入
Power BI 提供用于将仪表板和报表嵌入应用的 API。 在嵌入内容时，Power BI API 提供一组固定不变的功能，并提供对最新 Power BI 功能（如仪表板、网关和应用工作区）的访问权限。

## <a name="a-single-api"></a>单个 API
嵌入 Power BI 内容时，有两个主要方案。  为组织中的用户（拥有 Power BI 许可证）嵌入内容；为用户和客户嵌入内容且不要求他们拥有 Power BI 许可证。 两种方案都可使用 Power BI REST API。 

对于没有 Power BI 许可证的客户和用户，可以使用同一 API 为组织或客户提供服务，将仪表板和报表嵌入自定义应用程序中。 客户会看到该应用程序管理的数据。 对于组织中的 Power BI 用户，他们可以直接在 Power BI 中或者在嵌入式应用程序的上下文中使用附加的选项来查看他们自己的数据。 可以充分利用 JavaScript 和 REST API 的功能以满足你的嵌入需要。

若要查看有关嵌入工作原理的示例，请参阅 [JavaScript 嵌入示例](https://microsoft.github.io/PowerBI-JavaScript/demo/)。

## <a name="embedding-for-your-organization"></a>为组织嵌入内容
通过为组织嵌入内容，可以扩展 Power BI 服务。 应用程序的用户在查看其内容时必须登录到 Power BI 服务。 组织中的用户登录后，只能访问他们拥有的，或者在 Power BI 服务中与之共享的仪表板和报表。 

为组织嵌入内容的示例包括内部 Web 应用、SharePoint Online Web 部件和 Microsoft Teams 集成。

若要为组织嵌入内容，请参阅以下演练：

* [将仪表板集成到应用](integrate-dashboard.md)
* [将磁贴集成到应用](integrate-tile.md)
* [将报表集成到应用](integrate-report.md)

为 Power BI 用户进行嵌入时，通过 [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) 可使用编辑和保存等自助服务功能。

## <a name="embedding-for-your-customers"></a>为客户嵌入内容
通过为客户嵌入内容，可为没有 Power BI 帐户的用户嵌入仪表板和报表。 客户无需了解有关 Power BI 的一切。 至少需要有一个 Power BI Pro 帐户才能创建嵌入式应用程序。 Power BI Pro 帐户充当应用程序的主帐户。 将其视为代理帐户。 借助 Power BI Pro 帐户，还可以生成嵌入令牌，用于访问应用程序拥有/管理的 Power BI 服务中的仪表板和报表。 

*为客户嵌入内容的示例是，出售给其他公司的 ISV 应用。*

![为客户嵌入内容的嵌入流](media/embedding/powerbi-embed-flow.png)

若要嵌入仪表板、报表和磁贴，使用的 API 与为组织嵌入内容时使用的 API 相同。

> [!IMPORTANT]
> 尽管嵌入操作依赖于 Power BI 服务，但在为客户嵌入内容时并不依赖于 Power BI Pro。 用户不需要注册 Power BI 来查看应用程序中嵌入的内容。
> 
> 

准备迁移到生产环境时，必须为应用工作区分配容量。 Microsoft Azure 中的 Power BI Embedded 提供对应用使用的容量。

有关嵌入方法的详细信息，请参阅[如何嵌入 Power BI 仪表板、报表和磁贴](embedding-content.md)。

如果使用的是 Power BI 工作区集合 Azure 服务，请参阅[从 Power BI 工作区集合 Azure 服务迁移内容](migrate-from-powerbi-embedded.md)，了解如何迁移内容。

## <a name="next-steps"></a>后续步骤
[如何嵌入 Power BI 仪表板、报表和磁贴](embedding-content.md)  
[如何将 Power BI Embedded 工作区集合内容迁移到 Power BI](migrate-from-powerbi-embedded.md)  
[什么是 Power BI Premium？](../service-premium.md)  
[JavaScript API Git 存储库](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git 存储库](https://github.com/Microsoft/PowerBI-CSharp)  
[JavaScript 嵌入示例](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[嵌入式分析容量规划白皮书](https://aka.ms/pbiewhitepaper)  
[Power BI Premium 白皮书](https://aka.ms/pbipremiumwhitepaper)  

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

