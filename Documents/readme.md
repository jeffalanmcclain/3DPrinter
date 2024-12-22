# List of things to do
- [x]Install umbilical
- [x]Fix adapter cable GND/Vin swapped
- [x]Make up new umbilical from frame to toolhead
- [ ]Look into X-axis resonance
 - [ ]Is it affected by putting printer on hardwood floor instead of shakey card table
- [x]Design webcam mount integrated into Apex-eng corner bracket
 - [x]print it and test it
- [x]Rerun Voron Calibration Cube
- [ ]Build StealthBurner
- [ ]Put endstop switch on Z-axis max?
- [x]Rewrite entire HOME routine to force safer X/Y order operation (and skip if not needed)
- [ ]Fix/Improve the feed between Extruder and HE on XOL toolhead

# Debug Stuff

- To check for errors on canbus (non-invasive)
```candump can0,0~0,#FFFFFFFF```

- To generate canbus loading (kills klipper, if it is running)
```cangen -e -g 0.12 can0```

- To watch for traffic on the canbus
watch -n 1 -d "ip -details -statistics link show can0"
watch -n 1 "tc -s qdisc show dev can0"

- To watch load on the canbus (as percentage %)
```canbusload can0@1000000 -b -c```