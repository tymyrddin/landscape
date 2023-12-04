# Detecting honeypots

Honeypot detection lies in an attacker's ability to detect, and find out the deceptive nature (IoCs) of the honeypot. 

Often this relies on the limited ability of a honeypot to align with an attacker's mental model. This mental model is based on the attacker's expectation of what a realistic environment should look like. And that is based on experience. 

***Note: If you manage to fingerprint any of the used honeypots, make sure to let the creators know.***

There are also some legal constraints that, due to the nature of defenders having to abide by the law, enter in the design. For example, a honeypot bot that is part of a botnet cannot legally perform denial of service attacks to systems. Attackers can knowingly look for signs of such legal constraints. 

And in this arms race turn, [honeypot designs are improved to conceal them better](concealed.md).
