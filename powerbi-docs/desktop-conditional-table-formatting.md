---
title: Power BI Desktop 中的条件表格格式设置
description: 对表格应用自定义格式设置
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 9599b40940c9d9cca254bb2ed2e87c161cce371f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="conditional-formatting-in-tables"></a>表格中的条件格式设置
通过表格的条件格式设置，可根据单元格值或其他值/字段指定自定义单元格背景色，还可使用渐变色。 若要访问条件格式，请在 Powr BI Desktop“可视化效果”窗格的“字段”格中，选择要设置其格式的“值”格中值旁边的向下箭头（或右键单击该字段）。 只能管理“字段”格的“值”区域中字段的条件格式。

![表格的条件格式设置](media/desktop-conditional-table-formatting/table-formatting_1.png)

在随即显示的对话框中，可以配置颜色，以及最小和最大值。 如果选择“散射”框，还可以配置一个可选的“居中”值。

![散射色](media/desktop-conditional-table-formatting/table-formatting_2.png)

也可根据数据模型中的字段建立颜色渐变层。 此外，可指定所选字段的聚合类型（在“将颜色应用到”字段中指定所选字段进行跟踪）。

![字段的基本颜色](media/desktop-conditional-table-formatting/table-formatting_2b.png)

应用到表后，使用上述步骤应用的自定义格式将替代应用到已进行条件格式设置的单元格的任意自定义表格样式。

![表格式化](media/desktop-conditional-table-formatting/table-formatting_3.png)

只要选择一个数值作为格式设置的基础，还可将条件格式应用于文本和日期字段。 

若要从可视化效果中删除条件格式，只需再次右键单击该字段，并选择**删除条件格式**即可。

![删除表格式设置](media/desktop-conditional-table-formatting/table-formatting_4.png)

