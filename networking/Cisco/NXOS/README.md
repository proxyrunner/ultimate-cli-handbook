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