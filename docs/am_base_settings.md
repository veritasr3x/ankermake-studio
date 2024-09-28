# Base Settings
If the printer choice is an "M5-Variant", inherited settings are called from the _machine base common_ section. Here are some interesting excerpts:

- Size and Coordinates
    - bed shape: 0x0,235x0,235x235,0x235
    - max print height: 250
    - z offset: 0
- Advanced
    - relative e distances: 1
    - firmware retraction: 0
    - use volumetric e: 0
    - variable layer height: 1
- Machine Limits
    - feedrates
    - accelerations
    - jerks
- Extruder
    - size
    - layer height limits
    - retraction

```
        # Custom G-code
                start_gcode = M104 S{first_layer_temperature[0]} ; set final nozzle temp\nM190 S{first_layer_bed_temperature[0]} ; set and wait for bed temp to stabilize\nM109 S{first_layer_temperature[0]} ; wait for nozzle temp to stabilize\nG28 ;Home\n;LAYER_COUNT:{total_layer_count}\n
                autoemit_temperature_commands = 1
                end_gcode = M104 S0\nM140 S0\n;Retract the filament\nG92 E1\nG1 E-1 F300\nG28 X0 Y0\nM84
                before_layer_gcode = ;BEFORE_LAYER_CHANGE\n;{layer_z}\n;LAYER:{layer_num+1}
                layer_gcode = ;AFTER_LAYER_CHANGE\nG92 E0
                toolchange_gcode = 
                between_objects_gcode = 
                color_change_gcode = M600
                pause_print_gcode = M601
                template_custom_gcode = 
```
