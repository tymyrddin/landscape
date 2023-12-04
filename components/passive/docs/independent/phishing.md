# Detection, analysis and prevention of phishing

Phishing attempts to trick people into clicking on fraudulent links in emails. The link typically takes the person to a seemingly legitimate site with a malware download.

## Detection

* Hover the cursor over the `From` address to confirm the email address and then cross-check the website the official email address and domain used.
* Take note of the spelling of the sender address and email subject line, which may contain small details.
* Look for inconsistencies in grammar and small spelling mistakes in content.
* Check links before you leap. Hover the cursor over the link, and the destination address displays in a tiny bar down the bottom of a browser. On mobile phones, hold down on the link, and a pop-up window with the link will appear.
* An urgent warning tries to frighten people into reacting without considering the consequences.
* "Clickbait" titles on social media, advertising or publications are attention-grabbing.
* Generic greetings are not the common practices of legitimate companies.
* Poor quality logos that are unclear or smaller than usual.

Mind that with AI-driven content tools broadly available at a low or no cost, adversaries are using such tools to make their phishing emails and text messages appear more realistic than ever before. Trust your gut, and if suspicious, do some analysis.

## Analysis

* Copy and paste the entire email header and run an [email header analysis tool](https://testlab.tymyrddin.dev/docs/phishing/header). It is good to use multiple resources as each tool might reveal information that another tool may not.
* [Extract urls from the text](https://testlab.tymyrddin.dev/docs/phishing/url) for further analysis.
* [Check sender's IP address and urls found in the text](https://testlab.tymyrddin.dev/docs/phishing/ip).
* If the email has an attachment: Obtain the attachment safely. If you don't know how, ask someone who does. Get its hash and [check the file's reputation](https://testlab.tymyrddin.dev/docs/phishing/rep) with the hash to see if it's a known malicious document.
* Upload it to a [sandbox](https://testlab.tymyrddin.dev/docs/phishing/sandbox) for dynamic analysis.

## Prevention

* Never open an attachment unless certain that the communication is from a genuine source.
* Monitor personal and private accounts and look at the settings. Multifactor verification is a feature that secures email and work accounts.
* Set up at least two email addresses: a private address and a public address.
   * The private address should not be your first and last name, and be protected by never being used on publicly accessible online resources. Or masked. Proton vault and other services allow for this. Or use a graphics file. If it is discovered, change it.
   * The public address as a temporary address and needs to be changed frequently. Consider using a number of public addresses. That way you can perhaps trace which services may be selling addresses to spammers or have been compromised and its data sold on the black market.
* Only open email accounts with providers that include spam filtering.
* Do not respond to any spam, ever.
* Think before you click 'unsubscribe'.
* Web browsers include settings to restrict access to dangerous websites, and when one attempts to access a bad site, an alert message appears. Do not ignore these warnings and do not visit that website or access that file.
* Keep your browser updated, and install the NoScript extension.

## Other mitigations

* [Email security (SPF, DKIM, DMARC)](https://mailserver.tymyrddin.dev/)
* SPAM filters (flags or blocks incoming emails based on reputation)
* Email labels (alert users that an incoming email is from an outside source)
* Email address/domain/URL Blocking (based on reputation or explicit denylist, preferably whitelisting)
* Attachment blocking (based on the extension of the attachment)
* Attachment sandboxing (detonating email attachments in a sandbox environment to detect malicious activity)
* Security awareness training (internal phishing campaigns)

## Related labs (examples)

* [Basic phishing labs](./../../hands-on/thm/cases.md)
* [The Greenholt phish](./../../hands-on/thm/greenholt.md)
