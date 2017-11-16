## <a name="using-the-username-or-userprincipalname-dax-function"></a>使用 username() 或 userprincipalname() DAX 函数
可在数据集内利用 DAX 函数 username() 或 userprincipalname()。 可在 Power BI Desktop 中的表达式内使用它们。 将在 Power BI 服务内使用你发布的模型。

在 Power BI Desktop 中，username() 将返回采用域\用户格式的用户，userprincipalname() 将返回采用 user@contoso.com 格式的用户。

在 Power BI 服务中，username() 和 userprincipalname() 都将返回用户的用户主体名称 (UPN)。 这看起来类似于电子邮件地址。

