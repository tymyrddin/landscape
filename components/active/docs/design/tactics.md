# Tactics

## Decoys

Decoys can be used to distract attackers from real targets. Honeypots or honeynets are sets of devices designed to attract attackers,  but record the actions of adversaries and alert administrators of potential breaches. Honeypots can be used for researching PTTs (procedures, tools and techniques) of adversaries and assist with generating effective defensive measures.

There are lots of [honeypots](roadmaps.md), but your selection will depend on your environment and [what you want to get out of it](taxonomies.md).

## At home

A honeyclient is a tool designed to mimic the behaviour of a user-driven network client application, such as a web browser, and be exploited by an attacker's content. [Thug](https://testlab.tymyrddin.dev/docs/active/thug) seems something to have fun with at home.

## Attribution

Getting attribution is particularly useful in combination with documents that are a beacon when opened, such as when integrated with a tool like [Molehunt](https://testlab.tymyrddin.dev/docs/active/molehunt).

The [Browser Exploitation Framework (BeEF)](https://testlab.tymyrddin.dev/docs/se/beef) is a tool often used by adversaries and in pentesting, and can also be used in defence by gathering information from the remote party from within his or her web browser.

Another tool that can assist with attribution is honeypot systems that have built-in attribution capability features, like [HoneyBadger](https://testlab.tymyrddin.dev/docs/active/honeybadger), which has geolocation features to determine where an attacker is located.

## Traps

Another possible tactic is trapping adversary activity by generating a maze of fake web content using tools like Spidertrap, Weblabyrinth, and/or by creating a haystack of honeypot hosts using [Nova](https://testlab.tymyrddin.dev/docs/active/honeybadger) is also a good tactic. An adversary can get lost within these, even when using crawlers, spending hours or days to sort out what is real and what is not.



