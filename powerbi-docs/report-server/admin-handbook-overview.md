---
title: "管理员手册概述：Power BI 报表服务器"
description: "欢迎阅读 Power BI 报表服务器的管理员手册。Power BI 报表服务器是用于存储和管理 Power BI 报表、移动报表和分页报表的本地位置。"
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 6434084ab59cf842544dbcf9e373a8f6985a9ee3
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2018
---
# <a name="administrator-handbook-overview-power-bi-report-server"></a>管理员手册概述：Power BI 报表服务器
欢迎阅读 Power BI 报表服务器的管理员手册。Power BI 报表服务器是用于存储和管理 Power BI 报表、移动报表和分页报表的本地位置。

![](media/admin-handbook-overview/admin-handbook.png)

本手册将帮助你了解如何规划、部署和管理 Power BI 报表服务器这些相关概念。

## <a name="installing-and-migration"></a>安装和迁移
必须安装 Power BI 报表服务器，才能开始使用。 我们提供了有关如何处理此任务的信息。

在开始安装、升级或迁移到 Power BI 报表服务器之前，请先查看报表服务器的[系统要求](system-requirements.md)。

### <a name="installing"></a>安装
若要部署新的 Power BI 报表服务器，请参阅以下对你有所帮助的文档。 为了方便你快速入门，我们提供了快速入门文档。 也可以查看安装文档，了解完整详情。

* [快速入门：安装 Power BI 报表服务器](quickstart-install-report-server.md)
* [安装 Power BI 报表服务器](install-report-server.md)

### <a name="migration"></a>迁移
无法就地升级 SQL Server Reporting Services。 如果要让现有 SQL Server Reporting Services 实例成为 Power BI 报表服务器，必须进行迁移。 还有其他可能原因需要执行迁移。 请查看迁移文档，了解更多详细信息。

[迁移报表服务器安装](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>配置报表服务器
报表服务器的配置选项有很多。 要使用 SSL 吗？ 要配置电子邮件服务器吗？ 要与 Power BI 服务集成以固定可视化效果吗？

可以在报表服务器配置管理器中指定大部分配置。 有关更多详细信息，请查看[配置管理器](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode)文档。

## <a name="security"></a>安全性
安全和保护措施对每个组织都非常重要。 可以查看[安全](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection)文档，了解身份验证、授权、角色和权限。

## <a name="next-steps"></a>后续步骤
[快速入门：安装 Power BI 报表服务器](quickstart-install-report-server.md)  
[如何查找报表服务器产品密钥](find-product-key.md)  
[安装更适合 Power BI 报表服务器的 Power BI Desktop](install-powerbi-desktop.md)  
[安装报表生成器](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[下载 SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

