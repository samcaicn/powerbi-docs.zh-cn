---
title: 为组织将 Power BI 内容嵌入应用程序
description: 了解如何使用 Power BI API，为组织将报表、仪表板或磁贴集成到或嵌入 Web 应用中。
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: cfc450216202f332f518955d28cb71df6aa0b800
ms.sourcegitcommit: f2b106b5eb338a64f903e8ce6793bccb07f9440a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2018
ms.locfileid: "39105260"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-organization"></a>教程：为组织将 Power BI 报表、仪表板或磁贴嵌入应用程序
本教程演示在为组织将 Power BI 嵌入应用程序时，如何使用“Power BI .NET SDK”以及“Power BI JavaScript API”将报表集成到应用程序中。 通过 Power BI，可以使用“用户拥有数据”将报表、仪表板或磁贴嵌入应用程序。 借助“用户拥有数据”，应用程序可以扩展 Power BI 服务。

![查看应用程序](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

在本教程中，了解如何：
>[!div class="checklist"]
>* 在 Azure 中注册应用程序。
>* 将 Power BI 报表嵌入到应用程序。

## <a name="prerequisites"></a>先决条件
需要 Power BI Pro 帐户和 Microsoft Azure 订阅才可开始操作。

* 如果未注册 Power BI Pro，请在开始之前[注册以获得免费试用](https://powerbi.microsoft.com/en-us/pricing/)。
* 如果没有 Azure 订阅，请在开始之前先创建一个[免费帐户](https://azure.microsoft.com/free/?WT.mc_id=A261C142F)。
* 你需要具有自己的 [Azure Active Directory 租户](create-an-azure-active-directory-tenant.md)安装程序。
* 你需要安装 [Visual Studio](https://www.visualstudio.com/)（2013 版或更高版本）。

## <a name="setup-your-embedded-analytics-development-environment"></a>设置嵌入式分析开发环境

在开始将报表、仪表板和磁贴嵌入到应用程序中之前，需要确保环境已设置为允许嵌入。 在设置过程中，需要执行以下操作。

可跟随[载入体验工具](https://aka.ms/embedsetup/UserOwnsData)完成操作，以便快速开始并下载示例应用程序，它会逐步引导你创建环境并嵌入报表。

但是，如果选择手动设置环境，则可以继续进行下面的操作。
### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>在 Azure Active Directory (Azure AD) 中注册应用程序

向 Azure Active Directory 注册应用程序，以允许应用程序访问 Power BI REST API。 此操作能够为应用程序建立标识，并指定对 Power BI REST 资源的权限。

1. 接受 [Microsoft Power BI API 条款](https://powerbi.microsoft.com/api-terms)。

2. 登录到 [Azure 门户](https://portal.azure.com)。

    ![Azure 门户主视图](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

3. 在左侧导航窗格中，依次选择“所有服务”**、**“应用注册”和“新应用程序注册”。

    ![应用注册搜索](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)</br>
    ![新应用注册](media/embed-sample-for-your-organization/embed-sample-for-your-organization-004.png)

4. 按照提示进行操作，并创建新的应用程序。 对于“用户拥有数据”，需要使用“Web 应用/API”作为应用程序类型。 还需要提供“登录 URL”，Azure AD 用其返回令牌响应。 输入特定于应用程序的值（例 如， http://localhost:13526/).

    ![创建应用](media/embed-sample-for-your-organization/embed-sample-for-your-organization-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>在 Azure Active Directory 中向应用授予权限

除了应用注册页中提供的权限之外，还需要对应用程序启用其他权限。 需要使用全局管理员帐户登录才可启用权限。

### <a name="use-the-azure-active-directory-portal"></a>使用 Azure Active Directory 门户

1. 在 Azure 门户中，转到[应用注册](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade)，再选择要用于嵌入内容的应用。

    ![选择应用](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

2. 选择“设置”，然后在“API 访问权限”下选择“所需权限”。

    ![所需权限](media/embed-sample-for-your-organization/embed-sample-for-your-organization-008.png)

3. 选择“Windows Azure Active Directory”并请务必选中“以登录用户身份访问目录”。 选择**保存**。

    ![Windows Azure AD 权限](media/embed-sample-for-your-organization/embed-sample-for-your-organization-011.png)

4. 选择**添加**。

    ![添加权限](media/embed-sample-for-your-organization/embed-sample-for-your-organization-012.png)

5. 选择“选择 API”。

    ![添加 API 访问权限](media/embed-sample-for-your-organization/embed-sample-for-your-organization-013.png)

6. 选择“Power BI 服务”，然后选择“选择”。

    ![选择 PBI 服务](media/embed-sample-for-your-organization/embed-sample-for-your-organization-014.png)

7. 选择“委派权限”下的所有权限。 需要逐一选中这些选项才能保存所做的选择。 完成时选择“保存”。

    ![选择委托的权限](media/embed-sample-for-your-organization/embed-sample-for-your-organization-015.png)

## <a name="setup-your-power-bi-environment"></a>设置 Power BI 环境

### <a name="create-an-app-workspace"></a>创建应用工作区

如果为客户嵌入报表、仪表板或磁贴，则必须将内容放在应用工作区中。

1. 首先，创建工作区。 选择“工作区” > “创建应用工作区”。 这将是放置应用程序需要访问的内容的地方。

    ![创建工作区](media/embed-sample-for-your-organization/embed-sample-for-your-organization-020.png)

2. 为工作区命名。 如果对应的“工作区 ID”不可用，则进行编辑以给定一个唯一的 ID。 这也是应用的名称。

    ![命名工作区](media/embed-sample-for-your-organization/embed-sample-for-your-organization-021.png)

3. 需要设置几个选项。 如果你选择“公开”，则组织中的任何人都可以看到工作区内容。 而如果选择“专用”，则意味着只有工作区的成员可以查看其内容。

    ![私有/公共](media/embed-sample-for-your-organization/embed-sample-for-your-organization-022.png)

    创建组后，将不能更改公共/私有设置。

4. 还可以选择成员是可以“编辑”还是具有“仅查看”访问权限。

    ![添加成员](media/embed-sample-for-your-organization/embed-sample-for-your-organization-023.png)

5. 添加你要允许其访问工作区的用户的电子邮件地址，然后选择“添加”。 无法添加组别名，只能添加单个用户别名。

6. 确定每个人员的身份是成员还是管理员。管理员可以编辑工作区本身，包括添加其他成员。 成员可以编辑工作区中的内容，除非他们只具有“仅查看”访问权限。 管理员和成员均可以发布应用。

    现在，可以查看新工作区。 Power BI 创建工作区并将其打开。 它显示在你作为成员的工作区的列表中。 作为管理员，你可以选择省略号(…) 返回并进行更改，添加新成员或更改其权限。

    ![创建工作区](media/embed-sample-for-your-organization/embed-sample-for-your-organization-025.png)

### <a name="create-and-publish-your-reports"></a>创建并发布报表

可使用 Power BI Desktop 创建报表和数据集，然后将这些报表发布到应用工作区。 发布报表的最终用户需要拥有 Power BI Pro 许可证才可发布到应用工作区。

1. 从 GitHub 下载示例[博客演示](https://github.com/Microsoft/powerbi-desktop-samples)。

    ![报表示例](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026-1.png)

2. 在 Power BI Desktop 中打开示例 PBIX 报表

   ![PBI Desktop 报表](media/embed-sample-for-your-organization/embed-sample-for-your-organization-027.png)

3. 发布到应用工作区

   ![PBI Desktop 报表](media/embed-sample-for-your-organization/embed-sample-for-your-organization-028.png)

    现在即可在 Power BI 服务在线版中查看报表。

   ![PBI Desktop 报表](media/embed-sample-for-your-organization/embed-sample-for-your-organization-029.png)

## <a name="embed-your-content-using-the-sample-application"></a>嵌入使用示例应用程序的内容

请按照这些步骤，使用示例应用程序开始嵌入内容。

1. 要开始操作，请从 GitHub 下载[用户拥有数据示例](https://github.com/Microsoft/PowerBI-Developer-Samples)。  有 3 个不同的示例应用程序，分别用于[报表](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)、[仪表板](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)和[磁贴](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)。  本文下面讨论的步骤针对的是报表应用程序。

    ![“用户拥有数据”应用程序示例](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026.png)

2. 在示例应用程序中打开 Cloud.config 文件。 需要填充几个字段才能成功运行该应用程序。 ClientID 和 ClientSecret。

    ![云配置文件](media/embed-sample-for-your-organization/embed-sample-for-your-organization-030.png)

    使用 Azure 中的“应用程序 ID”填写“ClientID”信息。 应用程序使用“ClientID”向你从其请求权限的用户标识其自身。

    若要获取“ClientID”，请执行下列步骤：

    登录到 [Azure 门户](https://portal.azure.com)。

    ![Azure 门户主视图](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    在左侧导航窗格中，依次选择“所有服务”和“应用注册”。

    ![应用注册搜索](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    选择要使用 ClientID 的应用程序。

    ![选择应用](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    你应该会看到列为 GUID 的“应用程序 ID”。 使用此“应用程序 ID”作为应用程序的“ClientID”。

    ![客户端 ID](media/embed-sample-for-your-organization/embed-sample-for-your-organization-007.png)

    用 Azure 的“应用注册”部分的“密钥”部分，填写 ClientSecret 信息。

    若要获取“ClientSecret”，请执行下列步骤：

    登录到 [Azure 门户](https://portal.azure.com)。

    ![Azure 门户主视图](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    在左侧导航窗格中，依次选择“所有服务”和“应用注册”。

    ![应用注册搜索](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    选择要使用 ClientSecret 的应用程序。

    ![选择应用](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    选择**设置**。

    ![设置](media/embed-sample-for-your-organization/embed-sample-for-your-organization-038.png)

    选择“密钥”。

    ![密钥](media/embed-sample-for-your-organization/embed-sample-for-your-organization-039.png)

    在“说明”中填写一个名称，选择“持续时间”，然后选择“保存”即可获得应用程序的该值。 保存“密钥值”并关闭“密钥”边栏选项卡后，值字段将仅在“隐藏”模式下显示，此时无法检索“密钥值”。 如果忘记了密钥值，需要在 Azure 门户中新建密钥值。

    ![密钥](media/embed-sample-for-your-organization/embed-sample-for-your-organization-031.png)

     使用 Power BI 中的“应用工作区 GUID”填写“groupId”信息。

    ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    使用 Power BI 中的“报表 GUID”填写“reportId”信息。

    ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

3. 运行应用程序！

    首先在 Visual Studio 中选择“运行”。

    ![运行应用程序](media/embed-sample-for-your-organization/embed-sample-for-your-organization-033.png)

    然后选择“获取报表”。

    ![选择内容](media/embed-sample-for-your-organization/embed-sample-for-your-organization-034.png)

    现在，可以在示例应用程序查看报表。

    ![查看应用程序](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

## <a name="embed-your-content-within-your-application"></a>在应用程序中嵌入内容
即使可以使用 [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) 完成嵌入内容的步骤，也可使用 .NET SDK 编写本文中所述的示例代码。

若要将报表集成到 Web 应用中，请使用 Power BI REST API/Power BI C# SDK 和 Azure Active Directory (AD) 授权访问令牌来获取报表。 然后，使用相同的访问令牌加载报表。 Power BI Rest API 向特定 Power BI 资源提供、编程访问权限。 有关详细信息，请参阅 [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) 和 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)。

### <a name="get-an-access-token-from-azure-ad"></a>从 Azure AD 获取访问令牌
在应用程序中，需要先从 Azure AD 获取访问令牌，再调用 Power BI REST API。 有关详细信息，请参阅[对用户进行身份验证并获取 Power BI 应用的 Azure AD 访问令牌](get-azuread-access-token.md)。

### <a name="get-a-report"></a>获取报表
若要获取 Power BI 报表，请使用[获取报表](https://docs.microsoft.com/rest/api/power-bi/reports/getreports)操作，它将获取 Power BI 报表的列表。 在报表列表中，可以获取报表 ID。

### <a name="get-reports-using-an-access-token"></a>使用访问令牌获取报表
[获取报表](https://docs.microsoft.com/rest/api/power-bi/reports/getreports)操作将返回报表的列表。 可以获取报表列表中的一个报表。

若要执行 REST API 调用，必须添加格式为“持有者 {访问令牌}”的授权标头。

#### <a name="get-reports-with-the-rest-api"></a>使用 REST API 获取报表

下面的代码示例演示如何使用 REST API 检索报表。

[示例应用程序](#embed-your-content-using-the-sample-application)的 Default.aspx.cs 文件中提供了获取要嵌入的内容项（报表、仪表板或磁贴）的示例**。

```csharp
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>使用 .NET SDK 获取报表
可以使用 .NET SDK 检索报表列表，而不用直接调用 REST API。 下面的代码示例演示如何列出报表。

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It is used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

### <a name="load-a-report-using-javascript"></a>使用 JavaScript 加载报表
可以使用 JavaScript 将报表加载到网页上的 div 元素中。

下面的代码示例演示如何从给定工作区检索报表。

[示例应用程序](#embed-your-content-using-the-sample-application)的 Default.aspx 文件中提供了加载要嵌入的内容项（报表、仪表板和磁贴）的示例**。

```javascript
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```javascript
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    }
  );
}
```

## <a name="using-a-power-bi-premium-dedicated-capacity"></a>使用 Power BI Premium 专用容量

现在你已完成应用程序的开发，接下来请回到应用工作区了解专用容量。

### <a name="create-a-dedicated-capacity"></a>创建专用容量
通过创建专用容量，则可获得在应用工作区中拥有内容专用资源这一优势。 如果工作区未分配到专用容量，则视为使用共享容量。 可使用 [Power BI Premium](../service-admin-premium-purchase.md) 创建专用容量。

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>为应用工作区分配专用容量

创建专用容量后，可将该专用容量分配给应用工作区。 要完成此操作，请按照下列步骤执行。

1. 在“Power BI 服务”中，展开工作区并针对要嵌入内容的工作区选择相应省略号。 然后选择“编辑工作区”。

    ![编辑工作区](media/embed-sample-for-your-organization/embed-sample-for-your-organization-036.png)

2. 展开“高级”，启用“专用容量”，然后选择所创建的专用容量。 然后，选择“保存”。

    ![分配专用容量](media/embed-sample-for-your-organization/embed-sample-for-your-organization-024.png)

3. 选择“保存”后，应用工作区名称旁边应显示一个钻石形状。

    ![与容量绑定的应用工作区](media/embed-sample-for-your-organization/embed-sample-for-your-organization-037.png)

## <a name="next-steps"></a>后续步骤
本教程介绍了如何使用 Power BI 组织帐户将 Power BI 内容嵌入应用程序。 现在，你可以尝试使用应用将 Power BI 内容嵌入应用程序。  还可以尝试为第三方客户嵌入 Power BI 内容。

> [!div class="nextstepaction"]
> [从应用嵌入内容](embed-from-apps.md)

> [!div class="nextstepaction"]
>[为第三方客户嵌入内容](embed-sample-for-customers.md)

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)
