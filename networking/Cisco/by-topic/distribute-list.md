# Distribute Lists

```
R3(config)# access-list 7 permit 10.10.11.0 0.0.0.255
R3(config)# access-list 7 permit 10.10.12.0 0.0.0.255
R3(config)# router ospf 10
R3(config-router)# redistribute eigrp 100
R3(config-router)# distribute-list 7 out eigrp 100
```
