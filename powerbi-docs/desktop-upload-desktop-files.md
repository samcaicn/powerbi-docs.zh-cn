---
title: "从 Power BI Desktop 进行发布"
description: "从 Power BI Desktop 进行发布"
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: deb3e76fff2f8b5d1a275df70f485b02d94523b7
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="publish-from-power-bi-desktop"></a>从 Power BI Desktop 进行发布
将 **Power BI Desktop** 文件发布到 **Power BI 服务**后，模型中的数据以及你在“**报表**”视图中生成的所有报表都会发布到 Power BI 工作区。 你将看一个同名的新数据集以及工作区导航器中的任何报表。

从 **Power BI Desktop** 发布文件等效于在 Power BI 中使用“**获取数据**”连接并上载 **Power BI Desktop** 文件。

> [!NOTE]
> 在报表 Power BI 中进行的任何更改（例如，添加、删除或更改报表中的可视化效果）将不会保存到原始 Power BI Desktop 文件中。
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>发布 Power BI Desktop 数据集和报表
1. 在 Power BI Desktop 中，单击\>**文件** \> **发布** \> **发布到 Power BI**，或在功能区上单击**发布**。  
   ![](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)
2. 登录到 Power BI。

完成后，你将获得一个链接，可使用该链接在 Power BI 站点中打开报表。  
    ![](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="re-publish-or-replace-a-dataset-published-from-power-bi-desktop"></a>重新发布或替换从 Power BI Desktop 中发布的数据集
发布 **Power BI Desktop** 文件后，数据集和你在 **Power BI Desktop** 中生成的所有报表都会上载到 Power BI 站点。 重新发布 **Power BI Desktop** 文件后，Power BI 站点中的数据集将替换为 **Power BI Desktop** 文件中已更新的数据集。

此过程很直接，但你仍应了解几个事项 ︰

* 如果 Power BI 中有两个或多个与 **Power BI Desktop** 文件同名的数据集，则发布操作可能会失败。 请确保你在 Power BI 中只具有一个同名的数据集。 也可以重命名文件然后进行发布，这将创建一个与文件同名的新数据集。
* 如果重命名或删除列或度量值，则你已在 Power BI 中具有的含该字段的任何可视化可能会被破坏。 
* Power BI 将忽略对现有列某些格式的更改。 例如，如果你将列的格式从 0.25 更改为 25%。
* 如果你为 Power BI 中的现有数据集配置了刷新计划，然后重新发布添加了新数据源的文件，必须在执行下一次计划的刷新之前在“管理数据源”中签署它们。

