# Infostealer-as-a-Service (IaaS)

Infostealer attacks are typically financially motivated. Infostealers are a type of MaaS that extracts data from infected devices. An adversary buys an InfoStealer from a [marketplace](marketplace.md), spreads the malware onto as many machines as possible, collects and organises the information, and then sells the information on the black market (dark web or Telegram).

## How infostealers are distributed

* The InfoStealer is embedded into a document (for example, in a Microsoft Word document or a Microsoft Excel spreadsheet). Then the doc is sent out as an attachment in cleverly worded [phishing](../mitre/phishing.md), enticing people to open the file. 
* Via a convincing site with a lookalike domain, the logo of a trusted brand, and a design that tricks unsuspecting users into voluntarily downloading the InfoStealer, thinking that it is a legitimate app. 
* By [squatting an app](../mitre/supply-chain.md), and then making that corrupted application available for download from app stores. 

Then putting a social engineering cherry on top: Paying for advertising on Google Ads and Facebook Ads to trick more people into downloading the malware from a fake site or App store. Using paid ads to distribute malware works wonders because it leverages the trust that people have in both the advertising platform and the brand that they are impersonating on a fake site or the app in the store. If a user sees an ad after making a query in a search engine, they implicitly assume that it is safe to click because they trust the search engine.

## What info it tries to steal

* Credentials used for online banking, email accounts, social media sites, and FTP services.
* Credit card details.
* Emails.
* Hardware information.
* Operating system information.
* Cryptocurrency wallets.
* Screenshots.
* Specific file types (commonly images, documents, spreadsheets, etc.)

The stolen data is analysed and any valuable information is collated and organised into a database, which can then be sold on the [black market](marketplace.md).

## Who is targeted

Healthcare and financial services are the most targeted sectors with infostealers.

## How to defend

The increased sophistication and complexity is making it more difficult for defenders to detect and prevent infostealers.

## Resources

* [Your Guide to Top Infostealers in 2022](https://blog.morphisec.com/infostealer-comparison)


