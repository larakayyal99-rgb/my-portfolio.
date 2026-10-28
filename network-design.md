# Network design

The original network placed most devices in one subnet. My proposal separates them by function and uses OPNsense to control traffic between segments.

## Address plan

| Segment | Subnet | Gateway | Addressing |
| --- | --- | --- | --- |
| USERS | 10.20.10.0/23 | 10.20.10.1 | DHCP |
| SERVERS | 10.20.20.0/27 | 10.20.20.1 | Static or DHCP reservation |
| MANAGEMENT | 10.20.30.0/27 | 10.20.30.1 | Static or DHCP reservation |
| GUEST | 10.20.40.0/24 | 10.20.40.1 | DHCP |
| PRODUCTION | 10.20.50.0/26 | 10.20.50.1 | Static or DHCP reservation |
| IOT | 10.20.60.0/26 | 10.20.60.1 | Static or DHCP reservation |
| PRINTERS | 10.20.70.0/27 | 10.20.70.1 | Static or DHCP reservation |

I chose a /23 for USERS to leave room for growth. It provides 510 usable addresses, including the gateway. Smaller segments use smaller subnets.

Internal clients would use DC01 at 10.20.20.10 for DNS. The proposed USERS DHCP pool is 10.20.10.50–10.20.11.240. Guest DNS would be separate from internal name resolution.

## Access rules

| Source | Destination | Intended access |
| --- | --- | --- |
| USERS | WEB01 | HTTPS on TCP 443 |
| USERS | DC01 and FILE01 | Required directory, DNS, and file services |
| USERS | PRINTERS | Required printing services |
| USERS | MANAGEMENT | Block |
| GUEST | Internal networks | Block |
| GUEST | Internet | Allow approved web access |
| Authorized admin endpoints | Management targets | Allow required administration services |
| PRODUCTION and IOT | Internal resources | Allow only documented dependencies |

These are design rules, not an exported firewall configuration. Exact ports, rule order, VLAN IDs, DHCP relay, and IPv6 behavior still need to be defined and tested. DHCP reservations also require the appropriate DHCP configuration.

[Back to overview](README.md)
