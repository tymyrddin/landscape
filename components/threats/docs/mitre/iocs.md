# Signs of a compromise @home

These patterns are based on business contexts, and most are not useful for home use, unless you run servers locally. The network patterns boldfaced *are* useful in a home context.

* ***If outbound traffic patterns are suspiciously unusual, you can keep a closer eye on it to check if something nefarious is happening.***
* Anomalies in the behaviour (activity) of privileged user accounts.
* Login attempts from countries with which you have no exchanges otherwise.
* An existing user tries to log in many times.
* Failed logins for user accounts that do not exist.
* A wave in Database Read Volume (exfiltration).
* A sudden increase in Hypertext Markup Language (HTML) response size (exfiltration).
* The same file is requested many times (in different ways).
* ***Unusual ports are being used.***
* Changes to the Windows registry or system files (persistence).
* ***Anomalous Domain Name System (DNS) requests from a specific host.***

Note that Indicators of compromise (IOCs) refer to data that indicates a system may have been infiltrated by a cyber threat. 

Indicators of attack (IOAs) are different from IOCs in that they focus on identifying the activity associated with the attack while the attack is happening, whereas IOCs focus on examining what happened after an attack has occurred.

And for our purposes @home and @org, the distinction is a moot point, and we just use what we can.

