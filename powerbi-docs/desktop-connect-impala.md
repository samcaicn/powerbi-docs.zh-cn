---
title: 在 Power BI Desktop 中连接到 Impala 数据库
description: 通过 Power BI Desktop 轻松连接并使用 Impala 数据库
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9b00120a0c4c22ba8f031663ab19d94d2c482d3b
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34287684"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>在 Power BI Desktop 中连接到 Impala 数据库
在 Power BI Desktop 中，你可以连接到 **Impala** 数据库，并以 Power BI Desktop 中使用其他所有数据源相同的方式使用基础数据。

## <a name="connect-to-an-impala-database"></a>连接到 Impala 数据库
若要连接到 Impala 数据库，请从 Power BI Desktop 中的“主页”功能区选择“获取数据”。 在左侧的类别中选择“数据库”，然后将看到 Impala。

![](media/desktop-connect-impala/connect_impala_2.png)

在出现的 **Impala** 窗口中，将你的 Impala 服务器名称键入或粘贴到框中，然后选择“确定”。 请注意，可以选择将数据直接**导入**到 Power BI 中，或使用 **DirectQuery**。 可以了解有关[使用 DirectQuery](desktop-use-directquery.md) 的详细信息。

![](media/desktop-connect-impala/connect_impala_3a.png)

出现提示时，输入你的凭据，或匿名连接。 Impala 连接器支持匿名、基本（用户名 + 密码）和 Windows 身份验证。

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> 输入用户名和密码以连接特定 **Impala** 服务器后，Power BI Desktop 在后续连接尝试中会使用这些相同的凭据。 可以通过“文件”>“选项和设置”>“数据源设置”来修改这些凭据。
> 
> 

连接成功后，将会出现“导航器”窗口，并显示服务器上可用的数据。你可以从这些数据中选择要在 **Power BI Desktop** 中导入和使用的一个或多个元素。

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>注意事项和限制
对于 Impala 连接器，需要牢记以下限制和注意事项：

* 支持在本地数据网关上使用 Impala 连接器（使用三种支持的身份验证机制的任一一种）。

## <a name="next-steps"></a>后续步骤
你可以使用 Power BI Desktop 连接到各种数据。 有关数据源的详细信息，请参阅下列资源：

* [Power BI Desktop 入门](desktop-getting-started.md)
* [Power BI Desktop 中的数据源](desktop-data-sources.md)
* [使用 Power BI Desktop 调整和合并数据](desktop-shape-and-combine-data.md)
* [通过 Power BI Desktop 连接到 Excel 工作簿](desktop-connect-excel.md)   
* [直接将数据输入到 Power BI Desktop 中](desktop-enter-data-directly-into-desktop.md)   

