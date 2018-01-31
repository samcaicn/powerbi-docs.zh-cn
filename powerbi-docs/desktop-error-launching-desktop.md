---
title: "解决启动 Power BI Desktop 时的问题"
description: "解决启动 Power BI Desktop 时的问题"
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 515832b9e6b737a942b08b491b78337d78398ee3
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>解决 Power BI Desktop 不启动时的问题
在 Power BI Desktop 中，已安装且正在运行旧版 Power BI 本地数据网关的用户可能无法启动 Power BI Desktop，因为 Power BI 本地网关对本地计算机的命名管道施加了管理策略限制。 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>解决本地数据网关和 Power BI Desktop 存在的问题
可通过三种方法，解决与本地数据网关相关的问题，并允许启动 Power BI Desktop：

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>解决方案 1：安装最新版 Power BI 本地数据网关
最新版 Power BI 本地数据网关不会对本地计算机施加命名管道限制，这样 Power BI Desktop 就可以正常启动了。 如需继续使用 Power BI 本地数据网关，建议采用此解决方案。 可以从[此位置](https://go.microsoft.com/fwlink/?LinkId=698863)下载最新版 Power BI 本地数据网关。 请注意，此链接是指向安装可执行文件的直接下载链接。

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>解决方案 2：卸载或停止运行 Power BI 本地数据网关 Windows 服务
如果不再需要使用 Power BI 本地数据网关，可以卸载或停止运行 Power BI 本地数据网关 Windows 服务。这样一来，便会撤消策略限制，并允许启动 Power BI Desktop。

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>解决方案 3：使用管理员特权运行 Run Power BI Desktop
或者，可以管理员身份启动 Power BI Desktop，这也会使其成功启动。 仍建议安装最新版 Power BI 本地数据网关，如本文先前部分中所述。

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>帮助解决在启动 Power BI Desktop 时遇到的其他问题
我们会尽可能地收录 Power BI Desktop 出现的问题。 我们会定期查看可能会对大量客户造成影响的问题，并将其收录到我们的文章中。

如果无法启动 Power BI Desktop 不是由于本地数据网关所致，或先前的解决方案不起作用，可以向 [Power BI 支持](https://support.powerbi.com) (https://support.powerbi.com) 提交支持事件，这样有助于我们发现并解决用户遇到的问题。

如果今后在使用 Power BI Desktop 时遇到其他问题（我们希望不会出现问题或出现的问题很少），启用跟踪和收集日志文件将有助于更好地隔离和发现问题。 若要启用跟踪，请依次选择“文件”、“选项和设置”、“选项”和“诊断”，再选中“诊断选项”下的“启用跟踪”。 我们认识到，必须运行 Power BI Desktop，才能设置此选项，这更有助于解决今后发生的与启动 Power BI Desktop 相关的问题。

