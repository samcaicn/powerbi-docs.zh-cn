---
title: 管理员如何管理 Power BI Desktop 登录窗体
description: 了解打开 Power BI Desktop 时如何管理初始登录窗体。
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/02/2018
ms.author: davidi
ms.openlocfilehash: f35553acd65aeea2c1bf02b04fcbd665af4b99ea
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721078"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>管理员如何管理 Power BI Desktop 登录窗体
首次启动 Power BI Desktop 时，将会看到登录窗体。 若要继续操作，可以填写信息或登录 Power BI。 管理员可以使用注册表项来管理此窗体。 

![Power BI Desktop 的初始登录窗体](media/desktop-admin-sign-in-form/sign-in-form.png)

管理员可以使用以下注册表项禁用登录窗体。 还可以使用全局策略将其推送到整个组织。

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

值为 0 将禁用此对话框。

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

