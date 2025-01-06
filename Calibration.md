# Calibration with/in Klipper

common first steps for getting klipper setup before your first print. Heres some helpful links
Config questions?
https://github.com/KevinOConnor/klipp...
Klipper config checks 
https://github.com/KevinOConnor/klipp...
Pressure advance tuning
   • Klipper Pressure Advance Tuning MADE ...  


From https://youtu.be/GhuBHEcjNH4?si=HP4MA6_YVfNuKo85
TODO add to [heater_bed] section 
pwm_cycle_time: 0.01666 (if 60hz power grid)  us canada 
pwm_cycle_time: 0.02        (if 50hz power grid)


## Bed leveling 

### Spring Screw change 
   DONE 
### screws_tilt_adjust
helps to level the bed by telling how much to turn the weels. 

text article on screws_tilt_adjust:  https://www.printsleo3d.com/screwtilt

bed screws 
old values 
screw1: 25, 205 # Using rear left to take measurements as harder to reach
screw1_name: rear left screw
screw2: 195, 205
screw2_name: rear right screw
screw3: 195, 35
screw3_name: front right screw
screw4: 25, 35
screw4_name: front left screw


```printer.cfg
[screws_tilt_adjust]
screw1_name: front left screw
screw2_name: front right screw
screw3_name: rear right screw
screw4_name: rear left screw
screw1: -5, 30     #screw coordinates need to be measure for YOUR specific printer
screw2: 155, 30
screw3: 155, 190
screw4: -5, 190  # 
horizontal_move_z: 10.
speed: 50.   #speed of travel moves between screws
screw_thread: CW-M3  # CW clock wise or CCW counterclockwise for the bed to go up. Measure your bed screw m3=3mm / m4=4mm / m5=5mm
```

coordinates for each of the four bed leveling screws as they relate to the position of the BL Touch not the nozzle -meaning place the BL Touch over each screw and use the current coordinates-
Or as close as possible if the probe can't be on top of the screw

        left             + 170 0               right 
front 72,77  44,00                       244,00  44,00
        73
    +  0     170   

back  72,77 214,00                       243.77 214,00
       73                                  244

Calibrating E-steps, temperature tolerances, and flow are a great way to start.

Should I get the max x and y values changed to maximise the area available for the probe ? 

use the SCREW_TILT_CALCULATE (in tools menu)
and follow the resulting recommendations repeat until under 5 minutes 

# Probe z offset 


probing middle at  147  154  



remove coasting 


[gcode_macro start_print]

>>> Start G code macro 
