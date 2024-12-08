 ```
  ___   ___     __________    ___        ________   ________   ________      
 |\  \ |\  \   |\   ____  \  |\  \      |\   ____\ |\  _____\ |\   ____\     
 \ \  \/   /|_ \ \  \__|\  \ \ \  \     \ \  \___| \ \  \___| \ \  \___|     
  \ \   ____  \ \ \  \ \ \  \ \ \  \     \ \  \     \ \   __\  \ \  \  ___   
   \ \  \__ \  \ \ \  \_\_\  \ \ \  \     \ \  \____ \ \  \_|   \ \  \|\  \  
    \ \__\ \ \__\ \ \_________\ \ \__\     \ \______\ \ \__\     \ \_______\ 
     \|__|  \|__|  \|_________|  \|__|      \|______|  \|__|      \|_______| 

```
_____________

### Download: https://github.com/Koi-TF2/Koi-Config/archive/refs/heads/Release.zip

#### Current version: 6.8 (Dec 8th, 2024)

_____________

##### HOW TO INSTALL:
1. Copy the "koi_cfg" folder, "autoexec.cfg" file, and "config.cfg" file into TF2's default "cfg" folder. (Location for the default cfg folder is `Steam\steamapps\common\Team Fortress 2\tf\cfg`)

2. Copy the "koi_custom" folder into TF2's default "custom" folder. (Location for the default custom folder is `Steam\steamapps\common\Team Fortress 2\tf\custom`)

3. Add the "Advanced launch options" through steam. To do this: 
   - Find TF2 in your steam library
   - Right click on the game, and then click on "Properties"
   - Under the "General" tab, you will see a "Set Launch Options" area
   - Paste in the line of launch options seen below into that area, and then click OK

  #### Fullscreen @ 1080p 240hz (Recommended for best performance): 
`-dxlevel 95 -full -w 1920 -h 1080 -freq 240 -novid -nojoy -nosteamcontroller -nohltv -noquicktime -precachefontchars -useforcedmparms -noforcemaccel -noforcemspd`
  #### Windowed Borderless @ 1080p 240hz (Better for multitasking on multiple monitors, better alt+tab): 
`-dxlevel 95 -sw -w 1920 -h 1080 -noborder -freq 240 -novid -nojoy -nosteamcontroller -nohltv -noquicktime -precachefontchars -useforcedmparms -noforcemaccel -noforcemspd`
  


4. **HIGHLY RECOMMENDED - IMPORTANT**: Install Broesel Hud & the Broesel Hud Customizations. To do this:
   - Prerequisites: 1) have the "koi_custom" folder already installed. 2) extract/open the Broesel Hud zip archive found in this repo.
   - After both above prerequisites are complete: Install the hud. From the main "Broesel Hud" folder inside the hud zip, there will be a "resource" and "scripts" folder. Drag both into the "koi_custom" folder. When prompted, choose to **replace the existing files** that have the same names so that the Broesel Hud files overwrite the existing ones.
   - Once Broesel Hud is installed, install the items in the "Broesel Hud Customizations" folder from the hud zip. Inside this folder there are numbered customization folders which are HIGHLY RECOMMENDED. To make the install process quick and easy, there is also an "ALL-QUICK" folder with all recommended customizations inside ready to be added. Drag the cooresponding "scripts", "materials", and "resource" folders into the "koi_custom" folder. Similarly to the previous step, choose to replace the existing files so that the customization files overwrite the existing ones.
   - NOTE 1: "tf_hud_target_id_disable_floating_health" needs to be set to "1" when using this hud. **It is already set to 1 by default in this config**. If you are NOT using Broesel Hud then it may be better to keep this on 0. It can be found in "koi_cfg/hud+ui.cfg" at the very top of the file, just in case.
   - NOTE 2: The hud customizations include a custom crosshair. If you do not use the Broesel Hud customizations, you will need to re-enable the regular game crosshair. To do so, go to "koi_cfg/crosshair.cfg" and change the "cl_crosshair_scale" value to "28". Additionally, you will need to go to "koi_cfg\enhancements\zoom_toggle.cfg" and change the values of "cl_crosshair_scale" to "12" on zoomin and "28" on zoomout. All of these scale values have been set to 0 by default so that the built-in crosshair is not visible (so as to not have the default game crosshair collide with the custom crosshair).

_____________

5. Optional 1: "Streamer" Mode (Hide usernames) with Broesel Hud:
- Hide usernames from the killfeed:
  - Inside `scripts\Hudlayout.res`, find `HudDeathNotice` and change: `"TextFont" "surface11"` to `"TextFont" "redacted8"`. Note that this does not hide weird characters or symbols from player names. If you want to completely remove names fully, use `"TextFont" ""` instead
- Hide usernames from the killcam:
  - Inside `resource\ui\FreezePanel_Basic.res`, find `FreezeLabelKiller` and change: `"labelText" "%killername%"` to `"labelText" ""`
  - Also inside `resource\ui\FreezePanel_Basic.res`, find `itempanel` and change: `"xpos" "r200"` and `"ypos" "0"` to `"xpos" "9999"` and `"ypos" "9999"` respectively (this prevents the killcam weapon-display panel from showing up, which contains "\<playername\> is carrying:". This also prevents malicious weapon names/descriptions from being displayed on killcam. Note that this DOES NOT disable the item inspect/display panel entirely - you can still inspect and see other player's items in spectate and while waiting for respawn. This ONLY disables being able to see the weapon of the player who killed you within the killcam specifically)
- Hide \<playername\> is on a killstreak popup notifications:
  - Use "cl_hud_killstreak_display_time 0". The cl_hud_killstreak_display_time cvar can be found in "koi_cfg/hud+ui.cfg" at the top of the file (by default it is set to 3 seconds)
- Changing these values does not hide player names from the scoreboard (tab), from voicechat, or from friendly medics/friendly players when moused-over
- It is recommended to use "commstoggle" with this mode, which toggles on/off both text and voice chat when key pressed. Bound to "\\" (backslash key) by default. Or alternatively open console and type "commstoggle"

6. Optional 2: Using the custom sprays found within the "Sprays" zip. These can be installed by placing any of the "vgui" folders (1 for each spray) directly into `Steam\steamapps\common\Team Fortress 2\tf\materials` and **NOT** into the "koi_custom" folder's material section (sprays are not meant to be placed into the custom folder). Please note that within the "sprays.cfg" file in "koi_cfg", the variable cl_logofile "materials/vgui/logos/spray.vtf" has been pre-set. What this means is only 1 spray named "spray.vtf" can be used at a time. Using multiple sprays and changing between them therefore does not work (unless spray file is renamed or config is changed).

_____________

7. Note 1: When viewing other player's demo files (.dem), make sure your "config.cfg" file is set to Read-Only. Doing so will prevent the other player's custom settings seen within the demo file from being placed into your own game files, potentially overwriting config settings. This will not impact viewing your own demos since they only utilize your own settings.

8. Note 2: Sometime in 2021 RGL made any "oversized heal particles" illegal. Because of this ban, I have created a custom rule-friendly overheal particle which turns the default stock overheal particles bright green for higher visibility. They are completely stock and not oversized, only the color has been changed for better visibility. This rule-friendly particle file is used by default with this config. Please note that I have still included the previous large overheal particles in this config in a backup folder located here `koi_custom/particles/BACKUP/` in case anyone wants to use them. As a reminder: if you do choose to use the oversized particles in RGL, I am not responsible for issues you may run into with the admins - this is your warning. If RGL decides to allow the large particles again then I will remove this note from this readme and make the large particles default again.
