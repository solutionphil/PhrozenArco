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
- ☑️ Added Adaptive Mesh with individual number of meshing points depending on object size (needs Orca Adjustments-[Machine Start G-Code](https://github.com/user-attachments/assets/56eb1a2b-4e3b-472f-a754-c0f7bf5e4327) and [Printer Settings](https://github.com/user-attachments/assets/5b15faf3-d276-43f8-820f-73795828afc5) )📐
 - ... new feature will be added soon here

Instructions📑:
1. Upload it into the Klipper config folder (same 📁 where printer.cfg is located) 
2. In printer.cfg add on top the line: [include AddOn.cfg] 

<br/>
<br/>
<br/>

> [!CAUTION]
> 
> Disclaimer:
>Working with electricity and electronic components can be dangerous. Always ensure you take the necessary safety precautions when handling electrical devices.
>
>This software and associated documentation are provided "as is" without warranty of any kind, either express or implied, including but not limited to the implied warranties of merchantability and fitness for a particular purpose. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of >contract, tort, or otherwise, arising from, out of, or in connection with the software or the use or other dealings in the software.
>
>Use this software at your own risk. The authors are not responsible for any damage to your equipment, personal injury, or any other consequences resulting from the use of this software.
