# Phishing for information

[Phishing](./../../passive/independent/phishing.md), [Smishing](./../../passive/mobile/smishing.md), and [Vishing](./../../passive/mobile/vishing.md) are classified as [Technique ID 1598 (T1598)](https://attack.mitre.org/techniques/T1598/), and it contains three sub-techniques: Spearphishing Service, Spearphishing Attachment and Spearphishing Link.

* Monitor for suspicious email activity, such as numerous accounts receiving messages from a single unusual/unknown sender. Filtering based on DKIM+SPF or header analysis can help detect when the email sender is spoofed. 
* For followed links, check for references to uncategorized or known-bad sites. URL inspection within email and messages (including expanding shortened links) can also help detect links leading to known malicious sites.
* Monitor social media traffic for suspicious activity, including messages requesting information as well as abnormal file or data transfers (especially those involving unknown, or otherwise suspicious accounts).
* Monitor and analyse traffic patterns and packet inspection associated to protocol(s) that do not follow the expected protocol standards and traffic flows (like extraneous packets that do not belong to established flows, gratuitous or anomalous traffic patterns, anomalous syntax, or structure). 
* Consider correlation with process monitoring and command line to detect anomalous processes execution and command line arguments associated to traffic patterns (monitor anomalies in use of files that do not normally initiate connections for respective protocol(s)).
* Monitor network data for uncommon data flows. Processes using the network that do not normally have network communication or have never been seen before are suspicious.

The [NIST phishing incident response playbook](https://www.incidentresponse.org/workflows/download/Phishing.pdf) contains the 7 steps of the NIST incident response process for investigating phishing.

## Network detection resources

* [Wireshark: SMTP](https://www.wireshark.org/docs/dfref/s/smtp.html)
* [SMTP codes](https://www.mailersend.com/blog/smtp-codes)
* [Wireshark: IMF](https://www.wireshark.org/docs/dfref/i/imf.html)
