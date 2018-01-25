---
title: "使用 Power BI 连接到 Azure 安全中心"
description: "适用于 Power BI 的 Azure 安全中心"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: e26a26d7cba2ae3d68586a2e0dcdf87481009bd6
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-azure-security-center-with-power-bi"></a>使用 Power BI 连接到 Azure 安全中心
通过将 Azure 安全数据与 Power BI 连接来深入了解 Azure 工作负荷安全性。 Power BI 会自动基于 Azure 安全中心数据来创建仪表板和报表，从而使你可以分析和浏览数据。

连接到适用于 Power BI 的 [Azure 安全中心内容包](https://app.powerbi.com/getdata/services/azure-security-center)。

## <a name="how-to-connect"></a>如何连接
1. 选择左侧导航窗格底部的**获取数据**。
   
   ![](media/service-connect-to-azure-security-center/getdata.png)
2. 在**服务**框中，选择**获取**。
   
   ![](media/service-connect-to-azure-security-center/services.png)
3. 选择**Azure 安全中心** \> **获取**。
   
   ![](media/service-connect-to-azure-security-center/asc.png)
4. 指定订阅 ID。 请参阅下面有关[查找这些参数](#FindingParams)的详细信息。
   
   ![](media/service-connect-to-azure-security-center/params.png)
5. 对于**身份验证方法**，选择**oAuth2**\>**登录**。 出现提示时，输入你的 Azure 凭据。
   
    ![](media/service-connect-to-azure-security-center/creds.png)
6. 审批后，导入过程将自动开始。 导入完成后，在导航窗格中将会出现新的仪表板、报表和模型。 选择仪表板查看已导入的数据。
   
     ![](media/service-connect-to-azure-security-center/dashboard.png)

**下一步？**

* 尝试在仪表板顶部的[在“问答”框中提问](power-bi-q-and-a.md)
* 在仪表板中[更改磁贴](service-dashboard-edit-tile.md)。
* [选择磁贴](service-dashboard-tiles.md)以打开基础报表。
* 虽然数据集将按计划每日刷新，你可以更改刷新计划或根据需要使用**立即刷新**来尝试刷新

## <a name="whats-included"></a>包含的内容
该内容包中包含资源安全统计信息、警报分析和预防分析等方面的深入见解。

## <a name="system-requirements"></a>系统要求
此内容包需要可以在启用 Azure 安全中心的情况下访问订阅 ID。 请在 Azure 门户的 [Azure 安全中心](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityDashboardStartBladeV2)中查看详细信息。

内容包还要求用户使用组织帐户（非个人帐户）连接。

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>查找参数
可通过两种简单的方法来查找订阅 ID。

1. 从 https://portal.azure.com -&gt; 浏览 -&gt; 订阅 -&gt; 订阅 ID
2. 从 https://manage.windowsazure.com -&gt; 设置 -&gt; 订阅 ID

订阅 ID 会是一组较长的数字和字符，类似于上面步骤 \#4 中的示例。 

## <a name="troubleshooting"></a>故障排除
数据可能需要一些时间来进行加载，具体取决于你的帐户的大小。 如果你在登录期间遇到错误，请确认你的参数和帐户启用了 Azure 安全中心。

如果内容包加载但不显示任何数据，请确认正使用组织帐户连接。 虽然 Azure 安全中心支持个人帐户，但如果用户使用非组织的帐户连接，则 API（和内容包）不返回预期值。 请提供组织帐户的访问权限并再次尝试连接。

## <a name="next-steps"></a>后续步骤
[Power BI 入门](service-get-started.md)

[在 Power BI 中获取数据](service-get-data.md)

