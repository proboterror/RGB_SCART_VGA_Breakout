# JVC TM-1011G RGB SCART / VGA Breakout with S-Video

For RGB/SCART modding JVC, SONY PVM video monitors and consumer CRT TVs.

Modified version for JVC TM-1011G.

- Adjusted board mounting holes / layout.
- Added S-Video (Mini-DIN 4 pin) optional connector with 510 Ohm load resistors.
- Removed CSYNC load resistors / capacitor / solder jumper. CSYNC directly connected to output.

Continuation of [RGB SCART Breakout board](https://github.com/proboterror/RGB_SCART_Breakout).

Features:
- SCART / VGA inputs are not switchable. Simultaneous connection are NOT RECOMMENDED, use at own risk.
- Protection diodes on SCART Blanking / VGA +5V inputs against back current with 2 devices connected.
- 3.5 mm mini jack connector for SCART input.
- Optional S-Video connector.

## Schematics:<br>
![Scheme](images/scheme.png)

## Board view:<br>
![Front](images/pcb_front.png)
![Back](images/pcb_back.png)
![Front preview](images/pcb_front_preview.png)
![Back preview](images/pcb_back_preview.png)
![PCB dimensions](images/pcb_dimensions.png)

## Bill of Materials
|Reference|Value|Footprint|Qty|
|-----|-----|-----|-----|
|C1,C2,C3|100nF|0805|3|
|D1,D2|BAT54W|Diode_SMD:D_SOD-123|2|
|J1|SCART-F|CS-102 (SCART-21S)|1|
|J3|DE15 Socket / DSUB-15-HD / VGA| DSUB-15-HD_Socket_Horizontal P2.29x1.90mm EdgePinOffset3.03mm MountingHolesOffset4.94mm|1|
|J11|SJ1-3535NG|CUI/Same Sky Device SJ1-3535NG|1|
|R1,R2,R3|0R/24R/30R|0805|3|
|R6,R7,R8|75R/51R|0805|3|
|R9,R10|510R|0805|2|
|J2|Mini-DIN 4 pin socket||1|
|R11|1K/1K2/4K7|0805|1|
|R12|2.3K/2K8/10K|0805|1|

Notes:
- All resistors are 1%.
- RGB termination / voltage divider resistors values are depending on monitor jungle (chroma/deflection) IC. 
For jungle ICs with 0.7Vpp RGB inputs (like TDA8366):
R1, R2, R3: 0 Ohm,
R6, R7, R8: 75 Ohm.
For jungle ICs with 0.5Vpp RGB inputs (like TA1276AN):
R1, R2, R3: 32 Ohm,
R6, R7, R8: 75 Ohm.
Attenuation / divider resistors R1, R2, R3 can be changed to 24 Ohm, and termination resistors R6, R7, R8 to 51 Ohm for “proper” 75 Ohm termination.
- Blanking voltage divider / pulldown resistors values are depends on jungle IC requirements.
For 3V inputs use R11=1K/1.2K, R12=2.3K/2.8K, and so on.
Some ICs require pulldown R12=10~50K.
R12 can be omitted but R11=120R~180R is recommended to limit current.
- More info on Blanking voltage divider: [sector.sunthar.com/guides/crt-rgb-mod](https://sector.sunthar.com/guides/crt-rgb-mod/rgb-mux.html#how-to-use-the-voltage-divider-on-the-board)
