# PilotsDeck_FNX
This Binary is used read out some (Quartz) Displays of the Fenix A320 and write their Data to FSUIPC Offsets. There PilotsDeck (or any other Application using FSUIPC basically) can pick it up to display it on the StreamDeck.<br/>
To make one Thing directly clear: it is a **HACK**. Literally: It accesses the Process Memory directly (read-only!) to get the Data. It will likely break with the next Update (until I'll managed to find the correct Spots again).<br/>Currently compatible with Fenix Version **1.0.2.104**.<br/>

# Installation
Put the Folder/Binary generally anywhere you want, but *don't* use: Any Application's Folder (e.g. MSFS, Fenix, StreamDeck) or any of the User Folders (Documents, Downloads, etc).<br/>

It is designed to be started by FSUIPC - add this to your ini File:
```
[Programs]
RunIf1=READY,KILL,X:\PATH\YOU\USED\PilotsDeck_FNX2PLD.exe
```
But you can also start it manually when MSFS/FSUIPC are loaded (Main Menu).

# Usage
When it is running (started either automatically or manually) just set up your Flight as you normally would.<br/>
It waits 20 Seconds after the Fenix Executables are loaded before scanning the Memory - just make sure you hit "Ready to Fly" before the Time runs out! Else some Memory Locations can't be found. You can configure the Delay to match your Loading Times / Behaviour.<br/>
Note that this Application has no Window - you have to use Task Manager if you want to see if is running or check it's Log.<br/>
The Memory Scan usually takes under one Second and the time it takes for an Update Cycle is arround 0,3ms on average (on my System).

# Configuration
You can configure some Parameters in the PilotsDeck_FNX2PLD.dll.config File:
- **offsetBase**: The first (FSUIPC) Offset Address to use (hexadecimal), defaults to 0x5408
- **updateIntervall**: The time between each Update in Milliseconds, defaults to 50
- **waitReady**: The time to wait before the User clicked "Ready to Fly" in Seconds, defaults to 20

