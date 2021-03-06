---
title: Power BI 中的常见问题
description: 浏览有关 Power BI 服务、Power BI Desktop 和 Power BI 移动应用的常见问题和解答列表。
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: a234a05c028ab71e30377965ae78b56451f5bca4
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46566294"
---
# <a name="frequently-asked-questions-about-power-bi"></a>有关 Power BI 的常见问题
* 如果你有其他问题，请[尝试询问 Power BI 社区](http://community.powerbi.com/)。
* 仍有问题？ 请访问 [Power BI 支持页](https://powerbi.microsoft.com/support/)。

## <a name="what-is-microsoft-power-bi"></a>什么是 Microsoft Power BI？
Power BI 是一种基于云的业务分析服务，使任何人能够用更快的速度、更高的效率以及在更深入了解的情况下，可视化和分析数据。 它通过生动展示数据的易用仪表板、交互式报表和引人注目的可视化效果，让用户看到更广泛的数据。 阅读有关[什么是 Power BI](../power-bi-overview.md) 的详细信息。

## <a name="whats-the-difference-between-power-bi-pro-and-power-bi-premium"></a>Power BI Pro 与 Power BI Premium 之间的区别是什么？
Power BI Pro 是单个许可证，允许访问 Power BI 服务中的所有内容和功能，包括共享内容以及与其他 Pro 用户协作的功能。 只有 Pro 用户可以将内容发布到应用工作区，使用这些内容，共享仪表板并订阅仪表板及报表。 

Premium 提供专用容量，在 Power BI 中具有更高的一致性并支持更大的数据量。 对于个人用户，Premium 还允许 Pro 用户广泛分发内容，且不要求查看内容的每个收件人用户都提供许可证。

## <a name="how-much-does-power-bi-cost"></a>Power BI 价格是多少？
Power BI Desktop 是免费的。 Power BI Pro 还可提供 60 天的免费试用版。 有关定价，请参阅 [Power BI 定价](https://powerbi.microsoft.com/pricing)。

## <a name="what-if-i-have-questions-about-power-bi-premium"></a>如果有关于 Power BI Premium 的问题，应该怎么办？
与 Power BI Premium 相关的问题，请参阅 [Power BI Premium 常见问题解答](../service-premium-faq.md)。

## <a name="how-do-i-find-out-who-in-my-organization-has-a-power-bi-account"></a>如何查明组织中谁具有 Power BI 帐户？
可查看 Power BI 的 Azure Active Directory 集成应用程序报表，从而发现组织中的活跃用户。 Azure AD 报表并不会指出每个用户拥有的许可证类型。 它只报告哪些用户已登录到 Power BI 及其登录时间。 有关详细信息，请参阅[查找已登录的 Power BI 用户](../service-admin-access-usage.md)。

## <a name="what-is-power-bi-desktop"></a>什么是 Power BI Desktop？
Power BI Desktop 是一款免费的桌面应用程序，可将其直接安装在自己的计算机上。 Power BI Desktop 通过提供具有高度交互性的可视化效果的高级数据浏览、定型、建模和报告创建功能，紧密配合 Power BI 服务进行工作。 你可以将工作保存到文件，并将数据和报表直接发布到 Power BI 站点，以与其他人共享。 阅读有关[什么是 Power BI Desktop](../desktop-what-is-desktop.md) 的详细信息。

## <a name="what-do-i-need-to-use-power-bi"></a>使用 Power BI 需要什么？
仅需要 Web 浏览器和工作电子邮件地址。 可使用 .gov 和 .mil 电子邮件地址进行注册。 有关详细信息，请参阅[在 Power BI 服务中注册你的美国政府组织](../service-govus-signup.md) 

## <a name="why-do-i-have-to-sign-up-with-my-work-email"></a>为什么必须使用我的工作电子邮件注册？
Power BI 不支持由使用者电子邮件服务或电信提供商提供的电子邮件地址。 了解有关 [Power BI 自助服务注册过程](../service-self-service-signup-for-power-bi.md)的详细信息。

## <a name="is-government-academic-and-nonprofit-pricing-available-for-power-bi"></a>Power BI 是否提供政府部门、学术机构和非营利性组织定价？
是的，从 Microsoft 直接购买时，可提供非营利性组织定价。 可通过 [Microsoft 非营利性组织](https://www.microsoft.com/en-us/nonprofits/power-bi)网站了解详细信息并注册。 政府部门和学术机构定价通过 MOSP/Direct、EA 和 Open 授权计划提供。 政府定价也适用于联合。 

## <a name="is-power-bi-available-on-premises"></a>Power BI 在本地可用吗？
Power BI 服务 [https://powerbi.com](https://powerbi.com) 不可用作专用的内部云服务。 但是，还有其他三个选项可用于查看和处理本地数据。 

### <a name="on-premises-data-gateway"></a>本地数据网关
通过 Power BI 和 Power BI Desktop，可以安全地连接到自己的本地数据源。 通过[本地数据网关](../service-gateway-onprem.md)，可以实时连接到本地 SQL Server Analysis Services 服务器以及其他数据源。 还可以使用集中式网关设置计划刷新。 如果网关不可用，则可以使用 [Power BI Gateway - Personal](../service-gateway-personal-mode.md) 从本地数据源刷新数据。

### <a name="power-bi-report-server"></a>Power BI 报表服务器
Power BI 报表服务器是在自己的本地环境中部署的解决方案，用于创建、发布和管理报表，然后以不同的方式将报表传送给不同的用户：通过 Web 浏览器、移动设备或通过用户收件箱中电子邮件的形式。 详细了解 [Power BI 报表服务器](../report-server/get-started.md)。

### <a name="power-bi-mobile-apps"></a>Power BI 移动应用
还可以[通过 Power BI 移动应用查看本地 Power BI 报表、Reporting Services 移动报表和 KPI](mobile/mobile-app-ssrs-kpis-mobile-on-premises-reports.md)。

## <a name="does-power-bi-support-mobile-devices"></a>Power BI 是否支持移动设备？
是的。 Power BI 拥有适用于 Android 手机和平板电脑、iOS 设备和 Windows 10 设备的本机应用。 从对应的应用商店下载以下 [Power BI 移动应用](https://powerbi.microsoft.com/mobile)之一：  

* [Apple App Store](http://go.microsoft.com/fwlink/?LinkId=526218)
* [Google Play](http://go.microsoft.com/fwlink/?LinkID=544867&clcid=0x409)
* [Windows 应用商店](http://go.microsoft.com/fwlink/?LinkId=526478)

## <a name="what-data-sources-can-i-connect-to"></a>我可以连接到哪些数据源？
Power BI 数据源的列表很广泛，但它可以分为以下几种：

* 来自 [Excel 和 Power BI Desktop 文件](../service-get-data-from-files.md)的数据。
* [服务的内容包](end-user-connect-to-services.md)，其中包含现成的仪表板、报表和服务的数据集（如 Salesforce）。 除了建立数据连接，Power BI 还为每种服务提供预建仪表板和报表。
* 连接到数据库和其他数据集（如 [Azure SQL Database](../service-azure-sql-database-with-direct-connect.md) 和 SQL Server [Analysis Services](../sql-server-analysis-services-tabular-data.md) 表格数据）的连接器。

阅读 Power BI 中有关[获取数据](../service-get-data.md)的详细信息。

## <a name="what-are-content-packs"></a>什么是内容包？
[服务的内容包](end-user-connect-to-services.md) 作为 Power BI 体验的一部分，是常用服务的预建解决方案。 受支持服务的订阅者可以从 Power BI 快速连接到他们的帐户，并通过实时仪表板和已为其预建的交互式报表看到他们的数据。  我们发布了 Salesforce.com、Marketo 和 Adobe Analytics 等常见服务的内容包。 详细了解如何[使用内容包连接服务](end-user-connect-to-services.md)。

[组织内容包](../service-organizational-content-pack-introduction.md)为用户、BI 专业人员和系统集成商提供用于构建他们自己的内容包的工具，以共享组织内专为特定目的构建的仪表板、报表和数据集。

## <a name="what-do-i-need-to-install-in-order-to-use-power-bi"></a>为了使用 Power BI，我需要安装什么？
要免费使用 Power BI 服务，你只需 Web 浏览器和电子邮件。

若要浏览数据并在 Power BI Desktop 中创建报表，请免费下载 [Power BI Desktop](http://powerbi.microsoft.com/designer)。

可以从对应的应用商店免费下载 Power BI 移动应用：

* [App Store](http://go.microsoft.com/fwlink/?LinkId=526218)
* [Google Play](http://go.microsoft.com/fwlink/?LinkID=544867&clcid=0x409)
* [Windows 应用商店](http://go.microsoft.com/fwlink/?LinkId=526478)

## <a name="am-i-limited-to-one-copy-of-power-bi-desktop-for-my-entire-company"></a>我只能安装和使用整个公司的一个 Power BI Desktop 副本吗？
Power BI Desktop 软件许可条款有说明，“你可以在本地安装和使用软件的一个副本。” 这并不意味着只能安装和使用整个公司的一个 Power BI Desktop 副本。 公司的每位用户都可以在其本地安装和使用一个副本。

## <a name="where-do-i-get-started-with-power-bi"></a>从哪里可以获得 Power BI Desktop 入门教程？
以下资源可以用来帮助你入门：

* [Power BI 博客](http://blogs.msdn.com/b/powerbi/)
* [网络研讨会](../webinars.md)
* 我们 [YouTube 频道](https://www.youtube.com/user/mspowerbi)上的入门视频
* [Power BI Desktop 入门](../service-get-started.md)文章
* [加入我们的社区](https://community.powerbi.com/)并提出问题
* 有关更多建议，请参阅[如何获取帮助的 10 条提示](../service-tips-for-finding-help.md)

## <a name="what-browsers-does-power-bi-support"></a>Power BI 支持哪些浏览器？
以下是 [Power BI 支持的浏览器](end-user-browsers.md)的完整列表。

## <a name="what-regions-and-languages-does-power-bi-support"></a>Power BI 支持哪些区域和语言？
以下是 [Power BI 所支持的区域和语言](../supported-languages-countries-regions.md)的完整列表。

## <a name="how-can-i-buy-power-bi-pro-in-my-country"></a>在我所在的国家/地区如何购买 Power BI Pro？
可以直接购买或者通过在 [www.powerbi.com](http://www.powerbi.com) 与代表聊天的方式购买 Power BI Pro 许可证。

你还可以找到 [Microsoft 合作伙伴](https://partner.microsoft.com/)以帮助你实现 Power BI。

## <a name="what-happens-if-my-power-bi-pro-license-expires"></a>如果我的 Power BI Pro 许可证已过期，会发生什么情况？
Power BI Pro 许可证过期后，还有 30 天宽限期。

Power BI Pro 的订阅生命周期与 Office 365 相同。 有关详细信息，请参阅 [Office 365 商业版订阅过期时，我的数据和访问权限会发生什么变化？](https://support.office.com/article/What-happens-to-my-data-and-access-when-my-Office-365-for-business-subscription-ends-4436582f-211a-45ec-b72e-33647f97d8a3)

## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI 是否满足特定于国家、地区和行业的合规性要求？
在 [Microsoft 信任中心](http://go.microsoft.com/fwlink/?LinkId=785324)了解有关 Power BI 合规性的详细信息。

## <a name="where-can-i-learn-more-about-security"></a>从何处可以了解有关安全性的详细信息？
在此 [Power BI 安全](http://go.microsoft.com/fwlink/?LinkId=829185)白皮书和我们的 [Power BI 安全支持文章](../service-admin-power-bi-security.md)中了解有关 Power BI 的安全、隐私和合规性的详细信息。

## <a name="what-has-happened-to-the-power-bi-for-office-365-experience"></a>Power BI for Office 365 体验发生了什么问题？
Power BI for Office 365 体验已被弃用。

## <a name="how-do-i-undo-in-power-bi"></a>如何在 Power BI 中撤消操作？
与许多其他 Microsoft 服务和软件相类似，Power BI 提供了撤消上一项命令的简单方法。 

* 若要**撤消**上一操作或最近几项操作，请按 CTRL+Z。

## <a name="next-steps"></a>后续步骤
* [什么是 Power BI？](../power-bi-overview.md)
* 更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)
* 仍有问题？ 请访问 [Power BI 支持页](https://powerbi.microsoft.com/support/)

