# CMOS Operational Amplifier Design Using Cadence Virtuoso

## Design Specifications

The Op-Amp was designed using the **GPDK 180 nm CMOS technology** in Cadence Virtuoso.

The target specifications are listed below:

| Parameter | Specification |
|-----------|---------------|
| Technology | GPDK 180 nm |
| Supply Voltage, \(V_{DD}\) | 1.8 V |
| DC Gain, \(A_v\) | 55 dB |
| Gain-Bandwidth Product (GBW) | 30 MHz |
| Slew Rate | 22 V/µs |
| Phase Margin (PM) | ≥ 60° |
| Positive ICMR | ≥ 1.6 V |
| Negative ICMR | ≤ 0.6 V |
| Load Capacitance, \(C_L\) | 1.5 pF |
| (u_n Cox) | 370 µA/V² |
| (u_p Cox) | 56 µA/V² |


A two-stage Miller-compensated CMOS operational amplifier consisting of an NMOS differential input pair with a PMOS current-mirror active load, followed by a PMOS common-source gain stage with an NMOS current-source load. An NMOS bias circuit establishes the current-source bias, while a Miller compensation capacitor provides frequency compensation and stability for the specified capacitive load.

<img width="902" height="786" alt="image" src="https://github.com/user-attachments/assets/5ffce14d-5367-47d7-875c-944bd6c3e4ae" />



## Design Methodology

### 1. Miller Compensation Capacitor and Slew Rate Constraint

The initial design parameters obtained from the compensation and slew-rate requirements are:

| Parameter | Designed Value |
|-----------|---------------:|
| Load capacitance \(C_L\) | 1.5 pF |
| Minimum \(C_C\) | 0.33 pF |
| Selected \(C_C\) | 900 fF |
| Required slew rate | 22 V/µs |
| Calculated tail current \(I_5\) | 19.8 µA |
| Selected tail current \(I_5\) | ≈ 20 µA |


<img width="820" height="647" alt="image" src="https://github.com/user-attachments/assets/a159b059-be1e-4b06-96ea-cde53b9b1672" />



