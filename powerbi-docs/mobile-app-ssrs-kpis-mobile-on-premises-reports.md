---
title: "在 Power BI 移动应用中查看本地报表和 KPI"
description: "使用 Power BI 移动应用，可以通过触控移动设备实时访问 SQL Server Reporting Services 和 Power BI 报表服务器中的本地业务信息。"
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 99fceab5904deaa510edd213c349dcfb2e38ac28
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>在 Power BI 移动应用中查看本地报表服务器报表和 KPI
适用于：

| ![iPhone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android 手机](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android 平板电脑](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone |iPad |Android 手机 |Android 平板电脑 |

使用 Power BI 移动应用，可以通过触控移动设备实时访问 Power BI 报表服务器和 SQL Server 2016 Reporting Services (SSRS) 中的本地业务信息。 

 ![移动应用中的报表服务器主文件夹](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>要做的第一件事
移动应用是用于查看 Power BI 内容（而不是创建内容）的地方。

* 你和组织中的其他报表创建者可以[使用 Power BI Desktop 创建 Power BI 报表，然后将报表发布到 Power BI 报表服务器 Web 门户中](report-server/quickstart-create-powerbi-report.md)。 
* 可以[在 Web 门户中直接创建 KPI](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services)，将它们整理到文件夹中，然后标记为收藏项，方便你快速找到。 
* 可以使用 SQL Server 2016 企业版移动报表发布服务器[生成 Reporting Services 移动报表](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher)，然后将其发布到 [Reporting Services Web 门户](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode)。  

然后，在 Power BI 移动应用中，最多连接五个报表服务器，以查看整理到文件夹中或标记为收藏夹的 Power BI 报表和 KPI。 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>不使用服务器连接在移动应用中探索示例
即使无权访问 Reporting Services Web 门户，也仍可以探索 Reporting Services 移动报表和 KPI 的功能。 

1. 点击左上角的 ![全局导航按钮 ](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) ，然后点击右上角的齿轮图标 ![齿轮图标](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png)。
2. 点击“Reporting Services 示例”，然后转到相应位置，与示例 KPI 和移动报表进行交互。
   
   ![Reporting Services 示例](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-server"></a>连接本地服务器
可以在 Power BI 移动应用中查看本地 Power BI 报表、Reporting Services 移动报表和 KPI。 

1. 在移动设备中，打开 Power BI 应用。
2. 如果你尚未登录到 Power BI，请点击“报表服务器”。
   
   ![登录报表服务器](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   如果你已登录到 Power BI 应用，请点击全局导航按钮 ![全局导航按钮 ](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png)，然后点击右上角的齿轮图标 ![齿轮图标](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) 。
3. 点击“连接到服务器”。
   
    ![连接到服务器](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)
4. 填写服务器地址以及用户名和密码。 对服务器地址使用如下格式：
   
     `http://<servername>/reports`
   
     OR
   
     `https://<servername>/reports`
   
   > [!NOTE]
   > 在连接字符串前面加上 http 或 https。
   > 
   > 
   
    ![“连接到服务器”对话框](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. （可选）在“高级选项”下，可以为服务器命名易记名称（如果需要的话）。
6. 此时，服务器显示在左侧导航栏中（在此示例中，服务器名为“Power BI 报表服务器”）。
   
   ![左侧导航窗格中的报表服务器](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>在 Power BI 应用中查看 Power BI 报表和 KPI
Power BI 报表、Reporting Services 移动报表和 KPI 的文件夹与它们在 Reporting Services Web 门户上的文件夹相同。 

* 点击 Power BI 报表 ![Power BI 报表图标](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png)。 它将以横向模式打开，并可在 Power BI 应用中与之交互。
  
    ![Power BI 报表](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* 在 Power BI Desktop 中，报表所有者可以为 Power BI 移动应用[优化报表](desktop-create-phone-report.md)。 在你的移动手机上，已优化的报表都具有一个特殊的图标 ![Optimized Power BI report icon](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png)和布局。
  
    ![为移动设备优化的 Power BI 报表](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* 点击 KPI 以在焦点模式中看到它。
  
    ![焦点模式下的 KPI](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>查看你收藏的 KPI 和报表
可以在 Web 门户上将 KPI 和报表标记为收藏项，然后在移动设备上的一个方便使用的文件夹中查看它们，以及收藏的 Power BI 仪表板。

* 点击**收藏夹**。
  
   ![左侧导航窗格中的收藏夹](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server.png)
  
   你在 Web 门户中收藏的 KPI 和报表，以及 Power BI 服务中的 Power BI 仪表板全都在此页上：
  
   ![“收藏夹”页中的 Power BI 报表和仪表板](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>删除与报表服务器的连接
1. 在左侧导航栏的底部，点击“设置”。
2. 点击不想连接到的服务器的名称。
3. 点击“删除服务器”。

## <a name="next-steps"></a>后续步骤
* [Power BI 入门](service-get-started.md)  
* 是否有任何问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

