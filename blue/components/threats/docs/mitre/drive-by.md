# Drive-by compromise

[Drive by downloads](./../../passive/independent/drive-by.md) are categorised by MITRE as [Mobile Technique ID T1456](https://attack.mitre.org/techniques/T1456/)

_Adversaries may gain access to a system through a user visiting a website over the normal course of browsing. With this technique, the user's web browser is typically targeted for exploitation, but adversaries may also use compromised websites for non-exploitation behavior such as acquiring an Application Access Token._

***Note: Linux powers the Internet with 74.2% of all web servers running on it.***

* Monitor for newly constructed network connections to untrusted hosts that are used to send or receive data, and for other unusual network traffic that may indicate additional tools transferred to the system. 
* Use network intrusion detection systems (with SSL/TLS inspection), to look for known malicious scripts (recon, heap spray, and browser identification scripts have been frequently reused), common script obfuscation, and exploit code.
