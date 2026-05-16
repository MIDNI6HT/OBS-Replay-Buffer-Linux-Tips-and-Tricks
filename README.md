# Tips and Tricks to make a Shadowplay like Replay Buffer in OBS

## Enabling the Replay buffer

Go to Settings → Output 

Select "Advanced" Output Mode at the top and then navigate to "Replay Buffer" tap and Enable it with the checkbox.

<img width="980" height="364" alt="image" src="https://github.com/user-attachments/assets/011fc9e3-8e75-4c91-bcc6-5263e79ae13d" />

Select the replay buffer desired time and if you have a good amount of memory in your system, increase the Maximum memory a little. I have set mine to 2048 MB later on.

## Setting Replay Buffer Hotkeys

In the settings menu, navigate to "Hotkeys" and then search for "Replay" in the hotkey search bar at the top.

You can set both the "Start Replay Buffer" and "Stop Replay Buffer" hotkeys to the same shortcut if you want it to work like a toggle. The sound notification script below would be helpful to make out the state of the replay buffer then.

<img width="970" height="278" alt="image" src="https://github.com/user-attachments/assets/689f4ab0-7cc9-4b8c-9ca7-a753c7ee1f8e" />

Note: If you're running OBS Studio Flatpak on wayland, you might need to use this [script](https://github.com/vol1t/OBS-Studio-Flatpak-XWayland-Universal-Fix) to enable global hotkeys even when the app is not in focus.

# OBS Linux Replay Buffer Sound Notifications
This is a simple Lua script that plays a .wav sound whenever the replay buffer is saved, enabled, or disabled. It has been adapted for Linux support using PulseAudio or ALSA.

## Installation

1. Ensure that aplay (ALSA) or paplay (PulseAudio) is installed on your system. Run 'aplay' or 'paplay' and see if the commands work for you, if not, try installing them following your own distro's instructions. This script is set to use 'paplay'by default.

Ensure that the sound file is in a format supported by the utility (e.g., .wav for aplay and .wav/.ogg for paplay).

2. Use the sounds in the repo or any .wav sound but make sure to match its name either in "Replay_Buffer_Sound.lua" (edit with any text editor) or rename your .wav files to match what is already in the script.

3. Put the audio files in the same location with "Replay_Buffer_Sound.lua"
   - A good way to keep things tidy is to create a separate "scripts" folder somewhere in your Home and keep all your scripts there in case you need to back up your OBS Settings.

4. Go to OBS → Tools → Scripts → + and then select the script file.

This Lua script was forked from https://gist.github.com/snakecase/e816384a071cec31efbb4b9e429c108d


## Tips for autostart

Make sure to enable the system tray and minimize to system tray in the general settings (See pic below)

![image](https://github.com/user-attachments/assets/e3245b94-6c60-43b0-a0a7-4154fe96563a)

Set up OBS Studio to auto-start using your own desktop environment's autostart options and then add the launch argument "--startreplaybuffer" to start the replay buffer automatically at startup.

For example on Linux Mint using Cinnamon 6.2.9:

![image](https://github.com/user-attachments/assets/7102947c-2942-4690-9006-0eecb8d2e30d)

On Bazzite using KDE Plasma 6.6:

<img width="1199" height="849" alt="image" src="https://github.com/user-attachments/assets/eb5df54e-17aa-42f6-8d37-1dca592878ab" />



## Credits

* [upgradeQ](https://gist.github.com/upgradeQ/b2412242d76790d7618d6b0996c4562f)
* [gima](https://gitlab.com/gima/obsnotification)
* [AkazaRenn](https://gist.github.com/AkazaRenn/98871c04daef7130ffa25b3f47bf1dbc)
* [GTMoraes](https://github.com/GTMoraes)

Thank you guys!

