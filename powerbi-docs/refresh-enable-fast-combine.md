---
title: "禁用隐私设置"
description: "如何启用 Personal Gateway 中的快速合并以对刷新禁用隐私设置。"
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 1e68f7df5214e038df8bcd1584acb815c0af98bf
ms.sourcegitcommit: 70e9239e375ae03744fb9bc122d5fc029fb83469
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>禁用 Power BI Gateway - Personal 中的隐私设置
> [!NOTE]
> 提供适用于 Power BI 的个人网关新版本，称为“本地数据网关（个人模式）”。 下面的文章介绍了以前版本的个人网关（称为 Power BI Gateway-Personal），它将在 2017 年 7 月 31 日之后停用并停止工作。 有关新版本的个人网关的信息（包括如何安装新版本），请参阅[本地数据网关（个人模式）文章](service-gateway-personal-mode.md)。 快速合并还可用于新版本的个人网关，该功能也在该文章中进行了介绍。
> 
> 

通过个人网关使用时，根据数据源的隐私设置，可能收到以下错误。

> *处理数据集中的数据时出错。*
> 
> *[无法合并数据] &lt;查询部分&gt;/&lt;…&gt;/&lt;…&gt; 正在访问的数据源具有无法一起使用的隐私级别。请重新生成此数据组合。*
> 
> 

若要解决此错误，可开启**快速合并**。 **快速合并**将忽略允许合并不同数据源的隐私设置。

> [!NOTE]
> 合并数据时不会考虑隐私级别。 这可能会导致在合并数据时向其他数据源公开敏感数据或机密数据。
> 
> 

## <a name="what-is-fast-combine"></a>什么是快速合并？
若要了解有关隐私级别和快速合并的详细信息，请参阅 [Privacy Levels](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)（隐私级别）。 隐私级别将默认设置为专用，这就可能导致上述错误。 这是因为设置为专用会将数据源从其他源隔离。 说明这种设置有问题的一个例子便是导致参数化查询从其他数据源获取输入。

启用快速合并将忽略隐私设置并允许执行发生。

## <a name="turn-on-fast-combine"></a>启用快速合并
可使用以下步骤启用个人网关的快速合并。 本地数据网关不具有此设置。

1. 打开 **ConnectorConfig.xml**。  它可能位于你计算机中的两个位置中的一个。  如果你是计算机管理员，将是以下位置。
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    如果你不是管理员，则将是以下位置。
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
    
2. 将值为 true 的 **&lt;EnableFastCombine&gt;** 元素添加到配置文件。 添加此元素将启用**快速合并**。
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. 退出并重新启动网关配置屏幕。
4. 你将看到让你知晓快速合并已启用的状态。
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>禁用快速合并
1. 打开 **ConnectorConfig.xml**。  它可能位于你计算机中的两个位置中的一个。  如果你是计算机管理员，将是以下位置。
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    如果你不是管理员，则将是以下位置。
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2. 删除配置文件中的 **&lt;EnableFastCombine&gt;** 元素。 删除此元素将禁用**快速合并**。
3. 退出并重新启动网关配置屏幕。
4. 你将不再看到让你知晓**快速合并**已启用的状态。

## <a name="next-steps"></a>后续步骤
[本地数据网关（个人模式）- 新版本的个人网关](service-gateway-personal-mode.md)
[隐私级别](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Power BI Desktop 中的常见查询任务](desktop-common-query-tasks.md)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

