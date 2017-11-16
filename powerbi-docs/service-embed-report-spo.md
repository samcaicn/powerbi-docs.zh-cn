---
title: "使用报表 Web 部件在 SharePoint Online 中嵌入报表"
description: "借助 Power BI 新推出的适用于 SharePoint Online 的报表 Web 部件，可以在 SharePoint Online 页面中轻松嵌入交互式 Power BI 报表。"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/01/2017
ms.author: asaxton
ms.openlocfilehash: bb3ab7c8f9791aa535e86b8c9b21361c95e4389b
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>使用报表 Web 部件在 SharePoint Online 中嵌入报表
借助 Power BI 新推出的适用于 SharePoint Online 的报表 Web 部件，可以在 SharePoint Online 页面中轻松嵌入交互式 Power BI 报表。

使用新的“**在 SharePoint Online 中嵌入**”选项时，嵌入的报表绝对安全，因此你可以轻松创建安全的内部门户。

## <a name="requirements"></a>要求
若要让“**在 SharePoint Online 中嵌入**”报表正常呈现，需要满足一些要求。

* 适用于 SharePoint Online 的 Power BI（预览）Web 部件要求使用[新式页面](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)。

## <a name="embed-your-report"></a>嵌入报表
若要将报表嵌入 SharePoint Online，首先需要获取报表的 URL，然后在 SharePoint Online 中将此 URL 用于新的 Power BI（预览）Web 部件。

### <a name="get-a-url-to-your-report"></a>获取报表的 URL
1. 在 Power BI 服务中查看报表。
2. 选择“**文件**”菜单项。
3. 选择“**在 SharePoint Online (预览)中嵌入**”。
   
    ![](media/service-embed-report-spo/powerbi-file-menu.png)
4. 复制对话框中的 URL。
   
    ![](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)
   
   > [!NOTE]
   > 还可以使用在查看报表时 Web 浏览器地址栏中显示的 URL。 此 URL 包含当前查看的报表页名称。 若要嵌入不同的页，需要从 URL 中删除报表部分。
   > 
   > 

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>将 Power BI 报表复制到 SharePoint Online 页面
1. 打开相应的 SharePoint Online 页面，然后选择“**编辑**”。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)
   
    或者，在 SharePoint Online 中选择“**+ 新建**”，新建新式网站页面。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)
2. 依次选择 **+** 和“**Power BI (预览)**”Web 部件。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)
3. 选择“**添加报表**”。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)
4. 将报表 URL 粘贴到属性窗格中。 这就是从上述步骤中复制的 URL。 此时，报表会自动加载。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)
5. 选择“**发布**”，让 SharePoint Online 用户可以看到此更改。
   
    ![](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="granting-access-to-reports"></a>授予报表访问权限
在 SharePoint Online 中嵌入报表不会自动授予用户报表查看权限。 需要在 Power BI 服务中设置报表查看权限。

> [!IMPORTANT]
> 请务必在 Power BI 中检查哪些人员可以查看报表，然后向未列出的人员授予访问权限。
> 
> 

在 Power BI 服务中授予报表访问权限的方法有两种。 若要使用 Office 365 组生成 SharePoint Online 团队网站，请在 Power BI 服务中将用户列为应用工作区的成员。 这样就能确保用户可以查看相应组的内容。 有关详细信息，请参阅[在 Power BI 中创建和分发应用](service-create-distribute-apps.md)。

或者，可以按下列步骤来授予用户报表访问权限。

1. 将一个磁贴从报表添加到仪表板。
2. 与需要报表访问权限的用户共享此仪表板。 有关详细信息，请参阅[与同事和其他人共享仪表板](service-share-dashboards.md)。
   
    如果将仪表板与安全组共享，用户至少必须登录 Power BI 一次，才能访问报表。

## <a name="allowing-free-users-access-to-reports"></a>允许 Free 版用户访问报表
Free 版用户可以查看使用适用于 SharePoint Online 的 Power BI Web 部件嵌入的报表。 向 Free 版用户授予访问权限的方式与向 Pro 版用户授予访问权限一样，如上面的[授予报表访问权限](#granting-access-to-reports)中所述。 报表所在的工作区也必须获得 Power BI Premium 容量支持。 

例如，如果应用工作区中有一个报表，必须将此应用工作区分配给 Power BI Premium 容量。 还必须将 Free 版用户添加到此应用工作区的成员列表中。

## <a name="web-part-settings"></a>Web 部件设置
下面介绍了可以为适用于 SharePoint Online 的 Power BI Web 部件调整的设置。

![](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| 属性 | 说明 |
| --- | --- |
| 页名称 |设置 Web 部件显示的默认页。 从下拉列表中选择一个值。 如果下拉列表中未显示任何页，要么是因为报表只有一页，要么是因为粘贴的 URL 包含页名称。 从 URL 中删除报表部分即可选择特定页。 |
| 显示 |用于调整报表如何能与 SharePoint Online 页面浑然一体的选项。 |
| 显示导航窗格 |显示或隐藏报表页导航窗格。 |
| 显示筛选窗格 |显示或隐藏筛选窗格。 |

## <a name="multi-factor-authentication"></a>多重身份验证
如果 Power BI 环境要求使用多重身份验证进行登录，系统可能会提示你使用安全设备登录，从而验证你的身份。 如果未使用多重身份验证登录 SharePoint Online，而 Power BI 环境又要求使用经过安全设备验证的帐户，就会发生这种情况。

> [!NOTE]
> Azure Active Directory 2.0 尚不支持多重身份验证。 用户会看到“*错误*”消息。 如果用户使用安全设备重新登录 SharePoint Online，则可以查看报表。
> 
> 

## <a name="reports-that-do-not-load"></a>报表没有加载
Power BI（预览）Web 部件中可能无法加载报表，并显示以下消息。

*无法加载此内容。*

![](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

看见此消息的常见原因有两个。

1. 无权访问报表。
2. 报表已遭删除。

应与 SharePoint Online 页面的所有者联系，让其帮助你解决此问题。

## <a name="known-issues-and-limitations"></a>已知问题和限制
* 适用于 SharePoint Online 的 Power BI（预览）Web 部件不支持屏幕阅读器或键盘导航。
* **错误：“出错，请尝试注销并重新登录，然后重新访问此页。相关 ID:未定义; http 响应状态: 400;服务器错误代码: 10001;消息:缺少刷新令牌”**
  
  如果看到此错误，请尝试执行下列一项操作。
  
  1. 注销并重新登录 SharePoint。 请务必在重新登录前关闭所有浏览器窗口。
  2. 如果用户帐户要求进行多重身份验证 (MFA)，请务必使用多重身份验证设备（如手机应用、智能卡等）登录 SharePoint
* 添加 Power BI（预览）Web 部件时，看到登录提示，但无法登录。 在这种情况下，将看到以下错误消息之一：
  
  * *我们需要你重新登录。重新登录后，便可以重新回到此处。*
  * *出错，请尝试注销并重新登录，然后重新访问此页。*
  
  若要解决此问题，请确保租户设置为“*针对所有人的首次发布*”，如本文前面的**要求**部分中所述。 为了启用单一登录 (SSO)，Power BI web 部件依赖 SharePoint 提供的 *身份验证 API* ，这些 API 仅在选择 *针对所有人的首次发布* 后可用。
* Power BI 不支持 SharePoint Online 支持的本地化语言。 因此，可能无法在嵌入的报表中看到正确的本地化内容。
* 如果使用的是 Internet Explorer 10，可能会遇到问题。 可以查看 [Power BI 支持的浏览器](service-browser-support.md)和 [Office 365 支持的浏览器](https://products.office.com/office-system-requirements#Browsers-section)。

## <a name="next-steps"></a>后续步骤
[在 Office 365 中设置标准发布或首次发布选项](https://support.office.com/article/Set-up-the-Standard-or-First-Release-options-in-Office-365-3B3ADFA4-1777-4FF0-B606-FB8732101F47)  
[允许或禁止最终用户创建新式网站页面](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
[在 Power BI 中构建和分发应用](service-create-distribute-apps.md)  
[与同事和其他人共享仪表板](service-share-dashboards.md)  
[Power BI Premium 有哪些特权？](service-premium.md)  

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

