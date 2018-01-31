---
title: "Power BI 存档工作区"
description: "管理 Office 365 租户之后的 Power BI 存档工作区"
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
ms.date: 06/28/2017
ms.author: maghan
ms.openlocfilehash: 7698a1207f19382430fb8e225543b32b6aebcd49
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-archived-workspace"></a>Power BI 存档工作区
借助 Power BI，任何人都可以在几分钟内进行注册并开始使用服务。  组织的 IT 部门以后可以选择针对组织中的用户接管 Power BI 的管理。  如果进行这种接管，则你会得益于对组织中的用户和权限进行集中管理，并且你能够利用简化登录（使用在组织中用于其他服务的相同用户名和密码）。 

在 IT 部门开始管理 Power BI 之前创建的任何内容都会置于 Power BI 存档工作区中，可从 [Power BI](https://app.powerbi.com) 的左侧导航栏访问该工作区。  应在“我的工作区”中开始创建新 Power BI 内容，这由组织的 IT 部门进行保护和管理。  存档工作区会继续存在，但是对于可以对存档工作区中的内容执行的操作存在一些限制。  若要删除这些限制，你需要将内容从存档工作区迁移到“我的工作区”（由 IT 部门进行管理）。

## <a name="restrictions-in-your-archived-workspace"></a>存档工作区中的限制
不会从存档工作区中删除任何内容。  可以继续获取数据、创建报表和仪表板以及刷新数据集。  将内容与之共享的现有用户也仍然能够在其存档工作区中查看内容。

但是，对存档工作区中的内容存在一些限制：

* **OneDrive for Business。**  对于存档工作区中的数据集，无法再从 OneDrive for Business 获取数据或进行刷新。  如果你尝试连接到此源，则会收到警告。
* **共享仪表板。**  无法在存档工作区中与其他用户共享仪表板。  已获得访问权限的任何用户都继续能够通过访问其存档工作区来查看共享仪表板。
* **创建组。**  无法在存档工作区中创建组。
* **对 Power BI 移动应用的访问权限。**  虽然仍可以在存档工作区中查看 Web 内容，但此内容将不再出现在 Power BI 移动应用中。

## <a name="migrating-content-in-your-archived-workspace"></a>迁移存档工作区中的内容
若要继续使用 Power BI，你应在“我的工作区”（由 IT 部门进行管理）中创建新内容。   还应计划将存档工作区中的任何内容都迁移到“我的工作区”。  迁移内容的方式取决于内容类型：

* **Excel 或 Power BI Desktop 数据集。**  从存档工作区切换到“我的工作区”，然后重新上载 Excel 或 Power BI Desktop 文件（通过单击“我的数据”按钮），可以迁移这些数据集。  如果设置了计划的刷新，则需要在“我的工作区”中为新数据集重新配置这些设置。
* **其他数据集。**  切换到“我的工作区”，然后单击“获取数据”按钮，重新连接在存档工作区中创建的其他任何数据集。  可能需要重新输入安全或连接信息。
* **报表。**  重新上载相应 Excel 或 Power BI Desktop 文件或重新连接内容包后，Excel 或 Power BI Desktop 文件中包含的报表或作为内容包的一部分安装的报表会自动重新创建。  如果你通过 Power BI 服务创建了自己的报表，则需要在“我的工作区”中重新创建这些报表。
* **仪表板。**  在“我的工作区”中重新连接内容包时，作为内容包的一部分安装的仪表板会自动重新创建。  如果你通过 Power BI 服务创建了自己的仪表板，则需要在“我的工作区”中重新创建这些仪表板。

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

