---
title: "为本地数据网关配置代理设置"
description: "有关本地数据网关代理设置配置的信息。"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 6fb6250f8cd82c7057abe3f9cf9792dc733ea4b6
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>为本地数据网关配置代理设置
你的工作环境可能要求你通过代理访问 Internet。 这会阻止本地数据网关连接到该服务。

## <a name="does-your-network-use-a-proxy"></a>你的网络是否使用代理？
superuser.com 上的以下文章讨论了尝试确定网络上有无代理的可行方法。

[如何确定我正在使用的代理服务器？(SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>配置文件位置和默认配置
在 .NET 配置文件中配置代理信息。 位置和文件名将因所用网关而异。

### <a name="on-premises-data-gateway"></a>本地数据网关
本地数据网关涉及两个主要配置文件。

**配置**

第一个用于实际配置网关的配置屏幕。 如果你在配置网关时遇到问题，可查看此文件。

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Windows 服务**

第二个用于与 Power BI 服务进行交互并处理请求的实际 Windows 服务。

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
> [!NOTE]
> 提供适用于 Power BI 的个人网关新版本，称为“本地数据网关（个人模式）”。 本文的这一部分介绍了以前版本的个人网关（称为 Power BI Gateway-Personal），它将在 2017 年 7 月 31 日之后停用并停止工作。 有关新版本的个人网关的信息（包括如何安装新版本），请参阅[本地数据网关（个人模式）文章](service-gateway-personal-mode.md)。
> 
> 

可以按两种方式之一安装个人网关。 安装为 Windows 服务（管理）或用户模式应用程序。 在安装过程中确定安装方式。 因此，你的配置文件可能位于两个位置之一，具体取决于网关的安装方式。 可检查这两个位置。

**配置**

第一个用于实际配置网关的配置屏幕。 如果你在配置网关时遇到问题，可查看此文件。

对于 *Windows 服务*，位置如下。

    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\GWConfig.exe.config
    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

对于*用户模式应用程序*，位置如下。

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\GWConfig.exe.config
    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

**Windows 服务**

第二个用于与 Power BI 服务进行交互并处理请求的实际 Windows 服务。

对于 *Windows 服务*，位置如下。

    C:\Program Files\Power BI Personal Gateway\1.0\Gateway\diawp.exe.config

对于*用户模式应用程序*，位置如下。

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Gateway\diawp.exe.config

## <a name="configuring-proxy-settings"></a>配置代理设置
默认代理配置如下。

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

默认配置适用于 Windows 身份验证。 如果你的代理服务器使用另一种形式的身份验证，则你将需要更改设置。 如果你不确定，则应与你的网络管理员联系。

若要了解有关 .NET 配置文件代理元素配置的详细信息，请参阅 [defaultProxy 元素（网络设置）](https://msdn.microsoft.com/library/kd3cf2ex.aspx)

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>将网关服务帐户更改为域用户
当配置代理设置以使用默认凭据时，如上文所述，你可能会遇到关于代理的身份验证问题。 这是因为默认服务帐户是服务 SID，而不是经过身份验证的域用户。 你可以更改网关的服务帐户，以允许对代理进行正确的身份验证。

> [!NOTE]
> 建议使用托管的服务帐户以避免重置密码。 了解如何通过 Active Directory 创建[托管服务帐户](https://technet.microsoft.com/library/dd548356.aspx)。
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>更改本地数据网关服务帐户
1. 更改**本地数据网关服务**的 Windows 服务帐户。
   
    此服务的默认帐户是 NT SERVICE\PBIEgwService。 你会想要在 Active Directory 域内将其更改为域用户帐户。 或者，你会想要使用托管服务帐户以避免更改密码。
   
    你会想要在 Windows 服务属性中的“登录”选项卡上更改帐户。
2. 重启**本地数据网关服务**。
   
    从管理员命令提示符中，发出以下命令。
   
        net stop PBIEgwService
   
        net start PBIEgwService
3. 重启**本地数据网关服务配置器**。 可选择 Windows“开始”按钮，然后搜索*本地数据网关*。
4. 登录到 Power BI。
5. 使用恢复密钥还原网关。
   
    这将使新的服务帐户能够解密存储的数据源凭据。

## <a name="next-steps"></a>后续步骤
[本地数据网关（个人模型）](service-gateway-personal-mode.md)
[防火墙信息](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

