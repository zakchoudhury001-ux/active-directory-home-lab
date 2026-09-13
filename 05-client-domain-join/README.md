# Client Domain Join

## Objective

Join a client machine to the `zak.lab.local` Active Directory domain and verify that the domain join was successful.

## Environment

- Domain Controller: DC01
- Client Machine: CLIENT01
- Domain: zak.lab.local
- Operating System: Windows Server 2022
- Azure Virtual Network: vnet-centralus-1
- Subnet: snet-centralus-1

## What I Did

1. Created a separate client VM named `CLIENT01`.
2. Connected CLIENT01 to the same Azure virtual network and subnet as DC01.
3. Configured CLIENT01 to use DC01 (`172.16.0.4`) as its DNS server.
4. Tested network connectivity between CLIENT01 and DC01 using `ping`.
5. Tested DNS resolution for `zak.lab.local` using `nslookup`.
6. Joined CLIENT01 to the `zak.lab.local` domain.
7. Restarted CLIENT01 to apply the domain membership changes.
8. Verified after the restart that CLIENT01 was successfully joined to `zak.lab.local`.

## Network and DNS Verification

I first tested connectivity to the Domain Controller:

```cmd
ping 172.16.0.4
