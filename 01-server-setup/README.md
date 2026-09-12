# Step 1 – Windows Server VM

## Objective

Deploy a Windows Server 2022 VM in Microsoft Azure as the foundation for the Active Directory environment.

## Configuration

- VM: DC01
- OS: Windows Server 2022 Datacenter
- VM Size: D2als_v7
- Region: UK West
- OS Disk: 30 GiB Standard SSD
- VNet: vnet-centralus-1
- Subnet: 172.16.0.0/24
- Private IP: 172.16.0.4

## Azure Resources

- Virtual Machine
- Network Interface (NIC)
- Public IP
- Network Security Group
- Virtual Network
- Subnet

## What I Learned

- A VNet provides a private network within Azure.
- A NIC connects the VM to the VNet.
- The private IP allows communication within the Azure network.
- The Domain Controller should have a stable private IP.

## Status

- [x] Windows Server VM deployed
- [x] Network configured
- [x] Private IP configured as Static


## Azure Resource Topology

![Azure Resource Topology](./Screenshot%202026-09-12%20at%2018.05.43.png)
