---
title: "Power BI 网关入门"
description: "了解有关 Power BI 数据网关的基础知识。"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: e56af5ae1c59afc7d7aef01450bb1c778eb70b14
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="getting-started-with-power-bi-gateways"></a>Power BI 网关入门
欢迎使用 Power BI Gateway 入门指南。 本文中简短的分步过程可帮助你熟悉网关概念、它的工作原理，以及如何安装、配置和运行你自己的网关。  

![](media/service-gateway-getting-started/gw_gettingstarted_0a.png)

网关可以说是一个技术性课题，并且由于每个网络和企业各不相同，因此网关的复杂性较为显著。 要攻克这种复杂性，我们可以从基础知识开始入手。

## <a name="how-power-bi-gateways-work"></a>Power BI 网关的工作原理
**网关**是一种便于访问驻留在本地专用网络上的数据的软件，方便后续在 Power BI 等云服务中使用这些数据。 这类似于网关守卫侦听连接请求，并仅在用户请求满足特定条件（如是否允许他们使用网关）时才授权访问。 这允许组织将数据库和仓库保留在本地网络，并安全地使用该数据的子集在 Power BI 中创建引人注目的报表和仪表板。

此外，网关还能通过加密和压缩经过网关的所有数据，以及用于连接数据源的任何密码来保护访问权限和数据的安全。 这一切听上去非常简单，但还要考虑许多细节。

有时，你希望有一个自己专用的网关，原因是你可能有一个大型 Excel 工作簿以及三个 SQL 数据库，其中包含多年销售和市场营销运行数据，并且你想要创建一个 Power BI 仪表板以从各个角度显示这些销售情况。 你是创建报表的唯一人员，这是你的 Excel 工作簿，并且仅由你使用这些数据库来创建 Power BI 报表。 你需要一个仅供个人使用的网关，而不与其他人共享这些数据源。

其他情况下，你所在的组织可能具有来自不同供应商（包括 Analysis Services、SAP、Oracle、IBM）的各类数据库以及各种其他数据源，并且你需要很多人访问这些内容，方便他们创建大量报表。 在这种情况下，你需要一个可以让你配置所有这些源的访问权限的网关，然后需要与组织中的许多人共享。 这完全是一种不同的网关。

幸运的是，Power BI 提供了两种网关，分别适用于这两种情况。 Power BI 提供的这两种网关服务如下所示：

* 本地数据网关（个人模式）– 允许一位用户连接到源，且无法与其他人共享。 只能与 Power BI 协同使用。
* **本地数据网关** – 允许多个用户连接到多个本地数据源，可由 Power BI、PowerApps、Flow 和 Azure 逻辑应用使用，只需安装一个网关即可实现。

这两种网关执行类似的功能：方便对驻留在本地专用网络上的数据进行访问，从而在 Power BI 等基于云的服务中使用该数据。 个人网关只能由一个人使用，并且只能由 Power BI 使用，本地数据网关可由多个用户和多个服务使用。

正常使用网关有三个步骤或阶段：

* 安装网关
* 将用户添加到网关（允许他们使用网关）
* 连接到数据源

此外，使用网关还可以方便你执行其他重要的事项：

* 刷新本地数据，以便使用新数据更新 Power BI 报表

刷新数据意味着 Power BI 仪表板和报表的外观会更新并反映最新数据。 因此，当有人查看你使用本地数据创建的报表时，该报表可以显示最新信息，即使是不久前创建的报表也是如此。

第一个步骤（即安装网关）很容易实现。 此外，还可以很方便地允许用户访问网关，只需将其添加到 Power BI 的对话框中即可。 连接到数据源的操作比较复杂，因为数据源的数量较多，并且每个数据源都有它自己的连接要求和细微差异。 我们将在其他指南中专门介绍此过程，本文着重介绍网关相关步骤。

我们先执行简单的步骤，逐步完成网关安装。

## <a name="install-the-gateway"></a>安装网关
要安装网关，请打开 Power BI 服务（你可以使用此链接在浏览器中启动 Power BI 服务并登录），然后使用你的 Power BI 帐户登录。 在 Power BI 服务中，选择右上角的“下载图标”，如下图所示，然后选择“数据网关”。

![](media/service-gateway-getting-started/gw_gettingstarted_01.png)

将转到下载页，在该页上单击“下载网关”按钮开始下载。

![](media/service-gateway-getting-started/gw_gettingstarted_02.png)

此屏幕简要介绍了网关概念。 它还提供了几条重要的**警告**：当你安装网关时，它实际上在你执行安装的计算机上运行。 如果该计算机关闭，那么网关也会关闭（因此它在未运行不会工作）。 此外，不推荐在使用无线网络的计算机上安装，而应使用连接到有线网络的计算机进行安装。

准备就绪后，选择“下一步”继续进行设置。

![](media/service-gateway-getting-started/gw_gettingstarted_03.png)

此处需要决定要安装的网关，是本地网关还是个人网关。 在本指南中，我们将安装本地数据网关。

做决定时请注意以下几点：

* 两个网关都需要 64 位 Windows 操作系统。
* 网关不能安装在域控制器上。
* 同一台计算机上最多可以安装两个本地数据网关，分别在两个模式（个人和标准）下运行。 
* 在同一台计算机上，不能有多个网关在相同模式下运行。
* 可以在不同计算机上安装多个本地数据网关，并通过同一 Power BI 网关管理界面管理所有这些网关（个人网关除外，见下一注意点）。
* 只能为每个 Power BI 用户运行一个个人模式网关。 如果为同一用户安装另一个人模式网关，即使是在其他计算机上，最新安装也会替换现有旧安装。

选择“下一步”后，将开始安装网关。 你需要指定它的安装位置，通常推荐默认位置。

![](media/service-gateway-getting-started/gw_gettingstarted_06.png)

安装过程很快，过程中会显示一个状态栏。

![](media/service-gateway-getting-started/gw_gettingstarted_06a.png)

即将完成时，你需要确定用于网关的帐户。 这应该是用于登录 Power BI 的帐户（用户名和密码）；网关与你的 Power BI 帐户关联，你可以从 Power BI 服务配置网关。

![](media/service-gateway-getting-started/gw_gettingstarted_07.png)

按下图所示登录。

![](media/service-gateway-getting-started/gw_gettingstarted_08.png)

登录后，需要创建“恢复密钥”。 我们将在另一篇文章中深入讨论这些信息，现在只需要知道你将需要它来恢复或移动网关。

![](media/service-gateway-getting-started/gw_gettingstarted_09.png)

所有操作执行完毕后，你将看到一个窗口，显示网关已就绪。

![](media/service-gateway-getting-started/gw_gettingstarted_10.png)

这就是本地网关的安装过程。 这个过程确实非常简单。 然后，下一步是**添加用户**或**添加数据源**；你可以在初始配置后首先添加其中一个。

下一节介绍如何将用户添加到网关，在此之后，我们将讨论下一步，即如何将数据源添加到网关。

## <a name="add-users-to-a-gateway"></a>将用户添加到网关
安装网关后，我们从 **Power BI 服务**中管理网关。 若要获取网关的管理屏幕，请在 Power BI 服务中选择右上角的“齿轮”图标，然后选择“管理网关”。

![](media/service-gateway-getting-started/gw_gettingstarted_15.png)

在 Power BI 服务画布内将显示一个页面，你可以在其中管理网关。 **网关设置**页如下所示。

![](media/service-gateway-getting-started/gw_gettingstarted_12.png)

如果点击或单击“管理员”，会看到以下管理员的管理页。 请注意，此页仅表示哪些用户可以*管理*网关，并且网关用户均使用不同页从每个各数据源中进行添加（或删除），我们会在接下来的几个章节中对此进行回顾。

![](media/service-gateway-getting-started/gw_gettingstarted_13.png)

在安装和验证（成功连接到）数据源后，它会显示在此“管理网关”屏幕左侧与其关联的网关下，如下图所示。 请注意，在右侧窗格中，可以在“数据源设置”和“用户”这两个部分之间进行切换。 紧随其后的屏幕是“数据源设置”部分。

![](media/service-gateway-getting-started/gw_gettingstarted_16.png)

选择“用户”后，将显示一个文本框，可以在其中键入你想要授予其对所选数据源访问权限的组织用户。 在下面的屏幕中，你可以看到我添加的 Maggie 和 Adam。

当你开始在文本框中键入电子邮件地址时，Power BI 将显示其电子邮件地址与所键入内容相匹配的用户列表，方便你单击名称并将其添加到列表。

你还可以添加电子邮件组（别名），从而允许用户组或个人进行访问。

![](media/service-gateway-getting-started/gw_gettingstarted_17.png)

选择“添加”后，添加的成员会显示在框中，你还可以根据需要添加更多用户。 删除用户的操作同样非常简单。 只需选中用户名称旁边的复选框，然后选择框下面的“删除”按钮。

![](media/service-gateway-getting-started/gw_gettingstarted_18.png)

以上就是步骤的全部内容。 请注意，需要将用户添加到你希望向其授予访问权限的每个数据源。 每个数据源具有一个单独的用户列表，必须分别将用户添加到每个数据源。

## <a name="adding-data-sources"></a>添加数据源
当然，需要添加数据源才能使网关发挥作用。 这正是所介绍的 Power BI 网关的复杂之处：有许多不同的数据源可供使用，并且每个数据源都有其自己的要求（通常情况下，它需要有自己要求的驱动程序）。

在向你介绍另一篇文章之前，我们先来了解如何添加数据源。 在 **Power BI 服务**的“管理网关”页上，选择你想要添加数据源的网关，然后选择页面左上角的“添加数据源”（位于网关列表上方）。

执行此操作时，右侧窗格中会显示“数据源设置”面板，如下图所示。 你可以在此处命名你的数据源（在“数据源名称”文本框中输入），然后从“数据源类型”下拉列表中选择其类型。

![](media/service-gateway-getting-started/gw_gettingstarted_14.png)

好了，你已成功安装网关，并且已经准备好添加数据源。 太棒了！ 请参阅下节中的资源，了解有关数据源的信息、有关使用网关的更多详细信息以及其他有用信息。

## <a name="next-steps"></a>后续步骤
[使用本地数据网关](service-gateway-onprem.md)  
[深入了解本地数据网关](service-gateway-onprem-indepth.md)  
[本地数据网关（个人模式）](service-gateway-personal-mode.md)
[本地数据网关疑难解答](service-gateway-onprem-tshoot.md)  

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

