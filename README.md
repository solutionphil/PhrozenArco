# PhrozenArco
AddOns, hints, tips and tricks for the Phrozen Arco FDM printer

## config/AddOn.cfg
Functions 💥:
- ☑️ Added [respond] & [exclude_object] for console outputs and ORCA part selection :c
- ☑️ Added an startup beep using the integrated beeper 🎵
- ☑️ Added PID control for more quiet board fan operation (🫶 thanks to [eknofsky](https://github.com/eknofsky)) 🎧 ⚠️[need to comment out the old fan control section in printer.cfg](https://github.com/user-attachments/assets/8166b5c8-1e5e-40b5-8dd1-d662d7d2ea1b)
- ☑️ Added Screws_Tilt_Adjust functionality to get instructions for leveling the bed (triggered in console using screws_tilt_calculate) 🪛
- ☑️ Added Z_Tilt_Adjust for levelling the left and right Z-Axis (triggered by entering Z_Tilt_Adjust in console or click the [small icon](https://github.com/user-attachments/assets/8f263903-70f9-4fa7-9d32-b4b9a3c52ba4) aside of homing in mainsail) 📏
- ☑️ Added for Screws_Tilt_Adjust and Z-Tilt_Adjust a homing first before performing the action to avoid scratching the bed under unhomed condition 🏠
- ☑️ Added Adaptive Mesh with individual number of meshing points depending on object size (⚠️ needs Orca Adjustments)📐
- ☑️ Added Light Toggle switch for Mainsail (🫶 thanks to Jay S. and Edwin T.) 💡
- ☑️ 🔥Added M600 support. After executing M600 it automatically retracts out the filament. Take out the old filament and put the new filament in. Press [resume](https://github.com/user-attachments/assets/94c5e294-aff2-47f3-8124-f709c646ad53) in Mainsail Dashboard and wait until it loads the filament (need to push it little  bit until you feel its taken it). Press again [resume](https://github.com/user-attachments/assets/94c5e294-aff2-47f3-8124-f709c646ad53) and it should proceed printing with the new filament :). ⚠️There is only interaction over the Mainsail Dashboard possible. The LCD does not support this function (at least Im not aware of how it would be triggered).
 - ... new feature will be added soon here

Instructions📑:
1. Upload it into the Klipper config folder (same 📁 where printer.cfg is located) 
2. In printer.cfg add on top the line: [include AddOn.cfg]
3. In printer.cfg put # in front of the old mainboard fan control section ([CLICK HERE TO SEE THE EDITED VERSION](https://github.com/user-attachments/assets/8166b5c8-1e5e-40b5-8dd1-d662d7d2ea1b))


## config/Orca_Gcode.md
Functions 💥:
- ☑️ Added adaptive bed meshing to Orca
- ☑️ Added Layer Info to Orca for showing Layer numbers in Mainsail

Instructions📑:
1. Copy the code snippets for Start G-code from the file in Orca under Printer Settings--Machine G-code--[Machine Start G-Code](https://github.com/user-attachments/assets/56eb1a2b-4e3b-472f-a754-c0f7bf5e4327)
2. Change Values for adaptive bed mesh under Printer Settings--[Basic Information](https://github.com/user-attachments/assets/5b15faf3-d276-43f8-820f-73795828afc5)
3. Copy the code snippets for Layer change G-code from the file in Orca under Printer Settings--Machine G-code--[Layer Change Gcode](https://github.com/user-attachments/assets/1b46c960-d7ca-45a8-9369-41161494569d)


## config/printer.cfg
Functions 💥:
- ☑️ Setting the value hold_current

Description📑:
Adding hold_current to the x,y and z steppers has main benefits of reducing stepper motor heat and power consumption during idle periods, especially for motors that remain stationary for longer durations. This can help improve component longevity and reduce thermal stress. Setting it for x and y in an range of 50-70% of run_current can support smoother printing. The Arco has for the high speeds a pretty high current set and this can cause small vibrations on idle. A lower hold_current reduces this possible vibrations. For the z axis its beneficial to set it on the same value like run_current. A lower hold_current can cause one or both sides unevenly sinking down a bit on idle.
I use for myself a hold current of around 60% for x and y. The z axis is running on 0.9 both and optionally you can set a value of 0.5 to the extruder.

Instructions📑:
1. Open printer.cfg in config 📁 (easiest way is in mainsail over machine and clicking on printer.cfg)
2. Add hold_current under [tmc5160 stepper_x],[tmc5160 stepper_y],[tmc2209 stepper_z],[tmc2209 stepper_z1]and optionally under [tmc2209 extruder]
   ⚠️[Example here](https://github.com/user-attachments/assets/8352638e-08a7-4158-9276-61496bce998a) 
3. Click save & restart ... done 🏁


## Mainsail: sorting macros
Functions 💥:
- ☑️ Optimizing macro section in the Mainsail Dashboard
  
Description📑:  
Under the following link is a nice explanation for managing the G-code macros in the dashboard [LINK](https://docs.mainsail.xyz/overview/settings/macros)<br>
This helps to tidy up the dashboard view 🧹


 ## Hardware Z-Rod Mod 
Functions 💥:
- ☑️ Smoother Gantry movement on Z-axis

Description📑:
The Arco has by default on top and bottom ball bearings which guide the z-rods. This design can cause z-banding. The effect gets stronger the more the z-rods are bend. If you are actually good with the print quality---keep the machine stock. I would just recommend you to do this modification as a more experienced user and if you experience z-banding issues.
Other than that I can just say a big 🫶 thanks to Joost v.d.L. for redesigning the top caps and managing how to fight the z-banding.
Here is the link with the files and some more informations [CLICK](https://www.printables.com/model/1428999-phrozen-arco-z-lead-screw-flexing-top-cap-set)🔥



<br/>

> [!CAUTION]
> 
> Disclaimer:
>Working with electricity and electronic components can be dangerous. Always ensure you take the necessary safety precautions when handling electrical devices.
>
>This software and associated documentation are provided "as is" without warranty of any kind, either express or implied, including but not limited to the implied warranties of merchantability and fitness for a particular purpose. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of >contract, tort, or otherwise, arising from, out of, or in connection with the software or the use or other dealings in the software.
>
>Use this software at your own risk. The authors are not responsible for any damage to your equipment, personal injury, or any other consequences resulting from the use of this software.
