## <a name="limitations"></a>限制
以下是云模型上有关行级安全性的当前限制列表。

* 如果你以前有在 Power BI 服务中定义了角色和规则，则将需要在 Power BI Desktop 中重新创建它们。
* 只能通过使用 Power BI Desktop 客户端在创建的数据集上定义 RLS。 若想为使用 Excel 创建的数据集启用 RLS，首先需要将你的文件转换为 PBIX 文件。 [了解详细信息](../desktop-import-excel-workbooks.md)
* 仅支持 ETL 和 DirectQuery 连接。 在本地模型上处理到 Analysis Services 的实时连接。
* 问与答以及 Cortana 此时不受 RLS 的支持。 如果对所有模型配置了 RLS，你将无法看到仪表板的问与答输入框。 这还在规划之中，但具体日程尚不可知。
* 对于使用 RLS 的数据集，暂不支持外部共享。
* 对于任何给定的模型，可以分配给安全角色的 Azure AD 主体（即单个用户或安全组）的最大数量为 1,000。 若要将大量用户分配给角色，请确保分配安全组，而不是单个用户。

## <a name="known-issues"></a>已知问题
有一个已知的问题，那就是当尝试从 Power BI Desktop 发布以前已发布过的内容时，将收到一个错误信息。 该场景如下所示。

1. Anna 有一个已发布到 Power BI 服务且已配置了 RLS 的数据集。
2. Anna 在 Power BI Desktop 中更新报表并重新发布。
3. Anna 收到一个错误。

**解决方法：** 重新从 Power BI 服务中发布 Power BI Desktop 文件，直到此问题得到解决。 可以通过选择“获取数据” > “文件”来执行此操作。 

