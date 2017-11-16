---
title: "Power BI 报表服务器中的新增功能"
description: "了解 Power BI 报表服务器中的新增功能。 本文涉及主要功能方面，并会在新功能发布时随之进行更新。"
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
ms.date: 10/31/2017
ms.author: asaxton
ms.openlocfilehash: d351a117307e86c7b0750e9bcdf813b08b28bb0f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI 报表服务器中的新增功能
了解 Power BI 报表服务器中的新增功能。 本文涉及主要功能方面，并会在新功能发布时随之进行更新。

若要下载 Power BI 报表服务器和针对 Power BI 报表服务器进行了优化的 Power BI Desktop，请转到[使用 Power BI 报表服务器进行本地报告](https://powerbi.microsoft.com/report-server/)。

![提示](media/whats-new/fyi-tip.png "提示") 有关最新发行说明，请参阅 [Power BI 报表服务器 - 发行说明](release-notes.md)。

有关相关的“新增功能”的信息，请参阅：

* [Power BI 服务中的最近更新](../service-whats-new.md)
* [Power BI Desktop 中的新增功能](../desktop-latest-update.md)
* [Power BI 移动应用中的新增功能](../mobile-whats-new-in-the-mobile-apps.md)
* [Power BI 团队博客](https://powerbi.microsoft.com/blog/)

## <a name="october-2017-release"></a>2017 年 10 月版本
### <a name="power-bi-report-data-sources"></a>Power BI 报表数据源
Power BI 报表服务器中的 Power BI 报表可以连接到各种数据源。 可以导入数据和计划数据刷新，或者直接使用 DirectQuery 或与 SQL Server Analysis Services 的实时连接查询数据。 请参阅支持计划的刷新和支持“Power BI 报表服务器中的 Power BI 报表数据源”中的 DirectQuery 的数据源列表。

### <a name="scheduled-data-refresh-for-imported-data"></a>导入的数据的计划数据刷新
在 Power BI 报表服务器中，可以设置计划的数据刷新，以使用嵌入式模型（而不是实时连接或 DirectQuery）使 Power BI 报表中的数据始终保持最新。 由于使用嵌入式模型导入数据，一次它会与原始数据源断开连接。 它需要更新以便数据保持最新状态，而计划的刷新就可以实现这一点。 详细了解“Power BI 报表服务器中 Power BI 报表的计划刷新”。

### <a name="editing-power-bi-reports-from-the-server"></a>从服务器编辑 Power BI 报表
可以从服务器打开和编辑 Power BI 报表 (.pbix) 文件，而且可以找回上传的原始文件。  这意味着，如果数据已由服务器刷新，则在首次打开该文件时将不会刷新数据。 需要在本地手动刷新才能查看更改。

### <a name="large-file-uploaddownload"></a>大型文件上传/下载
可以上传最大 2 GB 的文件（在 SQL Server Management Studio (SSMS) 的报表服务器设置中，此限制默认设置为 1 GB）。  这些文件存储在数据库中，就像它们适用于 SharePoint 一样，并且不需要对 SQL Server 目录进行任何特殊配置。  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>通过 OData 源访问共享数据集
可以使用 OData 源从 Power BI Desktop 访问共享数据集。 有关详细信息，请参阅[在 Power BI 报表服务器中通过 OData 源访问共享数据集](access-dataset-odata.md)。

### <a name="scale-out"></a>横向扩展
此版本支持横向扩展。使用负载均衡器并设置服务器关联以获得最佳体验。 请注意，该方案尚未针对横向扩展进行优化，因此，将看到模型可能会在多个节点之间复制。 该方案将在没有网络负载均衡器和粘性会话的情况下运行。 但是，加载模型 N 次时，不仅会看到跨节点的内存过度使用，而且连接之间的性能会下降，因为在模型抵达两个请求之间的新节点时会对其进行流式传输。  

### <a name="administrator-settings"></a>管理员设置
管理员可以在服务器场的 SSMS 高级属性中设置以下属性：

* EnableCustomVisuals：True/False
* EnablePowerBIReportEmbeddedModels：True/False
* EnablePowerBIReportExportData：True/False
* MaxFileSizeMb：默认值现在为 1000
* ModelCleanupCycleMinutes：检查并从内存中收回模型的频率
* ModelExpirationMinutes：根据上次使用时间，定义模型过期并被收回的时长
* ScheduleRefreshTimeoutMinutes：一个模型的数据刷新可能需要的时长。 默认情况下，此值为两个小时。  没有固定上限。

**配置文件 rsreportserver.config**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>开发人员 API
为 SSRS 2017 引入的开发人员 API (REST API) 已针对 Power BI 报表服务器进行了扩展，以便处理 Excel 文件和 .pbix 文件。 一个可能的用例是以编程方式从服务器下载文件，对文件进行刷新，然后重新发布文件。 例如，这是使用 PowerPivot 模型刷新 Excel 工作簿的唯一方法。

请注意，有一个单独的新 API 适用于将在 Swagger 的 Power BI 报表服务器版本中进行更新的大型文件。 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) 和 Power BI 报表服务器的内存占用情况
Power BI 报表服务器现在可在内部托管 SQL Server Analysis Services (SSAS)。 这并非特定于计划的刷新。 托管 SSAS 可以极大地扩展报表服务器的内存占用情况。 AS.ini 配置文件在服务器节点上可用，因此，如果用户熟悉 SSAS，可能想要更新设置，其中包括最大内存限制和磁盘缓存等。有关详细信息，请参阅 [Analysis Services 中的服务器属性](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services)。

### <a name="viewing-and-interacting-with-excel-workbooks"></a>查看 Excel 工作簿并与之交互
Excel 和 Power BI 包含行业中独一无二的一套工具。 同时，它们使业务分析师更轻松地收集数据、构建数据模型、分析并以可视化方式浏览数据。 除了在 Web 门户中查看 Power BI 报表之外，企业用户现在也可以使用 Power BI 报表服务器中的 Excel 工作簿执行相同的操作，从而向用户提供单个位置来发布和查看其自助服务 Microsoft BI 内容。

我们已发布了[如何将 Office Online Server (OOS) 添加到 Power BI 报表服务器预览环境的演练](excel-oos.md)。 具有批量许可帐户的客户可以从批量许可服务中心免费下载 OOS，并且将具有仅查看功能。 配置后，用户可以查看具有以下特点的 Excel 工作簿并与之交互：

* 没有外部数据源依赖关系
* 实时连接到外部 SQL Server Analysis Services 数据源
* 具有 PowerPivot 数据模型

### <a name="support-for-new-table-and-matrix-visuals"></a>支持新的表和矩阵视觉对象
Power BI 报表服务器现在支持新的 Power BI 表和矩阵视觉对象。 若要创建具有这些视觉对象的报表，需要 2017 年 10 月发布的更新的 Power BI Desktop 版本。 它不能与 Power BI Desktop（2017 年 6 月）版本并行安装。 对于最新版本的 Power BI Desktop，请在 [Power BI 报表服务器下载页](https://powerbi.microsoft.com/report-server/)上选择“高级下载选项”。

## <a name="june-2017"></a>2017 年 6 月
* Power BI 报表服务器已正式发布 (GA)。

## <a name="may-2017"></a>2017 年 5 月
* Power BI 报表服务器预览版已发布
* 可以在本地发布 Power BI 报表
  * 支持自定义视觉对象
  * 仅支持 Analysis Services 实时连接，今后将会支持更多数据源。
  * Power BI 移动应用更新为显示在 Power BI 报表服务器中托管的 Power BI 报表
* 通过注释增强了报表协作

## <a name="next-steps"></a>后续步骤
[Power BI 报表服务器发行说明](release-notes.md)  
[用户手册](user-handbook-overview.md)  
[管理员手册](admin-handbook-overview.md)  
[快速入门：安装 Power BI 报表服务器](quickstart-install-report-server.md)  
[安装报表生成器](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[下载 SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

