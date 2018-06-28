---
title: 远程配置 Power BI iOS 移动应用对报表服务器的访问权限
description: 了解如何为报表服务器远程配置 iOS 移动应用。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2018
ms.author: maggies
ms.openlocfilehash: bbade67c9510b8d316364d991c09444712309514
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "34722169"
---
# <a name="configure-power-bi-ios-mobile-app-access-to-a-report-server-remotely"></a>远程配置 Power BI iOS 移动应用对报表服务器的访问权限

在本文中，可了解如何使用组织的 MDM 工具来配置 Power BI iOS 移动应用对报表服务器的访问权限。 若要进行此设置，IT 管理员将创建应用配置策略，指定要推送到应用的必要信息。 

 然后，由于已配置报表服务器连接，Power BI iOS 移动应用用户就可以更轻松地连接到其组织的报表服务器。 


## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>在 MDM 工具中创建应用配置策略 

管理员在 Microsoft Intune 中执行这些步骤，即可创建应用配置策略。 在其他 MDM 工具中，生成应用配置策略的步骤和体验可能有所不同。 

1. 连接 MDM 工具。 
2. 创建并命名新的应用配置策略。 
3. 选择要将此应用配置策略分发到的用户。 
4. 创建键值对。 

键值对拼写如下表所示。

|密钥  |类型  |说明  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | 字符串 | 报表服务器 URL </br> 应以 http/https 开头 |
| com.microsoft.powerbi.mobile.ServerUsername | 字符串 | [可选] </br> 要用于连接服务器的用户名。 </br> 如果不存在此项，应用将提示用户键入用于连接的用户名。| 
| com.microsoft.powerbi.mobile.ServerDisplayName | 字符串 | [可选] </br> 默认值为“报表服务器” </br> 应用中用于表示服务器的友好名称 | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | 布尔 | 默认值为 True </br> 如果设置为“True”，这将替代移动设备中已有的任何报表服务器定义（将删除已配置的现有服务器）。 </br> 将“替代”设置为 True 还可防止用户删除该配置。 </br> 设置为“False”将添加推送值，并保留任何现有设置。 </br> 如果移动应用中已配置相同的服务器 URL，应用将按原样保留该配置，且不会要求用户为同一服务器重新进行身份验证。 |

下面的示例使用 Intune 设置配置策略。

![Intune 配置设置](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-a-report-server"></a>最终用户连接到报表服务器

发布应用配置策略后，为该策略定义的通讯组列表中的用户和设备启动 Power BI iOS 移动应用时，将获得以下体验。 

1. 他们将看到一条消息，表示已为移动应用配置报表服务器，然后点击“登录”。

    ![登录报表服务器](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  在“连接到服务器”页上，已填写报表服务器详细信息。 他们将点击“连接”。

    ![已填写报表服务器详细信息](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. 他们将键入密码进行身份验证，然后点击“登录”。 

    ![已填写报表服务器详细信息](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

现在，他们就可查看存储在报表服务器上的 KPI 和 Power BI 报表并与之交互。

## <a name="next-steps"></a>后续步骤
[管理员概述](admin-handbook-overview.md)  
[安装 Power BI 报表服务器](install-report-server.md)  

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

