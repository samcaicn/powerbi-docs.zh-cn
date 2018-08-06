---
title: Power BI 中的连接器扩展性
description: 连接器扩展能力、功能、安全设置和经过认证的连接器
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/25/2018
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: c63357df043ff6a646562d398a07d8042dd5a0ee
ms.sourcegitcommit: 7fb0b68203877ff01f29724f0d1761d023075445
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2018
ms.locfileid: "39256531"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI 中的连接器扩展性

在 Power BI 中，客户和开发人员可以通过多种方式扩展其能够连接到的数据源，例如使用现有连接器和通用数据源（如 ODBC、OData、Oledb、Web、CSV、XML、JSON）。 除这些数据源外，开发人员还可以创建称为**自定义连接器**的数据扩展插件，并对连接器进行认证，使其成为**经过认证的连接器**。

在以前版本的 Power BI 中，使用功能开关启用了使用**自定义连接器**的功能。 现在，有一个菜单可供安全地控制想要允许在系统上运行的自定义代码的级别：所有自定义连接器，或仅限 Microsoft 在“获取数据”对话框中认证和分发的连接器。

## <a name="custom-connectors"></a>自定义连接器

**自定义连接器**能够容纳各种可能性，包括对业务至关重要的小型 API，以及 Microsoft 尚未实施的大型行业特定服务。 大多数此类连接器将由供应商自行分发，如果需要特定的数据连接器，则应联系供应商。

若要使用**自定义连接器**，请将它们放在 *\[Documents]\\Power BI Desktop\\Custom Connectors* 文件夹中，并按照以下部分所述调整安全设置。

无需调整安全设置即可使用**经过认证的连接器**。

## <a name="data-extension-security"></a>数据扩展插件安全性

若要更改数据扩展插件安全设置，请在 **Power BI Desktop** 中依次选择“文件”>“选项和设置”>“选项”>“安全”。

![控制是否想要能够使用“数据扩展插件安全性”选项加载自定义连接器](media/desktop-connector-extensibility/data-extension-security-1.png)

在“数据扩展插件”下，可从两个安全级别中进行选择：

* （推荐）仅允许加载经过认证的扩展
* （不推荐）允许加载任何插件而不发出警告

如果计划使用**自定义连接器**或你或第三方开发并分发的连接器，则必须选择“（不推荐）允许加载任何插件而不发出警告”。 除非计划运行**自定义连接器**，否则我们不建议使用该安全设置。

使用 **（推荐）** 安全设置时，如果系统中存在自定义连接器，则会显示错误，说明由于安全原因而无法加载连接器。

![对话框将说明，由于安全设置而无法加载自定义连接器，在本例中为 TripPin](media/desktop-connector-extensibility/data-extension-security-2.png)

若要解决该错误并使用这些连接器，你必须将安全设置更改为之前所述的 **（不推荐）** 设置，然后重启 **Power BI Desktop**。

## <a name="certified-connectors"></a>经过认证的连接器

数量有限的数据扩展插件会被视为**经过认证**，此类经过认证的连接器可通过“获取数据”对话框获得，但负责维护和支持的仍然是创建连接器的第三方开发人员。 虽然 Microsoft 会分发这些连接器，但我们不对其性能或持续正常工作负责。

如果想要认证自定义连接器，请让供应商与 Microsoft 联系。
