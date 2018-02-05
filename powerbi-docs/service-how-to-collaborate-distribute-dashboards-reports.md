---
title: "应如何在 Power BI 中开展协作并进行共享？"
description: "在 Power BI 中，可以通过多种不同的方式针对仪表板、报表和磁贴开展协作并进行共享。 每种方法都各有千秋。"
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: lukaszp
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 02/28/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/18
ms.author: maggies
ms.openlocfilehash: 032d07616464dcda8cc4cc38b1440936e5393a98
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="how-should-i-collaborate-and-share-dashboards-and-reports-in-power-bi"></a>在 Power BI 中应如何针对仪表板及报表开展协作并进行共享？
你已创建仪表板和报表。 可能也会和同事协作处理它们。 这样就需要其他人有权限访问它们。 分发的最好方式是什么？

在本文中，我们将对比 Power BI 中这些用于协作和共享选项： 

* 在应用工作区中与同事进行协作，创建有价值的报表和仪表板。
* 将这些仪表板和报表打包为应用，并将其发布到到更大的组或整个组织。
* 在服务或 Power BI 移动应用中与几位用户共享仪表板或报表。
* 发布到 Web，任何人都可以在其中查看和与之交互。
* 打印。 

无论选择了哪个选项，要共享仪表板，都需要 [Power BI Pro 许可证](service-free-vs-pro.md)，或者该内容需要位于[高级容量](service-premium.md)中。 许可证要求因查看仪表板的同事而各不相同，具体取决于所选择的选项。 以下各节将进行详细说明。 

![Power BI 服务中的应用](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-apps-home-blog.png)

Power BI 服务中的应用

## <a name="collaborate-with-coworkers-to-create-an-app"></a>与同事协作创建应用
假设你和你的队友想要将 Power BI 见解发布到你的组织。 最好的方法是构建一个应用。 应用是仪表板和报表的集合，生成应用的目的是为组织提供关键指标。 

若要构建应用，需要具备应用工作区，并且你的队友需要成为该工作区的成员。 将应用工作区视为你和队友可以在 Power BI 仪表板和报表上进行协作的临时区域。 你们所有人均可以在 Power BI Desktop 中创建报表，并将这些报表发布到应用工作区，同时你们所有人都需要 Power BI Pro 许可证。

![应用工作区](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-apps-workspaces.png)

如果只需要与同事共享已完成的仪表板，则请勿将他们添加到应用工作区。 反之，请[在应用工作区中创建仪表板](service-create-distribute-apps.md)并向同事发布应用。 

## <a name="publish-your-app-to-a-broad-audience"></a>向广泛的受众发布应用
假设你想要将仪表板分发给广泛的受众。 你和同事创建了一个应用工作区，然后在此应用工作区中创建并优化了仪表板、报表和数据集。 现在选择所需的仪表板和报表，并将它们作为应用向安全组或通讯组列表的成员发布，或者将其发布到整个组织。 

![“发布应用”图标](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-app-publish-600.png)

可以在 Power BI 服务 ([https://powerbi.com](https://powerbi.com)) 中轻松找到应用并进行安装。 可以向业务用户发送应用的直接链接，或者他们可以在 AppSource 中搜索此应用。 如果 Power BI 管理员已授予你权限，则可以将应用自动安装到同事的 Power BI 帐户中。 阅读有关[发布应用](service-create-distribute-apps.md#publish-your-app)的详细信息。 

安装应用后，他们可以在浏览器或移动设备中查看应用。

对于查看你的应用的用户，他们同样需要拥有 Power BI Pro 许可证，或者应用需要存储在 Power BI 高级容量中。 请阅读[什么是 Power BI Premium？](service-premium.md)了解详细信息。

## <a name="share-dashboards-and-reports"></a>共享仪表板和报表
假设你已在自己的“我的工作区”或应用工作区中完成仪表板和报表，并且希望其他人也有权访问它。 一种用于访问的方法是共享它。 

![“共享”图标](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-share-in-situ.png)

需要 Power BI Pro 许可证才能共享内容，你与之共享的人员也需要许可证才能共享，或者该内容需要位于[高级容量](service-premium.md)中。 你共享仪表板或报表时，他们可以查看仪表板并与其交互，但不能编辑。 除非将行级别安全性 (RLS) 应用到基础数据集，否则他们会看到你在仪表板和报表中看到的相同数据。 如果你允许，与之共享的同事可以与其他同事共享。 

也可以与组织外的用户共享。 他们可以查看仪表板并与之交互，但不能共享它。 

有关从 Power BI 服务[共享仪表板和报表](service-share-dashboards.md)的详细信息。 此外，还可以向链接添加筛选器并[共享报表的筛选视图](service-share-reports.md)。

## <a name="annotate-and-share-from-the-power-bi-mobile-apps"></a>从 Power BI 移动应用添加批注并共享
在适用于 iOS 和 Android 设备的 Power BI 移动应用中，可以为磁贴、报表或视觉对象添加批注，并通过电子邮件与任何人共享。 

![在移动应用中批注并共享](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-iphone-annotate.png)

在共享磁贴、报表或视觉对象快照时，收件人看到的与你发送邮件时的内容完全一致。 邮件还包含仪表板或报表的链接。 如果他们有 Power BI Pro 许可证，或者该内容位于[高级容量](service-premium.md)中，并且你已与他们共享对象，则他们可以打开此对象。 可以向任何人（不仅仅是同一电子邮件域的同事）发送磁贴的快照。

有关从 iOS 和 Android 移动应用[添加注释并共享磁贴、报表和视觉对象](mobile-annotate-and-share-a-tile-from-the-mobile-apps.md)的详细信息。

还可以通过适用于 Windows 10 设备的 Power BI 应用[共享磁贴快照](mobile-share-tile-windows-10-phone-app.md)。

## <a name="publish-to-the-web"></a>发布到 Web
可以通过在任意设备上将交互式视觉对象嵌入到博客文章、网站、社交媒体以及其他联机交流媒介，将 Power BI 报表发布到整个 Internet。 Internet 上的任何人都可以查看你的报表，并且你无法控制谁可以查看已发布的内容。 他们不需要 Power BI 许可证。 只能将可以编辑的报表发布到 Web。 如果是与你共享的报表或者报表位于应用内部，则无法将其发布到 Web。 有关[发布到 Web](service-publish-to-web.md) 的详细信息。

## <a name="print-or-save-as-pdf-or-other-static-file"></a>打印或另存为 PDF 或其他静态文件
可以在 Power BI 服务中打印整个仪表板、仪表板磁贴、报表页或可视化效果，或将其另存为 PDF（或其他静态文件格式）。 一次只能打印一页报表，而不能一次打印整个报表。 有关[打印或另存为静态文件](service-print.md)的详细信息。

## <a name="next-steps"></a>后续步骤
* 想提供反馈？ 请转到 [Power BI 社区站点](https://community.powerbi.com/)提出你的建议。
* [与同事和他人共享仪表板](service-share-dashboards.md)
* [在 Power BI 中构建和发布应用](service-create-distribute-apps.md)
* 更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)。

