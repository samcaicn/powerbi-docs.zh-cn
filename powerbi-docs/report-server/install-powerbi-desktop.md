---
title: "安装更适合 Power BI 报表服务器的 Power BI Desktop"
description: "了解如何安装更适合 Power BI 报表服务器的 Power BI Desktop"
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 12/05/2017
ms.author: maggies
ms.openlocfilehash: efae785bb063e1bfb1b8333e36447dcaa66a70b4
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>安装更适合 Power BI 报表服务器的 Power BI Desktop
了解如何安装更适合 Power BI 报表服务器的 Power BI Desktop。

若要为 Power BI 报表服务器创建 Power BI 报表，需要下载并安装已针对 Power BI 报表服务器进行优化的 Power BI Desktop。 此版本不同于用于 Power BI 服务的 Power BI Desktop。 使用此版本可确保报表服务器能够与已知版本的报表和模型交互。 

> [!NOTE]
> 可在同一台计算机上并行安装 Power BI Desktop 和已针对 Power BI 报表服务器进行优化的 Power BI Desktop。

## <a name="download-and-install-power-bi-desktop"></a>下载并安装 Power BI Desktop

确保使用已针对 Power BI 报表服务器进行优化的最新 Power BI Desktop 版本的最简单方法是从报表服务器的 Web 门户启动。

1. 在报表服务器 Web 门户中，选择“下载”箭头 >“Power BI Desktop”。

    ![从 Web 门户下载 Power BI Desktop](media/install-powerbi-desktop/report-server-download-web-portal.png)

    或者，可以在 Microsoft 下载中心直接转到[“Microsoft Power BI Desktop”](https://go.microsoft.com/fwlink/?linkid=861076)（已针对 Power BI 报表服务器进行优化 - 2017 年 10 月版）。

2. 在“下载中心”页中，选择“下载”。

3. 根据所用的计算机选择： 

    - **PBIDesktopRS.msi**（32 位版本）或

    - **PBIDesktopRS_x64.msi**（64 位版本）。

1. 下载安装程序后，运行 Power BI Desktop（2017 年 10 月版）安装向导。
2. 安装结束时，请选中“立即启动 Power BI Desktop”。
   
    此时，它会自动启动，可以开始使用了。

## <a name="verify-you-are-using-the-correct-version"></a>验证使用的是否是正确版本
可以查看 Power BI Desktop 中的启动屏幕或标题栏，验证使用的是否是 Power BI Desktop 正确版本。 标题栏指示了版本的发行月份和年份。

![已针对 Power BI 报表服务器进行优化的 Power BI Desktop 的标题栏](media/quickstart-create-powerbi-report/report-server-desktop-october-2017-version.png)

Power BI 服务的 Power BI Desktop 版本不会在标题栏中显示发行月份和年份。

## <a name="file-extension-association"></a>文件扩展名关联
如果在同一台计算机上安装了 Power BI Desktop 和更适合 Power BI 报表服务器的 Power BI Desktop，后安装的 Power BI Desktop 与文件扩展名 .pbix 相关联。 也就是说，双击 .pbix 文件后，启动的是后安装的 Power BI Desktop。

如果先安装的是 Power BI Desktop，后安装的是更适合 Power BI 报表服务器的 Power BI Desktop，那么单击所有 .pbix 文件后默认打开的是更适合 Power BI 报表服务器的 Power BI Desktop。 如果希望在打开 .pbix 文件时默认启动的是 Power BI Desktop，请在 Power BI 服务中重新安装 Power BI Desktop。

始终可以打开要优先使用的 Power BI Desktop 版本。 然后，在 Power BI Desktop 中打开文件。

在 Power BI 报表服务器中编辑 Power BI 报表或在 Web 门户中新建 Power BI 报表时，始终都会打开正确版本的 Power BI Destop。

## <a name="next-steps"></a>后续步骤
至此，已安装 Power BI Desktop，可以开始创建 Power BI 报表了。

[快速入门：为 Power BI 报表服务器创建 Power BI 报表](quickstart-create-powerbi-report.md)  
[Power BI Desktop 入门](../desktop-getting-started.md)  
引导式学习：[Power BI Desktop 入门](../guided-learning/gettingdata.yml#step-2)  
[用户手册概述：Power BI 报表服务器](user-handbook-overview.md)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

