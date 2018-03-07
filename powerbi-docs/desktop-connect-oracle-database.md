---
title: "连接到 Oracle 数据库"
description: "将 Oracle 连接到 Power BI Desktop 必需的步骤和下载内容"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6308b2e201b669bf17ee636677232b365d62e332
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-an-oracle-database"></a>连接到 Oracle 数据库
若要将 Oracle 数据库与 **Power BI Desktop** 连接，运行 Power BI Desktop 的计算机上必须安装了正确的 Oracle 客户端软件。 你使用的 Oracle 客户端软件取决于已安装的 Power BI Desktop 版本 - **32 位**版本或 **64 位**版本。

**支持的版本**：Oracle 9 及更高版本、Oracle 客户端软件 8.1.7 及更高版本。

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>确定安装了哪个版本的 Power BI Desktop
若要确定安装了哪个版本的 Power BI Desktop，请选择**文件 > 有关**，然后查看**版本：**行。 下图中安装的是 64 位版本的 Power BI Desktop：

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>安装 Oracle 客户端
对于 **32 位**版本的 Power BI Desktop，请使用以下链接来下载并安装 **32 位** Oracle 客户端：

* [32 位 Oracle Data Access Components (ODAC) 和 Oracle Developer Tools for Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

对于 **64 位**版本的 Power BI Desktop，请使用以下链接来下载并安装 **64 位** Oracle 客户端：

* [适用于 Windows x64 的 64 位 ODAC 12c Release 4 (12.1.0.2.4)](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>连接到 Oracle 数据库
一旦安装了匹配的 Oracle 客户端驱动程序后，你就可以连接到 Oracle 数据库。 执行以下步骤建立连接。

1. 在“获取数据”窗口中，选择**数据库 > Oracle 数据库**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. 在出现的 **Oracle 数据库**对话框中，提供服务器的名称，并选择**连接**。 如果需要 SID，则可以使用格式 *ServerName/SID*进行指定。
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. 如果想要使用本机数据库查询导入数据，可以将你的查询放在 **SQL 语句**框中，通过展开 **Oracle 数据库**对话框的**高级选项**分区实现。
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. 一旦你的 Oracle 数据库信息输入 Oracle 数据库对话框（包括如 SID 或本机数据库查询的任何可选信息），请选择**确定**以连接。
5. 如果 Oracle 数据库需要数据库用户凭据，请在出现提示时，输入这些凭据。

