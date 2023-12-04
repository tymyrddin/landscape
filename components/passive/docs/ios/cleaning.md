# Detecting and removing iOS malware

iOS malware is not as common as malware for other devices, but any device always has a risk of getting infected. Phones contain more sensitive information than PC's and Workstations. It usually contains pictures, credit cards, private messages, and other valuable data. 

***If you think it will turn into a "legal issue", DO NOT shut the device down or try to remove the malware, and call in a first responder instead.***

## Detecting

* If the symptoms appeared immediately after installing an app, that app may be the guilty party
* Look for unfamiliar apps: Swipe through the screen and look for the apps that you don’t remember installing. To see a list of every app you’ve installed from the App Store, tap the Apps icon at the bottom of the store, tap your profile photo, then tap ***Purchased***. If there’s an app on your phone that is not in this list (and does not come from Apple), it is likely malware. 
* Find out whether your phone is jailbroken:
   * Check for the Cydia app on the iPhone in question.  You can use Spotlight to search for it and if it comes up, the iPhone is jailbroken.
   * Check for modifications. The whole point of jailbreaking an iPhone is to add features to it that are not available out of the box. They may not be obvious but a cursory look through the device can give clues.
* Go to ***Settings -> Battery and monitor usage***. Tap on ***Show Detailed Usage*** to view the breakdown of foreground and background usage. If you find an app that you don’t recognise, it is a candidate for removal. 
* Go to ***Settings > Mobile Network*** and scroll down to ***Mobile Data***. Is that level normal for your device?

## Removing

### Try these first

* Restarting your iPhone can, in some cases, get rid of malware. Unlikely, but can. How to do this depends on your iPhone. 
* Clear History & Website Data: 
  * Open ***Settings*** on your device and tap ***Safari***. 
  * Tap ***Clear History and Website Data***. 
  * Confirm.

### Deleting an app and its configuration profile

* Deleting an app
  * Touch and hold the app until it jiggles.
  * Then tap the delete button in the upper-left corner of the app to delete it. If you see a message that says, "Deleting this app will also delete its data," tap ***Delete***.
* If the app has a configuration profile, delete it.
  * Go to ***Settings -> General -> Profiles*** or ***Profiles & Device Management***, then tap the app’s configuration profile.
  * Then tap ***Delete Profile***. If asked, enter your device passcode, then tap ***Delete***.
* Restart

### Fail

* If this did not work, do a Reset to factory settings
  * Make an iTunes backup or iCloud backup
  * Go to ***Settings -> General -> Reset -> Erase All Contents and Settings***
  * Enter your passcode to confirm the reset
  * Set up device again
  * Restore the backup to your device. If for any reason you are not able to restore, it most likely contains malware. Then restore one of the previous backups to your device instead, and delete the infected backup from iTunes or iCloud.
* If a factory reset did not work, replace device. Most cases of malware are user-made and involve acts like jailbreaking, and Apple’s warranty does not cover this issue.
