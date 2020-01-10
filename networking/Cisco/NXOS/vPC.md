# Configuring vPC on N7k

## Disable fabricpath

Disable the fabricpath feature, which removes fabricpath configuration form interfaces and VLANs.

```
N7K-A-Pod8# configure terminal
N7K-A-Pod8(config)# no feature-set fabricpath
# Feature-set Operation may take up to 95 minutes depending on the size of configuration.
N7K-A-Pod8(config)# no vlan 50
N7K-A-Pod8(config)# interface ethernet 4/25-31
N7K-A-Pod8(config-if-range)# switchport mode trunk
```

```
N7K-B-Pod8# configure terminal
N7K-B-Pod8(config)# no feature-set fabricpath
# Feature-set Operation may take up to 95 minutes depending on the size of configuration.
N7K-B-Pod8(config)# no vlan 50
N7K-B-Pod8(config)# interface ethernet 4/25-31
N7K-B-Pod8(config-if-range)# switchport mode trunk
```

```
N5K-A-8# configure terminal
N5K-A-8(config)# no feature-set fabricpath
# Feature-set Operation may take up to 95 minutes depending on the size of configuration.
N5K-A-8(config)# no vlan 50
N5K-A-8(config)# interface ethernet 1/1-4
N5K-A-8(config-if-range)# switchport mode trunk
```

```
N5K-A-8# configure terminal
N5K-A-8(config)# no feature-set fabricpath
# Feature-set Operation may take up to 95 minutes depending on the size of configuration.
N5K-A-8(config)# no vlan 50
N5K-A-8(config)# interface ethernet 1/1-4
N5K-A-8(config-if-range)# switchport mode trunk
```

### Validate via Description, CDP, and Interfaces

Review the interface connectivity by examining the descriptions that are assigned to the interfaces. Compare the output to your topology diagram for all interfaces that are in use.

```
N7K-A-Pod8# show interface description

-------------------------------------------------------------------------------
Interface                Description
-------------------------------------------------------------------------------
mgmt0                    --

-------------------------------------------------------------------------------
Port          Type   Speed   Description
-------------------------------------------------------------------------------
Eth4/25       eth    10G     Connects to N7K-B-Pod8 4/25 - vPC peer-link
Eth4/26       eth    10G     Connects to N7K-B-Pod8 4/26 - vPC peer-keepalive
Eth4/27       eth    10G     Connects to 9396-A E1/8
Eth4/28       eth    10G     Connects to 6248-A E1/8
Eth4/29       eth    10G     Connects to 5672-A-8 E1/1
Eth4/30       eth    10G     Connects to 5672-B-8 E1/1
Eth4/31       eth    10G     Connects to N7K-B-Pod8 E4/31
Eth4/32       eth    10G     --
```

### Show CDP Neighbor

#### Note that FEXs do not appear in CDP Neighbor

```
N7K-A-Pod8# show cdp neighbors
Capability Codes: R - Router, T - Trans-Bridge, B - Source-Route-Bridge
                  S - switch, H - Host, I - IGMP, r - Repeater,
                  V - VoIP-Phone, D - Remotely-Managed-Device,
                  s - Supports-STP-Dispute

Device-ID           Local Intrfce  Hldtme Capability  Platform      Port ID
MGMT-SW              mgmt0          169    R S I       WS-C2960XR-48  Gig1/0/1
N7K-B-Pod8(JAF1752AKGC)
                    Eth4/25        130    R S I s     N7K-C7009     Eth4/25
N7K-B-Pod8(JAF1752AKGC)
                    Eth4/26        132    R S I s     N7K-C7009     Eth4/26
UCS-A(SSI184706W7)
                    Eth4/28        142    S I s       UCS-FI-6248UP Eth1/8
N5K-A-8(FOC1912R11S)
                    Eth4/29        164    R S I s     N5K-C5672UP   Eth1/1
N5K-B-8(FOC1912R0ZD)
                    Eth4/30        147    R S I s     N5K-C5672UP   Eth1/1
N7K-B-Pod8(JAF1752AKGC)
                    Eth4/31        132    R S I s     N7K-C7009     Eth4/31

Total entries displayed: 7
```
### Show interface brief

```
N7K-A-Pod8# show interface brief | include up
Eth4/25       1       eth  trunk    up      none                        10G(D) --
Eth4/26       1       eth  trunk    up      none                        10G(D) --
Eth4/27       1       eth  trunk    up      none                        10G(D) --
Eth4/28       1       eth  trunk    up      none                        10G(D) --
Eth4/29       1       eth  trunk    up      none                        10G(D) --
Eth4/30       1       eth  trunk    up      none                        10G(D) --
Eth4/31       1       eth  trunk    up      none                        10G(D) --
<... output omitted ...>
```
