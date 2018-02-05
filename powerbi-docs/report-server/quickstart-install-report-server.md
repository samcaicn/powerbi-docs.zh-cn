---
title: "快速入门：安装 Power BI 报表服务器"
description: "Power BI 报表服务器本身安装起来非常快。 从下载到安装和配置，只需几分钟，即可快速上手使用。"
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
ms.date: 01/29/2018
ms.author: maghan
ms.openlocfilehash: 3ddf8870fd4fb3186ff884220fc4a7de7632c78d
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="quickstart-install-power-bi-report-server"></a>快速入门：安装 Power BI 报表服务器
Power BI 报表服务器本身安装起来非常快。 从下载到安装和配置，只需几分钟，即可快速上手使用。

如果要直接快速上手使用新服务器，可以参阅本文，快速了解如何安装报表服务器。 若要详细了解如何安装报表服务器，请参阅[安装 Power BI 报表服务器](install-report-server.md)。

 下载 ![下载](media/quickstart-install-report-server/download.png "下载")

若要下载 Power BI 报表服务器，请转到[使用 Power BI 报表服务器进行本地报告](https://powerbi.microsoft.com/report-server/)。 

转到 Microsoft 下载中心下载 [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=861076)（已针对 Power BI 报表服务器进行优化 - 2017 年 10 月版）。

![提示](media/quickstart-install-report-server/fyi-tip.png "提示") 有关最新发行说明，请参阅 [Power BI 报表服务器 - 发行说明](release-notes.md)。

<iframe width="640" height="360" src="https://www.youtube.com/embed/zacaEb9A4F0?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="before-you-begin"></a>开始之前
建议在安装 Power BI 报表服务器之前先查看[安装 Power BI 报表服务器所要满足的硬件和软件要求](system-requirements.md)。

## <a name="step-1-download"></a>第 1 步：下载
将 Power BI 报表服务器的安装文件下载到本地。 若要下载 Power BI 报表服务器，请转到 [Microsoft 下载中心](https://go.microsoft.com/fwlink/?linkid=839351)。

![下载 Power BI 报表服务器](media/quickstart-install-report-server/download-pbireportserver.png)

## <a name="step-2-run-installer"></a>第 2 步：运行安装程序
运行下载的 PowerBIReportServer.exe 文件，然后在安装屏幕上逐步完成安装。 将有机会选择安装路径和要安装的版本。 可以选择有效期为 180 天的评估版，也可以选择开发者版本或提供产品密钥。

![安装 Power BI 报表服务器](media/quickstart-install-report-server/pbireportserver-install.png)

## <a name="step-3-configure-the-server"></a>第 3 步：配置服务器
安装完毕后，将运行配置管理器来完成设置服务器。 需要创建 ReportServer 目录数据库，并确认 Web 门户和 Web 服务 URL。

![配置 Power BI 报表服务器](media/quickstart-install-report-server/pbireportserver-configure.png)

## <a name="step-4-browse-to-web-portal"></a>第 4 步：转到 Web 门户
至此，你已配置报表服务器，应该可以打开浏览器转到服务器的 Web 门户了。 默认情况下，地址为 `http://localhost/reports`。 还可以使用计算机名称（而不是使用默认的 localhost）进行浏览，但前提是未被任何类型的防火墙拦截。

![Power BI 报表服务器 Web 门户](media/quickstart-install-report-server/web-portal.png)

## <a name="next-steps"></a>后续步骤
[管理员手册](admin-handbook-overview.md)  
[如何查找报表服务器产品密钥](find-product-key.md)  
[安装 Power BI 报表服务器](install-report-server.md)  
[安装更适合 Power BI 报表服务器的 Power BI Desktop](install-powerbi-desktop.md)  
[Power BI 报表服务器的浏览器支持](browser-support.md)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

