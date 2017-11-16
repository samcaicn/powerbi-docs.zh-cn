---
title: "检查自定义视觉对象以保障安全和隐私"
description: "在启用自定义视觉对象之前，应查看有关视觉对象的安全和隐私以确保它适合组织的标准。"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 09/05/2017
ms.author: asaxton
ms.openlocfilehash: 40c2c713615f6e9e5378d36b6b228dc864bcb57c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="review-custom-visuals-for-security-and-privacy"></a>检查自定义视觉对象以保障安全和隐私
在启用自定义视觉对象之前，应查看有关视觉对象的安全性和隐私以确保它适合组织的标准。

## <a name="enable-a-custom-visual"></a>启用自定义视觉对象
<a name="enable"></a>在你选择“**启用自定义视觉对象**”前，报表中的自定义视觉对象处于禁用状态，如下所示。  

![](media/service-custom-visuals-review-for-security-and-privacy/emptyvisual.png)

## <a name="considerations-before-you-enable-a-custom-visual"></a>启用自定义视觉对象前的注意事项
<a name="considerations"></a>

> [!WARNING]
> 自定义视觉对象包含的代码可能存在安全或隐私风险，因此在选择“启用自定义视觉对象”前，报表中的自定义视觉对象处于禁用状态。 决定是否启用自定义视觉对象时应考虑以下注意事项：
> 
> 

1. 确保信任报表中所用自定义视觉对象的作者和来源
2. 若不确定下一步操作，应求助 IT 团队，让其决策是否应对你所查看的报表启用自定义视觉对象。
3. 如果有人与你共享包含自定义视觉对象的报表，即使分享者是与你关系密切的同事，你也并非一定要启用该自定义视觉对象。 可以回过头想想手头的任务是否一定需要启用自定义视觉对象。 若对自定义视觉对象没有信心，你始终可以要求对方提供不包含自定义视觉对象的报表。

## <a name="security-best-practices-for-it-professionals-to-enable-a-custom-visual"></a>IT 专业人员启用自定义视觉对象的安全性最佳做法
<a name="security"></a>

> [!WARNING]
> 自定义视觉对象包含的代码可能存在安全或隐私风险，因此在选择“启用自定义视觉对象”前，报表中的自定义视觉对象处于禁用状态。 可按照多种最佳做法评估自定义视觉对象以保障安全和隐私。
> 
> 

1. 在组织内对自定义视觉对象进行审核。 经审核的自定义视觉对象将通过内部网站（如 SharePoint 文档库或 OneNote 文档）与内部用户共享。
2. 为业务用户提供自定义视觉对象正确使用方式的指导，以及可将安全和隐私问题发送到的电子邮件组。
3. 评估自定义视觉对象 pbiviz 文件中的 JavaScript 代码。

**评估自定义时间对象中的 JavaScript 代码**

自定义视觉对象使用 JavaScript，因此可能包含安全或隐私风险。 如果你收到来自未知来源的自定义视觉对象或含有自定义视觉对象的 pbix 文件，可能需要查看 JavaScript 以确定它是否安全。

若要评估自定义视觉对象中的 JavaScript 代码，请提取自定义视觉对象代码。 下面介绍了如何提取代码：  

1. 将 pbiviz 文件保存到文件夹。
2. 将该文件重命名为 .zip 文件。
3. 将该 zip 文件提取到本地文件夹。

## <a name="custom-visual-file-contents"></a>自定义可视化对象文件内容
pbiviz 文件的内容如下：

| **文件** | **说明** |
|:--- |:--- |
| ./package.json |清单文件，为自定义视觉对象指示要加载的文件。 |
| ./resources |包含自定义视觉对象使用的 CSS、TypeScript 和 JavaScript。 |
| ./resources/&lt;name&gt; |&lt;名称&gt;是自定义视觉对象的名称。 |
| ./resources/&lt;名称&gt;.css |自定义视觉对象的 css 资源文件。 |
| ./resources/&lt;名称&gt;.js |用户单击“启用”自定义视觉对象时或“导入”自定义视觉对象后执行的代码。 警告 JavaScript 代码可能存在安全或隐私风险。 |
| ./resources/&lt;名称&gt;.ts |TypeScript 格式的视觉对象 JavaScript 源代码。 警告 JavaScript 或 TypeScript 代码可能存在安全或隐私风险。 |
| ./resources/&lt;名称&gt;.png |向用户显示的视觉对象图标。 |

提取 pbiviz 文件后，即可评估代码。 应查找以下最佳方案和威胁。

## <a name="best-practices-to-evaluate-the-javascript-or-typescript-code"></a>评估 JavaScript 或 TypeScript 代码的最佳方案
**JavaScript** 或 **TypeScript** 代码可能存在安全或隐私风险。 应查找以下最佳方案和威胁。

### <a name="best-practices-to-evaluate-javascript-code"></a>评估 JavaScript 代码的最佳方案
* 请始终评估 .js 文件内容。 这是实际运行的代码。 可能会出现 .ts 文件内容无法编译为自定义视觉对象中包含的 .js 文件的情况。
* 请始终评估 .ts 文件内容。 你可以将 .ts 文件加载到**开发人员工具**中，导出视觉对象，并将新建 .pbiviz 文件中的生成 .js 文件与视觉对象中包含的原始 .js 文件进行对比
* 检查自定义视觉对象的图标是否与用户熟悉的其他视觉对象过于相似。
* 请始终使用具有最低权限且无法访问任何敏感数据的测试帐户评估视觉对象。 理想情况下，测试帐户是不含 Power BI 以外服务登录信息的本地帐户。

### <a name="threats-to-look-for-in-javascript-code"></a>JavaScript 代码中应查找的威胁
* 同时在编辑和查看模式下使用视觉对象时，请检查网络活动。 确保对提出的请求感到满意。 除非视觉对象作者已提前进行通信，否则你不应看到对 Power BI 域外资源的请求。
* 你看到的离开 Power BI 域的所有数据都应符合你的“正常”使用情况预期。 例如，当视觉对象实现使用 iFrame 观看其他网站中视频是视频播放器时，IFrame 请求中应有信息流动以便正确呈现视频。 但是，如果你看到跨网络传输整个数据集，则可能需要进一步确认这是否为必需的理想情况。
* 检查自定义视觉对象是否发送或存储个人身份数据。
* 检查自定义视觉对象是否试图访问本地计算机资源，例如向磁盘写入文件或访问 Cookie。
* 检查自定义视觉对象是否包含模糊代码或用途不明的代码。
* 保存过去已检查的每个视觉对象的副本。
* 如果你正在检查此前已检查视觉对象的更新，请务必检查更改。 请始终对更新进行与第一次收到视觉对象时所执行的检查同样严格的检查
* 如果发现可疑或不明代码，请联系我们，我们会随时为你提供帮助。

## <a name="next-steps"></a>后续步骤
[Power BI 中的可视化效果](power-bi-report-visualizations.md)  
[Power BI 中的自定义可视化效果](power-bi-custom-visuals.md)  
[从 Office 应用商店下载和使用自定义视觉对象](service-custom-visuals-office-store.md)  
[向报表 (Power BI Desktop) 添加自定义视觉对象](power-bi-custom-visuals-use.md)  
[向报表（Power BI 服务）添加自定义视觉对象](power-bi-report-add-custom-visual.md)  
[将自定义视觉对象发布到 Office 应用商店](developer/office-store.md)  
[自定义视觉对象开发人员工具入门](service-custom-visuals-getting-started-with-developer-tools.md)  
[如何认证自定义视觉对象](power-bi-custom-visuals-certified.md)    
[视频：与 Sachin Patney 和 Nico Cristache 一起创建 Power BI 的自定义可视化效果](https://www.youtube.com/watch?v=kULc2VbwjCc)  

更多问题？ [尝试在 Power BI 社区中提问](http://community.powerbi.com/)

