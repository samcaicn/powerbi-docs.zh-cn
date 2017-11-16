---
title: "Power BI 中的模板内容包体验"
description: "模板内容包体验"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 10/09/2017
ms.author: asaxton
ms.openlocfilehash: bf7dbb16a1b84ab4045a1de4d80199c8d27e682a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="template-content-pack-experiences-in-power-bi"></a>Power BI 中的模板内容包体验
本节重点介绍了连接到 ISV [内容包](../service-connect-to-services.md)的用户典型体验。 

通过连接到已发布的内容包，尝试连接体验，地址是 https://app.powerbi.com/getdata/services（例如以下所述的 [GitHub 内容包](https://app.powerbi.com/getdata/services/github)）。

## <a name="connect"></a>连接
若要开始，用户需浏览内容包库并选择要连接的内容包。 内容包条目提供名称、图标以及为用户提供详细信息的描述性文本。

![连接](media/template-content-pack-experience/github_data.png)

![连接](media/template-content-pack-experience/github_connect.png)

## <a name="parameters"></a>参数
选择后，将提示用户提供参数（如果需要）。 内容包创建过程中作者以声明的方式提供参数对话框。

当前的参数 UI 是非常基本的 – 没有枚举下拉列表的方法且数据输入验证限制为正则表达式。

![参数](media/template-content-pack-experience/github_params.png)

## <a name="credentials"></a>凭据
提供参数后，将提示用户登录。  如果源支持多个类型的身份验证，用户应选择相应的选项。 如果源需要 OAuth，那么当用户按“登录”后，将弹出该服务的登录 UI。  否则，用户可以在提供的对话框中输入其凭据。

![凭据](media/template-content-pack-experience/github_login.png)

![连接](media/template-content-pack-experience/github_creds2.png)

## <a name="instantiation"></a>实例化
登录成功后，内容包中的项目（模型、报表和仪表板）会显示在导航栏中。  这些项目将添加到每个用户的帐户中。  数据以异步方式加载来填充数据集（模型）。  然后，用户就能够使用仪表板、报表和模型。

默认情况下，会为用户配置每日刷新计划，这将重新评估模型中的查询。  提供给用户的凭据必须允许他们可不在场刷新数据。

![实例化](media/template-content-pack-experience/github_dashboard.png)

## <a name="exploration-and-monitoring"></a>浏览和监视
内容包被包含到用户帐户后，用户就可以搜索和监视数据/见解。

这通常包括：

* 查看并自定义仪表板。
* 查看并自定义报表。
* 使用自然语言提出有关数据的问题
* 使用浏览画布浏览数据模型中的数据

应考虑提供自然语言建模（同义词）和易于理解的模型架构，以实现更好的浏览体验。

