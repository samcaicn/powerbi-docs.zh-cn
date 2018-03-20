---
title: "在 Power BI Desktop 中连接到 Adobe Analytics（预览版）"
description: "轻松连接并使用 Adobe Analytics Power BI Desktop"
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
ms.date: 03/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: efd6d066e2f98f86248730917c2f4aa0c8a39983
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="connect-to-adobe-analytics-in-power-bi-desktop-preview"></a>在 Power BI Desktop 中连接到 Adobe Analytics（预览版）
在 Power BI Desktop 中，可连接到“Adobe Analytics”并使用基础数据（就像在 Power BI Desktop 中使用其他所有数据源一样）。 

![从 Adobe Analytics 中获取数据](media/desktop-connect-adobe-analytics/connect-adobe-analytics_01.png)

## <a name="enable-the-adobe-analytics-connector-preview"></a>启用 Adobe Analytics 连接器预览版 
由于 Adobe Analytics 连接器当前为预览版，因此启用预览版功能之后，才能在“获取数据”窗口中使用连接器。 若要启用连接器的预览版功能，请在 Power BI Desktop 中依次选择“文件”、“选项和设置”、“选项”和“预览版功能”，再选中“书签”旁的复选框。 

![在“选项”中启用 Adobe Analytics 连接器预览版](media/desktop-connect-adobe-analytics/connect-adobe-analytics_02.png)

选择启用 Adobe Analytics 连接器预览版后，需重启 Power BI Desktop。

## <a name="connect-to-adobe-analytics-data"></a>连接到 Adobe Analytics 数据
若要连接到 Adobe Analytics 数据库，请在 Power BI Desktop 中的“主页”功能区选择“获取数据”。 在左侧类别中选择“联机服务”，此时显示“Adobe Analytics 连接器”。

![从 Adobe Analytics 中获取数据](media/desktop-connect-adobe-analytics/connect-adobe-analytics_01.png)

在显示的 Adobe Analytics 窗口中，选择“登录”按钮，然后提供登录到 Adobe Analytics 帐户的凭据。 随即显示 Adobe 登录窗口，如下图所示。

![登录到 Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_03.png)

出现提示时，输入你的用户名和密码。 建立连接后，可在 Power BI 的“导航器”对话框中预览和选择多个维度和度量值，以创建单个表格输出。 还可提供所选项所需的任何必要输入参数。 

![使用导航器选择数据](media/desktop-connect-adobe-analytics/connect-adobe-analytics_04.png)

你可以**加载**选定的表，该操作将把整个表格加载到 **Power BI Desktop**中，或者你也可以**编辑**查询，这将打开**查询编辑器**，以便筛选和优化要使用的数据集，然后将优化后的数据集加载到 **Power BI Desktop** 中。

![在导航器中加载或编辑数据](media/desktop-connect-adobe-analytics/connect-adobe-analytics_05.png)


## <a name="next-steps"></a>后续步骤
你可以使用 Power BI Desktop 连接到各种数据。 有关数据源的详细信息，请参阅下列资源：

* [Power BI Desktop 入门](desktop-getting-started.md)
* [Power BI Desktop 中的数据源](desktop-data-sources.md)
* [使用 Power BI Desktop 调整和合并数据](desktop-shape-and-combine-data.md)
* [通过 Power BI Desktop 连接到 Excel 工作簿](desktop-connect-excel.md)   
* [直接将数据输入到 Power BI Desktop 中](desktop-enter-data-directly-into-desktop.md)   

