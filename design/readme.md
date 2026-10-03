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

###  Miller Compensation Capacitor and Slew Rate Constraint

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

### Design of Differential Input Transistors (M1) and (M2)

| Parameter | Value |
|-----------|------:|
| Target GBW | 30 MHz |
| Miller capacitor \(C_C\) | 900 fF |
| Required \(g_m\) | ≈ 180 µS |
| Tail current \(I_5\) | 20 µA |
| Current per input transistor | ≈ 10 µA |
| \(\mu_n C_{ox}\) | 370 µA/V² |
| Calculated \((W/L)_{1,2}\) | ≈ 4.4 |
| Selected \((W/L)_{1,2}\) | ≈ 5 |

Thus, (M1) and (M2) are designed with an aspect ratio of approximately:


The following handwritten calculation shows the design of the differential input transistors.

<img width="606" height="482" alt="Screenshot 2026-10-04 002347" src="https://github.com/user-attachments/assets/6ee4d958-66bf-4248-bb10-330b259ceca0" />



### M3 and M4 — PMOS Current-Mirror Load

| Parameter | Value |
|---|---:|
| \(V_{DD}\) | 1.8 V |
| \(ICMR(+)\) | 1.6 V |
| \(|V_{t3,\max}|\) | 0.45 V |
| \(|V_{t1,\min}|\) | 0.40 V |
| \(\mu_p C_{ox}\) | 56 µA/V² |
| Calculated \((W/L)_{3,4}\) | 15.87 |
| **Selected \((W/L)_{3,4}\)** | **16** |


<img width="645" height="531" alt="image" src="https://github.com/user-attachments/assets/d39a36a7-f1e0-401a-b5d4-2a087b902229" />


### M5 and M8 — NMOS Current-Source / Bias Transistors

| Parameter | Value |
|---|---:|
| \(ICMR(-)\) | 0.8 V |
| \(|V_{t1,\max}|\) | 0.63 V |
| \(V_{DS,sat}\) | ≥ 70 mV |
| \(\mu_n C_{ox}\) | 370 µA/V² |
| \(W/L\) of M1/M2 | 5 |
| Current \(I_5=I_8\) | 20 µA |
| Calculated \((W/L)_{5,8}\) | ≈ 22 |
| **Selected \((W/L)_{5,8}\)** | **22** |



<img width="637" height="530" alt="image" src="https://github.com/user-attachments/assets/b8cd4a99-6561-44c7-bfb1-32cf4a262a72" />



### M6 — Second-Stage PMOS Transistor

The second-stage transconductance is selected to be approximately ten times the input-stage transconductance:

\[
g_{m6}\geq10g_{m1}
\]

| Parameter | Value |
|---|---:|
| \(g_{m1}\) | ≈ 180 µS |
| Target \(g_{m6}\) | ≈ 2 mS |
| \(\mu_p C_{ox}\) | 56 µA/V² |
| \((W/L)_4\) | 16 |
| \(I_4\) | 10 µA |
| Calculated \((W/L)_6\) | ≈ 215 |
| **Selected \((W/L)_6\)** | **215** |


<img width="612" height="552" alt="image" src="https://github.com/user-attachments/assets/de8a9d08-5b71-4894-bcbb-b3fefdb52030" />


### M7 — Second-Stage NMOS Current-Source Load

The current through M7 is chosen to match the required second-stage current.

| Parameter | Value |
|---|---:|
| \(g_{m6}\) | ≈ 2000 µS |
| \(g_{m7}\) | ≈ 150 µS |
| \(I_6\) | ≈ 133 µA |
| \(I_5\) | 20 µA |
| \((W/L)_5\) | 22 |
| Calculated \((W/L)_7\) | ≈ 146.6 |
| **Selected \((W/L)_7\)** | **147** |


<img width="867" height="667" alt="image" src="https://github.com/user-attachments/assets/78c9bbcd-3d83-4887-a0b7-95689012dcc9" />
