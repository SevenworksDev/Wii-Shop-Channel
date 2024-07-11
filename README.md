# Sevenworks Wii Shop Channel
This repo is for sharing some stuff that may be useful for future development of the Wii Shop Channel. If your an unprofessional skid or horrible learner then back off this isn't for you.
# Building
## 1. Force WSC to show your content.
First you need the 0000005e and 0000005f files from `title/00010002/48414241/content` on your Wiis NAND (YOU NEED THE LATEST SYSTEM UPDATE AND WII SHOP CHANNEL WAD)
## Patching Opera
Download the tools from https://szs.wiimm.de/wszst/ for extracting these special .app files then run `wszst.exe EXTRACT 0000005f.app` if the wszst bin folder is in your %PATH%.  
Navigate to `0000005f.d/arc/opera/myfilter.ini` and replace everything with this:
```ini
[prefs]
prioritize excludelist=0

[include]
file:/cnt/*
https://*.shop.wii.com/*
https://*
miip:*
http://*
https://*

[exclude]
*
```
Run `wszst -q C 0000005f.d` then rename 0000005f.u8 back to 0000005f.app. Boom all done!
## Patching the frontend
Install HxD and open 0000005e.app then replace `68 74 74 70 73 3A 2F 2F 6F 73 73 2D 61 75 74 68 2E 73 68 6F 70 2E 77 69 69 2E 63 6F 6D` with your own URL and `68 74 74 70 73 3A 2F 2F 6F 73 73 2D 61 75 74 68 2E 73 68 6F 70 2E 77 69 69 2E 63 6F 6D 2F` with your own URL along with the slash. (In my experience http:// works very well so use http protocol for your wii shop webserver.)  
If it warns you, you screwed up. Back out right now, do not save and fix your mistakes then save lmao.
## Ta-da
It should work now, have fun screwing around with a couple things.
<video src='https://github.com/SevenworksDev/Wii-Shop-Channel/assets/91027492/88e53c2e-89e0-4b54-9d45-23e4feb4143c' width='50%'/>

