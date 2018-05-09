---
title: 在 Power BI Desktop 中使用钻取
description: 了解如何在 Power BI Desktop 中的新报表页上向下钻取数据
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 4/10/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7be260a5989ffb6a9dc1b72dad90d227e0b6295b
ms.sourcegitcommit: bdb1fee3612bcc66153dcad8c4db2e99fb041014
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>在 Power BI Desktop 中使用钻取
通过在 Power BI Desktop 中使用钻取，可以在报表中创建一个侧重于特定实体（如供应商、客户或制造商）的页。 有了这个针对性报表页，用户就可以在其他报表页上右键单击数据点，钻取到具有针对性的页，来获取针对此上下文进行筛选后的详细信息。

![](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>使用钻取
1. 若要使用钻取，请创建一个具有视觉对象的报表页，这些视觉对象应该服务于你计划为其提供钻取的实体类型。 

    例如，如果要为制造商提供钻取，所创建钻取页中的视觉对象就应该体现总销售额、总出货量、按类别筛选的销售额、按地区筛选的销售额等等。 这样一来，当你钻取到该页时，视觉对象将特定于你所选的制造商。

2. 然后，在该钻取页上“可视化效果”窗格的“字段”部分，将你要钻取数据的字段拖动到“钻取筛选器”框中。

    ![](media/desktop-drillthrough/drillthrough_02.png)

    将字段添加到“钻取筛选器”框中后，Power BI Desktop 会自动创建“返回”按钮视觉对象。 该视觉对象在已发布的报表中变成一个按钮，使在 Power BI 服务中使用报表的用户可轻松返回到原始报表页（他们选择进行钻取的页）。

    ![](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>使用你自己的图像作为“后退”按钮    
 由于“后退”按钮是一个图像，可以使用你想要的任何图像来替换此视觉对象的图像，而且它仍然可以作为“后退”按钮正常运行，以便报表使用者可以返回到原始页面。

1. 在“开始”选项卡上，单击“图像”，然后找到图像并将其放置在钻取页上。
2. 在“钻取”页的“格式图像”部分下方选择新的图像，将“链接”滑块设置为“开”，并将“类型”设置为“后退”。 你的图像现充当“后退”按钮。

    ![](media/desktop-drillthrough/drillthrough_05.png)

    当“钻取”页完成，且用户在你的报表中（报表使用你在“钻取筛选器”框中输入的字段）右键单击数据点，上下文菜单会随即出现，以支持钻取到该页。

    ![](media/desktop-drillthrough/drillthrough_04.png)

    当报表使用者选择钻取时，会对该页进行筛选，显示他们右键单击的数据点的相关信息。 例如，如果他们右键单击有关 Contoso（制造商）的数据点，并选择钻取，那么他们所转到的钻取页将被筛选到 Contoso。

    > [!NOTE]
    > 只有“钻取筛选器”框中的字段才会被传递到钻取报表页。 不会传递其他上下文信息。
    > 
    > 

在报表中使用钻取就是这么简单。 通过这个有用的方法，用户可以获取选择用于钻取筛选器的实体信息的扩展视图。

