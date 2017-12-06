---
title: "本地数据网关"
description: "这是有关 Power BI 本地数据网关的概述。 你可以使用此网关来处理 DirectQuery 数据源。 还可以使用此网关刷新具有本地数据的云数据集。"
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
ms.date: 11/27/2017
ms.author: davidi
ms.openlocfilehash: 4693349715e7a38ae936318e9a8750e0b2f3fab0
ms.sourcegitcommit: 7742f952c20695dfb475f74965c0065b02c01521
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2017
---
# <a name="on-premises-data-gateway"></a>本地数据网关
本地数据网关的作用好似一架桥，提供本地数据（不在云中的数据）与 Power BI、Microsoft Flow、逻辑应用以及 PowerApps 服务之间快速且安全的数据传输。

你可以同时将单个网关与不同的服务一起使用。 如果使用的是 Power BI 和 PowerApps，可以对它们使用同一个网关。 它依赖于你登录的帐户。

> [!NOTE]
> 本地数据网关在所有模式下实现数据压缩和传输加密。
> 
> 

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-requirements-include.md)]

### <a name="limitations-of-analysis-services-live-connections"></a>Analysis Services 实时连接限制
你可以使用针对表格或多维实例的实时连接。

| **服务器版本** | **所需的 SKU** |
| --- | --- |
| 2012 SP1 CU4 或更高版本 |商业智能和企业版 SKU |
| 2014 |商业智能和企业版 SKU |
| 2016 |标准 SKU 或更高版本 |

* 不支持单元格级别格式和转译功能。
* 操作和命名集不会公开到 Power BI，但你仍然可以连接到包含操作或命名集的多维数据集，并创建视觉对象和报表。

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="download-and-install-the-on-premises-data-gateway"></a>下载并安装本地数据网关
若要下载网关，请选择“下载”菜单下的“数据网关”。 下载[本地数据网关](http://go.microsoft.com/fwlink/?LinkID=820925)。

![](media/service-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-install-include](./includes/gateway-onprem-install-include.md)]

## <a name="install-the-gateway-in-personal-mode"></a>在个人模式下安装网关
> [!NOTE]
> 个人模式仅适用于 Power BI。
> 
> 

安装个人网关后，你将需要启动 **Power BI Gateway - Personal 配置向导**。

![](media/service-gateway-onprem/personal-gateway-launch-configuration.png)

然后你需要登录到 Power BI 以使用云服务注册网关。

![](media/service-gateway-onprem/personal-gateway-signin.png)

你还需要提供 Windows 服务运行需要的 Windows 用户名和密码。 你可以自己指定一个不同的 Windows 帐户。 网关服务将使用此帐户运行。

![](media/service-gateway-onprem/personal-gateway-windows-service.png)

安装完成后，将需要转到 Power BI 中的数据集并确保已为本地数据源输入了凭据。

<a name="credentials"></a>

## <a name="storing-encrypted-credentials-in-the-cloud"></a>在云中存储加密凭据
将数据源添加到网关时，需要为该数据源提供凭据。 将使用这些凭据运行对数据源的所有查询。 云中存储凭据之前，使用非对称加密安全地加密凭据，以阻止在云中对其进行解密。 将凭据发送到运行网关的计算机，以便在访问数据源时对其进行本机解密。

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[!INCLUDE [gateway-onprem-how-it-works-include](./includes/gateway-onprem-how-it-works-include.md)]

## <a name="troubleshooting"></a>故障排除
如果在安装和配置网关时遇到问题，请务必参阅[本地数据网关疑难解答](service-gateway-onprem-tshoot.md)。 如果你认为你的防火墙有问题，请参阅故障排除文章中的[防火墙或代理](service-gateway-onprem-tshoot.md#firewall-or-proxy)部分。

如果你认为网关遇到代理问题，请参阅[为 Power BI Gateway 配置代理服务器设置](service-gateway-proxy.md)。

## <a name="next-steps"></a>后续步骤
[管理数据源 - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[管理数据源 - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[管理数据源 - SQL Server](service-gateway-enterprise-manage-sql.md)  
[管理数据源 - Oracle](service-gateway-onprem-manage-oracle.md)  
[管理数据源 - 导入/计划刷新](service-gateway-enterprise-manage-scheduled-refresh.md)  
[深入了解本地数据网关](service-gateway-onprem-indepth.md)  
[本地数据网关（个人模式）- 新版本的个人网关](service-gateway-personal-mode.md)
[为本地数据网关配置代理设置](service-gateway-proxy.md)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

