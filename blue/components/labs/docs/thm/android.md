# Android malware (static) analysis example

This static analysis sample case study is for a trojanised application [uploaded in Pithus (online analysis)](https://beta.pithus.org/report/ae05bbd31820c566543addbb0ddc7b19b05be3c098d0f7aa658ab83d6f6cd5c8)). The sample for local analysis with [jadx](https://testlab.tymyrddin.dev/docs/dfir/jadx) can be [downloaded here](https://pts-project.org/samples/sample_1.zip).

----

## First steps (Pithus)

Name package:

![Name package](../img/name-apk.png)

Hashes (MD5 and SHA256):

![Hash MD5](../img/hash-md5.png)

![Hash SHA256](../img/hash-sha256.png)

Size of the package:

![Size of APK](../img/apk-size.png)

## Getting into the APK

![APK Analysis](../img/apk-analysis.png)

With some quick online research, we can find that [the 3.65.979 version was released on 1 March 2021](https://www.apkmirror.com/apk/wire-swiss-gmbh/wire/wire-3-65-979-release/wire-secure-messenger-3-65-979-android-apk-download/).

![APK Threat Intel](../img/apk-threatintel.png)

The X.509 certificate was created to work from 26 April 2021, and the oldest files from the samples were identified around that time. Two months after the release of the version of the legit APK. 

In the ***APK Analysis*** tab of Pithus, we can find the main activity for this application:

![APK Threat Intel](../img/apk-main-activities.png)

```text
['org.xmlpush.v3.StartVersion', 'com.waz.zclient.LaunchActivity', 'com.waz.zclient.MainActivity', 
'com.waz.zclient.calling.CallingActivity', 'com.waz.zclient.preferences.PreferencesActivity', 
'com.waz.zclient.PopupActivity', 'com.waz.zclient.ShareActivity', 
'com.waz.zclient.controllers.notifications.ShareSavedImageActivity', 
'com.waz.zclient.appentry.AppEntryActivity', 'com.waz.zclient.ForceUpdateActivity', 
'com.waz.zclient.conversation.folders.moveto.MoveToFolderActivity', 
'androidx.biometric.DeviceCredentialHandlerActivity', 'com.google.android.gms.common.api.GoogleApiActivity']
```

Activities:

```text
org.xmlpush.v3.StartVersion
com.waz.zclient.LaunchActivity
com.waz.zclient.MainActivity
com.waz.zclient.calling.CallingActivity
com.waz.zclient.preferences.PreferencesActivity
com.waz.zclient.PopupActivity
com.waz.zclient.ShareActivity
com.waz.zclient.controllers.notifications.ShareSavedImageActivity
com.waz.zclient.appentry.AppEntryActivity
com.waz.zclient.ForceUpdateActivity
com.waz.zclient.conversation.folders.moveto.MoveToFolderActivity
androidx.biometric.DeviceCredentialHandlerActivity
com.google.android.gms.common.api.GoogleApiActivity
```

**org.xmlpush.v3.StartVersion** stands out from the crowd. The Java method `org.xmlpush.v3.q.c.a()` is meant for reconfiguring SMS.

In the same tab, in the section on ***Manifest analysis***, three actions are triggered by this activity:

![APK Manifest analysis](../img/apk-manifest-analysis.png)

Check the ***Behavior Analysis*** tab: This APK is requesting an extensive amount of permissions. This might not be entirely suspicious, depending on what this application is doing. 

The ***Threat analysis*** section on that page is based on [Quark](https://github.com/quark-engine/quark-engine). The first crime identified:

![APK Threat analysis](../img/apk-threat-analysis.png)

And contains this unbelievable action (making it hard for a user to find the app in the menu):

![Hide the current app's icon](../img/apk-hide-icon.png)

The ***Behavior analysis*** section on the ***Behavior analysis*** tab contains ***Tcp sockets***:

![Tcp sockets](../img/apk-tcp-sockets.png)

Only `okio/Okio.java` is probably not malicious. The Okio library is built on top of Java's InputStream and OutputStream classes, and provides a higher-level API for working with these types of streams. It also includes support for working with other data sources, such as files, sockets, and in-memory data structures.

The ***Network Analysis*** tab shows domains that have been identified and are queried by the APK. More advanced malware will obfuscate the domain or IP it communicates to avoid detection, and in such cases this tab does not reveal much.

## Hunting

Continuing the research to find other samples that are identical or similar to the first sample. This can give an understanding of the type of victims being targeted and the Tactics, Techniques, and Procedures (TTPs) malicious actor(s) are using.

In the ***Fingerprints*** tab, scroll down to the ***SSdeep*** and ***Dexofuzzy*** results and click on the magnifying glass on the right. Dexofuzzy gives results, and the ***Threat Intel*** tab a little more, but the link to VirusTotal reveals vendors do not detect maliciousness in similar files.

![Dexofuzzy results](../img/apk-similarity.png)

Logging into Pithus, you can create Yara rules for hunting. Pithus only supports vanilla Yara for the moment. If you try to use modules, it will not work.

## Search (Pithus)

On the home page of Pithus, there is a query field available. The ***help*** button is essential.

For example, to search for the sha256 hash of the sample:

```text
sha256:ae05bbd31820c566543addbb0ddc7b19b05be3c098d0f7aa658ab83d6f6cd5c8
```

To search for the non-malicious class that was identified:

```text
java_classes:okio/okio
```

## First steps (jadx)

Package name and version:

![Name package](../img/jadx1.png)

Application name:

![Application name](../img/jadx2.png)

## Signing certificate

![Signing certificate information](../img/jadx3.png)

If permitted by your internal guidelines, you can search for the SHA256 of the sample on multiple online services such as VirusTotal, or [download the legit version of the app](https://www.apkmirror.com/apk/wire-swiss-gmbh/wire/wire-3-65-979-release/), also for other comparisons (like permissions).

| SHA-256 Fingerprint                                                                             | Valid from                    |
|-------------------------------------------------------------------------------------------------|-------------------------------|
| E1 4F 25 46 56 FF 86 9B B7 38 AE C5 86 56 04 21 71 C8 62 5C 9D EF BC C6 EB 4F 24 D4 1D 4E C9 29 | Mon Apr 26 12:51:28 CEST 2021 |
| 16 26 E3 F8 5D FD 84 34 F7 86 66 44 48 61 F4 E5 C8 FB 37 7A 28 4C 1C 30 4C B9 D5 85 28 8F A3 52 | Tue Feb 12 12:53:31 CET 2013  |

## Requested permissions

Review the permissions and assess if these are legitimate permissions for the app's purpose. Instincts and gut feelings are worth investigating.

![Requested permissions](../img/jadx4.png)

Does this app really need to be able to write, send and receive SMS messages?

## Frosting

The short analysis with Pithus gave us that the sample is ***not frosted***.

## FinSpy

VirusTotal results:

![VirusTotal FinSpy](../img/vt1.png)

Pithus hunt:

![Pithus FinSpy](../img/pithus-finspy.png)

## Resources

* [Manifest.permission](https://developer.android.com/reference/android/Manifest.permission)
* [Permissions on Android](https://developer.android.com/guide/topics/permissions/overview)
* [Android app permissions explained and how to use them](https://www.androidauthority.com/app-permissions-886758/)
* [FinSpy spyware analysis](https://defensive-lab.agency/2020/09/finspy-android/) (similar sample)

