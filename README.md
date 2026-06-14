# Portal-patcher
a script to compile Portal for Apple Silicon

This script will create an Apple Silicon version of Portal for macOS.

It is adapted from [this guide](https://jxhug.notion.site/Guide-to-Installing-Portal-Using-Source-Engine-on-macOS-660803f9ced149cfa1647d38fd5a7092) from 2023 which had these issues:
- compiler commands were outdated with the latest updates to Clang
- Valve updated the Source Engine and Portal's files with Half Life 2's anniversary edition which have rendering issues with the older version of the Source Engine used for this port
- the guide had you painstakingly copy and paste each command in the terminal

This script aims to fix all these issues and create an application bundle with minimal user interaction. The script will match the game's localization to your system language settings. Note: you must own Portal on your Steam account for this to work.

## How to use:

- Download Portal.command.zip in the releases
- unzip the file if necessary
- Double click Portal.command. You will have a Gatekeeper alert preventing the script from running, go to system settings > security and privacy, scroll down and click "open anyway".

The script will open the terminal, it will make sure you have all the required dependencies, download/update them if necessary, and prompt you for your Steam login so that it can download the older version of Portal

- type your Steam login and hit enter

you will then be prompted for your Steam password (the terminal won't display anything when you type it, that's normal)
- type your Steam password and hit enter

if necessary, you will then be asked for your Steam guard code. Type it and hit enter.

the script will then download the older version of Portal, download the Source Engine, compile the files and create a Mac version of Portal where the script is located. Depending on your machine, the whole operation can take up to about 15 minutes.
