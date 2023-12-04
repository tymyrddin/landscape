# MFA bypass attacks

Attackers use various methods to MFA bypass attacks, including social engineering, phishing, and exploiting vulnerabilities in the authentication process.

## MFA fatigue

After having obtained stolen username and password credentials from a black market, attackers can attempt repeated logins to the targeted user accounts, who then are bombarded with login verification requests. Through sheer frustration or by accident, users eventually click on the link or confirmation request. That action then gives the threat actor a way in.

## MitM

"In the olden days", adversaries only needed to get username and password combinations, so they made a fake authentication webpage and attempt to trick users into entering their credentials. With MFA everywhere, adversaries need username and password combination and the digital token or one-time password used as the second form of authentication.

A new tactic is to use MitM instead, and insert themselves between the user and the legitimate login page. Users will receive a request to access their MFA provider, through [phishing](../mitre/phishing.md) (including [smishing](../mobile/smishing.md), [vishing](../mobile/vishing.md) or [OTP bots](../mobile/otp-bots.md), that entices users to click on a link, which then directs them through a malicious proxy server to the legitimate login page. The adversaries capture the credentials on the proxy server and then modify the session cookie to gain access. And variations on that scenario.

## Token stealing

Making life easier for users, "session cookies" are stored on endpoint devices, so users don’t have to re-authenticate during sessions. These can be stolen and placed within the session of the adversary, making the browser believe the actual trusted user is being authenticated.

## Future

MFA was invented to protect authentication. Do we need another layer to protect MFA? 

There are discussions about mechanisms going beyond something one knows (password) and/or something one possesses (phone, fob) and/or even what one is (fingerprint, retinal print). Maybe we'll be using who one is, in the form of episodic memory because who are we but the stories we tell (ourselves), or in the form of our thoughts, because "I think therefor I am" ... ? Do we really want who we are externalised on the web, our memories, our imagination, up for grabs?
