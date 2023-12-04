# Catching and removing macOS daemons and launch agents

## Automagically assisted

* [EtreCheck](https://etrecheck.com/) (free for the first five reports)
* [Lingon X](https://www.peterborgapps.com/lingon/)
* [KnockKnock](https://objective-see.org/products/knockknock.html)
* [BlockBlock](https://objective-see.org/products/blockblock.html)

## Manually

Open the Activity Monitor app, and choose View -> All Processes. At the top are two main processes: `kernel_task` and 
`launchd`, with process ID (PID) 0 and 1 respectively. `launchd` is the primary parent process when the system starts. 
It is also the last process to exit when the system shuts down. Do NOT remove it.

The core responsibility of `launchd` is to launch other processes or jobs on a scheduled or on-demand basis. These 
processes come in two flavours: LaunchDaemons and LaunchAgents.

* LaunchDaemons typically run as root, and can be found in `/System/Library/LaunchDaemons` (native macOS processes) and 
`/Library/LaunchDaemons` (installed third-party apps).
* LaunchAgents start when a user logs in. They can access the user interface and display information, and can be found 
in `Library/LaunchAgents` (all user accounts), `~/Library/LaunchAgents` (user account), and 
`/System/Library/LaunchAgents` (macOS only).

Before logging in, `launchd` runs services and other components specified in `.plist` files from the LaunchDaemons 
folder. After logging in, `launchd` runs services and components defined in `.plist` files from the LaunchAgents 
folders. Those in `/System/Library` are all part of macOS and protected by System Integrity Protection.

`.plist` files follow the standard reverse domain naming system: company name, followed by an application identifier, 
and ending with the property list file extension (.plist). For example, `co.clario.Clario.plist`.

The public LaunchDaemon and LaunchAgent folders are open to both legitimate and illegitimate apps. 
You can monitor these folders with Folder Actions.

### Folder actions

1. Open the AppleScript Editor app. 
2. Click Preferences and choose General -> Show Script menu in menu bar
3. Click the Script Menu icon and choose Folder Actions -> Enable Folder Actions 
4. Select Attach Script to Folder in that same menu
5. A dialog box will pop up. Select add - new item alert
6. Click OK to open a Finder window. 
7. Select the user LaunchDaemon folder and click Choose

Repeat the procedure for every LaunchAgents folder. Then:

8. Open Finder and click Go > Go to Folder
9. Type `~/Library/LaunchAgents` and click Go
10. Right-click the LaunchAgents folder, and choose Services -> Folder Actions Setup to bind the new item alert script to each folder.
11. In the dialog box that pops up, you'll see the list of folders in the left column and script in the right column. If there are no scripts, click the plus (+) button and add new item alert.scpt.

Now macOS will show an alert popup whenever a new item is added to one of these folders, allowing you to immediately know
when illegitimate apps try to inject themselves into the system in the background.

### Remove items

Be careful. Not all third-party `.plist` files are malicious. They can be:

* Components of legitimate installed apps
* Remnants of old apps you no longer use
* Leftovers from previous macOS upgrades
* Migration Assistant leftovers
* PUPs (potentially unwanted programs), adware, and malware

DO NOT delete any components of installed apps. To remove remnants of old apps, leftovers from previous macOS upgrades, 
PUP's, adware and malware, just delete the `.plist` file and reboot.

## Related

* [Endpoint detection and response](blue-dfir:index)
* [Malware analysis](blue-malware:index)
