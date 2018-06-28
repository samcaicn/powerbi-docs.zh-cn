---
title: Power BI Desktop 中的条件表格格式设置
description: 对表格应用自定义格式设置
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 70aa61d6a02bea1b7058a68b20718008ace1b8c8
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "34480879"
---
# <a name="conditional-formatting-in-tables"></a>表格中的条件格式设置 
通过表格的条件格式设置，可根据单元格值或其他值/字段指定自定义单元格颜色，包括使用渐变色。 也可用数据条显示单元格值。 

若要访问条件格式，请在 Powr BI Desktop“可视化效果”窗格的“字段”格中，选择要设置其格式的“值”格中值旁边的向下箭头（或右键单击该字段）。 只能管理“字段”格的“值”区域中字段的条件格式。

![“条件格式”菜单](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

以下各节逐一介绍了这三个条件格式选项。 可在单个表列中使用一个选项或组合使用多个选项。

> [!NOTE]
> 应用到表后，条件格式将替代应用到已进行条件格式设置的单元格的任意自定义表格样式。

若要从可视化效果中删除条件格式，只需再次右键单击该字段，并选择删除条件格式和要删除的格式类型即可。

![删除条件格式菜单](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

## <a name="background-color-scales"></a>背景色阶

选择“条件格式”和“背景色阶”后，将显示以下对话框。

![背景色阶对话框](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

可通过将数据模型中的某一字段设置为“着色依据”，选择将其作为着色依据。 此外，可使用“汇总”值，为选定字段指定聚合类型。 在“将颜色应用到”字段中指定要着色的字段，以便进行跟踪。只要选择一个数值作为格式设置的基础，即可将条件格式应用于文本和日期字段。

![“着色依据”字段](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

若要对给定值范围使用离散的颜色值，请选择“根据规则着色”。 若要使用色谱，请将“根据规则着色”保持为未选中状态。 

![背景色阶对话框](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

### <a name="color-by-rules"></a>根据规则着色

选择“根据规则着色”后，可以输入一个或多个值范围，每个范围使用一种设定的颜色。  每个值范围以“如果”值条件、“和”值条件和一种颜色开头。

![“根据规则着色”值范围](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

使用给定颜色填充包含处于每个范围内的值的表单元格。 下图中包含三条规则。

![“根据规则着色”示例](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules.png)

示例表现如下所示：

![使用“根据规则着色”选项的示例表](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)


### <a name="color-minimum-to-maximum"></a>最小值到最大值着色

可以配置最小值和最大值及其颜色。 如果选择“散射”框，还可以配置一个可选的“居中”值。

![“散射”按钮](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

示例表现如下所示：

![使用散射色的示例表](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

## <a name="font-color-scales"></a>字体色阶

选择“条件格式”和“字体色阶”后，将显示以下对话框。 此对话框类似于“背景色阶”对话框，但更改的是字体颜色而不是单元格背景色。

![“字体色阶”对话框](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

示例表现如下所示：

![使用字体色阶的示例表](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="data-bars"></a>数据条

选择“条件格式”和“数据条”后，将显示以下对话框。 

![数据条对话框](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

默认情况下，“仅显示数据条”选项处于未选中状态，因此表格单元格同时显示数据条和实际值。

![使用数据条和值的示例表](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

如果“仅显示数据条”选项处于选中状态，表单元格将仅显示数据条。

![仅使用数据条的示例表](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)
