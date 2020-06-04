# Administrative Commands

## Privilege and User Modes

## Turn on SCP

> ip scp server enable

### Bypass user-exec mode to privilege mode

```
conf t
# Select the access type
# line con 0
# line vty 0 15
privilege level 15 
```


## Timed Reload

```
reload in 10                         
```

## 

```
Reload scheduled in 10 minutes by console
Reload reason: Reload Command
Proceed with reload? [confirm]
```

## 

```
R2#show reload  
*Jan  2 18:03:43.727: %SYS-5-SCHEDULED_RELOAD: Reload requested for 18:13:42 UTC Thu Jan 2 2020 at 18:03:42 UTC Thu Jan 2 2020 by console. Reload Reason: Reload Command.
R2#show reload
Reload scheduled in 9 minutes by console
Reload reason: Reload Command
```

## 

```
R2#reload cancel

***
*** --- SHUTDOWN ABORTED ---
***
*Jan  2 18:03:50.671: %SYS-5-SCHEDULED_RELOAD_CANCELLED:  Scheduled reload cancelled at 18:03:50 UTC Thu Jan 2 2020 
```
