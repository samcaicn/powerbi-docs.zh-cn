---
title: "Power BI 报表服务器发行说明"
description: "本主题介绍了 Power BI 报表服务器存在的限制和问题。"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 7f59e3788b24344b5f86b146fb41e440eb0a2098
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-server-release-notes"></a>Power BI 报表服务器发行说明
本主题介绍了 Power BI 报表服务器存在的限制和问题。

若要下载 Power BI 报表服务器和针对 Power BI 报表服务器进行了优化的 Power BI Desktop，请转到[使用 Power BI 报表服务器进行本地报告](https://powerbi.microsoft.com/report-server/)。

## <a name="october-2017"></a>2017 年 10 月
* 支持 Power BI 报表中的导入数据
* 能够在 Web 门户中查看 Excel 工作簿。 这可通过配置 Office Online Server 实现。
* 支持新的 Power BI 表和矩阵视觉对象。
* REST API 支持

## <a name="june-2017"></a>2017 年 6 月
* 2017 年 6 月没有任何新项目。

## <a name="may-2017"></a>2017 年 5 月
* 必须使用更适合 Power BI 报表服务器的 Power BI Desktop 创建 Power BI 报表，才能对 Power BI 报表服务器使用此类报表。 可以单击此页顶部的下载链接来下载 Power BI Desktop。
* Power BI 报表仅支持与 Analysis Services（表格模型或多维数据集）的实时连接。
* 不支持 R 视觉对象。

问题和客户影响：如果卸载同一台计算机上安装的 SQL Server Reporting Services 和 Power BI 报表服务器之一，将无法再使用报表服务器配置管理器连接未卸载的报表服务器。

解决方法：若要解决此问题，必须在卸载其中一个服务器后执行以下操作。

1. 在管理员模式下启动命令提示符。
2. 转到未卸载的报表服务器的安装目录。
   
    Power BI 报表服务器的默认位置：C:\Program Files\Microsoft Power BI Report Server
   
    SQL Server Reporting Services 的默认位置：C:\Program Files\Microsoft SQL Server Reporting Services
3. 然后，转到下一个文件夹。 不是“SSRS”就是“PBIRS”，具体视未卸载的报表服务器而定。
4. 转到 WMI 文件夹。
5. 运行以下命令：
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    如果看到以下错误消息，可以忽略。
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>后续步骤
[Power BI 报表服务器中的新增功能](whats-new.md)  
[用户手册](user-handbook-overview.md)  
[管理员手册](admin-handbook-overview.md)  
[快速入门：安装 Power BI 报表服务器](quickstart-install-report-server.md)  
[安装报表生成器](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[下载 SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

