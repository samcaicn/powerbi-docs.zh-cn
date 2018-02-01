---
title: "为组织将仪表板集成到应用中"
description: "了解如何使用 Power BI API 将仪表板集成到或嵌入 Web 应用中。"
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
ms.date: 10/05/2017
ms.author: maghan
ms.openlocfilehash: 36b19588d76c99cb712dc481752ebdee0c867f0d
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>为组织将仪表板集成到应用中
了解如何在为组织嵌入内容时，通过调用 REST API 和 Power BI JavaScript API，将仪表板集成到或嵌入 Web 应用中。

![嵌入的仪表板](media/integrate-dashboard/powerbi-embed-dashboard.png)

若要开始使用本演练，需要一个 **Power BI** 帐户。 如果没有帐户，可以[注册免费 Power BI 帐户](../service-self-service-signup-for-power-bi.md)，也可以创建自己的 [Azure Active Directory 租户](create-an-azure-active-directory-tenant.md)用于测试。

> [!NOTE]
> 要改用 EmbedToken 为客户嵌入仪表板吗？ 请参阅[为客户将仪表板、磁贴或报表集成到应用中](embed-sample-for-customers.md)。
> 
> 

若要将仪表板集成到 Web 应用中，请使用 Power BI REST API/Power BI C# SDK 和 Azure Active Directory (AD) 授权访问令牌来获取仪表板。 然后，使用相同的访问令牌加载仪表板。 **Power BI** API 向某些 **Power BI** 资源提供了编程访问权限。 有关详细信息，请参阅 [Power BI REST API 概述](https://msdn.microsoft.com/library/dn877544.aspx)和 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)。

## <a name="download-the-sample"></a>下载示例
本文展示了 GitHub 上 [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) 中使用的代码。 若要按照此演练操作，可以下载这个示例。

## <a name="step-1---register-an-app-in-azure-ad"></a>步骤 1 - 在 Azure AD 中注册应用
必须向 Azure AD 注册应用，才能执行 REST API 调用。 有关详细信息，请参阅[注册 Azure AD 应用以便嵌入 Power BI 内容](register-app.md)。

如果已下载[“集成仪表板”示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)，请使用注册后获取的客户端 ID 和客户端密码，以便此示例能够进行 Azure AD 身份验证。 若要配置此示例，请在 cloud.config 文件中更改客户端 ID 和客户端密码。

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>第 2 步 - 从 Azure AD 获取访问令牌
在应用内，需要先从 Azure AD 获取访问令牌，再调用 Power BI REST API。 有关详细信息，请参阅[对用户进行身份验证并获取 Power BI 应用的 Azure AD 访问令牌](get-azuread-access-token.md)。

## <a name="step-3---get-a-dashboard"></a>第 3 步 - 获取仪表板
若要获取 **Power BI** 仪表板，请使用[获取仪表板](https://msdn.microsoft.com/library/mt465739.aspx)操作，它将获取 **Power BI** 仪表板的列表。 从仪表板的列表中，你可以获取仪表板 ID。

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>使用访问令牌获取仪表板
使用在[第 2 步](#step-2-get-an-access-token-from-azure-ad)中检索的访问令牌，可以调用[获取仪表板](https://msdn.microsoft.com/library/mt465739.aspx)操作。 [获取仪表板](https://msdn.microsoft.com/library/mt465739.aspx)操作将返回仪表板列表。 可以获取仪表板列表中的一个仪表板。 下面是获取仪表板的完整 C# 方法。 

若要执行 REST API 调用，必须添加格式为“持有者 {访问令牌}”的授权标头。

#### <a name="get-dashboards-with-the-rest-api"></a>使用 REST API 获取仪表板
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>使用 .NET SDK 获取仪表板
可以使用 .NET SDK 检索仪表板列表，而不用直接调用 REST API。

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>第 4 步 - 使用 JavaScript 加载仪表板
可以使用 JavaScript 将仪表板载入网页上的 div 元素。

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

如果你下载并运行[集成仪表板示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)，示例外观将类似如下。

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>单击磁贴事件
在上述示例中，你可能已经注意到，可以处理单击仪表板上的磁贴时的事件。 有关事件的详细信息，请参阅[在 JavaScript API 内处理事件](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events)。

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

如果你已下载并运行[集成仪表板示例](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app)，单击磁贴将在仪表板下方输出文本。 文本如下所示。 这样一来，可以记录已单击的磁贴，再将用户转到相应位置。

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>使用组（应用工作区）
若要从组（应用工作区）嵌入仪表板，建议执行以下 REST API 调用，获取组中所有可用仪表板的列表。 若要查找有关此 REST API 调用的详细信息，请参阅[获取仪表板](https://msdn.microsoft.com/library/mt465739.aspx)。 必须在组中拥有权限，请求才能返回结果。

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

以上 API 返回可用仪表板的列表。 每个仪表板均有一个已创建的 EmbedUrl 属性，用以支持组嵌入。

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>限制
* 若要访问嵌入的仪表板，最终用户必须拥有 Power BI 帐户，且有权访问仪表板。 要么用户拥有仪表板，要么已与用户共享仪表板。
* 在嵌入的仪表板中暂不支持问答。
* 作为临时限制，在与安全组共享仪表板时，用户只有在 PowerBI.com 中访问仪表板后才能看到嵌入的仪表板。

## <a name="next-steps"></a>后续步骤
可以参考 GitHub 上的示例应用。 上面的示例均以此示例为依据。 有关详细信息，请参阅 [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)。

若要详细了解 JavaScript API，请参阅 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)。

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

