# Create an dual-stack VPN

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcorlib%2Fvpn%2Ftest%2FAzure%2Fazuredeploy.json" target="_blank">
    <img src="https://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fcorlib%2Fvpn%2Ftest%2FAzure%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

The template creates and configures the following Azure resources:

- a private virtual network
- two [Azure Public IP Addresses](https://docs.microsoft.com/azure/virtual-network/virtual-network-ip-addresses-overview-arm)
  - IPv4 address
  - IPv6 address
- port forwarding NAT via an [Azure Load Balancer](https://docs.microsoft.com/azure/load-balancer/load-balancer-overview) who binds the public IPs and forwards to the private IPs on the VM
- an [Azure Network Interface](https://docs.microsoft.com/azure/virtual-network/virtual-network-network-interface-vm) who has a private IPv4 and IPv6 address
- a linux [Azure Virtual Machine](https://docs.microsoft.com/azure/virtual-machines/linux/overview) who binds the network interface

Template output:

- **fqdn**: the fully qualified domain name for the VPN who resolves both A and AAAA records