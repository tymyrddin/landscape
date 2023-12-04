# Digital defence @home

Many government services and commercial sectors push apps on-line though, and increasingly people are obliged to use devices for education, work, and play. Often these apps are not very secure, while devices may be shared among family members, increasing the chance for exposure to malware. 

In this changing threat landscape, the digital divide becomes more visible than ever before. Many people have limited access to technology or lack the ability (skills, resources) to use technology securely. And the weakest spots are the most likely point of entry.

These write-ups are about understanding the landscape for securing the entire stack in our respective home and organisational contexts as good as we can ourselves, down to storage components and add-on peripherals, operating systems, virtualisation layers, system libraries and external APIs, etc. 

## Why?

History show us that holding the industry and governmental echelons accountable, works way too slow, if at all. [Why are we not building a defendable Internet?](https://www.youtube.com/watch?v=PLJJY5UFtqY).

## How?

* We can watch the [threat landscape](./threats/backdrop/README.md) change and discover old and new potential digital threats.
* We can [map our defensive capabilities](./threats/mitre/README.md) against the Mitre Att&Ck framework and overlay this map with the potential threats to our devices and (home) networks for discovering where and how best to invest our time and energy.
* We can prevent, detect and respond to attacks [using known tactics](./passive/README.md).
* For home and small organisational networks, we can buy Raspberry Pis (not expensive), install the [PiRogue suite](https://testlab.tymyrddin.dev/docs/mobile/pts) on it, and then [catch indicators of attack and compromise (IoAs and IoCs)](./threats/mitre/iocs.md). 
* We can do some [mobile app vetting and malware analysis](./hands-on/thm/README.md) ourselves, and share results back on Pithus. 
* If we run a server for our community, we can [harden it](https://server.tymyrddin.dev/). And we can harden our [webservers](https://webserver.tymyrddin.dev/) too. And a mailserver can be [made smarter](https://mailserver.tymyrddin.dev/).
* With enough passive defence covered, we can perhaps add some [active defence](./active/design/README.md) and set up a [honeyclient](./active/small/honeyclients.md) and/or [honeyports](./active/small/honeyports.md). 
* ...
* In security minded communities, we can design and organise security operations training. Not for "users", not for "employees", not for "activists", for ***people!*** Make it fun, with posters, simulations and [hands-on exercises](./hands-on/README.md).
