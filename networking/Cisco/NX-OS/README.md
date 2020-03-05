# NX-OS Command Handbook

Square brackets indicate a parameter that must be updated.

## Disable Fabric Path

```
configure terminal
no feature-set fabricpath
# Feature-set Operation may take up to 95 minutes depending on the size of configuration.
no vlan [50]
interface [ethernet 4/25-31]
switchport mode trunk
```

## Configure vPC Peer-Keepalive

```
configure terminal
vrf context [VPC-KEEPALIVE]
interface [ethernet 4/26]
no switchport
vrf member [VPC-KEEPALIVE]
# Warning: Deleted all L3 config on interface Ethernet4/26
ip addr [209.165.200.225/24]
```
