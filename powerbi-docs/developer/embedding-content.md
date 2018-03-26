---
title: 如何嵌入 Power BI 仪表板、报表和磁贴
description: 了解在应用程序中嵌入 Power BI 内容所需的步骤。
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/12/2018
ms.author: maghan
ms.openlocfilehash: 014601a4c85be53d6fd06a455d04e5ee1f8daf2d
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="embed-your-power-bi-dashboards-reports-and-tiles"></a>嵌入 Power BI 仪表板、报表和磁贴

了解在应用程序中嵌入 Power BI 内容所需的步骤。

Microsoft [发布了 Power BI Premium](https://powerbi.microsoft.com/blog/microsoft-accelerates-modern-bi-adoption-with-power-bi-premium/)，这是基于容量的全新许可模型，让用户可以更灵活地访问、共享和分发内容。 产品/服务还为 Power BI 服务提高其他可伸缩性和性能。 还发布了 Power BI Embedded，可方便用户在 Microsoft Azure 中创建容量。 Power BI Embedded 主要面向应用和客户。 

本文将介绍如何为组织和客户嵌入 Power BI 内容。 两种方案的步骤相似。 如果是专为客户嵌入内容的步骤，则会有标注。

为了实现此操作，你的应用程序需要完成以下几个步骤。 我们会完成所需的步骤，方便你在应用程序中创建和使用嵌入内容。

> [!NOTE]
> Power BI API 仍以组的形式引用应用工作区。 对组的任何引用都意味着正使用应用工作区工作。

## <a name="step-1-setup-your-embedded-analytics-development-environment"></a>步骤 1：设置嵌入式分析开发环境

在开始将仪表板和报表嵌入到应用程序中之前，需要确保环境已设置为允许嵌入。 在设置过程中，需要执行以下操作。

* [确保具有 Azure Active Directory 租户](embedding-content.md#azureadtenant)
* [创建 Power BI Pro 帐户](embedding-content.md#proaccount)
* [注册 Azure Active Directory 应用程序和权限](embedding-content.md#appreg)

> [!NOTE]
> Power BI 容量对应用开发毫无影响。 应用程序的开发人员将需要具有 Power BI Pro 许可证。

### <a name="azureadtenant"></a>Azure Active Directory 租户

需要一个 Azure Active Directory (Azure AD) 租户才可嵌入 Power BI 中的项目。 此租户必须至少有一个 Power BI Pro 用户。 还需要在租户内定义 Azure AD 应用。 可以使用现有 Azure AD 租户，也可创建一个专用于嵌入的新租户。

若要为客户嵌入内容，需要确定要使用的租户设置。

* 使用现有公司 Power BI 租户？
* 为应用程序使用单独的租户？
* 为每个客户使用单独的租户？

如果不想使用现有租户，则可以决定为应用程序或每个客户创建一个新租户，请参阅[创建 Azure Active Directory 租户](create-an-azure-active-directory-tenant.md)或[如何获取 Azure Active Directory 租户](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant)。

### <a name="proaccount"></a>创建 Power BI Pro 用户帐户

只需要一个 Power BI Pro 帐户即可嵌入内容。 但是，你可能想要有几个对各项目具有特定访问权限的不同用户。 下面介绍租户中可能需要考虑的用户。

租户中将需要存在以下帐户，并需要向其分配 Power BI Pro 许可证。 需要 Power BI Pro 许可证才能与 Power BI 中的应用工作区配合使用。

#### <a name="an-organizationtenant-admin-user"></a>组织/租户管理员用户

若要为客户嵌入内容，建议应用不要使用组织/租户全局管理员用户作为帐户。 这是为了最大限度地减少应用帐户在租户中拥有的访问权限。 建议将管理员用户设置为出于嵌入内容目的而创建的所有应用工作区的管理员。

#### <a name="accounts-for-analysts-that-will-create-content"></a>将创建内容的分析师帐户

你可能有多个为 Power BI 创建内容的用户。 对于创建内容并将内容部署到 Power BI 的每个分析师，都将需要一个相应的 Power BI Pro 帐户。

#### <a name="an-application-master-user-account-for-embedding-for-your-customers"></a>用于为客户嵌入内容的应用主用户帐户

主帐户是为客户嵌入内容时，应用将使用的帐户。 此方案通常适用于 ISV 应用。 主帐户实际上是组织中唯一需要的帐户。 此外可用作管理员和分析师帐户，但不建议这样做。 应用程序的后端将存储此帐户的凭据，并将其用于获取与 Power BI API 一起使用的 Azure AD 身份验证令牌。 此帐户可用于生成应用要对客户使用的嵌入令牌。

主帐户只是拥有用于应用的 Power BI Pro 许可证的常规用户。 此帐户必须是用于嵌入内容的应用工作区的管理员。

### <a name="appreg"></a>应用注册和权限

必须向 Azure AD 注册应用，才能执行 REST API 调用。 有关详细信息，请参阅[注册 Azure AD 应用以便嵌入 Power BI 内容](register-app.md)。

### <a name="create-app-workspaces"></a>创建应用工作区

若要为客户嵌入仪表板和报表，必须将这些仪表板和报表置于应用工作区中。 上面提到的主帐户必须是应用工作区的管理员。

[!INCLUDE [powerbi-service-create-app-workspace](../includes/powerbi-service-create-app-workspace.md)]

> [!NOTE]
> 非管理员用户最多只能创建 250 个 应用工作区。 若要创建更多工作区，需要使用租户管理员帐户。
>

### <a name="create-and-upload-your-reports"></a>创建并上传报表

可使用 Power BI Desktop 创建报表和数据集，然后将这些报表发布到应用工作区。 发布报表的最终用户需要拥有 Power BI Pro 许可证才可发布到应用工作区。

## <a name="step-2-embed-your-content"></a>步骤 2：嵌入内容

在应用程序内，需要对 Power BI 进行身份验证。 若要为客户嵌入内容，将在应用中存储主帐户的凭据。 有关详细信息，请参阅[对用户进行身份验证并获取 Power BI 应用的 Azure AD 访问令牌](get-azuread-access-token.md)。

通过身份验证后，在应用中使用 Power BI REST API 和 JavaScript API，将仪表板和报表嵌入应用中。 

若要为组织嵌入内容，请参阅以下演练：

* [将仪表板集成到应用](integrate-dashboard.md)
* [将磁贴集成到应用](integrate-tile.md)
* [将报表集成到应用](integrate-report.md)

若要为客户嵌入内容（通常适合 ISV），请参阅以下演练：

* [将仪表板、磁贴或报表集成到应用中](embed-sample-for-customers.md)

为客户嵌入内容时，必须使用嵌入令牌。 有关详细信息，请参阅 [GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx)。

## <a name="step-3-promote-your-solution-to-production"></a>步骤 3：将解决方案提升到生产环境

迁移到生产环境还需要额外执行几步。

### <a name="embedding-for-your-organization"></a>为组织嵌入内容

若要为组织嵌入内容，只需让人们知道如何转到应用即可。 

免费用户可以使用从应用工作区（组）嵌入的内容，前提是相应工作区受容量支持。 将免费用户列为应用工作区（组）的成员，否则将看到 401 未授权错误。 下表列出了 Office 365 中可用的 Power BI Premium SKU。

| 容量节点 | 总核心数<br/>（后端 + 前端） | 后端核心数 | 前端核心数 | DirectQuery/实时连接限制 | 高峰时间的最大显示页数 |
| --- | --- | --- | --- | --- | --- |
| EM3 |4 个虚拟核心 |2 个核心，10GB RAM |2 个核心 | |601-1,200 |
| P1 |8 个虚拟核心 |4 核，25 GB RAM |4 核 |每秒 30 个 |1,201-2,400 |
| P2 |16 个虚拟核心 |8 核，50 GB RAM |8 核 |每秒 60 个 |2,401-4,800 |
| P3 |32 个虚拟核心 |16 核，100 GB RAM |16 核 |每秒 120 个 |4,801-9600 |

> [!NOTE]
> 在租户中，只有作为全局管理员或帐单管理员才能购买 Power BI Premium。 有关如何购买 Power BI Premium 的信息，请参阅[如何购买 Power BI Premium](../service-admin-premium-purchase.md)。

### <a name="embedding-for-your-customers"></a>为客户嵌入内容

若要为客户嵌入内容，请执行以下操作。

* 如果使用单独的租户进行开发，必须确保应用工作区以及仪表板和报表可用于生产环境。 请务必在 Azure AD 中为生产租户创建应用，并按照第 1 步所述分配适当应用权限。
* 购买符合需求的容量。 请参阅下表，了解可能需要的 Power BI Embedded 容量 SKU。 有关详细信息，请参阅[嵌入式分析容量规划白皮书](https://aka.ms/pbiewhitepaper)。 准备购买时，可以在 [Microsoft Azure 门户](https://portal.azure.com)中完成购买。 若要详细了解如何创建 Power BI Embedded 容量，请参阅[在 Azure 门户中创建 Power BI Embedded 容量](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity)。

> [!IMPORTANT]
> 由于嵌入令牌仅用于开发测试，因此 Power BI 主帐户生成的嵌入令牌数量有限。 对于嵌入生产方案，[必须购买容量](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical)。 购买容量后便不会限制嵌入令牌生成。

| 容量节点 | 总核心数<br/>（后端 + 前端） | 后端核心数 | 前端核心数 | DirectQuery/实时连接限制 | 高峰时间的最大显示页数 |
| --- | --- | --- | --- | --- | --- |
| A1 |1 个虚拟核心 |0.5 个核心，3GB RAM |0.5 个核心 | 每秒 5 个 |1-300 |
| A2 |2 个虚拟核心 |1 个核心，5GB RAM |单核 | 每秒 10 个 |301-600 |
| A3 |4 个虚拟核心 |2 个核心，10GB RAM |2 个核心 | 每秒 15 个 |601-1,200 |
| A4 |8 个虚拟核心 |4 核，25 GB RAM |4 核 |每秒 30 个 |1,201-2,400 |
| A5 |16 个虚拟核心 |8 核，50 GB RAM |8 核 |每秒 60 个 |2,401-4,800 |
| A6 |32 个虚拟核心 |16 核，100 GB RAM |16 核 |每秒 120 个 |4,801-9600 |

* 编辑应用工作区，并在“高级”下为它分配容量。

    ![为应用工作区分配容量](media/embedding-content/powerbi-embedded-premium-capacity.png)

* 将更新后的应用部署到生产环境，并开始嵌入 Power BI 仪表板和报表。



## <a name="admin-settings"></a>管理员设置

全局管理员或 Power BI 服务管理员可以为租户启用或禁用 REST API。 Power BI 管理员可以为整个组织或各个安全组设定此设置。 默认情况下，为整个组织启用此功能。 此操作通过 [Power BI 管理门户](../service-admin-portal.md)完成。

## <a name="next-steps"></a>后续步骤

[使用 Power BI 嵌入](embedding.md)  
[如何将 Power BI Embedded 工作区集合内容迁移到 Power BI](migrate-from-powerbi-embedded.md)  
[什么是 Power BI Premium？](../service-premium.md)  
[如何购买 Power BI Premium](../service-admin-premium-purchase.md)  
[JavaScript API Git 存储库](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git 存储库](https://github.com/Microsoft/PowerBI-CSharp)  
[JavaScript 嵌入示例](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[嵌入式分析容量规划白皮书](https://aka.ms/pbiewhitepaper)  
[Power BI Premium 白皮书](https://aka.ms/pbipremiumwhitepaper)  

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

