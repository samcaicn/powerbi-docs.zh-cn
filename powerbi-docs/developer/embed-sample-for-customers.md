---
title: "为客户将 Power BI 内容嵌入应用中"
description: "了解如何使用 Power BI API，为客户将仪表板、磁贴或报表集成到或嵌入 Web 应用中。"
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/11/2018
ms.author: maghan
ms.openlocfilehash: c6b9edb929934a80886874fe421f11cc7462dbd8
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application"></a>将 Power BI 仪表板、磁贴或报表嵌入应用中
了解如何在为客户嵌入内容时，通过调用 Power BI .Net SDK 和 Power BI JavaScript API，将仪表板、磁贴或报表集成到或嵌入 Web 应用中。 这通常是 ISV 方案。

![嵌入的仪表板](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

若要开始按照此演练操作，需要有 Power BI Pro 帐户。 如果没有帐户，可以依次[注册免费 Power BI 帐户](../service-self-service-signup-for-power-bi.md)和 [Power BI Pro 试用版](../service-self-service-signup-for-power-bi.md#in-service-power-bi-pro-60-day-trial)，也可以创建自己的 [Azure Active Directory 租户](create-an-azure-active-directory-tenant.md)用于测试。

> [!NOTE]
> 要改为为组织嵌入仪表板？ 请参阅[为组织将仪表板集成到应用中](integrate-dashboard.md)。
> 
> 

若要将仪表板集成到 Web 应用，请使用 **Power BI** API 和 Azure Active Directory (AD) 授权**访问令牌**来获取仪表板。 然后，使用嵌入令牌加载仪表板。 **Power BI** API 向某些 **Power BI** 资源提供了编程访问权限。 有关详细信息，请参阅 [Power BI REST API 概述](https://msdn.microsoft.com/library/dn877544.aspx)、[Power BI .NET SDK](https://github.com/Microsoft/PowerBI-CSharp) 和 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)。

## <a name="download-the-sample"></a>下载示例
本文展示了 GitHub 上[“为组织嵌入内容”示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)中使用的代码。 若要按照此演练操作，可以下载这个示例。

## <a name="step-1---register-an-app-in-azure-ad"></a>步骤 1 - 在 Azure AD 中注册应用
必须向 Azure AD 注册应用，才能执行 REST API 调用。 有关详细信息，请参阅[注册 Azure AD 应用以便嵌入 Power BI 内容](register-app.md)。

如果已下载[“为组织嵌入内容”示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)，请使用注册后获取的客户端 ID，以便此示例能够进行 Azure AD 身份验证。 若要配置此示例，请在 web.config 文件中更改客户端 ID。

## <a name="step-2---get-an-access-token-from-azure-ad"></a>第 2 步 - 从 Azure AD 获取访问令牌
在应用内，需要先从 Azure AD 获取访问令牌，再调用 Power BI REST API。 有关详细信息，请参阅[对用户进行身份验证并获取 Power BI 应用的 Azure AD 访问令牌](get-azuread-access-token.md)。

若要查看相关示例，可以参阅 Controllers\HomeController.cs 中的每个内容项任务。

## <a name="step-3---get-a-content-item"></a>第 3 步 - 获取内容项
若要嵌入 Power BI 内容，需要执行几项操作，以确保能够正确嵌入内容。 虽然可以直接通过 REST API 完成所有这些步骤，但示例应用和本文中的示例都是使用 .NET SDK 执行这些操作。

### <a name="create-the-power-bi-client-with-your-access-token"></a>使用访问令牌创建 Power BI 客户端
建议使用访问令牌创建 Power BI 客户端对象，以便能够与 Power BI API 进行交互。 为此，使用 Microsoft.Rest.TokenCredentials 对象包装 AccessToken。

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>获取要嵌入的内容项
使用 Power BI 客户端对象检索对要嵌入的项的引用。 可以嵌入仪表板、磁贴或报表。 下面的示例展示了如何从给定工作区检索首个仪表板、磁贴或报表。

有关示例，请参阅[“应用拥有数据”示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)的 Controllers\HomeController.cs。

**仪表板**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**磁贴**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**报表**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>创建嵌入令牌
需要生成嵌入令牌，以便能够通过 JavaScript API 使用此令牌。 嵌入令牌特定于要嵌入的项。 也就是说，只要嵌入 Power BI 内容，就需要为其新建嵌入令牌。 有关详细信息（包括要使用哪个 accessLevel），请参阅 [GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx)。

> [!IMPORTANT]
> 由于嵌入令牌仅用于开发测试，因此 Power BI 主帐户生成的嵌入令牌数量有限。 对于嵌入生产方案，[必须购买容量](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical)。 购买容量后便不会限制嵌入令牌生成。

有关示例，请参阅[“为组织嵌入内容”示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)的 Controllers\HomeController.cs。

假设为 EmbedConfig 和 TileEmbedConfig 创建了类。 Models\EmbedConfig.cs 和 Models\TileEmbedConfig.cs 中提供了相关示例。

**仪表板**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**磁贴**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**报表**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```



## <a name="step-4---load-an-item-using-javascript"></a>第 4 步 - 使用 JavaScript 加载项
可以使用 JavaScript 将仪表板载入网页上的 div 元素。 此示例对仪表板、磁贴或报表使用 EmbedConfig/TileEmbedConfig 模型和视图。 有关使用 JavaScript API 的完整示例，可以参阅 [Microsoft Power BI 嵌入示例](https://microsoft.github.io/PowerBI-JavaScript/demo)。

[“为组织嵌入内容”示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)中提供了相关应用示例。

**Views\Home\EmbedDashboard.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>后续步骤
可以参考 GitHub 上的示例应用。 上面的示例均以此示例为依据。 有关详细信息，请参阅[“为组织嵌入内容”示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)。

若要详细了解 JavaScript API，请参阅 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)。

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

