# Apex Roleplaying Engine
The Apex Roleplaying Engine for Blizzard's StarCraft II provides a sandbox
environment where players can customize all the units, visuals and scenery of
a map, with the main objective of allowing players to create collaborative
stories or "roleplays" in StarCraft II maps. Apex provides tools for
efficiently creating and saving scenery and characters, along with tools for
storytelling. Apex provides full control over the map, so it can also be used
as a flexible general purpose testing environment.  

# Installation
To use Apex on a StarCraft II map first requires access to the
StarCraft II Editor (SC2Editor). Apex uses data, Galaxy scripts,
and player banks. There is an SC2 Mod already created
with all the data and Galaxy scripts required. To easily install, **use this
mod**! Only manually install Apex if you need to customize data or code
(e.g. if you need to add custom commands).

## Quick Installation
### Adding Apex Engine Mod
This assumes you have a map already created. After opening the map, go to  
**File > Dependencies**  
Hit **Add Other...** and go to the **Battle.net** tab in the window that opens.
After logging in to Battle.net, change the "Source" of files to
**Map/Mod Name** and search for "apex". You should be able to find the
**Apex RP Engine** mod published by Serobliss. Select this mod and hit OK.  

More preferably I recommend getting the **Serobliss Group Dependency** located in the
area as the Apex RP Engine, this dependency comes with all the dependencies most
modern maps use. Be sure to check **"latest"** on the top left so you get automated
updates. :) 

This mod should now be added to your "Document dependencies" list. Move this
mod file to the top of the list by pressing the up arrow button in the
middle of the window (next to the **[-]** button).  

Hit OK.

### Player banks
Now initialize player banks. In the top bar of the SC2 Editor, navigate to  
**Map > Preload Info... > Banks**  
You will be in the **Banks** tab. Click the green **[+]** button on the right.
This will create a new blank bank entry. Select this entry in the list and
near the bottom of the window for **Bank Name:** enter in the box
**ApexBank**. Hit OK.

### Running Apex
Go to the **Trigger Editor** (F6). Remove any existing **Map Initialization** event triggers. Create a new trigger with the event as **Map Initialization**. Create a new action and select **Run Trigger**. This will create a new trigger
in the action list which will say
```
Run Trigger (Check Conditions, Don't Wait until it finishes)
```
Select the **Trigger** and a window will appear with multiple triggers. Select
**apex_trig** and hit OK. The action should now say
```
Run apex_trig (Check Conditions, Don't Wait until it finishes)
```

You are now good to go! Run the map and see if the Apex engine works!

## Manual Installation
Manual installation presumes you have a full understanding of the SC2 Editor.

### Import Scripts and Chat UI
Download the [Apex repo](https://github.com/Joshykins/Apex-rp). In the
SC2 Editor, go to the map **Imports** (F9). Import the Apex engine repo
files **under a Apex directory.** That is, the **Apex.galaxy** file should
be found under the import path **Apex/Apex.galaxy**.  

### Data
Inside the **data/data.galaxy** file, there will be a list of const strings
prefixed by **libapx_BEHAVIOR**. These are all behaviors that must be
created in the SC2Editor for a map that uses Apex. Go to the **Data Editor**
(F7) and create all these behaviors with the names defined by the constants.
**If the names do not match, certain commands will not work ingame.**

### Adding Chat UI
Included in the repo imported should also be the **chat_frame.SC2Layout** file
under **Apex/chat_frame.SC2Layout**. Go back to the **Data Editor** (F7)
and go to the **Game UI Data** tab. In the **Default SC2 UI Settings** entry,
go to the **(Basic) UI: Custom Layout Files+** field and add the
**Apex/chat_frame.SC2Layout**.

### Player banks
Now initialize player banks. In the top bar of the SC2 Editor, navigate to  
**Map > Preload Info... > Banks**  
You will be in the **Banks** tab. Click the green **[+]** button on the right.
This will create a new blank bank entry. Select this entry in the list and
near the bottom of the window for **Bank Name:** enter in the box
**ApexBank**.

### Running Apex
Go to the **Trigger Editor** (F6). Create a new custom script (Ctrl + Alt + T)
that contains the code
```
include "apex/Apex.galaxy"
```

Now create a new trigger with event **Map Initialization** and create an action
to run the custom code
```
libapx_initialize();
```

Now test the map and see if the Apex engine works!


# Contact
**Github repo:** https://github.com/Joshykins/SCApex
**Lead developer:** @Joshykins / Serobliss (serobliss2@gmail.com)  
**SC2 Handle:** Serobliss  
** Developers:** @GPhazon / GPhazon (gphazon@gmail.com) 


# Acknowledgements
Apex has its roots in the original StarCraft II roleplaying engine
[Cortex](https://github.com/FabianPonce/CortexEngine) by lead developer
Fabian Ponce. Much of the Apex engine design philosophy and user commands are
inherited from this engine (though there have been many divergences).
Thus I would like to give a huge personal thanks to Ponce and the rest of the
original Cortex team for their early work on making a roleplaying environment
for StarCraft II.

Also, a big thank you to Xethyr for all of the work that he did making the Wyvern Engine.
