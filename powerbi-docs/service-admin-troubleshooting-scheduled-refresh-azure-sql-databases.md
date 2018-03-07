---
title: "Azure SQL 数据库计划刷新中的故障排除"
description: "Power BI 的 Azure SQL 数据库计划刷新中的故障排除"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 5f699ed013f35edd4f958b3c958e56ebeb05029c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI 的 Azure SQL 数据库计划刷新中的故障排除
有关设置计划刷新的详细步骤，请务必参阅[刷新 Power BI 中的数据](refresh-data.md)。

设置 Azure SQL 数据库的计划刷新时，若在编辑凭据时收到含错误代码 400 的错误消息，尝试按照以下步骤设置正确的防火墙规则：

1. 登录到 Azure 管理门户
2. 转到正在为其配置刷新的 Azure SQL 服务器
3. 在允许的服务区域中开启“Windows Azure 服务”

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

