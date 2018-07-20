---
title: Azure SQL 数据库计划刷新中的故障排除
description: Power BI 的 Azure SQL 数据库计划刷新中的故障排除
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 9439ac6bd0b4df568b964f548372fb94d2fd0b26
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34238517"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI 的 Azure SQL 数据库计划刷新中的故障排除
有关设置计划刷新的详细步骤，请务必参阅[刷新 Power BI 中的数据](refresh-data.md)。

设置 Azure SQL 数据库的计划刷新时，若在编辑凭据时收到含错误代码 400 的错误消息，尝试按照以下步骤设置正确的防火墙规则：

1. 登录到 Azure 管理门户
2. 转到正在为其配置刷新的 Azure SQL 服务器
3. 在允许的服务区域中开启“Windows Azure 服务”

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

