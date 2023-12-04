# Windows malware detection and removal

Disconnect from the internet.

### Switch to Safe Mode

1. Go to ***Updates & Security -> Recovery***
2. Choose ***Restart now*** in the Advanced startup section
3. When your machine restarts, a blue screen with a few options will appear 
4. ***Troubleshoot -> Advanced options -> Startup settings -> Restart***
5. Another blue window appears, find the ***Enable Safe Mode*** option. Click number 4 on your keyboard.

### Check for and remove unwanted applications

1. Go to ***Control Panel -> Uninstall*** a program
2. [Possibly unwanted apllications](windows-unwanted.md) (bloatware, and some can even be considered malware)
3. Check with DuckDuckGo whether unknown applications are legitimate or not (mind the spelling)
4. If the issues are recent, you can click on “Installed on” to find any newly installed programs that might be suspicious
5. If they are not legitimate, or if you are suspicious, delete them and empty your Trash. 

Note that this does not help much with trojans, evil files made to look like legitimate apps.  

### Delete temporary files 

1. Open the RUN window
2. Type "%temp%" and click "OK"
3. Delete all files and folders that are in this destination
4. Empty trash

Connect back to the internet.

Note that [this does not remove malicious Registry entries](windows-registry.md) which can make the malware persistent.

## Fail

* If all else fails, go to a previous [restore point](restore-point.md) or backup.
* If that fails too, the BIOS or restore points or backups may even be infected. It is possible for malware to 
persist across a re-format and re-install, if it is sufficiently ingenious and sophisticated: if for example, it 
can persist in the BIOS, in the firmware for peripherals (some hardware devices have firmware that can be updated, 
and thus could be updated with malicious firmware), or with a virus infecting data files on removable storage or 
on your backups. 