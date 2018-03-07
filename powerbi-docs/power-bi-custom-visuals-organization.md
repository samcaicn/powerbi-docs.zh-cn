---
title: "在 Power BI 中使用组织自定义视觉对象"
description: "在 Power BI 中使用、管理和创建组织的自定义视觉对象"
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
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: 6f7827f7804fcd52e7d922ebc8ffad5a8036b33c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="using-organization-custom-visuals-in-power-bi-preview"></a>在 Power BI 中使用组织自定义视觉对象（预览）

可以在 Power BI 中使用自定义视觉对象创建为你量身定做的唯一视觉对象类型或你尝试传达的数据见解。 通常由开发人员创建这些自定义视觉对象，在 Power BI 中包含的大部分视觉对象不是十分满足他们的需求时，常常会创建此类视觉对象。 

在某些组织中，自定义视觉对象尤为重要，可能必须使用它们来传递特定数据或组织的唯一见解，它们可能具有特殊数据要求，或者可以高亮显示专用业务方法。 此类组织需要开发自定义视觉对象，在其整个组织中共享这些视觉对象，并确保对其进行正常维护。 Power BI 自定义视觉对象（现处于预览状态）可让组织实现上述目标。 

下图显示了 Power BI 中的组织自定义视觉对象（预览）从管理员处通过开发和维护最终转到数据分析人员处的过程。

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

## <a name="how-to-enable-organizational-custom-visuals-preview"></a>如何启用组织的自定义视觉对象（预览）

组织自定义视觉对象当前处于预览状态，因此必须在 Power BI Desktop 中启用此功能。 若要启用此预览功能，从功能区选择“文件”>“选项和设置”>“选项”，然后在左侧窗格中选择“预览”功能，再选中“我的组织自定义视觉对象”旁边的复选框，如下图所示。

![](media/power-bi-custom-visuals-organizational/custom-visual-org-02.jpg)

由管理门户的 Power BI 管理员部署和管理组织视觉对象。 视觉对象一旦部署到组织的存储库，组织中的用户便可以轻松发现它们，并直接从 Power BI Desktop 将组织的自定义视觉对象导入其报表。

## <a name="using-organizational-custom-visuals"></a>使用组织的自定义视觉对象

若要详细了解如何在创建的报表中使用组织的自定义视觉对象，请参阅以下文章：[详细了解如何将组织的视觉对象导入报表](power-bi-custom-visuals.md)。
 
## <a name="administering-organizational-custom-visuals"></a>管理组织的自定义视觉对象

若要详细了解如何管理、部署和管理组织中的组织自定义视觉对象，请参阅以下文章：[详细了解如何部署和管理组织自定义视觉对象](https://go.microsoft.com/fwlink/?linkid=866790)。

> [!WARNING]
> 自定义视觉对象可能包含存在安全或隐私风险的代码。 在将其部署到组织存储库之前，请务必信任任何自定义视觉对象的作者和来源。 
> 

## <a name="considerations-and-limitations"></a>注意事项和限制
 
由于组织的自定义视觉对象处于预览状态，因此，需要了解并考虑一些注意事项和限制。
 
管理员：

* 不支持旧的自定义视觉对象（如不是基于新版本的 API 生成的自定义视觉对象）

* 尚不支持就地更新。 若要更新视觉对象，必须将新版本的视觉对象上传至组织存储库（还要确保其在 PBIVIZ 文件中具有相同的视觉对象 ID）。 然后报表作者可将新版本导入他们的报表，并在报表中就地替换其当前版本的视觉对象。

* 如果从存储库中删除自定义视觉对象，那么使用已删除的视觉对象的任何现有报表将不再呈现。 存储库中的删除操作是不可逆的。
 
最终用户：

* 不支持使用来自开放的商城 (AppSource) 和组织存储库的相同视觉对象（相同视觉对象 ID）。 在这种情况下，将使用已导入的最新视觉对象。

* 不支持在仪表板和报表中外部共享组织的视觉对象。 通过组织的自定义视觉对象查看仪表板的组织外部用户将看到一个空白的视觉对象。 

* Power BI 工作区集合不支持使用组织视觉对象

* 报表中发布到网站的组织自定义视觉对象将不会呈现

* 如果来自 AppSource 商城的 Visio 视觉对象、PowerApps 视觉对象和 GlobeMap 视觉对象通过组织存储库部署，它们将不会呈现

* 如果管理员从存储库中删除自定义视觉对象，且该视觉对象被用于某个报表中，则该视觉对象将不再呈现，同时必须从报表中将其删除才能保存报表