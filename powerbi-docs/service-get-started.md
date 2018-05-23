---
title: Power BI 服务入门
description: Power BI 服务入门
author: adamw
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: d66653ebe9232cb6da2f3c53b01e791ca9966db9
ms.sourcegitcommit: dcde910817720c05880ffe24755034f916c9b890
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
---
# <a name="get-started-with-power-bi-service-apppowerbicom"></a>Power BI 服务入门 (app.powerbi.com)
本教程将帮助你开启使用 ***Power BI 服务*** 之旅。 若要了解 Power BI 服务如何适应其他 Power BI 产品/服务，我们强烈建议你先阅读[什么是 Power BI](guided-learning/gettingstarted.yml?tutorial-step=1)。

![图片展示桌面、服务和移动之间的关系](media/service-get-started/power-bi-components.png)

Power BI 服务提供免费版本和 Pro 版本。 无论使用哪个版本，如果你已创建帐户，则只需打开浏览器并键入 app.powerbi.com 即可打开 Power BI 服务。 对于新用户，我们建议从 www.powerbi.com 入手。 在该网站中，可以先详细了解 Power BI，然后再登录到该服务。  如果你已做好试用的准备，请选择右上角显示的“免费注册”链接。 如果管理员已为你启用 Power BI，请不要使用“免费注册”按钮，而可直接转到 app.powerbi.com。 

![登录或免费注册](media/service-get-started/power-bi-sign-up.png)

如果你需要有关使用 Power BI Desktop 的帮助，请参阅 [Desktop 入门](desktop-getting-started.md)。 如果正在寻找有关 Power BI 移动端的帮助，请参阅[适用于移动设备的 Power BI 应用](mobile-apps-for-mobile-devices.md)。

> [!TIP]
> 更喜欢可以自主掌控进度的免费培训课程？ [在 EdX 上注册学习我们的“数据分析和可视化”课程](http://aka.ms/edxpbi)。

请在 YouTube 上观看我们的[播放列表](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP)。 不妨先从观看“Power BI 服务简介”视频入手：
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 
> 
> 

Microsoft Power BI 可帮助你及时掌握对你重要的信息。  借助 Power BI 服务，***仪表板***可帮助你对企业状况了如指掌。  你的仪表板显示各种***磁贴***，你可单击这些磁贴打开***报表***来进一步了解详情。  连接到多个***数据集***将所有相关数据组合在一起。 是否需要了解构成 Power BI 的构建块的帮助？  请参阅 [Power BI - 基本概念](service-basic-concepts.md)。

如果你在 Excel 或 CSV 文件中具有重要数据，你可以创建 Power BI 仪表板以便随时随地掌握最新信息，并与他人分享自己的见解。  你是否订阅了 SaaS 应用程序（如 Salesforce）？  从连接到 Salesforce 开始，基于该数据自动创建仪表板，或[查看可以连接到的所有其他 SaaS 应用](service-get-data.md)。 如果你是组织成员，请查看是否已向你发布任何[应用](service-create-distribute-apps.md)。

了解所有其他[获取 Power BI 数据](service-get-data.md)的方式。

## <a name="step-1-get-data"></a>步骤 1：获取数据
下面举例说明如何从 CSV 文件中获取数据。 想要学习此教程吗？ [下载此示例 CSV 文件](http://go.microsoft.com/fwlink/?LinkID=521962)。

1. [登录 Power BI](http://www.powerbi.com/)。 还没有帐户？ 别担心，可以免费注册。
2. Power BI 将在浏览器中打开。 在左侧导航栏底部选择“获取数据”。
   
   ![获取数据](media/service-get-started/getdata3.png)
3. 然后，选择“文件”。 
   
   ![获取文件](media/service-get-started/gs1.png)
4. 浏览到计算机上的该文件，然后选择“打开”。 如果已将文件保存在 OneDrive for Business 中，请选择相应的选项。 如果已将文件保存在本地，请选择“本地文件”。 
   
   ![“获取数据”>“文件”屏幕](media/service-get-started/gs2.png)
5. 在本教程中，我们将选择“导入”，以将 Excel 文件添加为数据集，然后就可以使用它来创建报表和仪表板。 如果选择“上传”，则整个 Excel 工作簿将上传至 Power BI，然后可以在 Excel Online 中打开它并进行编辑。
   
   ![选择“导入”](media/service-get-started/power-bi-import.png)
6. 数据集准备就绪后，选择“查看数据集”在报表编辑器中打开它。 

    ![“你的数据集已就绪”对话框](media/service-get-started/power-bi-gs.png)

    由于我们尚未创建任何可视化效果，报表画布是空白的。

    ![空白报表画布](media/service-get-started/power-bi-report-editor.png)

6. 在顶部菜单栏中可以看到，有一个“阅读视图”选项。 出现“阅读视图”选项意味着当前在“编辑视图”中操作。 

    ![“阅读视图”选项](media/service-get-started/power-bi-editing-view.png)

    同时，在“编辑视图”中，可以创建和修改报表，因为你是报表的所有者，也是创建者。 与同事共享报表时，他们只能在“阅读视图”中与报表交互，因为他们是使用者。 详细了解[阅读视图和编辑视图](service-reading-view-and-editing-view.md)。
    
    进行[简要了解](service-the-report-editor-take-a-tour.md)是熟悉报表编辑器的一个不错的方法
   > 
 

## <a name="step-2-start-exploring-your-dataset"></a>步骤 2 ：着手了解你的数据集
连接到数据后，请开始浏览数据。  发现有趣的内容后，可以创建仪表板来监视内容，并查看内容在不同时间的变化。 我们来看看具体的工作方式。
    
1. 在报表编辑器中，使用页面右侧的“字段”窗格生成可视化对象。  选中“**销售总额**”和“**日期**”旁边的复选框。
   
   ![字段列表](media/service-get-started/fields.png)

2. Power BI 会分析数据并创建可视化对象。  如果先选择“日期”，你将看到一个表格。  如果先选择“销售总额”，你将看到一个图表。 切换到不同的数据显示方式。 让我们在折线图中查看此数据。 从**可视化对象窗格**中选择折线图图标（也称为模板）。
   
   ![已选中图标的报表编辑器](media/service-get-started/gettingstart5new.png)

3. 看起来不错，让我们将它固定到仪表板。 将鼠标悬停在可视化对象上，并选择“固定”图标。  固定此可视化对象时，它将存储在仪表板上并会不断更新，由此你可以大致跟踪最新值。
   
   ![“固定”图标](media/service-get-started/pinnew.png)

5. 由于这是新报表，因此在将可视化对象固定到仪表板之前，系统会提示保存。 为报表命名（例如“按时间的销售额”），然后选择“保存并继续”。 
   
   ![“保存报表”对话框](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
6. 我们将折线图固定到新仪表板并将其命名为“用于教程的财务示例”。 
   
   ![为报表命名](media/service-get-started/power-bi-pin.png)
   
 1. 选择“固定”。
   
    会显示一条成功消息（右上角附近），告知你可视化效果已作为磁贴添加到你的仪表板中。
   
    ![“已固定到仪表板”对话框](media/service-get-started/power-bi-pin-success.png)

8. 选择“转至仪表板”，查看以磁贴形式固定到新仪表板的折线图。 通过添加更多可视化对象磁贴和[重命名、调整大小、链接和重新定位磁贴](service-dashboard-edit-tile.md)来优化仪表板。
   
   ![固定了可视化效果的仪表板](media/service-get-started/power-bi-new-dashboard.png)
   
   在仪表板上选择新的磁贴，以便随时返回到报表。 Power BI 会将你返回到报表编辑器的“阅读视图”。 若要切换回“编辑视图”，请从顶部菜单栏中选择“编辑报表”。 进入“编辑视图”后，请继续浏览和固定磁贴。 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>步骤 3：使用“问答”继续探索（自然语言查询）
1. 要快速浏览数据，请尝试在问题解答框中进行询问。 “问答”问题框位于仪表板顶部（“提出有关数据的问题”），以及报表的顶部菜单栏中“提问”）。 例如，尝试键入“哪个市场的收入最高”。
   
   ![问答画布](media/service-get-started/powerbi-qna.png)

2. “问答”会搜索答案，并以可视化形式显示答案。 选择“固定”图标 ![“固定”图标](media/service-get-started/pbi_pinicon.png) 还可在仪表板上显示此可视化效果。
3. 将可视化对象固定到“用于教程的财务示例”仪表板。
   
    ![“固定到仪表板”对话框](media/service-get-started/power-bi-pin2.png)

4. 返回到仪表板，将会看到新磁贴。

   ![固定了图表的仪表板](media/service-get-started/power-bi-final-dashboard.png)

## <a name="next-steps"></a>后续步骤
准备好尝试了解更多内容？  可以参考以下主题来了解 Power BI。

* [连接到另一个数据集](service-get-data.md)。
* 与你的同事[共享仪表板](service-share-dashboards.md) 。
* 阅读[设计仪表板的提示](service-dashboards-design-tips.md)。
* 借助[移动设备上的 Power BI 应用程序](mobile-apps-for-mobile-devices.md)查看你的仪表板

还没有做好充分准备？ 请先了解以下主题，这些主题旨在帮助你适应 Power BI。

* [了解报表、数据集、仪表板和磁贴如何组合在一起](service-basic-concepts.md)
* 请访问我们的 [Power BI 引导式学习](guided-learning/index.md)站点，并学习几篇课程（非常简短）
* 观看一些 [Power BI 视频](videos.md)
* [了解我们提供了哪些示例供你使用](sample-datasets.md)

### <a name="stay-in-touch-with-power-bi"></a>时刻关注 Power BI 动态
* 关注 [Twitter 上的 @MSPowerBI](https://twitter.com/mspowerbi)
* 订阅我们的 [YouTube 视频信道](https://www.youtube.com/channel/UCy--PYvwBwAeuYaR8JLmrfg)
* 观看我们的 [Power BI 入门网络研讨会](webinars.md)点播
* 不确定从何处获得帮助？ 请查看我们的 [10 条关于如何获取帮助的提示](service-tips-for-finding-help.md)页

更多问题？ [尝试咨询 Power BI 社区](http://community.powerbi.com/)

