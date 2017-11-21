---
title: "使用 Power BI 连接到 Visual Studio Team Services"
description: "适用于 Power BI 的 Visual Studio Team Services"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 20ea9117cf1eee3d7b05be21e5964226349a58c1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-visual-studio-team-services-with-power-bi"></a>使用 Power BI 连接到 Visual Studio Team Services
使用 Power BI 的 Visual Studio Team Services 内容包深入分析 git 和 TFVC 团队项目。 建立连接后，将在仪表板上和报表中自动显示数据。 

连接到 [Visual Studio Team Services 内容包](https://app.powerbi.com/getdata/services/visual-studio-online)，或阅读有关使用 Power BI 进行 [Visual Studio Team Services 集成](https://powerbi.microsoft.com/integrations/visual_studio_online)的详细信息。

>[!NOTE]
>此内容包需要具有对启用了 OAuth 的帐户的访问权限。 以下是有关要求的详细信息。

## <a name="how-to-connect"></a>如何连接
1. 选择左侧导航窗格底部的**获取数据**。  
   ![](media/service-connect-to-visual-studio/pbi_getdata.png) 
2. 在**服务**框中，选择**获取**。  
   ![](media/service-connect-to-visual-studio/pbi_getservices.png) 
3. 选择 **Visual Studio Team Services** 内容包，并单击**获取**。     
   ![](media/service-connect-to-visual-studio/vsts.png)
4. 输入有关你的 Visual Studio Team Services 帐户的信息。 有关详细信息，请参阅下面的[查找这些参数](#FindingParams)。
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin.png)
   
   帐户名称即你的 visualstudio.com URL 的前面部分。    
   ![](media/service-connect-to-visual-studio/urlimage.png)
   
   项目名称即 Visual Studio Team Services 中每页顶部显示的名称：  
   ![](media/service-connect-to-visual-studio/projectimage.png)
5. 使用 oAuth2 通过 Visual Studio Team Services 进行身份验证。 因此，你可能会看到一个 VSTS 登录对话框。 
   
   > [!IMPORTANT]
   > 某些 Visual Studio Team Services 部署不支持 oAuth2。  如果登录失败，请按照故障排除部分中的指导进行操作。
   > 
   > 
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin2.png)
6. 按照 Visual Studio Team Services 身份验证屏幕进行操作，以授予 Power BI 的 Visual Studio 内容包对团队项目数据的权限。   
   ![](media/service-connect-to-visual-studio/vsoauthorizeapp450.png)
7. 连接到你的 Visual Studio Team Services 项目后，左侧导航窗格中将显示新的仪表板、报表和数据集。 新的项目会以黄色星号 \* 标记。  
   ![](media/service-connect-to-visual-studio/visualstudioonline800px.png) 

**下一步？**

* 尝试在仪表板顶部的[在“问答”框中提问](service-q-and-a.md)
* 在仪表板中[更改磁贴](service-dashboard-edit-tile.md)。
* [选择磁贴](service-dashboard-tiles.md)以打开基础报表。
* 虽然数据集将按计划每日刷新，你可以更改刷新计划或根据需要使用**立即刷新**来尝试刷新

## <a name="whats-included"></a>包含的内容
Power BI 中的 Visual Studio Team Services 可为你的报表提供各种表和字段。 内容包中所含内容的完整列表可以在此处找到：<https://www.visualstudio.com/get-started/report/vso-pbi-whats-available-vs>

## <a name="system-requirements"></a>系统要求
* 对有权限使用 REST API 收集数据的 Visual Studio Team Services 帐户的访问权限。  
* 在初始连接期间授予“Power BI”应用程序的权限。 若要断开 Power BI 连接并删除其访问你的 Visual Studio Team Services 帐户的授权，你可以在 Visual Studio Team Services 中“撤销”访问权限。 请参阅 <https://www.visualstudio.com/get-started/setup/change-application-access-policies-vs>。  

可在 <https://www.visualstudio.com/en-us/get-started/report/connect-vso-pbi-vs> 处找到更多详细信息。

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>查找参数
帐户名称即你的 visualstudio.com URL 的前面部分。    
    ![](media/service-connect-to-visual-studio/urlimage.png)

项目名称即 VSTS 中每页顶部显示的名称：  
    ![](media/service-connect-to-visual-studio/projectimage.png)

你还可以使用通配符选择多个项目。 例如，可通过只输入“\*”选择所有项目，或通过输入“Azure\*”选择所有以“Azure”开头的项目。

## <a name="troubleshooting"></a>故障排除
尝试登录 Visual Studio Team Services 时，可能收到“登录失败”消息。

无法成功进行身份验证有两个常见原因：

1) 使用个人帐户而非工作或学校帐户进行登录  

2) 你的 Visual Studio Team Services 部署不支持 oAuth 

**使用工作或学校帐户登录**  
如果你看到此问题，这可能意味着，你已使用你尝试从其加载数据的帐户之外的帐户进行 Visual Studio Team Services 身份验证 – 例如，如果你使用个人 Microsoft 帐户连接到 Visual Studio Team Services，而使用工作或学校帐户连接到 PowerBI，则会出现这种情况。

解决方法：  

* 单击“取消”退出配置对话框  
* 在个人帐户下注销 Visual Studio Team Services  
* 使用工作或学校帐户登录到 Visual Studio Online  
* 重新启动上面的“获取数据”过程 

使用工作或学校帐户 (Azure Active Directory / AAD) 进行连接：  
    ![](media/service-connect-to-visual-studio/vsologinscreen.png)

如果你看到此对话框，且想要使用你的工作或学校帐户 (Azure Active Directory) 进行连接，请确保单击左侧的链接以使用该帐户登录 - 请勿在右侧提供你的 AAD 凭据，因为它需要的是 Microsoft 帐户（你的个人帐户）。

**不支持 oAuth2 的 Visual Studio Team Services 部署**  
你的 VSTS 管理员可能已为你的 Visual Studio Team Services 部署禁用了 oAuth。  如果是这样，此时你将无法使用 Power BI 的 Visual Studio 内容包。 

![](media/service-connect-to-visual-studio/oauth.png)

## <a name="next-steps"></a>后续步骤
* [Power BI 入门](service-get-started.md)
* [获取数据](service-get-data.md)

