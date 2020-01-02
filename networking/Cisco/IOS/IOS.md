# IOS Commands

## Time Reload

```
R2#reload in 10                         
Reload scheduled in 10 minutes by console
Reload reason: Reload Command
Proceed with reload? [confirm]
R2#show reload  
*Jan  2 18:03:43.727: %SYS-5-SCHEDULED_RELOAD: Reload requested for 18:13:42 UTC Thu Jan 2 2020 at 18:03:42 UTC Thu Jan 2 2020 by console. Reload Reason: Reload Command.
R2#show reload
Reload scheduled in 9 minutes by console
Reload reason: Reload Command
R2#reload cancel
R2#


***
*** --- SHUTDOWN ABORTED ---
***

R2#
*Jan  2 18:03:50.671: %SYS-5-SCHEDULED_RELOAD_CANCELLED:  Scheduled reload cancelled at 18:03:50 UTC Thu Jan 2 2020 
R2#
```
