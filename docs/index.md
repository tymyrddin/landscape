# Digital defence @home

This project is about understanding the landscape and securing @home (and @smallorganisational) contexts as good as we can ourselves.
The approach is to pick the raisins out of the commercial porridge. What makes sense in our respective contexts?

The threat landscape is changing fast, as many government services and commercial sectors push their apps. Increasingly people are obliged to use digital devices for education, work, and play. 
These apps are not always secure, and with devices shared among family members, the chance for exposure to malware increases even further. 

Meanwhile, the digital divide becomes more visible than ever before. Many people have limited access to technology or lack the ability (skills, resources) to use technology securely.

## In a nutshell

* We can watch the [threat landscape](./threats/backdrop/README.md) change, and discover previously ignored and newly found potential digital threats.
* We can [map our defensive capabilities](./threats/mitre/README.md) against the Mitre Att&Ck framework and overlay this map with the potential threats to our @home devices and networks for discovering where and how best to invest our time and energy.
* We can prevent, detect and respond to attacks [using known tactics](./passive/README.md).
* For home and small organisational networks, we can buy Raspberry Pi's (not extremely expensive), install the [PiRogue suite](https://testlab.tymyrddin.dev/docs/mobile/pts) on it, and then [catch indicators of attack and compromise (IoAs and IoCs)](./threats/mitre/iocs.md). 
* We can do some [mobile app vetting and malware analysis](./hands-on/thm/README.md) ourselves, and share results back with the growing community of digital defenders. 
* If we run a server for a community, we can [harden it](https://server.tymyrddin.dev/). We can harden our [webservers](https://webserver.tymyrddin.dev/) too. And a mailserver can be [made smarter](https://mailserver.tymyrddin.dev/).
* With enough passive defence covered, we can perhaps add some [active defence](./active/design/README.md) and set up a [honeyclient](./active/small/honeyclients.md) and/or [honeyports](./active/small/honeyports.md) on our local networks. 
* ...
* In security minded communities, we can design and organise security operations training. Not for "users", not for "employees", not for "activists", for ***people!*** Making it fun, with hilarious simulations/roleplay and [hands-on exercises](./hands-on/README.md).
