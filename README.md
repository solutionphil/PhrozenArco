# PhrozenArco
AddOns, hints, tips and tricks for the Phrozen Arco FDM printer

## AddOn.cfg
Functions 💥:
- [x] Added [respond] & [exclude_object] for console outputs and ORCA part selection
- [x] Added an startup beep using the integrated beeper
- [x] Added PID control for board fan (way more silent and same performance)
- [x] Added Screws_Tilt_Adjust functionality to get instructions for leveling the bed (triggered in console using screws_tilt_calculate)
- [x] Added Z_Tilt_Adjust for levelling the left and right Z-Axis (triggered by entering Z_Tilt_Adjust in console or click the [small icon](https://github.com/user-attachments/assets/8f263903-70f9-4fa7-9d32-b4b9a3c52ba4) aside of homing in mainsail)
- [x] Added for Screws_Tilt_Adjust and Z-Tilt_Adjust a homing first before performing the action to avoid scratching the bed under unhomed condition
- [x] Added Adaptive Mesh with individual number of meshing points depending on object size
 

Instructions📑:
1. Upload it into the Klipper config folder (same place where printer.cfg is located)
2. In printer.cfg add on top the line: [include AddOn.cfg]
