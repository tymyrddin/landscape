# macOS malware detection and removal

### Check activity monitor

1. Open Activity Monitor from Applications -> Utilities
2. Go to the CPU tab
3. Click the % CPU column to sort high to low, and look for high CPU use
4. If you see a process that looks suspicious, do a DuckDuckGo search on it

### Check for unwanted applications

1. Go to the Applications folder
2. Look for any apps you do not recognize or do not remember installing
3. Check with DuckDuckGo whether they are legitimate or not
4. If they are not, or if you are suspicious, delete them and empty your Trash

Note that this does not help much with [trojans](../independent/analysing-trojans.md), evil files made to look like legitimate apps.  

### Look at login items

1. In System Preferences, select Users & Groups
2. Go to the Login Items tab
3. Look through the list, and select anything suspicious
4. Click the minus button to remove it

Note that [LaunchDaemons and LaunchAgents](daemons-and-agents.md) will not appear in this list.

## Fail

* If all else fails, go to a previous [point in time](time-machine.md) or backup.
* If that fails too, the `NVRAM` or Time Machine or backups may even be infected. It is possible for malware to persist across a re-format and re-install, if it is sufficiently ingenious and sophisticated: if for example, it can persist in NVRAM, in the firmware for peripherals (some hardware devices have firmware that can be updated, and thus could be updated with malicious firmware), or with a virus infecting data files on removable storage or on your backups. 

