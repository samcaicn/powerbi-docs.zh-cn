---
title: Power BI Gateway - Personal
description: Power BI Gateway - Personal
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 5c2274852c041b07a0ab4a09ed00c2dfa5d64cef
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2017
---
# <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
> [!NOTE]
> 提供适用于 Power BI 的个人网关新版本，称为“本地数据网关（个人模式）”。 下面的文章介绍了以前版本的个人网关（称为 Power BI Gateway-Personal），它将在 2017 年 7 月 31 日之后停用并停止工作。 有关新版本的个人网关的信息（包括如何安装新版本），请参阅[本地数据网关（个人模式）文章](service-gateway-personal-mode.md)。
> 
> 

**Power BI 个人网关**的作用类似于桥梁，用于在 Power BI 服务和支持[刷新](refresh-data.md)的本地数据源之间提供快速且安全的数据传输。 本文旨在让你深入了解网关的工作原理以及你是否需要网关。 我们还整理了有关个人网关的[有用视频](https://www.youtube.com/watch?v=de58vROLqZI)。 

它在你的计算机上作为服务安装和运行。 作为一种服务，它使用在配置期间指定的 Windows 帐户运行。 在某些情况下，网关作为应用程序运行。 稍后我们将详细了解有关内容。

当 Power BI 刷新本地数据源的数据时，网关可确保你的 Power BI 帐户具有相应的权限来连接此数据源，并查询其中的数据。

[Azure 服务总线](http://azure.microsoft.com/documentation/services/service-bus/)可保护 Power BI 和网关之间的数据传输。 服务总线在 Power BI 服务和你的计算机之间创建一个安全的通道。 由于网关提供了这种安全连接，因此通常无需在防火墙中打开一个端口。

在了解有关网关的详细信息之前，让我们先了解一下 Power BI 中使用的一些术语：

*数据集*是指从在线或本地数据源上载到 Power BI 服务的数据。 当使用“获取数据”功能连接并上载数据时将创建数据集。 在浏览器中的 Power BI 工作区的“我的工作区”窗格中显示数据集。 当你创建报表并将磁贴固定到仪表板时，你可以查看数据集中的数据。

*数据源*是指上载到数据集中的数据的实际来源。 它可以是任何来源：数据库、Excel 工作表、Web 服务，等等。使用 Excel 工作簿，可以创建一个简单的包含多行数据的工作表，此工作表可视为一种数据源。 你还可以使用 Excel 中的 Power Query 或 Power Pivot 连接并查询在线和本地数据源中的数据，所有操作都在同一个工作簿中完成。 借助 Power BI Desktop，可使用“获取数据”功能连接并查询在线和本地数据源中的数据。

通过本地数据网关安装个人网关。 可在 [Power BI 网关页](https://powerbi.microsoft.com/gateway/)进行下载。

## <a name="do-i-need-a-gateway"></a>是否需要一个网关？
在安装网关之前，请务必了解是否真的需要它。 这实际上取决于你的数据源：

### <a name="on-premises-data-sources"></a>本地数据源
若要刷新从组织中支持的本地数据源获取数据的数据集，则*必须*使用个人网关。

在使用网关时，支持对上载自以下数据源的数据集使用“立即刷新”和“计划刷新”功能：

* Microsoft Excel 2013（或更高版本）的工作簿，使用 Power Query 或 Power Pivot 连接并查询支持的本地数据源中的数据。 Power Query 或 Power Pivot 中的“获取外部数据”中显示的所有本地数据源都支持刷新，Hadoop 文件 (HDFS) 和 Microsoft Exchange 除外。
* Microsoft Power BI Desktop 文件，使用“获取数据”功能连接并查询支持的本地数据源中的数据。 “获取数据”中显示的所有本地数据源都支持刷新，Hadoop 文件 (HDFS) 和 Microsoft Exchange 除外。

### <a name="online-data-sources"></a>在线数据源
当你在使用 [**Web.Page** ](https://msdn.microsoft.com/library/mt260924.aspx) 功能时*才会需要*网关。 在其他情况下，若要刷新仅从在线数据源获取数据的数据集，则*无需*使用网关。

> [!NOTE]
> 使用 [Web.Page](https://msdn.microsoft.com/library/mt260924.aspx) 功能时，如果已重新发布 2016 年 11 月 18 日之后的数据集或报表，则仅需要网关。
> 
> 

在不使用网关的情况下，支持对上载自以下数据源的数据集使用“立即刷新”和“计划刷新”功能：

* 来自在线数据源的内容包（内容包\\服务）。 默认情况下，来自内容包的数据集每天自动更新一次，但是你也可以手动刷新或设置刷新计划。
* Microsoft Excel 2013（或更高版本）的工作簿，使用 Power Query 或 Power Pivot 连接并查询在线数据源中的数据。
* Microsoft Power BI Desktop 文件，使用“获取数据”功能连接并查询在线数据源中的数据。

**问：**如果 Excel 工作簿或 Power BI Desktop 文件同时从在线和本地数据源中获取数据，该如何选择？

**答：***需要*使用网关。 你需要安装并配置网关，以便刷新来自本地数据源的数据。

**问：**如果 Excel 工作簿中只有我键入的行数据，该如何选择？**

**答：***不需要*使用网关。 仅当工作簿使用 Power Query 或 Power Pivot 查询支持的本地数据源中的数据并将数据加载到数据模型时，才需要安装和配置网关

## <a name="setting-up-a-gateway-for-the-first-time"></a>首次设置网关
首次设置网关的流程分为三个步骤：

1. 下载并安装网关
2. 配置网关
3. 登录到 Power BI 中的数据源

让我们仔细了解一下每一个步骤。

### <a name="download-and-install-a-gateway"></a>下载并安装网关
> [!NOTE]
> 提供适用于 Power BI 的个人网关新版本，称为“本地数据网关（个人模式）”。 本文介绍了以前版本的个人网关（称为 Power BI Gateway - Personal），它将在 2017 年 7 月 31 日之后停用并停止工作。 有关新版本的个人网关的信息（包括如何安装新版本），请参阅[本地数据网关（个人模式）文章](service-gateway-personal-mode.md)。
> 
> 

当你首次针对支持的数据集单击“立即刷新”或“计划刷新”时，系统将提示你安装网关。 或者，若要下载网关，请选择“下载”菜单下的**数据网关**。 下载[本地数据网关](http://go.microsoft.com/fwlink/?LinkID=820925)。

你可以选择**个人网关**而不是 **本地数据网关**以便拥有自己的网关。

实际上安装网关并没有太多步骤。 和安装任何其他应用程序一样，你将选择要安装到的位置，阅读并接受许可协议。 但是需要了解一些重要事项。 尤其是你要安装网关的计算机类型和你在该计算机上登录 Windows 所使用的帐户类型。

> [!NOTE]
> 网关需要具有数据源访问权限。 如果你的个人计算机无法连接到数据源，可能要考虑在有权访问该数据源的计算机上安装[本地数据网关](service-gateway-onprem.md)。 一个示例是在托管于 Azure 中的虚拟机 (VM) 上安装了 SQL Server。 个人计算机可能无权访问该 VM。 可改为在该 VM 上安装本地数据网关，并在 Power BI 服务内配置数据源。
> 
> 

### <a name="computer-type"></a>计算机类型
你要安装网关的计算机类型很重要。

> [!NOTE]
> 只有 64 位 Windows 操作系统才支持个人网关。
> 
> 

在笔记本电脑上 - 为了进行计划刷新，需要启动并运行网关。 笔记本电脑通常处于关机或睡眠状态的时间多于运行状态。 如果在笔记本电脑上安装网关，请务必对笔记本将要运行的时间设置计划的刷新时间。 如果没有，那么在下次计划的刷新时间到来之前将不再尝试刷新。

在台式计算机上 - 没有太多的问题。 只需确保计算机和网关在计划的刷新时间内是运行的。 许多台式计算机会进入睡眠状态，如果处于睡眠状态则无法进行计划刷新。

一旦安装了一个网关，则无需安装另一个。 一个网关可用于任意数量的支持的数据集。 你无需在从中上载工作簿和 Power BI Desktop 文件的同一台计算机上安装网关。 下面是一个示例：假设你有一个连接到组织中 SQL Server 数据源的 Excel 工作簿。 你使用 Power BI 中的“获取数据”功能从笔记本电脑上上载此工作簿。 同时你有一个台式计算机始终保持运行状态，并且你在该计算机上安装和配置了网关。 在 Power BI 中，你已登录到数据源，并为数据集设置了刷新计划。  当计划的刷新时间到来时，Power BI 会与台式计算机上安装的网关建立安全连接。 然后网关安全地连接到数据源以获得更新。 对于刷新，不存在与从笔记本电脑上上载的原始工作簿的任何数据交换。

> [!NOTE]
> 可以在同一台计算机上安装个人和企业网关。
> 
> 

### <a name="windows-account"></a>Windows 帐户
安装网关时，将使用你的 Windows 帐户登录计算机。 你的 Windows 帐户所具有的权限类型将影响网关的安装方式和网关在 Windows 中的运行方式。

当你登录到 Windows：

|  | 具有管理员权限 | 没有管理员权限 |
| --- | --- | --- |
| **Power BI Gateway - Personal 的运行方式** |服务 |应用程序 |
| **计划的刷新** |只要计算机和网关服务正在运行，你无需在计划的刷新时间登录。 |必须在计划的刷新时间登录到你的计算机。 |
| **更改 Windows 帐户密码** |必须更改网关服务的密码。 如果网关所使用的帐户密码不再有效，则刷新将失败。 |网关将始终使用你当前登录时所用的帐户和密码运行。 如果你没有登录到 Windows，则网关将不运行，并且刷新将失败。 |

### <a name="configure-the-gateway"></a>配置网关
安装向导完成后，将提示你启动配置向导。 实际上配置网关并没有太多步骤。 你需要在向导中登录到 Power BI。 这对于向导与 Power BI 服务中的 Power BI 帐户建立连接是必需的。

如果使用具有管理员权限的帐户登录 Windows，那么将要求你输入 Windows 帐户凭据。 可以指定其他 Windows 帐户，但应记住权限决定网关的运行方式。 网关服务将使用此帐户运行。

### <a name="sign-in-to-data-sources"></a>登录数据源
配置向导完成后，网关已启动且正在运行，此时必须指定身份验证类型并登录数据集的每个数据源。 将在 Power BI 中完成此步骤。

![](media/personal-gateway/pg_dataset_settings_signin.png)

你只需指定身份验证类型，并一次登录到数据源。 你将从数据集的“设置”屏幕中的**管理数据源**部分登录。 如果有多个数据源，则必须登录每个数据源。 网关根据数据源确定默认的身份验证类型。 在大多数情况下，使用的是 Windows 身份验证；但是在某些情况下，数据源可能要求使用其他身份验证类型。 如果你不确定，请与你的数据源管理员联系。

## <a name="up-and-running"></a>启动并运行！
网关启动并运行之后，可以单击数据集的“计划刷新”，你将从中看到数据集的设置页面。

![](media/personal-gateway/pg_awintsales_settings.png)

此页显示：

1. 刷新状态 – 显示刷新成功和下一次计划的刷新时间。
2. **网关** - 显示网关是否已安装且在线。 如果网关已安装但不在线，则将禁用“管理数据源”和“计划刷新”设置。
3. **管理数据源** - 显示数据集连接到的数据源。 你可以登录或更改身份验证类型。 你只需要登录每个数据源一次。
4. **计划刷新** – 你可以在此处配置刷新计划设置。 如果网关不在线，则将禁用这些设置。
5. 刷新失败通知 – 默认情况下已选中该选项，如果计划的刷新失败，将向你发送一封电子邮件。

## <a name="updating-your-windows-account-password"></a>更新 Windows 帐户密码
当你安装网关时如果使用具有管理员权限的 Windows 帐户登录计算机，那么网关将使用在配置向导中指定的 Windows 帐户作为服务运行。 在大多数情况下，该帐户与你登录计算机所使用的 Windows 帐户相同。 如果更改了 Windows 帐户密码，那么也需要在网关中更改此密码，否则服务可能不运行，并且刷新将失败。 若要更改网关的 Windows 帐户密码，请在 Windows 桌面任务栏或在应用中选择个人网关图标。

![](media/personal-gateway/pg_programicon.png)

你可以在下图显示的页面中更新密码和检查网关的连接状态。

![](media/personal-gateway/pg_credentials.png)

## <a name="ports"></a>端口
网关使用以下出站端口进行通信：TCP 443（默认）、5671、5672、9350 至 9354。  网关不需要入站端口。

| 域名 | 出站端口 | 说明 |
| --- | --- | --- |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |高级消息队列协议 (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |基于 TCP 的服务总线中继侦听程序（要求使用端口 443 来获取访问控制令牌） |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| login.windows.net |443 |HTTPS |

如果需要将 IP 地址而不是域列入白名单，可下载并使用 Microsoft Azure 数据中心 IP 范围列表。 [下载](https://www.microsoft.com/download/details.aspx?id=41653)

## <a name="next-steps"></a>后续步骤
[本地数据网关（个人模式）- 新版本的个人网关](service-gateway-personal-mode.md)
[为 Power BI Gateway 配置代理设置](service-gateway-proxy.md)  
[Power BI Premium](service-premium.md)

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

