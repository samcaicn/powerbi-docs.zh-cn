---
title: "使用备用电子邮件地址"
description: "使用备用电子邮件地址"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 08/09/2017
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: c97f60e39d68060c8eb3396bac4eb7725dab9c86
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="using-an-alternate-email-address"></a>使用备用电子邮件地址
默认情况下，你用于注册 Power BI 的电子邮件地址用于向你发送有关 Power BI 中的活动的有关更新。  例如，当有人向你发送共享邀请时，它会转到此地址。

有时你可能希望这些电子邮件传递到备用电子邮件地址，而不是最初用于注册 Power BI 的电子邮件地址。

## <a name="updating-through-office-365-personal-info-page"></a>通过 Office 365 个人信息页面更新
1. 转到你的 [Office 365 个人信息页面](https://portal.office.com/account/#personalinfo)。  如果系统提示你使用用于 Power BI 的电子邮件地址和密码登录，请执行此操作。
2. 单击联系人详细信息部分中的编辑链接。  
   
   > [!NOTE]
   > 如果看不到编辑链接，则这意味着你的电子邮件地址由 Office 365 管理员管理，你需要与他们联系以更新你的电子邮件地址。
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. 在备用电子邮件字段中，输入希望将 Power BI 更新发送到的电子邮件地址。

> [!NOTE]
> 更改此设置不会影响用于发送服务更新、新闻稿和其他促销通讯信息的电子邮件地址。  这些内容会始终发送到在注册 Power BI 时最初使用的电子邮件地址。
> 
> 

## <a name="updating-with-powershell"></a>使用 PowerShell 更新
或者，可以通过适用于 Azure Active Directory 的 PowerShell 更新备用电子邮件地址。 此操作通过 [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) 命令完成。

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

有关详细信息，请参阅 [Azure Active Directory PowerShell 版本 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

