---
title: 使用备用电子邮件地址
description: 使用备用电子邮件地址
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/08/2018
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: adc78cceb8a6b6edd06896e53a1a64cf0d28b2b8
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
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

## <a name="updating-through-azure-active-directory"></a>通过 Azure Active Directory 进行更新
捕获 Power BI 的 Active Azure Directory (AAD) 内嵌令牌时，可使用三种不同类型的电子邮件。 这三种类型是：

* 与用户的 AAD 帐户相关联的主要电子邮件地址
* UserPrincipalName (UPN) 电子邮件地址
* “其他”电子邮件地址数组属性

Power 根据以下条件选择要使用的电子邮件：
1.  如果 AAD 租户的用户对象中存在邮件属性，则 Power BI 使用电子邮件地址的此邮件属性
2.  如果 UPN 电子邮件不是 \*.onmicrosoft.com 域电子邮件地址（“\@”符号后面的信息），则 Power BI 使用电子邮件地址的此邮件属性
3.  如果AAD 用户对象中存在“其他”电子邮件数组属性，则将使用该列表中的第一封电子邮件（因为该属性中可能包含电子邮件列表）
4. 如果不满足上述任一条件，则使用 UPN 地址

## <a name="updating-with-powershell"></a>使用 PowerShell 更新
或者，可以通过适用于 Azure Active Directory 的 PowerShell 更新备用电子邮件地址。 此操作通过 [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) 命令完成。

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

有关详细信息，请参阅 [Azure Active Directory PowerShell 版本 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

