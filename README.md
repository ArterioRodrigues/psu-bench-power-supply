# ATX PSU Bench Power Supply

Turn a standard ATX computer power supply into an adjustable bench power supply. A 3D-printed enclosure holds an ATX breakout board, a buck converter, and banana-style output terminals, so you get fixed 3.3V / 5V / 12V rails plus an adjustable output from a repurposed PC PSU.

> **Status:** Add photos of your finished build here (`/images/finished.jpg`).
<img width="5712" height="4284" alt="8A764AC3-320B-40B9-89CE-A1100759EF85" src="https://github.com/user-attachments/assets/9f05e019-2453-4cc9-891c-f90c6f1cfa2f" />
<img width="5712" height="4284" alt="IMG_0849" src="https://github.com/user-attachments/assets/5aad7122-eae2-4818-9745-a17a9453d9fc" />
---

## Features

- Fixed 3.3V, 5V, and 12V outputs from the ATX breakout board
- Adjustable DC output through a buck converter, fed from the PSU's 12V CPU (EPS) rail
- Banana-socket binding posts (red/black) for the adjustable output
- 3D-printed case in three parts (A, B, C)
- Designed to sit with a standard ATX power supply

---

## Parts List

| Qty | Part                                                                     | Notes                                                              |
| --- | ------------------------------------------------------------------------ | ------------------------------------------------------------------ |
| 1   | 3D printer filament                                                      | PLA works for light use. PETG is better for heat resistance.       |
| 1   | [MELIFE 24-Pin ATX Breakout Board](https://www.amazon.com/dp/B09GK8XGT9) | Sold as a 2-pack. Only one is needed.                              |
| 1   | [Buck Converter](https://www.amazon.com/dp/B0B7MBNP4G)                   | Adjustable step-down module.                                       |
| 2   | DIYhz M5 x 50mm banana binding posts (1 red, 1 black)                    | Sold as a 10-pack.                                                 |
| 1   | Standard ATX power supply                                                | Must have a 24-pin connector and an 8-pin (4+4) CPU/EPS connector. |
| -   | Hookup wire                                                              | About 18-20 AWG, red and black.                                    |
| -   | Soldering iron and solder                                                | Or crimp or screw connectors, depending on your buck converter.    |
| -   | Heat shrink tubing                                                       | Optional but recommended.                                          |

Tools: soldering iron, wire strippers, multimeter, small screwdriver, and a pair of pliers or a wrench for the binding post nuts.

---

## Printed Parts

All STL files are in the [`/stl`](./stl) folder. Update the folder name if yours differs.

| File         | Description                                |
| ------------ | ------------------------------------------ |
| `Part_A.stl` | main body   |
| `Part_B.stl` | front panel |
| `Part_C.stl` | cover       |

**Suggested print settings** (adjust to your printer):

- Layer height: 0.2 mm
- Infill: 20%
- Walls: 3 or more
- Supports: Replace with yes/no
- Material: PLA or PETG

---

## Wiring Overview

```
ATX PSU
 ├── 24-pin connector ──────────► ATX breakout board (3.3V / 5V / 12V / GND, power switch)
 └── 8-pin CPU (EPS) connector
        ├── Yellow (+12V) ──────► Buck converter  IN+
        └── Black  (GND)  ──────► Buck converter  IN-

Buck converter OUT+ ───────────► Red binding post
Buck converter OUT- ───────────► Black binding post
```

---

## Assembly Instructions

### ⚠️ Safety first

- **Unplug the PSU from the wall** before connecting or changing any wiring.
- Do not open the PSU case. Capacitors inside can hold a dangerous charge even when unplugged.
- Do not exceed your buck converter's input voltage, current, or power ratings. Check the specs for your module.
- Use a multimeter to confirm the output voltage **before** connecting anything you want to power.
- Never short the output terminals.

### Step 1: Print the parts

1. Download the STL files from this repo.
2. Slice and print **Part A, Part B, and Part C**.
3. Remove any supports and test-fit the parts together before wiring.

### Step 2: Connect the 24-pin ATX connector to the breakout board

1. Make sure the PSU is **unplugged** and the switch on its back is off.
2. Plug the PSU's 24-pin connector into the ATX breakout board. It is keyed, so it only fits one way.
3. The breakout board has labeled terminals for 3.3V, 5V, 12V, and GND, plus a power switch that handles the PS_ON signal. Check your board's labeling.

### Step 3: Locate the 12V pins on the 8-pin CPU connector

1. Find the 8-pin CPU/EPS connector on your PSU. It is often a 4+4 pin connector.
2. On this connector, the **yellow wires are +12V** and the **black wires are ground**.
3. Identify one yellow wire and one black wire. Check the pinout printed on your PSU's label if you are unsure.

> Tip: If you do not want to modify your PSU's cables, buy a CPU 8-pin extension or splice cable and use that. You can still use the PSU afterward.

### Step 4: Wire the buck converter input

1. Cut or tap one yellow (+12V) wire and one black (GND) wire from the 8-pin connector. Strip about 5 mm.
2. Connect **yellow (+12V)** to the buck converter **IN+**.
3. Connect **black (GND)** to the buck converter **IN-**.
4. Use heat shrink or tape on any exposed joints.

### Step 5: Install the output terminals

1. Insert the **red** binding post through the output hole in the printed case. Secure it with its nut.
2. Insert the **black** binding post the same way.
3. Solder or attach a wire to the rear screw end of each post.

### Step 6: Wire the buck converter output

1. Connect the buck converter **OUT+** to the **red** binding post.
2. Connect the buck converter **OUT-** to the **black** binding post.
3. Double-check polarity before moving on.

### Step 7: Assemble the case

1. Mount the breakout board, buck converter, and binding posts in the printed parts.
2. Route the wires so nothing is pinched when the case closes.
3. Fasten Part A, B, and C together. Add the screw type and size you used here.

### Step 8: Test

1. Set the buck converter's adjustment to its lowest setting.
2. Plug in the PSU and turn on the rear switch.
3. Use the breakout board's power switch to turn it on.
4. Measure the voltage across the red and black binding posts with a multimeter.
5. Adjust the buck converter to the voltage you want, then confirm it with the meter.
6. If the reading is wrong or nothing happens, unplug and recheck your wiring.

---

## Usage

1. Plug in the PSU and switch it on.
2. Turn on the breakout board switch.
3. Adjust the buck converter to your desired output voltage.
4. Connect your load to the red (+) and black (-) terminals.
5. Fixed 3.3V, 5V, and 12V rails are available on the breakout board.

---

## Specifications

Update these once you have tested your build.

| Spec               | Value                                     |
| ------------------ | ----------------------------------------- |
| Input              | 12V DC from the ATX CPU (EPS) rail        |
| Adjustable output  | Replace with your buck converter's range  |
| Max output current | Replace with your buck converter's rating |
| Fixed rails        | 3.3V, 5V, 12V (from the breakout board)   |

---

## Troubleshooting

| Problem                        | Possible cause                                                    |
| ------------------------------ | ----------------------------------------------------------------- |
| PSU fan does not spin          | Breakout board switch is off, or the 24-pin is not fully seated   |
| No output voltage              | Check the buck converter input wiring and polarity                |
| Output voltage will not adjust | Check the buck converter's potentiometer and input voltage        |
| Case parts do not fit          | Check printer calibration and scale, or print with more tolerance |

---

## License

Add your license here, for example MIT for code or CC BY-SA for the 3D models.

## Disclaimer

This project involves mains-powered equipment and high-current DC. Build and use it at your own risk. The author is not responsible for damage or injury.
