---
title: "Power BI Desktop 中的关系视图"
description: "Power BI Desktop 中的关系视图"
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: e94977a8b9a106798f0facd962d6e766f6410da3
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="relationship-view-in-power-bi-desktop"></a>Power BI Desktop 中的关系视图
**关系视图**显示模型中的所有表、列和关系。 这在模型包含许多表且其关系十分复杂时尤其有用。

让我们来看一下。

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  关系视图图标 – 单击可显示关系视图中的模型

**B.** 关系 – 可以将光标悬停在关系上方以显示所用列。 双击关系以在“编辑关系”对话框中将其打开。 

在上图中，你可以看到 *商店* 表中有一个与 *销售额* 表（其中同样含有 *StoreKey* 列）相关的 *StoreKey* 列。 我们可以看到这是*多对一* (\*:1) 关系，线中间的图标指出交叉筛选器方向设置为*两者*。 图标上的箭头表示筛选上下文流的方向。

有关关系的详细信息，请参阅[在 Power BI Desktop 中创建和管理关系](desktop-create-and-manage-relationships.md)。

