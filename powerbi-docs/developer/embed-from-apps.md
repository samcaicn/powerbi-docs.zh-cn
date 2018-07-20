---
title: 从应用嵌入报表或仪表板
description: 了解如何从 Power BI 应用（而不是从应用工作区）集成或嵌入报表或仪表板。
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: how-to
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 2817ccb25fc9aa6d3e8150c776558366dcf0ccb6
ms.sourcegitcommit: 0c870a006e525447497e678484874a2f137b9abd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39088830"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>从应用嵌入报表或仪表板

在 Power BI 中，可以创建应用，以将相关仪表板和报表汇总到一处，然后将其发布给组织中的大量人员。 如果所有用户都是 Power BI 用户，则这些应用的使用情况具有关联性，因此可以使用 Power BI 应用与他们共享内容。 我们将分享几个快速步骤，说明如何实现将已发布 Power BI 应用外的内容嵌入到第三方应用程序。

## <a name="how-to-grab-report-embed-url-for-embedding"></a>如何获取执行嵌入所需的报表嵌入 URL

1. 通过与自己共享或引导其他用户完成此流程，在用户工作区（“我的工作区”）中实例化应用程序。

2. 在 Power BI 服务中打开所需报表。

3. 转到“文件”->“在 SharePoint Online 中嵌入”，从此处获取报表嵌入 URL（如以下快照中所示），或调用 GetReports/GetReport REST API 并从响应中提取相应的报表 embedURL 字段（请注意，REST 调用不应具有 URL 中包含的工作区标识符，因为应用已在用户工作区中实例化）。

4. 将步骤 3 中检索到的嵌入 URL 用于 JS SDK。

    ![从应用嵌入内容](media/embed-from-apps/embed-from-app.png)

## <a name="how-to-grab-dashboard-embed-url-for-embedding"></a>如何获取执行嵌入所需的仪表板嵌入 URL

1. 通过与自己共享或引导其他用户完成此流程，在用户工作区（“我的工作区”）中实例化应用程序。

2. 调用 GetDashboards REST API 并从响应中提取相应的仪表板 embedURL 字段（请注意，REST 调用不应具有 URL 中包含的工作区标识符，因为应用已在用户工作区中实例化）。

3. 将步骤 4 中检索到的嵌入 URL 用于 JS SDK。

## <a name="next-steps"></a>后续步骤

另请了解如何为第三方客户和组织从应用工作区嵌入内容。

> [!div class="nextstepaction"]
>[为第三方客户嵌入内容](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[为组织嵌入内容](embed-sample-for-your-organization.md)