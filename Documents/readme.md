# List of things to do
- [x]Install umbilical
- [x]Fix adapter cable GND/Vin swapped
- [x]Make up new umbilical from frame to toolhead
- [x]Look into X-axis resonance
 - [x]Is it affected by putting printer on hardwood floor instead of shakey card table...some, but not the double issue.
 - [x]Need better cable swing support?  Don't think so.
 - [x]Get both EBB36 adxl345 and Carto working to compare.  Now I have even MORE questions...lol.
- [x]Design webcam mount integrated into Apex-eng corner bracket
 - [x]print it and test it
- [x]Rerun Voron Calibration Cube
- [x]Rewrite entire HOME routine to force safer X/Y order operation (and skip if not needed)
- [x]Fix/Improve the feed between Extruder and HE on XOL toolhead
  - [x]Order Stainless 4mm OD x 2mm ID tube
  - [x]Install in XOL
- [x]Restructure entire congig section into directories and move some things under manta.cfg
- [x]Document everything on GIT
  - [x]Initial refactored GIT structure
  - [x]Samba share on CM4
  - [x]Sync GIT to samba share
  - [x]Sym-link Siboor config in GIT structure to ~/printer_data/config
  - [x]Pull-sync to printer
  - [x]Ensure restart works
  - [x]Update links/images formatting into better table structure
- [x]Update Internal Spoolholder STL to have recessed spring/bolts
- [x]Work on reverse tunnel proxy service to gain external access
- [x]Install Fluidd/Mainsail as docker on NAS
- [ ]Update Carto FW when available to fix Coil Frequency error
- [ ]Build StealthBurner
- [ ]Put endstop switch on Z-axis max?


# Debug Stuff for TTC and canbus traffic

- To check for errors on canbus (non-invasive)

```
candump can0,0~0,#FFFFFFFF
```

- To generate canbus loading (kills klipper, if it is running)

```
cangen -e -g 0.12 can0
```

- To watch for traffic on the canbus

```
watch -n 1 -d "ip -details -statistics link show can0"
watch -n 1 "tc -s qdisc show dev can0"
```

- To watch load on the canbus (as percentage %)

```
canbusload can0@1000000 -b -c
```

- To graph klipper.log

```
~/klipper/scripts/graphstats.py /tmp/klippy.log -o loadgraph_host.png
```
