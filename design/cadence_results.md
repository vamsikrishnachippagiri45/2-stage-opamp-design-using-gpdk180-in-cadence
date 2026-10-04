
## Cadence Virtuoso Implementation

<img width="1415" height="576" alt="Screenshot 2026-10-03 232337" src="https://github.com/user-attachments/assets/97294bed-ea53-4966-adc2-8bc0ca88c1cc" />


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


## Simulation Results

The designed CMOS Op-Amp was simulated in Cadence Virtuoso using AC analysis to evaluate its open-loop gain, unity-gain bandwidth, and phase margin.

### AC Analysis Results

From the simulated frequency response:

- The low-frequency open-loop gain is approximately **52.95 dB**.
- The gain crosses **0 dB** at approximately **24.57 MHz**.
- The phase at the unity-gain frequency is approximately **81.01°**.
- Therefore, the simulated phase margin is approximately **81°**.

| Parameter | Target | Simulated Result |
|-----------|-------:|-----------------:|
| DC Gain | 55 dB | **52.95 dB** |
| Unity-Gain Bandwidth | 30 MHz | **24.57 MHz** |
| Phase Margin | ≥ 60° | **≈ 81°** |

### Gain Response

The simulated low-frequency gain is:

\[
A_v \approx 52.95\,dB
\]

The gain decreases with increasing frequency due to the dominant-pole behavior introduced by the Miller compensation.

### Unity-Gain Bandwidth

The magnitude response crosses 0 dB at approximately:

\[
\boxed{f_{UGB}\approx24.57\,MHz}
\]

This represents the simulated unity-gain bandwidth of the Op-Amp.

### Phase Margin

At the unity-gain frequency, the phase is approximately:

\[
\phi(f_{UGB})\approx81.01^\circ
\]

The phase margin is therefore approximately:

\[
\boxed{PM\approx81^\circ}
\]

Since:

\[
PM > 60^\circ
\]

the design satisfies the specified phase-margin requirement.

### Cadence AC Simulation

#### Gain Response

<img width="1733" height="802" alt="Screenshot 2026-10-03 232056" src="https://github.com/user-attachments/assets/38bbe15e-a51f-4757-a2c3-825ab04f71a6" />


#### Phase Response

<img width="1735" height="800" alt="Screenshot 2026-10-03 232025" src="https://github.com/user-attachments/assets/9b670cdd-1ea9-44a4-92db-d9f1a889bcc6" />


#### Gain and Phase at Unity-Gain Frequency

<img width="1542" height="786" alt="Screenshot 2026-10-03 231909" src="https://github.com/user-attachments/assets/8d7e5e8a-be23-44bc-be84-c403b319f152" />
