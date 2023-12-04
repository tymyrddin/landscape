# No device can ever be called secure

The Linux ecosystem was considered more secure by many, which possibly explains why Google, NASA, and the US DoD use it for their online infrastructures and systems. Wishful thinking. Like the misconception that Apple devices are immune to hacking and malware infection.

Any ransomware tool development must be lucrative for the threat actor, which used to be far less likely in the case of locking a mobile device, as compared with locking all the Windows systems in an organisation. 

The bring-your-own-device (BYOD) trend has been growing for many years though. With Android the most common operating system for mobile devices, ransomwares targeting Android are on the rise. Publicly known ransomware threats to iOS seem still less prevalent, but have been seen.

## *nix

Linux is on the list of the most used operating systems, for workstations, servers, mobiles (android is linux based), and IoT devices. Linux powers the Internet with 74.2% of all web servers running on it. Hence, a profitable target. 

* RansomEXX (or Defrat777) is one of the most common recent ransomware attacks against Linux. It was used against high-end targets in 2020 and 2021. It does not use C&C communication and targets was hard-coded.
* Tycoon is one of the most common Linux ransomwares. In late 2019 it was used in attacks against education organisations and companies in the software industry. Its payload is in a ZIP archive with a malicious Java Runtime Environment (JRE) component, hidden in a Java image file. Both Linux and Windows are vulnerable to Tycoon attacks.
* Erebus was originally Windows-based, and repurposed to target Linux servers. 
* QNAPCrypt focuses on infecting network-attached storage (NAS) Linux devices. 
* KillDisk also started on Windows and was later adapted for Linux environments.

## macOS

* LockBit operators created encryptors to target Mac devices for the first time. Supposedly the first-ever ransomware campaign focusing on macOS in particular.
* ThiefQuest (also known as EvilQuest) became a threat in June 2020, having been discovered by researcher Dinesh Devadoss. The program was found hiding in pirated versions of the Little Snitch app, which could be found on a Russian torrent platform.
* Inventive attackers have [used the "Geacon" Cobalt Strike tool attack](c2.md) for data theft, privilege elevation, and remote device control.
* MacStealer malware stole sensitive data from Apple users. Documents, iCloud keychain data, browser cookies, credit card credentials, etc.
* CloudMensis spreads through email attachments and can steal sensitive information and grant unauthorised access to users' systems. 
* JockerSpy can [infiltrate a system through fake websites](../mitre/drive-by.md) or bundled with [seemingly harmless software](../mitre/supply-chain.md). Once installed, it can monitor users' activities, capture keystrokes, and access personal data.

MacOS is turning into a goldmine, using malware persisting through other means without touching the filesystem. Living of the land (LOL). A user's password, for example, serves as decryption keys for its keychains. And the keychains can include credit card numbers and bank account PIN codes. A malware tricking users to reveal their password can even be used to  bypass MFA. 

## Apparently porting is well underway too

Some malware can infect Linux ***and*** Windows systems. StripedFly for example, is capable of a lot more than just mining cryptocurrency: it can execute commands remotely, grab screenshots and execute shellcodes, steal passwords and other sensitive data, record sounds using the integrated microphone, move to near endpoints using previously stolen credentials, abuse the EternalBlue exploit to worm into other systems, and mine Monero. Monero mining is now seen as a distraction, to prevent researchers from analysing the code further. This malware has infected over 1 million Windows and Linux computers around the globe since 2016, [according to Kaspersky](https://securelist.com/stripedfly-perennially-flying-under-the-radar/110903/).

## Resources

* [URLhaus Database](https://urlhaus.abuse.ch/browse/)
* [Linux virus](https://help.ubuntu.com/community/Linuxvirus)
* [Windows global threat activity](https://www.microsoft.com/en-us/wdsi/threats)
