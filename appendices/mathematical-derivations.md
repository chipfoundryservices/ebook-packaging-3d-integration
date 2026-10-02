# Mathematical Derivations: Advanced Packaging & 3D Integration

## A. Thermal Resistance & Heat Transfer

### A.1: Thermal Resistance Calculation

For a material layer with known thermal conductivity, cross-sectional area, and thickness:

$$R_{\text{thermal}} = \frac{d}{\kappa \cdot A}$$

**Variables:**
- $R_{\text{thermal}}$ = thermal resistance (K/W)
- $d$ = material thickness (meters)
- $\kappa$ = thermal conductivity (W/m·K)
- $A$ = cross-sectional area (m²)

**Application (Chapter 5):** TIM layer with κ = 25 W/m·K, thickness d = 50 μm, area = 100 mm²:

$$R_{\text{TIM}} = \frac{50 \times 10^{-6} \text{ m}}{25 \text{ W/m·K} \times (0.01 \text{ m})^2} = \frac{50 \times 10^{-6}}{2.5 \times 10^{-3}} = 0.02 \text{ K/W}$$

---

### A.2: Series Thermal Resistance (Multiple Layers)

Total thermal resistance for layers in series:

$$R_{\text{total}} = R_1 + R_2 + R_3 + \ldots + R_n$$

**Example (Chapter 5):** 500W chip with multi-layer path:
- Die-to-substrate TIM: 0.02 K/W
- Substrate thermal resistance: 0.08 K/W
- Substrate-to-lid bond: 0.05 K/W
- Lid-to-heatsink: 0.03 K/W
- Heatsink-to-air: 0.02 K/W

$$R_{\text{total}} = 0.02 + 0.08 + 0.05 + 0.03 + 0.02 = 0.20 \text{ K/W}$$

**Junction temperature:**
$$T_j = T_{\text{ambient}} + P \times R_{\text{total}} = 25°C + 500W \times 0.20 \text{ K/W} = 125°C$$

---

## B. Electromigration & Reliability

### B.1: Black's Equation (Electromigration MTTF)

Mean time to failure due to electromigration:

$$\text{MTTF} = A \cdot J^{-n} \cdot \exp\left(\frac{E_a}{k_B T}\right)$$

**Variables:**
- $J$ = current density (A/cm²)
- $n$ ≈ 2 (exponent for solder/copper)
- $E_a$ = activation energy (eV), typically 0.6-0.75 eV for Cu in solder
- $k_B$ = Boltzmann constant = 8.617 × 10⁻⁵ eV/K
- $T$ = absolute temperature (Kelvin)
- $A$ = pre-exponential constant (material-dependent)

**Application (Chapter 2):** Solder bump, 10 A current, 2.5 μm radius, 85°C:

$$J = \frac{I}{A} = \frac{10 \text{ A}}{\pi (2.5 \times 10^{-3})^2} = \frac{10}{1.96 \times 10^{-5}} = 510,000 \text{ A/cm}^2$$

At 85°C (358 K):
$$\text{MTTF} = A \cdot (510,000)^{-2} \cdot \exp\left(\frac{0.65}{8.617 \times 10^{-5} \times 358}\right)$$

$$\text{MTTF} = A \cdot 3.85 \times 10^{-12} \cdot \exp(21.2) ≈ 10^6 \text{ hours}$$

At 125°C (398 K):
$$\text{MTTF} = A \cdot (510,000)^{-2} \cdot \exp\left(\frac{0.65}{8.617 \times 10^{-5} \times 398}\right) ≈ 10^4 \text{ hours}$$

**Result:** 40°C temperature increase reduces MTTF by 100x.

---

### B.2: Temperature Dependence of MTTF

MTTF has exponential dependence on temperature. For a 10°C temperature increase:

$$\frac{\text{MTTF}_2}{\text{MTTF}_1} = \exp\left(\frac{E_a}{k_B} \left(\frac{1}{T_1} - \frac{1}{T_2}\right)\right)$$

**Example:** Comparing 85°C vs. 95°C:

$$\frac{\text{MTTF}_{95°C}}{\text{MTTF}_{85°C}} = \exp\left(\frac{0.65}{8.617 \times 10^{-5}} \left(\frac{1}{358} - \frac{1}{368}\right)\right)$$

$$= \exp(7540 \times 0.0000754) = \exp(0.568) ≈ 1.77$$

**Result:** 10°C temperature increase reduces MTTF by factor of ~1.77 (15% reduction per °C).

---

## C. Thermal Cycling & Fatigue

### C.1: Coffin-Manson Equation (Solder Fatigue)

Number of cycles to failure under thermal cycling:

$$N_f = C \cdot (\Delta \varepsilon)^{-m}$$

**Variables:**
- $N_f$ = number of cycles to failure
- $\Delta \varepsilon$ = strain range per cycle
- $m$ ≈ 1.5-2.0 (Coffin-Manson exponent for solder)
- $C$ = material constant (material and stress state dependent)

**Strain calculation:**

$$\Delta \varepsilon = \alpha_{\text{mismatch}} \cdot \Delta T$$

where $\alpha_{\text{mismatch}} = \alpha_{\text{solder}} - \alpha_{\text{substrate}}$

**Application (Chapter 5):** Thermal cycling −40°C to +125°C (ΔT = 165°C):

For SAC solder:
- $\alpha_{\text{solder}}$ = 24 ppm/K
- $\alpha_{\text{silicon}}$ = 2.6 ppm/K
- $\alpha_{\text{mismatch}}$ = 21.4 ppm/K

$$\Delta \varepsilon = 21.4 \times 10^{-6} \times 165 = 3.53 \times 10^{-3}$$

With $m$ = 1.8 and $C$ ≈ 10⁵ (typical for SAC solder):

$$N_f = 10^5 \times (3.53 \times 10^{-3})^{-1.8} = 10^5 \times (283)^{1.8} ≈ 10,000 \text{ cycles}$$

**Result:** Solder joint survives ~10,000 thermal cycles (27 years at 1 cycle/day).

---

### C.2: Arrhenius Model for Thermal Aging

Degradation rate increases exponentially with temperature:

$$A(t) = A_0 \cdot \exp\left(-\frac{E_a}{k_B T} \cdot t\right)$$

**Variables:**
- $A(t)$ = property at time $t$ (strength, modulus, etc.)
- $A_0$ = initial property
- $E_a$ = activation energy for degradation process
- $t$ = time (hours)

**Application (Chapter 5):** TIM material aging at 85°C vs. 125°C:

At 85°C (358 K), after 10 years (87,600 hours):
$$\frac{A(10yr)}{A_0} = \exp\left(-\frac{0.5 \text{ eV}}{8.617 \times 10^{-5} \times 358} \times 87,600\right) ≈ 0.75$$

At 125°C (398 K), after 10 years:
$$\frac{A(10yr)}{A_0} = \exp\left(-\frac{0.5 \text{ eV}}{8.617 \times 10^{-5} \times 398} \times 87,600\right) ≈ 0.35$$

**Result:** TIM loses 25% of property at 85°C over 10 years; loses 65% at 125°C (40°C = 3x faster degradation).

---

## D. Signal Integrity & Electrical

### D.1: Transmission Line Impedance

Characteristic impedance of interconnect transmission line:

$$Z_0 = \sqrt{\frac{L}{C}}$$

where $L$ = series inductance per unit length, $C$ = shunt capacitance per unit length

**For microstrip transmission line:**

$$Z_0 ≈ \frac{377}{\sqrt{\varepsilon_r}} \ln\left(\frac{4h}{d}\right)$$

**Variables:**
- $h$ = height above ground plane (μm)
- $d$ = trace width (μm)
- $\varepsilon_r$ = relative permittivity of dielectric

**Application (Chapter 4):** Micro-bump substrate routing:
- $h$ = 100 μm (trace height above ground)
- $d$ = 2 μm (trace width)
- $\varepsilon_r$ ≈ 4 (typical organic substrate)

$$Z_0 ≈ \frac{377}{\sqrt{4}} \ln\left(\frac{400}{2}\right) ≈ 188 \ln(200) ≈ 188 \times 5.3 ≈ 1000 \text{ Ω}$$

**Result:** Very high impedance (~1000 Ω) due to tight spacing. Impedance matching required for signal integrity.

---

### D.2: Propagation Delay (Transmission Line)

Signal propagation time through interconnect:

$$t_{\text{propagation}} = \frac{\text{length}}{v_p}$$

where $v_p = \frac{c}{\sqrt{\varepsilon_r}}$ = velocity of propagation

**Application (Chapter 4):** Chiplet interconnect (100 μm path, organic substrate):

$$v_p = \frac{3 \times 10^8 \text{ m/s}}{\sqrt{4}} = 1.5 \times 10^8 \text{ m/s}$$

$$t = \frac{100 \times 10^{-6} \text{ m}}{1.5 \times 10^8 \text{ m/s}} ≈ 0.67 \text{ ns}$$

**Result:** 100 μm interconnect introduces ~0.67 ns propagation delay.

---

## E. Wafer Warpage & Stress

### E.1: Wafer Warpage (Plate Bending Theory)

Maximum deflection of circular plate under uniform stress:

$$w = \frac{\sigma \cdot (1 - \nu^2)}{6E} \cdot \left(\frac{D}{2}\right)^2$$

where:
- $\sigma$ = biaxial stress (Pa)
- $\nu$ = Poisson's ratio (0.28 for Si)
- $E$ = Young's modulus (130 GPa for Si)
- $D$ = plate diameter (0.3 m for 300 mm wafer)

**Application (Chapter 6):** 150 MPa stress on 300 mm wafer:

$$w = \frac{150 \times 10^6 \times (1 - 0.28^2)}{6 \times 130 \times 10^9} \times (0.15)^2$$

$$w = \frac{150 \times 10^6 \times 0.92}{780 \times 10^9} \times 0.0225 ≈ 50 \text{ μm}$$

**Result:** 150 MPa stress causes ~50 μm bow across 300 mm wafer. Exceeds 3D NAND stack height (20-25 μm), causing delamination risk.

---

### E.2: Residual Stress from CTE Mismatch

Biaxial stress in composite material layer after cooling:

$$\sigma_{\text{residual}} = E_{\text{layer}} \times (\alpha_{\text{substrate}} - \alpha_{\text{layer}}) \times \Delta T$$

**Application (Chapter 6):** SiO₂ on Si after cooling 400°C:
- $E_{\text{SiO2}}$ = 70 GPa
- $\alpha_{\text{Si}}$ = 2.6 ppm/K
- $\alpha_{\text{SiO2}}$ = 0.5 ppm/K
- $\Delta T$ = 400°C

$$\sigma = 70 \times 10^9 \times (2.6 - 0.5) \times 10^{-6} \times 400$$

$$\sigma = 70 \times 10^9 \times 2.1 \times 10^{-6} \times 400 ≈ 59 \text{ MPa}$$

**Result:** 59 MPa tensile stress in SiO₂ layer. Multiple processing cycles can accumulate stress to 100-200 MPa, exceeding fracture strength (~100 MPa for thin SiO₂ films).

---

## F. Process Yield

### F.1: Binomial Yield Model

System yield with multiple independent failure modes:

$$Y_{\text{system}} = Y_1 \times Y_2 \times Y_3 \times \ldots \times Y_n$$

**Application (Chapter 6):** 3D NAND package yield:
- Chiplet 1 yield: 0.92
- Chiplet 2 yield: 0.88
- Bonding yield: 0.95
- Assembly yield: 0.97
- Test yield: 0.96

$$Y_{\text{system}} = 0.92 \times 0.88 \times 0.95 \times 0.97 \times 0.96 ≈ 0.73 = 73\%$$

**Result:** System yield is product of component yields. Single weak link (88%) pulls down entire system.

---

### F.2: Cpk to Yield Conversion

Process capability index relates to percentage of parts within specification:

$$\text{Yield} = 2 \times \Phi(C_{pk}) - 1$$

where $\Phi$ = cumulative normal distribution function

**Examples:**
- $C_{pk} = 1.0$ → Yield = 99.73% (2,700 ppm defect rate)
- $C_{pk} = 1.33$ → Yield = 99.95% (500 ppm defect rate)
- $C_{pk} = 1.67$ → Yield = 99.997% (30 ppm defect rate)
- $C_{pk} = 1.8$ → Yield = 99.9974% (13 ppm defect rate)

**Application (Chapter 2):** ASMPT bump printing (Cpk 1.8) vs. competitor (Cpk 1.2):
- ASMPT: 99.9974% → 13 bad bumps per million
- Competitor: 99.85% → 1,500 bad bumps per million
- For 10,000-bump package: ASMPT = 0.13 bad bumps; Competitor = 15 bad bumps
- System yield difference: ASMPT 98% vs. Competitor 85% (13% advantage)

---

## G. Capital Allocation Metrics

### G.1: ROIC (Return on Invested Capital)

$$\text{ROIC} = \frac{\text{NOPAT}}{\text{Invested Capital}}$$

where NOPAT = Net Operating Profit After Tax

**Application (Chapter 8):** ASMPT vs. TSMC:

**ASMPT:** Hardware + Service business
- NOPAT: $940M
- Invested Capital: $2.5B
- ROIC = $940M / $2.5B = 37.6%

**TSMC:** Pure foundry business
- NOPAT: $8.5B
- Invested Capital: $50B
- ROIC = $8.5B / $50B = 17%

**Result:** ASMPT ROIC (37.6%) is 2.2x higher than TSMC (17%) due to service moat and lower capex intensity.

---

## H. References & Further Reading

- Black, J.R. (1969). "Electromigration failure modes in aluminum metallization for semiconductor devices." *IEEE Transactions on Reliability*, R-18(4), 238-247.
- Coffin, L.F. (1954). "A study of the effects of cyclic thermal stresses on ductile metals." *Transactions of ASME*, 76(6), 931-950.
- SEMI Standard E35: Guide for Characterization of Semiconductor Wafer Warpage
- IPC-9701: Performance Test Methods for Area Array Solder Interconnections
- JEDEC Standard JC-45.3: Wafer Bond Strength Methodology
