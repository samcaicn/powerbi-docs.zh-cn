## <a name="firewall-or-proxy"></a>防火墙或代理
有关为你的网关提供代理信息的信息，请参阅[为 Power BI Gateway 配置代理设置](../service-gateway-proxy.md)。

可以在 PowerShell 提示符处运行 [Test-NetConnection](https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection) 以进行测试，从而确定防火墙或代理是否可能会阻止连接。 这将测试与 Azure 服务总线的连接性。 这仅测试网络连接，与云服务器服务或网关没有任何关系。 它有助于确定你的计算机是否可以实际连接到互联网。

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection 仅适用于 Windows Server 2012 R2 及更高版本。 还适用于 Windows 8.1 及更高版本。 在旧版操作系统中，可以使用 Telnet 测试端口连接性。
> 
> 

结果应与以下所示类似。 不同之处在于 TcpTestSucceeded。 如果 **TcpTestSucceeded** 不为 *true*，则你可能会被防火墙阻止。

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

如果你想做到面面俱到，请将 **ComputerName** 和 **Port** 值替换为对[端口](../service-gateway-onprem.md#ports)列出的相应项

防火墙可能也会阻止 Azure 服务总线与 Azure 数据中心之间的连接。 如果是这种情况，那么你需要把这些数据中心中你所在区域的 IP 地址列入白名单（取消阻止）。 你可以在[此处](https://www.microsoft.com/download/details.aspx?id=41653)获得 Azure IP 地址列表。

