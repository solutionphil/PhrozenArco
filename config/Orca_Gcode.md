Machine Start G-Code:

M107
G90
M140 S[bed_temperature_initial_layer_single]
M104 S140 
M190 S[bed_temperature_initial_layer_single]
M109 S140
M106 S255 
;G30
G28
BED_MESH_CALIBRATE_CUSTOM MESH_MIN_X={adaptive_bed_mesh_min[0]} MESH_MIN_Y={adaptive_bed_mesh_min[1]} MESH_MAX_X={adaptive_bed_mesh_max[0]} MESH_MAX_Y={adaptive_bed_mesh_max[1]}
;BED_MESH_CALIBRATE
;AUTO_LEVELING_2
M106 S0
G21
M83
M109 S[nozzle_temperature_initial_layer]
P0 M1
P28
P2 A1
{if total_toolchanges == 0}
T0
{endif}
SET_PRINT_STATS_INFO TOTAL_LAYER=[total_layer_count]


Layer Change G-Code:

;AFTER_LAYER_CHANGE [layer_num] @ [layer_z]mm
SET_PRINT_STATS_INFO CURRENT_LAYER={layer_num + 1}
