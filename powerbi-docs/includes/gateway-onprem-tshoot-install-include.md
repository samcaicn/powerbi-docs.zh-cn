## <a name="update-to-the-latest-version"></a>更新到最新版本
网关版本过期后，可能会遇到很多问题。  好的常规做法是确保所使用的是最新版本。  如果你已经一个月或更长时间没有升级网关，可能需要考虑安装网关最新版本，并检查此问题是否会重现。

## <a name="common-issues"></a>常见问题
以下是一些常见的问题及解决方案，这些解决方案已帮助了许多处于 Internet 访问受限环境的客户。

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="authentication-to-proxy-server"></a>对代理服务器的身份验证
代理可能需要对域用户帐户进行身份验证。 默认情况下，网关使用 Windows 服务登录用户的服务 SID。 将登录用户更改为域用户可有助于完成此操作。 有关详细信息，请参阅[将网关服务帐户更改为域用户](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user)。

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>你的代理服务器仅支持端口 80 和 443 通信
部分代理服务器将通信限制为仅端口 80 和 443。 默认情况下，与 Azure 服务总线的通信将发生在除 443 之外的端口上。

可以使用 HTTPS 替代直接 TCP，以强制网关与 Azure 服务总线通信。 需要修改 *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* 文件。 将值从 `AutoDetect` 更改为 `Https`。 默认情况下，此文件位于 *C:\Program Files\On-premises data gateway* 。

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>安装
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>错误：无法将用户添加到组。  (-2147463168   PBIEgwService   Performance Log Users   )
如果尝试在域控制器上安装网关，你可能会收到此错误。 不支持在域控制器上部署。 你需要在不是域控制器的计算机上部署网关。

