# 3d_print
Setup [Cura](https://ultimaker.com/en/products/ultimaker-cura-software) for Anet A6 printer.



### Printer setings

x: `220 mm`

y: `220 mm`

z: `250 mm`

Build plate shape: `Rectangular`

origin at center: [ ]

Heat bed: [x]

Gcode Flacor: `Marlin`

Start Gcode:
~~~
default_value": "G21 ;metric values
G90 ;absolute positioning
M82 ;set extruder to absolute mode
M107 ;start with the fan off
G28 X0 Y0 ;move X/Y to min endstops
G28 Z0 ;move Z to min endstops
M84 ;steppers off
M0 S12 ;wait 12 seconds
M17 ;turn steppers on
G1 Z10.0 F300 ;move the platform down 10mm
G92 E0 ;zero the extruded length
G1 F200 E8 ;extrude 8mm of feed stock
G92 E0 ;zero the extruded length again
M0 S5 ;wait 5 seconds
G1 F9000
M117 Printing...
~~~

### Printhead Settings

x min: `75 mm`

y min: `18 mm`

x max: `18 mm`

x max: `25 mm`

Gantry height: `99999999999 mm`

Number of extruders: `1`

Material diameter: `1.75 mm`

Nozzle size: `0.4 mm`

End Gcode:
~~~
M104 S0 ;extruder heater off
M140 S0 ;heated bed heater off (if you have it)
G91 ;relative positioning
G1 E-1 F300  ;retract the filament a bit before lifting the nozzle, to release some of the pressure
G1 Z+4 E-5 X-20 Y-20 F9000 ;move Z up a bit and retract filament even more
G28 X0 Y0 ;move X/Y to min endstops, so the head is out of the way
G1 Y210 F9000 ;move out to get part off
M84 ;steppers off
G90 ;absolute positioning
~~~
