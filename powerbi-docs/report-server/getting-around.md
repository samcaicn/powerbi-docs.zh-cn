---
title: "Power BI 报表服务器 Web 门户基础知识"
description: "了解如何导航和使用 Power BI 报表服务器 Web 门户。"
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
ms.date: 10/12/2017
ms.author: maggies
ms.openlocfilehash: 7d59531bfed80e854bc19b1df00aaf9cce7144d6
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="navigating-the-power-bi-report-server-web-portal"></a>导航 Power BI 报表服务器 Web 门户
Power BI 报表服务器 Web 门户是用于查看、存储和管理 Power BI 报表、移动报表和分页报表以及 KPI 的本地位置。

![报表服务器 Web 门户](media/getting-around/report-server-web-portal.png)

可以在任意新式浏览器中查看 Web 门户。 在 Web 门户中，可以将报表和 KPI 整理到文件夹中，并将它们标记为收藏项。 此外，还可以在门户上存储 Excel 工作簿。 在 Web 门户中，可以启动创建报表所需的工具：

* 使用 Power BI Desktop 创建的 Power BI 报表：可以在 Web 门户和 Power BI 移动应用中查看此类报表。
* 在报表生成器中创建的分页报表：更适合打印的布局固定的新式文档。
* 直接在 Web 门户中创建了 **KPI**。

在 Web 门户中，可以浏览报表服务器文件夹，也可以搜索特定报表。 可以查看报表及其常规属性，以及在报表历史记录中捕获的报表过往副本。 还可以订阅报表，将其传送到电子邮件收件箱或文件系统上的共享文件夹，具体视权限而定。

## <a name="web-portal-tasks"></a>Web 门户任务
可以在 Web 门户中执行许多任务，具体包括：

* 查看、搜索、打印和订阅报表。
* 创建、保护和维护用于整理服务器上项目的文件夹层次结构。
* 配置报表执行属性、报表历史记录和报表参数。
* 创建共享计划和共享数据源，让计划和数据源连接变得更易于管理。
* 创建数据驱动订阅，以扩充报表收件人列表。
* 创建链接的报表，以不同的方式重用和改用现有报表。
* 下载并打开常用工具，如 Power BI Desktop（报表服务器）、报表生成器和移动报表发布服务器。
* [创建 KPI](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services)。
* 发送反馈或功能请求。
* [向 Web 门户应用品牌](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal)
* [使用 KPI](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services)
* [使用共享数据集](https://docs.microsoft.com/sql/reporting-services/work-with-shared-datasets-web-portal)

## <a name="web-portal-roles-and-permissions"></a>Web 门户角色和权限
Web 门户是在浏览器中运行的 Web 应用。 启动 Web 门户后看到的具体页面、链接和选项视你在报表服务器中的权限而定。 如果你分配到的角色拥有全部权限，则有权使用一整套应用菜单和页面来管理报表服务器。 如果你分配到的角色拥有报表查看和生成权限，则只能看到执行这些活动所需的菜单和页面。 可以在不同的报表服务器上分配到不同的角色，甚至可以针对一个报表服务器上的不同报表和文件夹分配到不同的角色。

## <a name="start-the-web-portal"></a>启动 Web 门户
1. 打开 Web 浏览器。
   
    请参阅[支持的 Web 浏览器和版本](browser-support.md)列表。
2. 在地址栏中，键入 Web 门户 URL。
   
    默认情况下，URL 为 http://[ComputerName]/reports。
   
    可以将报表服务器配置为使用特定端口。 例如，http://[ComputerName]:80/reports 或 http://[ComputerName]:8080/reports
   
    Web 门户按照以下类别进行项目分类：
   
   * KPI
   * 移动报表
   * 分页报表
   * Power BI Desktop 报表
   * Excel 工作簿
   * 数据集
   * 数据源
   * 资源

## <a name="create-and-edit-power-bi-desktop-reports-pbix-files"></a>创建和编辑 Power BI Desktop 报表（.pbix 文件）
可以有权在 Web 门户中查看、上传、创建、整理和管理 Power BI Desktop 报表。

### <a name="create-a-power-bi-desktop-report"></a>创建 Power BI Desktop 报表
1. 依次选择“新建” > “Power BI 报表”。
   
    ![创建新的 Power BI 报表](media/getting-around/report-server-web-portal-new-powerbi-report.png)
   
    此时，Power BI Desktop 应用会打开。
   
    ![Power BI Desktop 应用](media/getting-around/report-server-powerbi-desktop-start.png)
2. 创建 Power BI 报表。 有关详细信息，请参阅[快速入门：Power BI 报表](quickstart-create-powerbi-report.md)。
3. 将报表上传到报表服务器中。

### <a name="edit-an-existing-power-bi-desktop-report"></a>编辑现有 Power BI Desktop 报表
1. 依次选择报表标题右上角的省略号（“...”）和“在 Power BI Desktop 中编辑”。
   
    ![在 Power BI Desktop 中编辑](media/getting-around/report-server-web-portal-pbix-ellipsis.png)
   
    此时，Power BI Desktop 应用会打开。
2. 更改并保存报表...[如何操作？]

## <a name="create-and-edit-paginated-reports-rdl-files"></a>创建和编辑分页报表（.rdl 文件）
可以有权在 Web 门户中查看、上传、创建、整理和管理分页报表。

### <a name="create-a-paginated-report"></a>创建分页报表
1. 依次选择“新建” > “分页报表”。
   
    此时，报表生成器应用会打开。
   
    ![新建报表生成器报表](media/getting-around/report-server-report-builder-new.png)
2. 创建分页报表。 有关详细信息，请参阅[快速入门：分页报表](quickstart-create-paginated-report.md)。
3. 将报表上传到报表服务器中。

### <a name="edit-an-existing-paginated-report"></a>编辑现有分页报表
1. 依次选择报表标题右上角的省略号（“...”）和“在报表生成器中编辑”。
   
    ![在报表生成器中编辑](media/getting-around/report-server-web-portal-rdl-ellipsis.png)
   
    此时，报表生成器应用会打开。
2. 更改并保存报表。

## <a name="upload-and-organize-excel-workbooks"></a>上传并整理 Excel 工作簿
可以有权上传、整理和管理 Power BI Desktop 报表和 Excel 工作簿。 它们会位于 Web 门户中的同一组。

工作簿存储在 Power BI 报表服务器中，与其他资源文件类似。 选择其中一个工作簿可以将其下载到本地桌面。 可以再次将其上传到报表服务器中，从而保存所做的更改。

## <a name="manage-items-in-the-web-portal"></a>管理 Web 门户中的项目
Power BI 报表服务器允许对 Web 门户中存储的项目进行精细化控制。 例如，可以对各个分页报表设置订阅、缓存、快照和安全保护措施。

1. 依次选择项目右上角的省略号（“...”）和“管理”。
   
    ![选择“管理”](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. 选择要设置的属性或其他功能。
   
    ![选择属性](media/getting-around/report-server-web-portal-manage-properties.png)
3. 选择**应用**。

详细了解如何[在 Web 门户中处理订阅](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal)。

## <a name="tag-your-favorite-reports-and-kpis"></a>将报表和 KPI 标记为收藏项
可以标记要收藏的报表和 KPI。 这样方便你快速找到，因为在 Web 门户和 Power BI 移动应用中，它们全都会被收集到一个“收藏夹”文件夹中。 

1. 依次选择要收藏的 KPI 或报表右上角的省略号（“…”）和“添加到收藏夹”。
   
    ![添加到收藏夹](media/getting-around/report-server-web-portal-favorite-ellipsis.png)
2. 在 Web 门户功能区上选择“**收藏夹**”，以在 Web 门户的“收藏夹”页上查看该收藏和其他收藏。
   
    ![查看收藏夹](media/getting-around/report-server-web-portal-favorites.png)
   
    现在，在 Power BI 移动应用中，可以查看这些收藏项，以及在 Power BI 服务中收藏的仪表板。
   
    ![查看移动应用中的收藏夹](media/getting-around/power-bi-iphone-faves-report-server.png)

## <a name="hide-or-view-items-in-the-web-portal"></a>在 Web 门户中隐藏或查看项目
可以在 Web 门户中隐藏项目，也可以选择查看隐藏项目。

### <a name="hide-an-item"></a>隐藏项目
1. 依次选择项目右上角的省略号（“...”）和“管理”。
   
    ![选择“管理”](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. 选择“隐藏此项”。
   
    ![选择隐藏](media/getting-around/report-server-web-portal-hide-property.png)
3. 选择**应用**。

### <a name="view-hidden-items"></a>查看隐藏项目
1. 依次选择右上角的“磁贴”（或“列表”）和“显示隐藏项目”。
   
    此时，隐藏项目会显示。 虽然它们为灰显，但仍可以打开并编辑。
   
    ![显示隐藏项目](media/getting-around/report-server-web-portal-show-hidden-grayed.png)

## <a name="search-for-items"></a>搜索项目
可以输入搜索词，然后便能看到可访问的所有内容。 搜索结果分为 KPI、报表、数据集和其他项目。 然后，可以与结果进行交互，并将它们添加到收藏夹中。  

![搜索项目](media/getting-around/report-server-web-portal-search.png)

## <a name="move-or-delete-items-in-list-view"></a>在列表视图中移动或删除项目
默认情况下，Web 门户在磁贴视图中显示其内容。

可以切换到列表视图，以便可以轻松地一次移动或删除多个项目。 

1. 依次选择“磁贴” > “列表”。
   
    ![切换视图](media/getting-around/report-server-web-portal-list-view.png)
2. 依次选择项目和“移动”或“删除”。

## <a name="next-steps"></a>后续步骤
[用户手册](user-handbook-overview.md)  
[快速入门：分页报表](quickstart-create-paginated-report.md)  
[快速入门：Power BI 报表](quickstart-create-powerbi-report.md)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

