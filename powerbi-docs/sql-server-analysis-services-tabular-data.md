---
title: "Power BI 中的 SQL Server Analysis Services 实时数据"
description: "Power BI 中的 SQL Server Analysis Services 实时数据。 这是通过为企业网关配置的数据源来实现。"
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
ms.date: 08/10/2017
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: e0053489b2591aa6ffc931b5022fda8bb3b44c8f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="sql-server-analysis-services-live-data-in-power-bi"></a>Power BI 中的 SQL Server Analysis Services 实时数据
在 Power BI 中，有两种方法可以连接到实时的 SQL Server Analysis Services 服务器。 获取数据时，可以连接到 SQL Server Analysis Services 服务器，或者可以连接到已连接到 Analysis Services 服务器的 [Power BI Desktop 文件](service-desktop-files.md)或 [Excel 工作簿](service-excel-workbook-files.md)。

 >[!IMPORTANT]
 >* 若要连接到实时的 Analysis Services 服务器，管理员必须安装并配置本地数据网关。 有关详细信息，请参阅[本地数据网关](service-gateway-onprem.md)。
 >* 当使用网关时，你的数据将保留在本地。  你基于数据创建的报表保存在 Power BI 服务中。 
 >* [问答自然语言查询](service-q-and-a-direct-query.md)对 Analysis Services 实时连接以预览提供。

## <a name="to-connect-to-a-model-from-get-data"></a>要在获取数据时连接到一个模型
1. 在“我的工作区”中，选择“获取数据”。 你还可以切换到组工作区中，如果有的话。
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdatabutton.png)
2. 选择**数据库和其他**。
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_1.png)
3. 选择 **SQL Server Analysis Services** > **连接**。 
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_2.png)
4. 选择一个服务器。 如果你未看见此处列出任何服务器，则表示未配置网关和数据源，或者在网关中的数据源的**用户**选项卡中未列出你的帐户。 请与你的管理员确认。
5. 选择想要连接到的模型。 该模型可以是表格或多维模型。

连接到模型后，该模型将在 Power BI 站点的**我的工作区/数据集**中显示。 如果切换到组工作区，那么数据集将在组中显示。

![](media/sql-server-analysis-services-tabular-data/connecttoas_dataset_5.png)

## <a name="dashboard-tiles"></a>仪表板磁贴
如果将视觉对象从报表固定到仪表板，那么将每 10 分钟自动刷新固定的磁贴。 如果更新了本地 Analysis Services 服务器中的数据，那么 10 分钟后会自动更新磁贴。

## <a name="next-steps"></a>后续步骤
[本地数据网关](service-gateway-onprem.md)  
[管理 Analysis Services 数据源](service-gateway-enterprise-manage-ssas.md)  
[本地数据网关疑难解答](service-gateway-onprem-tshoot.md)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

