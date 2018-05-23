---
title: 使用 Power BI 连接到 Project Online
description: 适用于 Power BI 的 Project Online
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 52bd4b5dc27ff127eadea49cb3e761d6cda4788d
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-project-online-with-power-bi"></a>使用 Power BI 连接到 Project Online
Microsoft Project Online 是一个灵活的在线解决方案，用于项目组合管理 (PPM) 和日常工作。 Project Online 使组织能够开始运转、排定项目资产组合投资优先级以及交付预期业务价值。 Power BI 的 Project Online 内容包允许你浏览你的项目数据的现成指标，如项目组合状态和项目合规性。

连接到 Power BI 的 [Project Online 内容包](https://app.powerbi.com/getdata/services/project-online)。

## <a name="how-to-connect"></a>如何连接
1. 选择左侧导航窗格底部的**获取数据**。
   
    ![](media/service-connect-to-project-online/getdata.png)
2. 在**服务**框中，选择**获取**。
   
   ![](media/service-connect-to-project-online/services.png)
3. 选择 **Microsoft Project Online** \> **获取**。
   
   ![](media/service-connect-to-project-online/mproject.png)
4. 在 **Project Web App URL** 文本框中，输入你要连接到的 Project Web Add (PWA) 的 URL，然后点击**下一步**。 请注意，如果你使用自定义域，则它可能与示例不同。
   
    ![](media/service-connect-to-project-online/params.png)
5. 对于身份验证方法，选择 **oAuth2** \> **登录**。 出现提示时，输入 Project Online 凭据，然后按照身份验证过程进行操作。
   
    ![](media/service-connect-to-project-online/creds.png)
    
请注意，需要拥有项目组合查看者、项目组合经理或管理员权限才能连接到 Project Web App。

6. 你将看到一个通知，指示你的数据正在加载。 根据帐户的大小，这可能需要一些时间。 Power BI 导入数据后，你将在左侧的导航窗格中看到新的仪表板、报表和数据集。 这是 Power BI 为显示数据而创建的默认仪表板。 可以修改此仪表板以便按所需方式显示数据。
   
   ![](media/service-connect-to-project-online/dashboard2.png)

**下一步？**

* 尝试在仪表板顶部的[在“问答”框中提问](power-bi-q-and-a.md)
* 在仪表板中[更改磁贴](service-dashboard-edit-tile.md)。
* [选择磁贴](service-dashboard-tiles.md)以打开基础报表。
* 虽然数据集将按计划每日刷新，你可以更改刷新计划或根据需要使用**立即刷新**来尝试刷新

## <a name="next-steps"></a>后续步骤
[Power BI 入门](service-get-started.md)

[在 Power BI 中获取数据](service-get-data.md)

