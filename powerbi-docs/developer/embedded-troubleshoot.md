---
title: "嵌入式应用程序疑难解答"
description: "本文介绍了从 Power BI 嵌入内容时可能会遇到的一些常见问题。"
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
ms.date: 2/26/2018
ms.author: maghan
ms.openlocfilehash: 78e3361578b82a9ebf69feae1f7a8ac54966bbc9
ms.sourcegitcommit: 0a16dc12bb2d39c19e6b0002b673a8c1d81319c9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="troubleshooting-your-embedded-application"></a>嵌入式应用程序疑难解答

本文介绍了从 Power BI 嵌入内容时可能会遇到的一些常见问题。

## <a name="tools-for-troubleshooting"></a>用于故障排除的工具

### <a name="fiddler-trace"></a>Fiddler 跟踪

[Fiddler](http://www.telerik.com/fiddler) 是 Telerik 提供的一款用于监视 HTTP 流量的免费工具。  可以从客户端计算机通过 Power BI API 来回查看。 这可能会显示错误和其他相关的信息。

![Fiddler 跟踪](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>浏览器中的 F12，用于前端调试

F12 将在你的浏览器中启动开发人员窗口。 它能够让你查看网络流量和其他信息。

![F12 浏览器调试](media/embedded-troubleshoot/browser-f12.png)

### <a name="extracting-error-details-from-power-bi-response"></a>从 Power BI 响应中提取错误详细信息

下面的代码片段展示了如何从 HTTP 异常中提取错误详细信息：

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
建议记录请求 ID（以及错误详细信息以供排查问题）。
请在联系 Microsoft 支持部门时提供请求 ID。

## <a name="app-registration"></a>应用注册

**应用注册失败**

Azure 门户或 Power BI 应用注册页面中的错误消息将提到权限不足的问题。 为了注册应用程序，你必须是 Azure AD 租户中的管理员，或者必须为非管理员用户启用应用程序注册。

**注册新应用时 Power BI 服务不会显示在 Azure 门户中**

至少一个用户必须注册 Power BI。 如果没看到 API 列表中列出 Power BI 服务，则表示没有用户注册 Power BI。

## <a name="rest-api"></a>REST API

**API 调用返回 401**

可能需要进一步调查 Fiddler 捕获。 Azure AD 中注册的应用程序可能缺少所需的权限范围。 验证 Azure 门户内 Azure AD 的应用注册中是否存在所需的范围。

**API 调用返回 403**

可能需要进一步调查 Fiddler 捕获。 发生 403 错误可能有几个原因。

* 用户已超过可在共享容量上生成的嵌入令牌的数量。 需要购买 Azure 容量以生成嵌入令牌，并将工作区中分配给该容量。 请参阅[在 Azure 门户创建 Power BI Embedded 容量](https://docs.microsoft.com/en-us/azure/power-bi-embedded/create-capacity)。
* Azure AD 身份验证标记已过期。
* 经过身份验证的用户不是组（应用工作区）的成员。
* 经过身份验证的用户不是组（应用工作区）的管理员。
* 可能不会正确列出身份验证标头。 请确保没有拼写错误。

应用程序的后端在调用 GenerateToken 前可能需要刷新身份验证标记。

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

**提供有效标识时生成标记失败**

由于几个不同的原因，GenerateToken 可能会失败，并提供有效标识。

* 数据集不支持有效标识
* 未提供用户名
* 未提供角色
* 未提供 DatasetId
* 用户没有正确的权限

若要验证是哪一个，请尝试以下操作。

* 执行 [get dataset](https://msdn.microsoft.com/library/mt784653.aspx)。 属性 IsEffectiveIdentityRequired 是否为 true？
* Username 是任何 EffectiveIdentity 必需的。
* 如果 IsEffectiveIdentityRolesRequired 为 true，则 Role 是必需的。
* DatasetId 是任何 EffectiveIdentity 必需的。
* 对于 Analysis Services，主用户必须是网关管理员。

## <a name="data-sources"></a>数据源

**ISV 希望相同的数据源有不同的凭据**

数据源可以为一个主用户提供一组凭据。 如果你需要使用不同的凭据，请创建其他的主用户。 然后，在每个主用户上下文中分配不同的凭据，并使用该用户的 Azure AD 标记嵌入。

## <a name="content-rendering"></a>内容呈现

**呈现或使用嵌入内容失败或超时**

请确保嵌入的标记未过期。 请确保检查嵌入的标记是否过期并刷新。 有关详细信息，请参阅[使用 JavaScript SDK 刷新标记](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example)。

**不会加载报表或仪表板**

如果用户无法查看报表或仪表板，请确保报表或仪表板在 powerbi.com 内正确加载。如果报表或仪表板没有在 powerbi.com 内加载，它将不会在你的应用程序中运行。

**报表或仪表板运行缓慢**

从 Power BI Desktop 或 powerbi.com 中打开该文件，验证性能是否可接受以排除应用程序或嵌入 API 的问题。


有关常见问题的解答，请参阅 [Power BI Embedded 常见问题解答](embedded-faq.md)。

更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)
