---
title: "在 Power BI 中使用书签（预览功能）"
description: "使用 Power BI Desktop 中的书签，可以保存报表中的视图和设置，并生成类似于情景的演示文稿"
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: e60ff6d06e4ac0cddf398ccfc1d30e4d97e0773c
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="use-bookmarks-to-share-insights-and-build-stories-in-power-bi-preview"></a>使用书签在 Power BI 中共享见解和创建情景（预览版）
使用 Power BI 中的“书签”，可以捕获当前配置的报表页视图（包括视觉对象的筛选器和状态），然后只需选择保存的书签即可恢复相应状态。 

还可以创建一系列书签，按所需的顺序进行排列，随后在演示文稿中逐个展示所有书签，以突出显示一系列见解，或要通过视觉对象和报表诠释的情景。 

![Power BI 中的书签](media/desktop-bookmarks/bookmarks_01.png)

书签的用途有许多。 可以使用书签跟踪自己的报表创建进度（书签易于添加、删除和重命名），也可以通过创建书签来生成类似于 PowerPoint 的演示文稿，依序逐一展示所有书签，通过报表诠释情景。 书签可能还有其他用途，具体取决于用户认为如何才能最有效地利用书签。

### <a name="enable-the-bookmarks-preview"></a>启用“书签”预览功能
自 2017 年 10 月发布的 Power BI Desktop 起，可以尝试新推出的“书签”功能，并用于 Power BI 服务中启用了书签的报表。 若要启用此预览功能，请依次选择“文件”>“选项和设置”>“选项”>“预览功能”，再选中“书签”旁边的复选框。 完成选择后需要重启 Power BI Desktop。

![在“选项”窗口中启用书签](media/desktop-bookmarks/bookmarks_02.png)

选中此复选框后，需要重启 **Power BI Desktop**。

## <a name="using-bookmarks"></a>使用书签
若要使用书签，请选择“视图”功能区，再选中“‘书签’窗格”对应的框。 

![通过选中“视图”功能区中的“‘书签’窗格”来显示此窗格。](media/desktop-bookmarks/bookmarks_03.png)

创建书签时，以下元素将与书签一起保存：

* 当前页
* 筛选器
* 切片器
* 排序顺序
* 钻取位置
* 可见性（对象可见性，使用“选择”窗格）
* 任何可见对象的“焦点”或“聚焦”模式

书签暂不保存交叉突出显示状态。 

配置报表页，确保它在书签中的显示效果符合自己的要求。 按照所需方式排列报表页和视觉对象后，选择“书签”窗格中的“添加”，添加一个书签。 

![添加书签](media/desktop-bookmarks/bookmarks_04.png)

此时，Power BI Desktop 创建书签，并为它命名一个通用名称。 可以选择书签名称旁边的省略号，再从出现的菜单中选择相应操作，从而轻松地重命名、删除或更新书签。

![选择省略号后选择书签的子菜单](media/desktop-bookmarks/bookmarks_05.png)

添加书签后，只需单击“书签”窗格中的书签，即可显示它。 

## <a name="arranging-bookmarks"></a>排列书签
创建书签时，可能会发现，书签的创建顺序不一定就是向受众展示书签的顺序。 这也没问题，因为可以轻松地对书签进行重新排序。

在“书签”窗格中，只需拖放书签，即可更改它们的顺序，如下图所示。 书签之间的黄色栏决定了书签的拖放目标位置。

![通过拖放更改书签顺序](media/desktop-bookmarks/bookmarks_06.png)

使用书签的“查看”功能时，书签顺序可能会变得非常重要，如下一部分所述。

## <a name="bookmarks-as-a-slide-show"></a>以幻灯片形式放映书签
若要依序展示一系列书签，可以选择“书签”窗格中的“查看”，开始放映幻灯片。

在“查看”模式下，有几项功能值得注意：

1. 书签名称显示在画布底部的书签标题栏中。
2. 书签标题栏中的箭头可用于移到下一个或上一个书签
3. 可以退出“查看”模式，具体方法为选择“书签”窗格中的“退出”，或选择书签标题栏中的“X”。 

![书签标题栏中与书签相关的功能](media/desktop-bookmarks/bookmarks_07.png)

在“查看”模式下，可以关闭“书签”窗格（单击此窗格上的“X”），为演示文稿提供更多空间。 同时，在“查看”模式下，所有视觉对象都可以进行交互和交叉突出显示，就像在其他情况下与它们交互时一样。 

## <a name="visibility---using-the-selection-pane"></a>可见性 - 使用“选择”窗格
发布书签后，同时也会引入新的“选择”窗格。 “选择”窗格列出了当前页上的所有对象，方便用户选择对象，并指定给定对象是否可见。 

![启用“选择”窗格](media/desktop-bookmarks/bookmarks_08.png)

可以使用“选择”窗格选择对象。 此外，还可以单击视觉对象右侧的眼睛图标，切换设置对象当前是否可见。 

![“选择”窗格](media/desktop-bookmarks/bookmarks_09.png)

添加书签时，每个对象的可见状态也随之保存，具体视“选择”窗格中的设置而定。 

请务必注意，“切片器”会继续筛选报表页，无论它们是否可见。 因此，可以创建切片器设置不同的多个书签，让一个报表页在各种书签中呈现出截然不同的显示效果（并突出显示不同的见解）。

## <a name="bookmarks-for-shapes-and-images"></a>形状和图像的书签关联
还可以将形状和图像与书签相关联。 借助此功能，在单击对象后，将会看到与这个对象相关联的书签。 

若要将书签分配给对象，请依次选择对象和“设置形状格式”窗格中的“关联”，如下图所示。

![向对象添加书签链接](media/desktop-bookmarks/bookmarks_10.png)

将“关联”滑块移至“开”后，便可以选择对象是链接还是书签。 如果选择书签，可以选择要与对象相关联的书签。

对于与书签相关联的对象，可以执行各种有意思的操作。 可以在报表页上创建可视内容表，也可以提供相同信息的不同视图（如视觉对象类型），只需单击对象即可。

在编辑模式下，可以在按住 Ctrl 的同时单击，从而访问关联的书签；在非编辑模式下，只需单击对象，即可访问关联的书签。 

## <a name="using-spotlight"></a>使用“聚焦”
与书签一起发布的另一项功能是“聚焦”。 使用“聚焦”，可以吸引用户注意特定图表。例如，在“查看”模式下呈现书签。

比较一下“聚焦”与“焦点”模式，看看它们有何不同。

1. 在“焦点”模式下，可以选择“焦点模式”图标，让一个视觉对象占满整个画布。
2. 使用“聚焦”模式，可以让页面上的其他所有视觉对象淡化到接近透明，从而按原始尺寸突出显示一个视觉对象。 

![比较“焦点”与“聚焦”模式](media/desktop-bookmarks/bookmarks_11.png)

如果在上一张图中单击视觉对象的“焦点”图标，页面如下所示：

![“焦点”模式](media/desktop-bookmarks/bookmarks_12.png)

相比之下，如果选择视觉对象的省略号菜单中的“聚焦”，页面如下所示：

![“聚焦”模式](media/desktop-bookmarks/bookmarks_13.png)

如果在添加书签时选择了上述模式中的任何一种，书签中会一直保留此模式（“焦点”或“聚焦”）。

## <a name="bookmarks-in-the-power-bi-service"></a>Power BI 服务中的书签
将包含至少一个书签的报表发布到 Power BI 服务后，可以在 Power BI 服务中查看这些书签，并与之交互。 对于发布的每个报表，至少必须在发布前在报表中创建一个书签，才能在 Power BI 服务中使用书签功能。

在报表中创建书签后，可以依次选择“视图”和“‘选择’窗格”，也可以依次选择“视图”和“‘书签’窗格”，从而显示每个窗格。

![在 Power BI 服务中查看“书签”和“选择”窗格](media/desktop-bookmarks/bookmarks_14.png)

在 Power BI 服务中，“书签”窗格的使用方式与在 Power BI Desktop 中一样，包括可以选择“查看”功能，依序展示书签，如同放映幻灯片一样。

请注意，必须使用灰色书签标题栏来浏览书签，而不是黑色箭头（黑色箭头用于切换报表页，而非书签）。

## <a name="limitations-and-considerations"></a>限制和注意事项
这一版“书签”预览功能有一些限制和注意事项。

* 如果自定义视觉对象是筛选器的源，则不支持书签。 若要使用自定义视觉对象（例如，Chiclet 切片器）筛选页面上的元素，并使用书签返回到此页面，那么页面可能会进行筛选，但自定义视觉对象不会进行更新来反映页面已经过筛选。 
* 创建书签时，报表窗格的交叉突出显示状态不会一起保存。 
* 如果在创建书签后在报表页上添加视觉对象，此视觉对象将以默认状态显示。 也就是说，如果在之前创建书签的页面中引入切片器，此切片器将在默认状态下运行。
* 创建书签后，如果移动视觉对象，书签中也会予以反映。 
* 将报表发布到 **Power BI 服务**时，报表中至少必须有一个书签，才能在此服务中使用书签。 发布的每个报表都必须满足此要求。
* 由于书签目前是一项预览版功能，它们尚不能在[**适用于报表服务器的 Power BI Desktop**](report-server/quickstart-create-powerbi-report.md) 中使用。

## <a name="next-steps"></a>后续步骤
若要详细了解与书签类似的功能或如何与书签交互，请参阅以下文章：

* [在 Power BI Desktop 中使用钻取](desktop-drillthrough.md)
* [在“焦点”模式下显示仪表板磁贴或报表视觉对象](service-focus-mode.md)

