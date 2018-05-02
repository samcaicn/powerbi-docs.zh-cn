---
title: 在 Power BI Desktop 中使用 SAP BW 连接器
description: 在 Power BI Desktop 中使用 SAP BW 连接器
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
ms.date: 04/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: d644f13f6c9b8ada62a0862fdcf92518512828f7
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="use-the-sap-bw-connector-in-power-bi-desktop"></a>在 Power BI Desktop 中使用 SAP BW 连接器
使用 Power BI Desktop 可以访问 SAP BusinessWarehouse (BW) 数据。

有关 SAP 客户如何在连接 Power BI 和现有 SAP Business Warehouse (BW) 系统的过程中受益的信息，请参阅 [Power BI and SAP BW 白皮书](https://aka.ms/powerbiandsapbw)。

## <a name="installation-of-sap-bw-connector"></a>安装 SAP BW 连接器
若要使用 **SAP BW 连接器**，请完成以下安装步骤：

1. 在本地计算机上安装 **SAP NetWeaver** 库。 你可以从 SAP 管理员处获取 **SAP Netweaver** 库，也可以直接从 [SAP 软件下载中心](https://support.sap.com/swdc)下载。 由于 **SAP 软件下载中心**的结构经常发生变化，因此没有有关站点导航的更多具体指导。 **SAP NetWeaver** 库通常还包括在 SAP 客户端工具安装中。
   
   可以搜索 SAP 注释 #1025361，获取最新版本的下载位置。 请确保 **SAP NetWeaver** 库（32 位或 64 位）的体系结构匹配 **Power BI Desktop** 安装，然后按照 SAP Note 安装 **SAP NetWeaver RFC SDK** 中包含的所有文件。
2. “获取数据”对话框的“数据库”类别中包含“SAP Business Warehouse 应用程序服务器”和“SAP Business Warehouse 消息服务器”相关条目。
   
   ![](media/desktop-sap-bw-connector/sap_bw_2a.png)

## <a name="sap-bw-connector-features"></a>SAP BW 连接器功能
通过 Power BI Desktop 中的 SAP BW 连接器，可从 SAP Business Warehouse 服务器多维数据集导入数据，或者可使用 DirectQuery。 

若要深入了解 SAP BW 连接器以及如何将其与 DirectQuery 一起使用，请参阅 [DirectQuery 和 SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)。

连接时，必须指定“服务器”、“系统编号”和“客户端 ID”才能建立连接。

![](media/desktop-sap-bw-connector/sap_bw_3a.png)

你还可以指定两个额外的“高级选项”：语言代码和针对指定服务器运行的自定义 MDX 语句。

![](media/desktop-sap-bw-connector/sap_bw_4a.png)

如果未指定任何 MDX 语句，则向你显示“导航器”窗口，其中将显示服务器上可用的多维数据集的列表，同时提供向下钻取以及从可用多维数据集中选择项的选项，包括维度和度量值。 Power BI 显示由 [BW 开放分析接口 OLAP BAPI](https://help.sap.com/saphelp_nw70/helpdata/en/d9/ed8c3c59021315e10000000a114084/content.htm) 公开的查询和多维数据集。

当从服务器中选择一个或多个项时，将基于它们的选择创建输出表的预览。

![](media/desktop-sap-bw-connector/sap_bw_5.png)

**导航器**窗口也提供了一些**显示选项**，允许你执行以下操作：

* **显示仅选定项与所有项（默认视图）：**此选项在验证最后一组选定项时十分有用。 查看此类容的另一种方法是选择预览区域中的列名称。
* **启用数据预览（默认行为）：**还可以控制是否应在此对话框中显示数据预览。 禁用数据预览会减少服务器调用的数量，因其将不再请求数据以进行预览。
* **技术名称：**对于多维数据集中的对象，SAP BW 支持技术名称的概念。 技术名称允许多维数据集所有者公开多维数据集对象的用户友好名称，而不是仅公开多维数据集中的那些对象的物理名称。

![](media/desktop-sap-bw-connector/sap_bw_6.png)

在**导航器**中选择所有必须的对象后，你可以通过选择**导航器**窗口底部的下列按钮之一，决定要执行的下一步操作。

* 选择**加载**将会触发将输出表的整个行集加载到 Power BI Desktop 数据模型中，然后将你带到**报表**视图，在此你可以使用**数据**或**关系**视图来开始对这些数据进行视觉化处理或进行进一步的修改。
* 选择**编辑**将打开**查询编辑器**，在整个列集引入到 Power BI Desktop 数据模型之前，你可以在其中执行其他数据转换和筛选步骤。

除了从 **SAP BW** 多维数据集导入数据之外，请记住，你还可以从 Power BI Desktop 中的很多其他数据源导入数据，然后将它们合并到单一报表中。 这将在 **SAP BW** 数据顶部将演示各种有趣的报表和分析方案。

## <a name="troubleshooting"></a>故障排除
本部分内容提供有关使用此预览版的 **SAP BW** 连接器的故障排除（和解决方案）。

1. 来自 **SAP BW** 的数值数据返回小数点，而不是逗号。 例如，1,000,000 的返回形式为 1.000.000。
   
   **SAP BW** 返回以 ,（逗号）或 . （句点）作为十进制分隔符的十进制数据。 为指定哪些 **SAP BW** 可用于十进制分隔符，**Power BI Desktop** 使用的驱动程序会调用 BAPI_USER_GET_DETAIL。 该调用返回一个名为 **DEFAULTS** 的结构，它包含一个名为 DCPFM 的字段，用于存储十进制格式表示法。 它采用以下三个值之一：
   
       ‘ ‘ (space) = Decimal point is comma: N.NNN,NN
       'X' = Decimal point is period: N,NNN.NN
       'Y' = Decimal point is N NNN NNN,NN
   
   报告此问题的客户发现，对于特定用户（显示不正确的数据的用户），对 *BAPI_USER_GET_DETAIL* 的调用失败，并显示类似于以下内容的错误消息：
   
       You are not authorized to display users in group TI:
           <item>
               <TYPE>E</TYPE>
               <ID>01</ID>
               <NUMBER>512</NUMBER>
               <MESSAGE>You are not authorized to display users in group TI</MESSAGE>
               <LOG_NO/>
               <LOG_MSG_NO>000000</LOG_MSG_NO>
               <MESSAGE_V1>TI</MESSAGE_V1>
               <MESSAGE_V2/>
               <MESSAGE_V3/>
               <MESSAGE_V4/>
               <PARAMETER/>
               <ROW>0</ROW>
               <FIELD>BNAME</FIELD>
               <SYSTEM>CLNTPW1400</SYSTEM>
           </item>
   
   为了修复此错误，用户必须要求他们的 SAP 管理员授予在 Power BI 中使用的 SAPBW 用户执行 *BAPI_USER_GET_DETAIL* 的权限。 需要确定的另一点是，用户是否具有必需的 *DCPFM* 值，如本故障排除解决方案前面的内容所述。
2. **SAP BEx 查询的连接**
   
   你可以通过启用特定属性执行 Power BI Desktop 中的“BEx”查询，如下图所示：
   
   ![](media/desktop-sap-bw-connector/sap_bw_8.png)

## <a name="next-steps"></a>后续步骤
有关 SAP HANA 和 DirectQuery 的详细信息，请查看以下资源：

* [DirectQuery 和 SAP HANA](desktop-directquery-sap-hana.md)
* [Power BI 中的 DirectQuery](desktop-directquery-about.md)
* [DirectQuery 支持的数据源](desktop-directquery-data-sources.md)
* [Power BI 和 SAP BW 白皮书](https://aka.ms/powerbiandsapbw)
