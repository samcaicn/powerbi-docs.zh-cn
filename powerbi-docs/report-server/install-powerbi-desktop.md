---
title: "安装更适合 Power BI 报表服务器的 Power BI Desktop"
description: "了解如何安装更适合 Power BI 报表服务器的 Power BI Desktop"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 06/20/2017
ms.author: asaxton
ms.openlocfilehash: 5fd5f41523ffcba03eb4749a9560922bcff42a7c
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>安装更适合 Power BI 报表服务器的 Power BI Desktop
了解如何安装更适合 Power BI 报表服务器的 Power BI Desktop。

需要下载并安装更适合 Power BI 报表服务器的 Power BI Desktop。 这不同于用于 Power BI 服务的 Power BI Desktop 版本。 为了确保报表服务器可以间接使用已知版本的报表和模型，需要安装此版本。 

> [!NOTE]
> 可以并行安装 Power BI Desktop 和更适合 Power BI 报表服务器的 Power BI Desktop。
> 
> 

## <a name="download-and-install"></a>下载和安装
可以从 [Microsoft 下载中心](https://go.microsoft.com/fwlink/?linkid=837581)或报表服务器 Web 门户中下载针对 Power BI 报表服务器进行了优化的 Power BI Desktop。

下载安装程序后，便可以安装 Power BI Desktop。

## <a name="verify-you-are-using-the-correct-version"></a>验证使用的是否是正确版本
可以查看 Power BI Desktop 中的启动屏幕或标题栏，验证使用的是否是 Power BI Desktop 正确版本。 标题栏将指示版本的发行月份和年份。

![](media/install-powerbi-desktop/powerbi-desktop-rs-title-bar.png "Power BI Desktop 的标题栏")

Power BI 服务的 Power BI Desktop 版本将不会在标题栏中显示发行月份和年份。

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

