# Portal-patcher
a script to compile Portal for Apple Silicon and Intel 64 bit

This script will create an Apple Silicon or Intel 6S bit version of Portal for macOS.

It is adapted from [this guide](https://jxhug.notion.site/Guide-to-Installing-Portal-Using-Source-Engine-on-macOS-660803f9ced149cfa1647d38fd5a7092) from 2023 which had these issues:
- compiler commands were outdated with the latest updates to Clang
- Valve updated the Source Engine and Portal's files with Half Life 2's anniversary edition which have rendering issues with the older version of the Source Engine used for this port
- the guide had you painstakingly copy and paste each command in the terminal

This script aims to fix all these issues and create an application bundle with minimal user interaction. The script will match the game's localization to your system language settings. Note: you must own Portal on your Steam account for this to work.

## How to use:

- to the right of this window, click "releases", expand "assets" if necessary and click on "Portal.Patcher.zip" to download it
- unzip the file if necessary
- Double click Portal.command. You will have a Gatekeeper alert preventing the script from running, go to system settings > security and privacy, scroll down and click "open anyway".

The script will open the terminal, it will make sure you have all the required dependencies, download/update them if necessary, and prompt you for your Steam login so that it can download the older version of Portal

- type your Steam login and hit enter

you will then be prompted for your Steam password (the terminal won't display anything when you type it, that's normal)
- type your Steam password and hit enter

if necessary, you will then be asked for your Steam guard code. Type it and hit enter.

the script will then download the older version of Portal, download the Source Engine, compile the files and create a Mac version of Portal in the same location as the script. Depending on your machine, the whole operation can take up to about 15 minutes. The terminal will output a bunch of stuff, and if successfull the last thing you'll see will be "--- Build and Processing Cycle Complete! ---".

## Updating the Steam version

If you don't want the game to run as an independant Application Bundle and want to have it work from Steam:

- after following the instructions above, right-click Portal.app and select "display contents"
- navigate to Contents/Resources/, select all the files inside and copy them
- in Steam, select your installed version of Portal in the library, click the gear icon and select Manage > browse local files, it'll open a Finder window where the Portal files are installed
- delete everything except hl2.sh
- paste the files you copied

Normally, Steam communicates with games through a dynamic library which isn't included in this port, so if you want to have Steam launch Portal in a language other than English, we have to set it up ourselves. In Steam, select Portal in your library, click on the gear icon, select "properties" and in General > Launch options, type this:
    -language french -audiolanguage french

replacing with your language instead of french. the tag '-language' is for the UI and '-audiolanguage' is for the dialogues.
Portal supports these languages for the audio:

russian  
spanish  
french  
german  

and these languages for the UI:

ukrainian  
swedish  
tchinese (for traditional Chinese)
schinese (for simplified Chinese)  
thai.dat  
thai  
turkish  
brazilian  
bulgarian  
czech  
danish  
dutch  
english  
finnish  
french  
german  
greek  
hungarian  
italian  
japanese  
korean  
koreana  
latam (for latin american Spanish)  
norwegian  
polish  
portuguese  
romanian  
russian  
spanish

you can now launch Portal from Steam

a similar script is available for [Half Life 2](https://github.com/nonoche2/HL2-patcher/tree/main)
