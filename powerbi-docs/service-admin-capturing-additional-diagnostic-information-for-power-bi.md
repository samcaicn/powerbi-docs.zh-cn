---
title: "捕获其他诊断信息"
description: "捕获其他诊断信息"
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
ms.date: 06/28/2017
ms.author: maghan
ms.openlocfilehash: cfd653c97371cadc069d6c8f67bf01c0ee74f2cf
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="capturing-additional-diagnostic-information"></a>捕获其他诊断信息
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>捕获 Power BI 的其他诊断信息
以下说明介绍了用于手动从 Power BI Web 客户端收集其他诊断信息的两种可能选择。  只需采用其中一种选择即可。

## <a name="network-capture---edge--internet-explorer"></a>网络捕获 - Edge 和 Internet Explorer
1. 通过 Edge 或 Internet Explorer 浏览到 [Power BI](https://app.powerbi.com)。
2. 按 F12 打开 Edge 开发人员工具。
3. 该操作将会显示开发人员工具窗口： 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. 切换到“网络”选项卡。它将列出已捕获的流量。 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. 你可以在窗口中浏览并重现任何可能会遇到的问题。 你可以在会话期间随时通过按 F12 来隐藏和显示开发人员工具窗口。
6. 若要停止捕获，你可以选择开发人员工具区域的“网络”选项卡上的红色方块。
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. 选择磁盘图标以“导出为 HAR”
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. 提供文件名称并保存该 HAR 文件。
   
    HAR 文件会包含有关浏览器窗口与 Power BI 之间的网络请求的所有信息。  这会包括每个请求的活动 ID、每个请求的精确时间戳以及返回到客户端的任何错误信息。  此跟踪还会包含用于填充屏幕上显示的视觉对象的数据。
9. 你可以提供该 HAR 文件以支持审阅。

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

