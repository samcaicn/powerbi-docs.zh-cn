---
title: "如何将 Power BI Embedded 工作区集合内容迁移到 Power BI"
description: "了解如何从 Power BI Embedded 迁移到 Power BI 服务，并利用这些进展在应用中进行嵌入。"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 07/21/2017
ms.author: asaxton
ms.openlocfilehash: 430f1d1a49e510bac66c448b2dceaad1f2537073
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-migrate-power-bi-embedded-workspace-collection-content-to-power-bi"></a>如何将 Power BI Embedded 工作区集合内容迁移到 Power BI
了解如何从 Power BI Embedded 迁移到 Power BI 服务，并利用这些进展在应用中进行嵌入。

Microsoft 最近[发布了 Power BI Premium](https://powerbi.microsoft.com/blog/microsoft-accelerates-modern-bi-adoption-with-power-bi-premium/)，这是一个基于容量的新许可模型，可提高用户访问、共享和分发内容方式的灵活性。 产品/服务还为 Power BI 服务提高其他可伸缩性和性能。

通过引入 Power BI Premium，Power BI Embedded 和 Power BI 服务开始进行融合以推动在应用中嵌入 Power BI 内容的进展。 这意味着，在嵌入内容时，将拥有一个 API 外围、一组一致的功能以及对最新 Power BI 功能（如仪表板、网关和应用工作区）的访问权限。 展望未来，你将能够从使用 Power BI Desktop 开始，移动到通过 Power BI Premium 实现的部署，这将在 2017 年第二个季度末公开发布。

当前 Power BI Embedded 服务将在聚合产品/服务公开发布后的一段有限时间内继续可用：企业协议客户可在其现有协议到期前使用该服务；通过直接渠道或 CSP 渠道获取 Power BI Embedded 的客户可在 Power BI Premium 公开发布一年内享受该服务。  本文将在以下方面提供指导：如何从 Azure 服务迁移到 Power BI 服务，以及应用程序中会进行哪些更改。

> [!IMPORTANT]
> 虽然 Power BI 服务上的迁移具有依赖项，但在使用**嵌入令牌**时，Power BI 上没有为应用程序的用户提供依赖项。 用户不需要注册 Power BI 来查看应用程序中嵌入的内容。 可使用此嵌入方法为非 Power BI 用户提供服务。
> 
> 

![](media/migrate-from-powerbi-embedded/powerbi-embed-flow.png)

## <a name="prepare-for-the-migration"></a>迁移准备
需要完成一些准备工作才能从 Power BI Embedded Azure 服务迁移到 Power BI 服务。 你将需要一个可用的租户，以及具有 Power BI Pro 许可证的用户。

1. 请确保你有权访问 Azure Active Directory (Azure AD) 租户。
   
    你将需要确定要使用的租户设置。
   
   * 使用现有公司 Power BI 租户？
   * 为应用程序使用单独的租户？
   * 为每个客户使用单独的租户？
     
     如果决定为应用程序或每个客户创建一个新租户，请参阅[创建 Azure Active Directory 租户](create-an-azure-active-directory-tenant.md)或[如何获取 Azure Active Directory 租户](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant)。
2. 在此新租户中创建一个用户，作为应用程序“主”帐户。 该帐户需要注册 Power BI，并获得 Power BI Pro 许可证。

## <a name="accounts-within-azure-ad"></a>Azure AD 中的帐户
租户中必须有以下帐户。

> [!NOTE]
> 这些帐户需要具有 Power BI Pro 许可证才能使用应用工作区。
> 
> 

1. 租户管理员用户。
   
    建议此用户成为为实现嵌入而创建的所有应用工作区的成员。
2. 将创建内容的分析师帐户。
   
    应根据需要将这些用户分配到应用工作区。
3. 应用程序主用户帐户或服务帐户。
   
    应用程序后端将存储此帐户的凭据，并将其用于获取与 Power BI REST API 一起使用的 Azure AD 身份验证令牌。 此帐户将用于生成应用程序的嵌入令牌。 此帐户还必须是为实现嵌入而创建的应用工作区的管理员。
   
   > [!NOTE]
   > 这只是组织中用于嵌入用途的常规用户帐户。
   > 
   > 

## <a name="app-registration-and-permissions"></a>应用注册和权限
你将需要在 Azure AD 中注册应用程序，并授予某些权限。

### <a name="register-an-application"></a>注册应用程序
必须向 Azure AD 注册应用，才能执行 REST API 调用。 除了转到 Power BI 应用注册页，这还包括转到 Azure 门户来应用其他配置。 有关详细信息，请参阅[注册 Azure AD 应用以便嵌入 Power BI 内容](register-app.md)。

应使用应用主帐户来注册应用。

## <a name="create-app-workspaces-required"></a>创建应用工作区（必需）
如果应用程序服务多个客户，则可以利用应用工作区以更好地进行隔离。 将在客户之间隔离仪表板和报表。 然后可以使用每个应用工作区的 Power BI 帐户以进一步隔离客户之间的应用程序体验。

> [!IMPORTANT]
> 不能使用个人工作区来利用嵌入到非 Power BI 用户功能。
> 
> 

你将需要具有 Pro 许可证的用户才能在 Power BI 中创建应用工作区。 默认情况下，创建应用工作区的 Power BI 用户将成为该工作区的管理员。

> [!NOTE]
> 应用主帐户必须是工作区的管理员。
> 
> 

## <a name="content-migration"></a>内容迁移
将内容从工作区集合迁移到 Power BI 服务可与当前解决方案同步进行，并且不需要停机。

可使用“迁移工具”帮助将内容从 Power BI Embedded 复制到 Power BI 服务。 尤其是有大量内容时。 有关详细信息，请参阅 [Power BI Embedded 迁移工具](migrate-tool.md)。

内容迁移主要依赖两个 API。

1. 下载 PBIX - 此 API 可用于下载 2016 年 10 月之后上传到 Power BI 的 PBIX 文件。
2. 导入 PBIX - 此 API 可用于将任何 PBIX 上传到 Power BI。

有关相关的代码片段，请参阅[用于从 Power BI Embedded 迁移内容的代码片段](migrate-code-snippets.md)。

### <a name="report-types"></a>报表类型
有多种类型的报表，每种报表的迁移流程都稍有不同。

#### <a name="cached-dataset--report"></a>缓存数据集和报表
缓存数据集是指已导入数据的 PBIX 文件，而不是采用实时连接或 DirectQuery 连接。

流

1. 从 PaaS 工作区调用下载 PBIX API。
2. 保存 PBIX。
3. 将导入 PBIX 调用到 SaaS 工作区。

#### <a name="directquery-dataset--report"></a>DirectQuery 数据集和报表
流

1. 调用 GET https://api.powerbi.com/v1.0/collections/{collection_id}/workspaces/{wid}/datasets/{dataset_id}/Default.GetBoundGatewayDataSources 并保存收到的连接字符串。
2. 从 PaaS 工作区调用下载 PBIX API。
3. 保存 PBIX。
4. 将导入 PBIX 调用到 SaaS 工作区。
5. 通过调用更新连接字符串 - POST https://api.powerbi.com/v1.0/myorg/datasets/{dataset_id}/Default.SetAllConnections
6. 通过调用获取 GW ID 和数据源 ID - GET https://api.powerbi.com/v1.0/myorg/datasets/{dataset_id}/Default.GetBoundGatewayDataSources
7. 通过调用更新用户凭据 - PATCH https://api.powerbi.com/v1.0/myorg/gateways/{gateway_id}/datasources/{datasource_id}

#### <a name="old-dataset--reports"></a>旧数据集和报表
这些数据集/报表是在 2016 年 10 月之前创建的。 下载 PBIX 不支持 2016 年 10 月之前上传的 PBIX

流

1. 从开发环境中获取 PBIX（内部源代码管理）。
2. 将导入 PBIX 调用到 SaaS 工作区。

#### <a name="push-dataset--report"></a>推送数据集和报表
下载 PBIX 不支持推送 API 数据集。 无法将推送 API 数据集从 PaaS 移植到 SaaS。

流

1. 使用数据集 JSON 调用“创建数据集” API，在 SaaS 工作区中创建数据集。
2. 为创建的数据集重新生成报表*。

通过尝试以下方法，可使用一些解决方法将推送 API 报表从 PaaS 迁移到 SaaS。

1. 将一些虚 PBIX 上传到 PaaS 工作区。
2. 克隆推送 API 报表，并将其绑定到步骤 1 中的虚 PBIX。
3. 使用虚 PBIX 下载推送 API 报表。
4. 将虚 PBIX 上传到 SaaS 工作区。
5. 在 SaaS 工作区中创建推送数据集。
6. 将报表重新绑定到推送 API 数据集。

## <a name="create-and-upload-new-reports"></a>创建并上传新报表
除了从 Power BI Embedded Azure 服务迁移的内容外，还可使用 Power BI Desktop 创建报表和数据集，然后将这些报表发布到应用工作区。 发布报表的最终用户需要拥有 Power BI Pro 许可证才可发布到应用工作区。

## <a name="rebuild-your-application"></a>重新生成应用程序
1. 需要修改应用程序以使用 Power BI REST API 和 powerbi.com 中的报表位置。
2. 使用应用程序的*主*帐户重新生成 AuthN/AuthZ 身份验证。 可以使用[嵌入令牌](https://msdn.microsoft.com/library/mt784614.aspx)来允许此用户代表其他用户执行操作。
3. 将报表从 powerbi.com 嵌入到应用程序。

## <a name="map-your-users-to-a-power-bi-user"></a>将用户映射到 Power BI 用户
在应用程序中，将在应用程序中管理的用户映射到应用程序的*主* Power BI 凭据。 此 Power BI *主*帐户的凭据将存储在应用程序中，并且可用于创建嵌入令牌。

## <a name="what-to-do-when-you-are-ready-for-production"></a>做好生产准备时应执行的操作
准备好迁移到生产环境时，需要执行以下操作。

* 如果要使用单独的租户进行开发，则需要确保应用工作区以及仪表板和报表在生产环境中可用。 还需要确保在 Azure AD 中为生产租户创建了应用程序，并按照步骤 1 中所述分配了适当的应用权限。
* 购买符合需求的容量。 使用[嵌入式分析容量规划白皮书](https://aka.ms/pbiewhitepaper)来帮助了解可能需要的内容。 准备好购买时，可在 [Office 365 管理中心](https://portal.office.com/adminportal/home#/catalog)内执行此操作。
  
  > [AZURE.INFORMATION] 有关如何购买 Power BI Premium 的信息，请参阅[如何购买 Power BI Premium](../service-admin-premium-purchase.md)。
  > 
  > 
* 编辑应用工作区，并在“高级”下将其分配给 Premium 容量。
  
    ![](media/migrate-from-powerbi-embedded/powerbi-embedded-premium-capacity.png)
* 将更新的应用程序部署到生产环境，并开始从 Power BI 服务嵌入报表。

## <a name="after-migration"></a>迁移后
应在 Azure 中执行一些清理操作。

* 删除 Azure Power BI Embedded 服务中部署的解决方案的所有工作区。
* 删除 Azure 中存在的任何工作区集合。

## <a name="next-steps"></a>后续步骤
[使用 Power BI 嵌入](embedding.md)  
[Power BI Embedded 迁移工具](migrate-tool.md)  
[用于从 Power BI Embedded 迁移内容的代码片段](migrate-code-snippets.md)  
[如何嵌入 Power BI 仪表板、报表和磁贴](embedding-content.md)  
[什么是 Power BI Premium？](../service-premium.md)  
[JavaScript API Git 存储库](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git 存储库](https://github.com/Microsoft/PowerBI-CSharp)  
[JavaScript 嵌入示例](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[嵌入式分析容量规划白皮书](https://aka.ms/pbiewhitepaper)  
[Power BI Premium 白皮书](https://aka.ms/pbipremiumwhitepaper)  

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

