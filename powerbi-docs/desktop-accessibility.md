---
title: Power BI Desktop 报表中的辅助功能
description: 用于创建可访问 Power BI Desktop 报表的功能和建议
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: bd0565420382fc22af67b1363b41f6d8ed6e92ab
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290743"
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>Power BI Desktop 报表中的辅助功能
Power BI Desktop 具有使残疾人士能够更轻松地使用 Power BI Desktop 报表并与之进行交互的功能。 这些功能包括通过键盘或屏幕阅读器使用报表、通过按 Tab 键将焦点移动到页面中的各个对象以及在可视化效果中方便地使用标记。

![在折线图和分区图中使用不同的标记来改善辅助功能](media/desktop-accessibility/accessibility_01.png)

> [!NOTE]
> 这些辅助功能在 2017 年 6 月 Power BI Desktop 和更高版本中可用。 我们也为将来的版本规划了其他辅助功能。
> 
> 

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>通过键盘或屏幕阅读器使用 Power BI Desktop 报表
从 2017 年 9 月发行版 Power BI Desktop 开始，可以按 ? 键显示一个窗口，其中介绍了中可在 Power BI Desktop 中使用的辅助功能键盘快捷方式。

![在 Power BI Desktop 中按 ? 键可显示辅助功能键盘快捷方式](media/desktop-accessibility/accessibility_03.png)

借助辅助功能的增强功能，可以使用以下方法通过键盘或屏幕阅读器使用 Power BI Desktop 报表：

可以使用 Ctrl+F6 在报表页选项卡或在给定的报表页中的对象之间切换焦点。

* 当焦点位于报表页选项卡上时，使用 Tab 或箭头键将焦点从一个报表页移到下一个报表页。 无论当前是否被选中，屏幕阅读器都会读出报表页的标题。 若要加载当前焦点所在的报表页，使用 Enter 或空格键。
* 当焦点位于已加载的报表页上时，使用 Tab 键将焦点转移到页面上的每个对象，其中包括所有文本框、图像、形状和图表。 屏幕阅读器读取对象的类型及其作者提供的该对象的说明。 

按 Alt+Shift+F10 可以将焦点移到视觉对象菜单。

按 Alt+Shift+F11 可以访问“查看数据”窗口。

![在 Power BI Desktop 中按 Alt+Shift+F11 可访问视觉对象的“查看数据”窗口](media/desktop-accessibility/accessibility_04.png)

创建这些附加辅助功能是为了让用户通过屏幕读取器和键盘导航充分利用 Power BI Desktop 报表。

## <a name="tips-for-creating-accessible-reports"></a>创建可访问报表的提示
以下提示可帮助你创建更易于访问的 Power BI Desktop 报表。

* 对于“行”、“区域”、“组合图”、“散点图”和“气泡”视觉对象，请启用标记，并对每行使用不同的标记形状。
  
  * 若要启用“标记”，可在“可视化效果”窗格中选择“格式”部分，展开“形状”部分，然后向下滚动查找“标记”切换，并将其切换为“开”。
  * 然后，从“形状”部分中的下拉列表框中选择每行（如果使用区域图表，则为区域）的名称。 在下拉列表下方，可以调整用于所选行的标记的许多方面，包括其形状、颜色和大小。
  
  ![在折线图和分区图中使用不同的标记来改善辅助功能](media/desktop-accessibility/accessibility_01.png)
  
  * 对每行使用不同的标记形状可使报表使用者更容易区分行（或区域）。
* 作为上一个项目符号的后续内容，不要依赖颜色传达信息。 使用行上的形状（标记，如上一项目符号中所述）很有帮助。
* 从主题库中选择一个高对比度、适合色盲人士的主题，然后使用[**主题**预览功能](desktop-report-themes.md)将其导入。
* 为报表上的每个对象提供替换文字。 这可确保报表使用者了解你想通过视觉对象表达的内容，即使他们看不见视觉对象、图像、形状或文本框。 在“可视化效果”窗格中选中对象（例如视觉对象、形状等），选择“格式”部分，展开“常规”，然后滚动到底部并填写“替换文字”文本框，可为 Power BI Desktop 报表上的任何对象提供“替换文字”。
  
  ![可在“可视化效果”>“格式”>“常规”>“替换文字”框中为报表中的任何对象添加替换文字](media/desktop-accessibility/accessibility_02.png)
* 请确保报表在文本和任意背景颜色之间有足够的对比度。
* 使用易于阅读的文本大小和字体。 文本太小或难以阅读的字体对辅助功能没有任何帮助。
* 包括所有视觉对象中的标题、轴标签和数据标签。

## <a name="considerations-and-limitations"></a>注意事项和限制
辅助功能存在一些已知问题和限制，如以下列表所述：

* 在 Power BI 服务中查看的报表（包括任何嵌入的报表）支持 JAWS。 虽然 Power BI Desktop 也支持 JAWS，但在打开任何 Power BI Desktop 文件前，必须先打开屏幕阅读器，这样屏幕阅读功能才能正常发挥作用。

## <a name="next-steps"></a>后续步骤
* [在 Power BI Desktop 中使用报表主题（预览版）](desktop-report-themes.md)

