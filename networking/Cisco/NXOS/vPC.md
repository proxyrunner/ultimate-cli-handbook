# Configuring vPC on N7k

## Disable fabricpath

Disable the fabricpath feature, which removes fabricpath configuration form interfaces and VLANs.

```
N7K-A-Pod8# configure terminal
N7K-A-Pod8(config)# no feature-set fabricpath
Feature-set Operation may take up to 95 minutes depending on the size of configuration.
N7K-A-Pod8(config)# no vlan 50
N7K-A-Pod8(config)# interface ethernet 4/25-31
N7K-A-Pod8(config-if-range)# switchport mode trunk
```

```
N7K-B-Pod8# configure terminal
N7K-B-Pod8(config)# no feature-set fabricpath
Feature-set Operation may take up to 95 minutes depending on the size of configuration.
N7K-B-Pod8(config)# no vlan 50
N7K-B-Pod8(config)# interface ethernet 4/25-31
N7K-B-Pod8(config-if-range)# switchport mode trunk
```

```
N5K-A-8# configure terminal
N5K-A-8(config)# no feature-set fabricpath
Feature-set Operation may take up to 95 minutes depending on the size of configuration.
N5K-A-8(config)# no vlan 50
N5K-A-8(config)# interface ethernet 1/1-4
N5K-A-8(config-if-range)# switchport mode trunk
```

```
N5K-A-8# configure terminal
N5K-A-8(config)# no feature-set fabricpath
Feature-set Operation may take up to 95 minutes depending on the size of configuration.
N5K-A-8(config)# no vlan 50
N5K-A-8(config)# interface ethernet 1/1-4
N5K-A-8(config-if-range)# switchport mode trunk
```
