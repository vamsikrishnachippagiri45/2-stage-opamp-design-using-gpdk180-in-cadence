
## Cadence Virtuoso Implementation

The designed two-stage CMOS Op-Amp was implemented at transistor level using **Cadence Virtuoso** with the **GPDK 180 nm CMOS technology**.

The schematic consists of the following devices:

| Device | Function | \(W/L\) |
|--------|----------|--------:|
| M1 | NMOS differential input transistor | 5 |
| M2 | NMOS differential input transistor | 5 |
| M3 | PMOS current-mirror load | 16 |
| M4 | PMOS current-mirror load | 16 |
| M5 | NMOS tail-current source | 22 |
| M6 | PMOS second-stage common-source transistor | 215 |
| M7 | NMOS second-stage current-source load | 147 |
| M8 | NMOS bias/reference transistor | 22 |

The main circuit parameters used in the schematic are:

| Parameter | Value |
|-----------|------:|
| Technology | GPDK 180 nm |
| Supply voltage \(V_{DD}\) | 1.8 V |
| Bias current \(I_{DC}\) | 20 µA |
| Miller compensation capacitor \(C_C\) | 900 fF |
| Load capacitance \(C_L\) | 1.5 pF |
