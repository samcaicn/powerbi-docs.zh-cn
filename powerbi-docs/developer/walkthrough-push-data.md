---
title: "将数据推送到数据集"
description: "将数据推送到 Power BI 数据集"
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
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: e62b08614a38502fb79f48f369013d32fd538659
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="push-data-into-a-power-bi-dataset"></a>将数据推送到 Power BI 数据集
借助 Power BI API，你可以将数据推送到 Power BI 数据集。 例如，想要扩展现有业务工作流以将关键数据推送到数据集时，即可使用它。 在本例中，你想要将带有“产品”表的“市场部市场营销”数据集推送到数据集。

在开始将数据推送到数据集之前，你需要 Azure Active Directory (Azure AD) 和 [Power BI 帐户](create-an-azure-active-directory-tenant.md)。

## <a name="steps-to-push-data-into-a-dataset"></a>将数据推送到数据集的步骤
* 步骤 1：[将应用注册到 Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* 步骤 2：[获取身份验证访问令牌](walkthrough-push-data-get-token.md)
* 步骤 3：[在 Power BI 中创建数据集](walkthrough-push-data-create-dataset.md)
* 步骤 4：[获取数据集以向 Power BI 表中添加行](walkthrough-push-data-get-datasets.md)
* 步骤 5：[向 Power BI 表中添加行](walkthrough-push-data-add-rows.md)

下一部分是关于推送数据的 Power BI API 操作的一般讨论。

## <a name="power-bi-api-operations-to-push-data"></a>推送数据的 Power BI API 操作
借助 Power BI REST API，你可以将数据源推送到 Power BI。 当应用向数据集添加行时，将使用更新的数据自动更新仪表板上的磁贴。 若要推送数据，请使用[创建数据集](https://msdn.microsoft.com/library/mt203562.aspx)操作和[添加行](https://msdn.microsoft.com/library/mt203561.aspx)操作。 若要查找数据集，请使用[获取数据集](https://msdn.microsoft.com/library/mt203567.aspx)操作。 进行以上任意操作时，可以传递组 ID 以将其用于组。 使用[获取组](https://msdn.microsoft.com/library/mt243842.aspx)操作以获取组 ID 的列表。 有关如何使用 Power BI REST API 的示例，请参阅 [APIARY 上的 Power BI REST API](http://docs.powerbi.apiary.io/)。

将数据推送到数据集的操作如下：

* [创建数据集](https://msdn.microsoft.com/library/mt203562.aspx)
* [获取数据集](https://msdn.microsoft.com/library/mt203567.aspx)
* [添加行](https://msdn.microsoft.com/library/mt203561.aspx)
* [获取组](https://msdn.microsoft.com/library/mt243842.aspx)

通过将 JavaScript 对象表示法 (JSON) 字符串传递给 Power BI 服务，在 Power BI 中创建数据集。 若要了解有关 JSON 的详细信息，请参阅 [JSON 简介](http://json.org/)。

数据集的 JSON 字符串具有以下格式：

**Power BI 数据集 JSON 对象**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

因此，对于我们的“市场部市场营销”数据集示例，将传递类似以下示例的 JSON 字符串。 在此示例中，**SalesMarketing** 是该数据集的名称，**产品**是表的名称。 定义表后，再定义表架构。 对于 **SalesMarketing** 数据集，表架构具有这些列：ProductID、制造商、类别、市场细分、产品和 IsCompete。

**数据集对象 JSON 示例**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

对于 Power BI 表架构，可以使用以下数据类型。

## <a name="power-bi-table-data-types"></a>Power BI 表数据类型
| **数据类型** | **限制** |
| --- | --- |
| Int64 |不允许使用 Int64.MaxValue 和 Int64.MinValue。 |
| 双精度 |不允许使用 Double.MaxValue 和 Double.MinValue 值。 NaN 某些函数（例如 Min、Max）中不支持使用正无穷和负无穷。 |
| 布尔 |无 |
| 日期时间 |在数据加载期间，我们将不足一天的值量化为 1/300 秒（3.33 毫秒）的整数倍。 |
| 字符串 |当前允许最多 12.8 万个字符。 |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>了解有关将数据推送到 Power BI 的详细信息
若要开始将数据推送到数据集，请参阅左侧导航窗格中的[步骤 1：将应用注册到 Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)。

[下一步 >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>后续步骤
[注册 Power BI](create-an-azure-active-directory-tenant.md)  
[创建数据集](https://msdn.microsoft.com/library/mt203562.aspx)  
[获取数据集](https://msdn.microsoft.com/library/mt203567.aspx)  
[添加行](https://msdn.microsoft.com/library/mt203561.aspx)  
[获取组](https://msdn.microsoft.com/library/mt243842.aspx)  
[JSON 简介](http://json.org/)  
[Power BI REST API 概述](overview-of-power-bi-rest-api.md)  
[APIARY 上的 Power BI REST API](http://docs.powerbi.apiary.io/)  
更多问题？ [尝试参与 Power BI 社区](http://community.powerbi.com/)

