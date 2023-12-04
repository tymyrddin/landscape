# Enabling controlled folder access (CFA)

Controlled folder access is supported on Windows Server 2019, Windows Server 2022, Windows 10, and Windows 11 clients.

This feature has been tested against various ransomware samples. Controlled Folder Access achieved what it was designed to do; successfully block ransomware from encrypting files located in protected folders.

* Type "Windows Defender Security Center" in search box and Enter.
* Select Virus & threat protection -> Virus & threat protection settings option from the main window.
* Locate the Controlled folder access section. 
* To enable the feature, click the On/Off toggle.
* Select the Protected folders sub-option underneath and add all the folders you want to restrict access to.
* The other sub-option underneath, Allow an app through Controlled folder access, will whitelist the apps that are allowed to access, edit, create or remove files from protected folders.
