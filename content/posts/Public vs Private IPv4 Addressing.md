---
title: "Public vs Private IPv4 Addressing"
date: "2025-08-17 00:54:03"
tags: ['networking', 'ipv4', 'nat']
draft: false
---

# Understanding Public and Private IP Addresses
---
## Private IP Addresses
A private IP address it used for communication within the same local network and is not routable over the public Internet. These IPs are typically assigned by a DHCP server within the local network, and--like any IP address--must be unique within the network to allow proper communication  between devices
To allow devices with private IP addresses to access the Internet, the router that connects the network to the Internet must perform Network Address Translation (NAT).
The IPv4 address ranges reserved for private networks are defined by RFC 1918. In most environments, one of these private subnets is selected and assigned to all internal devices. In IPv4 networks, it is strongly recommended to use an RFC 1918 private subnet together with NAT to enable Internet access from internal hosts.
### RFC 1918 PRIVATE IP ADDRESS SPACE
| CIDR Range     | IP Address Range              |
| -------------- | ----------------------------- |
| 10.0.0.0/8     | 10.0.0.0 - 10.255.255.255     |
| 172.16.0.0/12  | 172.16.0.0 - 172.31.255.255   |
| 192.168.0.0/16 | 192.168.0.0 - 192.168.255.255 |
---
## Public IP Addresses
A public IP address is routable over the Internet and can communicate with other external networks. In most cases, these addresses are assigned by an Internet Service Providers (ISPs). However, when a network requires hundreds or thousands of IPs, they can be allocated directly by a Regional Internet Registry (RIR) -- the organization responsible for IP address allocation and registration within a specific region.
Most home and small business networks are assigned a single public IPv4 address. Larger enterprise networks may have multiple public IPs, depending on their needs. However, in most scenarios, one public IP is enough, since NAT allow hundreds of internal devices to share a single public address for Internet access.
---
## Reserved and Documentation Addresses
In addition to the private ranges defined by RFC 1918, RFC 6890 defines other reserved blocks used for special purposes, such as documentation, testing, and benchmarking. It also includes the address space defined by RFC 6598, which is used for Carrier-Grade NAT (CGNAT) -- a technique used by ISPs to allow multiple NATed customer networks to share a single public IP.
### RFC 6890 IPv4 Reserved Address Space
| CIDR RANGE      | PURPOSE                         |
| --------------- | ------------------------------- |
| 192.0.2.0/24    | Documentation and example code  |
| 192.51.100.0/24 | Documentation and example code  |
| 203.0.113.0/24  | Documentation and example code  |
| 198.18.0.0/15   | Benchmarking network devices    |
| 169.254.0.0/16  | Link local (APIPA)              |
| 100.64.0.0/10   | Carrier-grade NAT space (CGNAT) |
| 192.0.0.0/24    | IETF Protocol Assignments       |
| 192.168.0.0/29  | DS-Lite                         |
| 192.88.99.0/24  | 6to4 Relay Anycast              |
| 240.0.0.0/4     | Reserved                        |
