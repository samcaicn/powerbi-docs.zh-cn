---
title: Power BI Premium 支持大型数据集
description: Power BI Premium 现在支持不超过 10 GB 的数据集。
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/27/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: fa05fd6808ebe78d5d17e2ad3d93fbcf22f7d3c9
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Power BI Premium 支持大型数据集

Power BI Premium 支持上传大小不超过 10 GB 的 Power BI Desktop (.pbix) 文件。 上传后，数据集可被刷新为不超过 12 GB 的大小。 要使用大型数据集，请将其发布到分配给高级容量的工作区。
 
## <a name="best-practices"></a>最佳做法

本节介绍处理大型数据集的最佳做法。

根据你的容量，大型模型可能会非常耗费资源；对于任何大于 1 GB 的模型，我们建议至少使用 P1 SKU。 下表介绍了适合各种 .pbix 大小的建议 SKU 型号：


   |SKU  |.Pbix 大小   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3    | 最多 10 GB   |



.pbix 文件表示处于高度压缩状态的数据。 数据在加载到内存中时可能会多次扩展，并且在数据刷新期间可能会在内存中再次扩展数次。

对大型数据集进行计划的刷新可能需要很长时间，并且会占用大量资源。 因此，不要安排太多的重叠刷新。 另外，还要注意，对于此容量中的所有数据集，计划的刷新作业的超时时间已经增加了一倍，达到了四个小时。

如果自从上次使用数据集以来已经过一段时间，则大型数据集的初始报表加载可能需要很长时间，因为模型已加载到高级容量的内存中。 需要较长时间加载的报表的加载条可显示加载进度。

如果你从高级容量中删除工作区，则模型和所有关联的报表和仪表板将不起作用。

尽管高级容量中的每个查询内存和时间约束要高得多，但强烈建议使用筛选器和切片器来将视觉对象限制为仅显示必要的内容。

## <a name="next-steps"></a>后续步骤
[什么是 Power BI Premium？](service-premium.md)  
[Power BI Premium 发行说明](service-premium-release-notes.md)  
[Microsoft Power BI Premium 白皮书](https://aka.ms/pbipremiumwhitepaper)  
[规划 Power BI Enterprise 部署白皮书](https://aka.ms/pbienterprisedeploy)  
[激活延长的 Power BI Pro 试用期](service-extended-pro-trial.md)  

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)
