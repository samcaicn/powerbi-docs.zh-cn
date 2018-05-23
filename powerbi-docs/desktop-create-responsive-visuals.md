---
title: 将 Power BI 视觉对象优化为适应任意大小
description: 了解如何在 Power BI Desktop 和 Power BI 服务的现有报表中将视觉对象优化为更适合在 Power BI 手机应用中显示。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: a6e683318c00a800f69334f90ce3a71d74489030
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>将 Power BI 视觉对象优化为适应任意大小
默认情况下，在创建新报表时，视觉对象为响应式：它们会动态缩放，尽可能显示最多的数据和见解，无论屏幕大小如何。 对于较旧的报表，也可以将其视觉对象设置为动态重设大小。

在视觉对象缩放时，Power BI 会优先确保显示数据视图。例如，自动删除填充，并将图例移至视觉对象顶部，这样即便视觉对象变小，也仍可提供信息。 在手机上的 Power BI 移动应用中，响应式视觉对象尤为有用。

![响应式视觉对象重设大小](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

任何包含 X 轴、Y 轴和切片器的视觉对象都可以响应式重设大小。

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>在 Power BI Desktop 中启用响应式设置
1. 在 Power BI Desktop 旧报表的“视图”选项卡上，确保自己处于“桌面设备布局”中。
   
    ![“桌面布局”图标](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. 选择视觉对象，在“可视化效果”窗格中，选择“格式”部分。
3. 展开“常规”，并将“响应式”滑至“开”。
   
    ![“响应式”为“开”](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     现在，[创建更适合在手机上显示的报表](desktop-create-phone-report.md)并添加此视觉对象后，它可以流畅地重设大小。

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>在 Power BI 服务中启用响应式设置
在 Power BI 服务中，可以为旧报表中的视觉对象启用响应式设置。 必须能够编辑报表。

1. 在 Power BI 服务报表中 ([https://powerbi.com](https://powerbi.com))，选择“编辑报表”。
2. 选择视觉对象，在“可视化效果”窗格中，选择“格式”部分。
3. 展开“常规”，并将“响应式”滑至“开”。
   
    ![“响应式”为“开”](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     现在，[创建此报表的手机视图](desktop-create-phone-report.md)并添加此视觉对象后，它可以流畅地重设大小。

## <a name="next-steps"></a>后续步骤
* [创建针对 Power BI 手机应用的优化报表](desktop-create-phone-report.md)
* [查看针对你的电话进行优化的 Power BI 报表](mobile-apps-view-phone-report.md)
* 更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

