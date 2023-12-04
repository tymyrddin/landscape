# Taxonomies of honeypots

A wide variety of honeypots exist, and some classification can be helpful.

## Purpose

According to purpose, honeypots can be divided into two main categories:

* A research honeypot is used to collect, monitor and analyse the activities of an attacker and the tools used to hack into the honeypot. It is used to discover an unknown vulnerability and attack.
* A production honeypot is focused on defence, and mainly implemented behind a firewall and usually concealed within the production network. Its purpose is to keep an attacker away from the actual system by creating an illusion of an actual system with vulnerabilities, and when attacked, alerts the system administrator of the intrusion.

## Interactivity

The level of interactivity provided to adversaries is also a useful distinction, with most honeypots falling into one of the below categories:

* Low-Interaction honeypots offer little interactivity to the adversary and are only capable of simulating the functions that are required to simulate a service and capture attacks against it. Adversaries are not able to perform any post-exploitation activity against these honeypots as they are unable to fully exploit the simulated service. Examples of low-interaction honeypots include mailoney and dionaea.
* Medium-Interaction honeypots collect data by emulating vulnerable services and the underlying OS, shell, and file systems. This allows adversaries to complete initial exploits and carry out post-exploitation activity. The system presented to adversaries is a simulation, and as a result, it is usually not possible for adversaries to complete their full range of post-exploitation activity as the simulation will be unable to function completely or accurately. Cowrie can function as a medium-interaction SSH honeypot.
* High-Interaction honeypots are fully complete systems, usually Virtual Machines, that include deliberate vulnerabilities. Adversaries should be able (but not necessarily allowed) to perform any action against the honeypot as it is a complete system. It is important that high-interaction honeypots are carefully managed, otherwise, there is a risk that an adversary could use the honeypot as a foothold to attack other resources. Cowrie can also operate as an SSH proxy and management system for high-interaction honeypots.

## Deployment location

Once deployed, honeypots can also be categorised by the exact location of deployment:

* Internal honeypots are deployed inside a LAN. This type can act as a way to monitor a network for threats originating from the inside, for example, attacks originating from trusted personnel or attacks that by-parse firewalls like phishing attacks. Ideally, these honeypots should never be compromised as this would indicate a significant breach.
* External honeypots are deployed on the open internet and are used to monitor attacks from outside the LAN. These honeypots are able to collect much more data on attacks since they are effectively guaranteed to be under attack at all times.

## Cyber kill chain

A ***must read***: [Three Decades of Deception Techniques in Active Cyber Defense - Retrospect and Outlook](https://arxiv.org/pdf/2104.03594.pdf) uses a tailored cyber kill chain model which can reflect the current threat landscape and a four-layer deception stack, a two-dimensional taxonomy is developed, based on which deception techniques are classified.
