---
title: "有关 Power BI Embedded 的常见问题"
description: "浏览有关 Power BI Embedded 的常见问题和解答列表。"
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
ms.date: 01/15/2018
ms.author: asaxton
ms.openlocfilehash: aa4401a6c913d38e471f83b88fec351308d25870
ms.sourcegitcommit: 259d7689bcb1683d4d63a245a9b02becea072139
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>有关 Power BI Embedded 的常见问题

* 如果你有其他问题，请[尝试询问 Power BI 社区](http://community.powerbi.com/)。
* 仍有问题？ 请访问 [Power BI 支持页](https://powerbi.microsoft.com/support/)。

## <a name="general"></a>常规

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded 是什么?

通过 Microsoft Power BI Embedded，应用程序开发人员将令人震撼的完全交互式报表、仪表板和磁贴嵌入到应用程序中，无需花费时间和费用重新生成自己的数据可视化和控件。

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Power BI Embedded 的目标受众是谁？

生产自己的应用程序的开发人员和软件公司，称为独立软件供应商 (ISV)。

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded 与 Power BI 服务有什么不同？

Power BI Embedded 适用于以下 ISV 或开发人员：正在构建应用程序和希望将视觉对象嵌入到这些应用程序中，以帮助他们的客户做出决策，而无需从头开始构建分析解决方案。 嵌入式分析使业务用户能够访问业务数据并执行查询，以在应用程序中使用这些数据获得洞察力。

另一方面，Power BI 则是一种“软件即服务”分析解决方案，为组织提供最关键业务数据的单一视图。

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium 与 Power BI Embedded 之间的区别是什么？

对于需要一个完整的 BI 解决方案的企业而言，Power BI Premium 可以根据它们的需要调整容量，从而提供组织、合作伙伴、客户和供应商的单一视图。 Power BI Premium 可以帮助组织做出决策。 Power BI Premium 是一款 SaaS 产品，能够让用户通过 Power BI 门户、移动应用和内部开发的应用使用内容。

Power BI Embedded 适用于正在构建应用程序和希望将视觉对象嵌入到这些应用程序中的 ISV 或开发人员。 由于 Power BI Embedded 适用于应用程序开发人员，应用程序的客户可以使用存储在 Power BI Embedded 容量上的内容（包括组织内外的任何人），因此 Power BI Embedded 能帮助你的客户做出决策。 Power BI Embedded 容量内容不能通过“一键式发布到 Web”或“一键式发布到 SharePoint”进行共享，并且不支持 SSRS 报告。

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Microsoft 建议客户购买 Power BI Premium 还是 Power BI Embedded？

Microsoft 建议企业购买企业级自助服务云 BI 解决方案 Power BI Premium，建议 ISV 购买云助力的嵌入式分析组件 Power BI Embedded。 但是，客户可以购买哪种产品没有限制。

在某些情况下，ISV（通常是大型 ISV）可能希望使用 P SKU 在组织内获得预打包 Power BI 服务的额外好处，并嵌入它们的应用程序中。 当然，如果有些企业只是对构建业务线应用程序和嵌入分析感兴趣，并且对使用预打包 Power BI 服务不感兴趣，它们可能会决定在 Azure 中使用 A SKU。

### <a name="how-many-embed-tokens-can-i-create"></a>我可以创建多少嵌入令牌？

使用 PRO 许可证的嵌入令牌仅用于开发和开发测试，因此 Power BI 主帐户生成的嵌入令牌数量有限。 必须[购买容量](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical)才能嵌入生产环境。 购买容量后便不会限制生成嵌入令牌的数量。

### <a name="when-will-power-bi-embedded-be-available-in-azure"></a>Power BI Embedded 将何时在 Azure 中可用？

Power BI Embedded 现已可用。

## <a name="technical"></a>技术

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-em-skus-in-office-365"></a>Azure 中的 A SKU 与 Office 365 中的 EM SKU 之间有什么区别？

PowerBI.com 是一个企业解决方案，包括软件即服务产品中的许多功能，例如社交协作、电子邮件订阅等

Power BI Embedded 是一组 API，可供开发人员在平台即服务产品中创建嵌入式分析解决方案。 对于嵌入式分析方案，应使用 PowerBI.com 帮助 ISV 和开发人员管理他们的嵌入式分析解决方案内容和租户级设置。

以下是可能用于各项的部分差异列表。

|功能  |Power BI Embedded<br>(A SKU) |Power BI Premium 容量<br>(EM SKU)  |
|---------|---------|---------|
|从 Power BI 应用工作区嵌入项目     |Azure 容量 |Office 365 容量 |
|需要使用报表的 Power BI 许可证 |否  |是 |
|在嵌入应用程序中使用 Power BI 报表 |是  |是 |
|在 SharePoint 中使用 Power BI 报表 |否 |是 |
|在 Teams 中使用 Power BI 报表 |否 |是 |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI 现在提供用于嵌入的三个 SKU：A SKU、EM SKU 和 P SKU。 应该为我的方案购买哪一个？

|  |A SKU (Power BI Embedded)  |EM SKU (Power BI Premium)  |P SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|购买     |Azure 门户 |Office |Office |
|用例 |* 在自己的应用程序中嵌入内容 |* 在自己的应用程序中嵌入内容<br>* 与 PowerBI.com 外部的 Power BI（免费）用户共享内容，并嵌入其他 SaaS 应用程序（SharePoint，Teams） |* 在自己的应用程序中嵌入内容<br>* 与 PowerBI.com 外部的 Power BI（免费）用户共享内容，并嵌入其他 SaaS 应用程序（SharePoint，Teams）<br>* 通过 PowerBI.com 与 Power BI（免费）用户共享内容  |
|账单 |每小时 |每月 |每月 |
|承诺  |无承诺 |每年  |每月/每年 |
|区别 |全弹性 - 可以在 Azure 门户中或通过 API 纵向/横向扩展、暂停/恢复资源  |可用于在 SharePoint Online 和 Microsoft Teams 中嵌入内容 |合并嵌入在应用程序中并在相同的容量中使用 Power BI 服务 |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>在 Azure 中创建 PBIE 容量的先决条件是什么？

- 需要登录到组织目录（不支持 MSA 帐户）。
- 需要有 Power BI 租户，即目录中至少有一个用户注册了 Power BI。 
- 需要在组织目录中有 Azure 订阅。

### <a name="how-can-i-monitor-capacity-consumption"></a>如何监视容量消耗量？

在近期路线图上通过 Azure 监视。 作为 Azure 资源的 Power BI Embedded 包括监视将显示运行状况和使用情况的 KPI。

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>我的容量缩放是否会自动调整以适应应用消耗量？

虽然现在没有自动缩放，但是所有 API 都可以在任何时候缩放。

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>什么是 Power BI Embedded 的身份验证模型？

Power BI Embedded 将继续使用 Azure AD 对主用户（指定的 Power BI Pro 许可用户）进行身份验证，进而对 Power BI 中的应用程序进行身份验证。

应用程序用户的身份验证和授权将由 ISV 执行，ISV 可以为其应用程序实施自己的身份验证。

如果你已有 Azure AD 租户，则可以使用现有的目录，也可以创建新的 Azure AD 租户以确保你的嵌入式应用程序内容安全。

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded 与其他 Azure 服务有什么不同？

购买 Azure 中的 Power BI Embedded 之前，ISV/开发人员必须拥有 Power BI 帐户。 你的 Power BI Embedded 部署区域由你的 Power BI 帐户决定。 管理你在 Azure 中的 Power BI Embedded 资源，以便：

* 纵向/横向扩展
* 添加容量管理员
* 暂停/恢复服务

使用 PowerBI.com 将工作区分配/取消分配给 Power BI Embedded 容量。

### <a name="what-deploy-regions-are-supported"></a>支持什么部署区域？

澳大利亚东南部、巴西南部、加拿大中部、美国东部 2、印度西部、日本东部、美国中北部、欧洲北部、美国中南部、亚洲东南部、英国南部、欧洲西部、美国西部和美国西部 2。

## <a name="licensing"></a>许可

### <a name="how-do-i-purchase-power-bi-embedded"></a>如何购买 Power BI Embedded？

Power BI Embedded 是通过 Azure 提供的。

### <a name="how-power-bi-embedded-be-metered"></a>Power BI Embedded 如何计费？

Power BI Embedded 按小时计费。

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Power BI Embedded 的使用情况如何体现在我的账单上？

根据部署的节点类型，Power BI Embedded 按可预测的每小时费用收费。 请注意，只要资源处于活动状态，那么即使没有使用也需要付费。 要停止计费，则需要主动暂停资源。 可以通过 Azure 或 ARM API 完成暂停。

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>如果我已经购买了 Power BI Premium，现在我想要获得在 Azure 中使用 Power BI Embedded 的某些好处，会发生什么？

客户将继续支付任何现有的 Power BI Premium 购买费用，直到他们当前的协议期结束，然后可能会根据当时的需要切换 Power BI Premium 采购。

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>我是否仍需要购买 Power BI Premium 才能访问 Power BI Embedded？

不是，Power BI Embedded 包括基于 Azure 的容量，你需要部署并解决方案分发给客户。

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>谁需要 Power BI Embedded 的 Power BI Pro 许可证，为什么？

任何需要将报表添加到 Power BI 工作区的分析师、任何需要使用 REST API 的开发人员、任何需要管理 Power BI 租户和容量的租户管理员都需要 Power BI Pro 许可证。

由于 Power BI Embedded 允许使用 Power BI 门户来管理和验证嵌入式内容，因此需要使用 Power BI Pro 许可证对 PowerBI.com 内部的应用进行身份验证，这样才能访问相应存储库中的报表。

### <a name="can-i-get-started-for-free"></a>开始我可以免费使用吗？

可以，你可以对 Power BI Embedded 使用你的 [Azure 信用额度](https://azure.microsoft.com/free/)

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>可以在 Azure 中获得 Power BI Embedded 的试用体验吗？

由于 Power BI Embedded 是 Azure 的一部分，可以利用[注册 Azure 时获得的 200 美元信用额度](https://azure.microsoft.com/free/)使用该服务。

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Power BI Embedded 的采购承诺是什么？ 

客户可以按小时为单位更改使用情况。 Power BI Embedded 服务没有月承诺或年承诺。

### <a name="where-is-power-bi-embedded-available-us-government-germany-china-what-is-the-timing"></a>哪里提供 Power BI Premium？ 美国政府？ 德国？ 中国？ 什么是计时？

Power BI Embedded 将在 GA 的 Azure 商业云中提供。  将来会添加主权云可用性。

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Power BI Embedded 是否适合非营利组织和教育机构？

非营利组织和教育机构可以购买 Azure。 Azure 对于这些类型的客户没有特殊定价。

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)
