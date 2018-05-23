---
title: 为组织将 Power BI 磁贴集成到应用中
description: 将磁贴集成到应用的演练，示例代码
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: 6ad2138ab37b20fa16a5455ab167ec9e6b7e159c
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>将磁贴集成到应用中（用户拥有数据）
了解如何在为组织嵌入内容时，通过调用 REST API 和 Power BI JavaScript API，将磁贴集成到或嵌入 Web 应用中。

![Web 应用中嵌入的磁贴](media/integrate-tile/powerbi-embedded-tile.png)

若要开始使用本演练，需要一个 **Power BI** 帐户。 如果没有帐户，可以[注册免费 Power BI 帐户](../service-self-service-signup-for-power-bi.md)，也可以创建自己的 [Azure Active Directory 租户](create-an-azure-active-directory-tenant.md)用于测试。

> [!NOTE]
> 要改用 EmbedToken 为客户嵌入磁贴吗？ 请参阅[为客户将仪表板、磁贴或报表集成到应用中](embed-sample-for-customers.md)。
> 
> 

若要将磁贴集成到 Web 应用中，请使用 Power BI REST API/Power BI C# SDK 和 Azure Active Directory (AD) 授权访问令牌来获取磁贴。 然后，使用相同的访问令牌加载磁贴。 **Power BI** API 向某些 **Power BI** 资源提供了编程访问权限。 有关详细信息，请参阅 [Power BI REST API 概述](https://msdn.microsoft.com/library/dn877544.aspx)和 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)。

## <a name="download-the-sample"></a>下载示例
本文展示了 GitHub 上 [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) 中使用的代码。 若要按照此演练操作，可以下载这个示例。

## <a name="step-1---register-an-app-in-azure-ad"></a>步骤 1 - 在 Azure AD 中注册应用
必须向 Azure AD 注册应用，才能执行 REST API 调用。 有关详细信息，请参阅[注册 Azure AD 应用以便嵌入 Power BI 内容](register-app.md)。

如果已下载 [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)，请使用注册后获取的客户端 ID 和客户端密码，以便此示例能够进行 Azure AD 身份验证。 若要配置此示例，请在 cloud.config 文件中更改客户端 ID 和客户端密码。

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>第 2 步 - 从 Azure AD 获取访问令牌
在应用内，需要先从 Azure AD 获取访问令牌，再调用 Power BI REST API。 有关详细信息，请参阅[对用户进行身份验证并获取 Power BI 应用的 Azure AD 访问令牌](get-azuread-access-token.md)。

## <a name="step-3---get-a-tile"></a>第 3 步 - 获取磁贴
若要获取 Power BI 磁贴，请使用[获取磁贴](https://msdn.microsoft.com/library/mt465741.aspx)操作，以获取给定仪表板中的 Power BI 磁贴列表。 在磁贴列表中，可以获取磁贴 ID 和嵌入 URL。

必须先检索仪表板 ID，然后才能获取磁贴。 若要了解如何检索仪表板，请参阅[将仪表板集成到应用中（用户拥有数据）](integrate-dashboard.md)。

### <a name="get-tiles-using-an-access-token"></a>使用访问令牌获取磁贴
使用在[第 2 步](#step-2-get-an-access-token-from-azure-ad)中检索的访问令牌，可以调用[获取磁贴](https://msdn.microsoft.com/library/mt465741.aspx)操作。 [获取磁贴](https://msdn.microsoft.com/library/mt465741.aspx)操作可返回磁贴列表。 可以获取磁贴列表中的一个磁贴。 下面展示了用于获取磁贴的完整 C# 方法。 

若要执行 REST API 调用，必须添加格式为“持有者 {访问令牌}”的授权标头。

#### <a name="get-tiles-with-the-rest-api"></a>使用 REST API 获取磁贴
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>使用 .NET SDK 获取磁贴
可以使用 .NET SDK 来检索仪表板列表，而不用直接调用 REST API。

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>第 4 步 - 使用 JavaScript 加载磁贴
可以使用 JavaScript 将磁贴加载到网页上的 div 元素中。

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

如果下载并运行了 [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)，示例将如下所示。

![Web 应用中嵌入的磁贴](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>使用组（应用工作区）
若要从组（应用工作区）嵌入磁贴，建议执行以下 REST API 调用，获取组仪表板中所有可用磁贴的列表。 若要详细了解此 REST API 调用，请参阅[获取磁贴](https://msdn.microsoft.com/library/mt465741.aspx)。 必须在组中拥有权限，请求才能返回结果。

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

上面的 API 返回可用磁贴列表。 每个磁贴都有已创建的 EmbedUrl 属性，此属性支持组嵌入。

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>后续步骤
在 PowerBI 中[嵌入磁贴](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed) - JavaScript Wiki

[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)。

GitHub 上的 [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) 示例。

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

