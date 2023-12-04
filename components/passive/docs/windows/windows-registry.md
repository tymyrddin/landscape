# Catching and removing malicious registry entries

## Automagically

* [Restoro](https://www.restoro.com/)
* [Iolo System Mechanic](https://www.iolo.com/products/system-mechanic/)

## Manually

Windows Registry is one of the most important built-in tools on your Windows computer. 
Registered malware is not uncommon. Check the Windows Registry for malware because any operation on your PC can make a 
footprint in it. And you can remove malware from the Windows Registry. 

1. Create a system restore point
2. Run regedit to open the Registry Editor
3. Go to HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
4. Scroll down and find the folders which start with Run
5. Click each folder to open the program list

Be careful. Not all are malicious. Check for:

* Misspelled names
* Unfamiliar programs
* Search with DuckDuckGo to find confirmation either way

If it turns out malicious, right-click on that entry and select Delete to remove it from Windows Registry.