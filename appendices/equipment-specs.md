# Equipment Specifications Reference

## A. Flip-Chip Bump Printing Equipment

### A.1: ASMPT Datapace 300 (Solder Paste Printing)

| Specification | Value | Unit | Notes |
|---|---|---|---|
| **Throughput** | 1,200 | bumps/minute | Production speed |
| **Bump pitch** | 55-40 | μm | Ultra-fine pitch capable |
| **Height uniformity** | ±2 | μm | Cpk 1.8 (industry-leading) |
| **Printing speed** | 10-50 | mm/s | Adjustable squeegee speed |
| **Squeegee pressure** | 100-300 | grams | Closed-loop feedback controlled |
| **Solder paste compatibility** | SAC305, SAC387 | — | Lead-free alloys |
| **Substrate size** | Up to 300×300 | mm | Supports multiple formats |
| **MTBF (Mean Time Between Failure)** | >3,000 | hours | ~4 months continuous operation |
| **Uptime** | 96-98% | % | Scheduled maintenance 2-4%/year |
| **Equipment cost** | 2-3 | $M | USD millions |
| **Annual service cost** | 0.5-0.8 | $M | Maintenance + consumables |

---

### A.2: ASML/Canon Reflow Oven (Convection)

| Specification | Value | Unit | Notes |
|---|---|---|---|
| **Zones** | 11 | zones | Independent temperature control |
| **Zone stability** | ±1.5 | °C | Per-zone temperature control |
| **Board uniformity** | ±3 | °C | Across full 300mm board |
| **Peak temp range** | 240-260 | °C | Adjustable for process |
| **Dwell time** | 10-30 | seconds | Time at peak temperature |
| **Cooling rate** | 0.5-4 | °C/s | Adjustable during cooling phase |
| **Nitrogen supply** | 50-200 | L/min | Inert atmosphere for low-oxidation reflow |
| **Conveyor speed** | 0.3-1.5 | m/minute | Process speed adjustment |
| **Equipment cost** | 1.5-2.5 | $M | USD millions |
| **Annual operating cost** | 0.2-0.4 | $M | Nitrogen, maintenance, electricity |

---

### A.3: Underfill Dispensing System

| Specification | Value | Unit | Notes |
|---|---|---|---|
| **Dispense method** | Jetting / needle | — | Precision placement |
| **Viscosity range** | 100-5,000 | cP | Centipoise (process-dependent) |
| **Temperature control** | ±2 | °C | Viscosity compensation |
| **Dispense accuracy** | ±20 | μm | Placement precision |
| **Cure profile** | 80-150 | °C | Integration with reflow oven |
| **Cure time** | 1-10 | hours | Process dependent |
| **Void content** | <1 | % | Target specification |
| **Standby** | Nitrogen purge | — | Prevents hardening in nozzle |
| **Equipment cost** | 0.5-1.5 | $M | USD millions |

---

## B. Wafer Bonding Equipment

### B.1: Amkly Hybrid Bonding System

| Specification | Value | Unit | Notes |
|---|---|---|---|
| **Bonding temperature** | 200-300 | °C | Process dependent |
| **Temperature uniformity** | ±1.5 | °C | Critical for stress control |
| **Contact pressure** | 1-5 | MPa | Uniform across wafer ±3% |
| **Vacuum chamber** | <0.1 | Pa | Base pressure (void prevention) |
| **Bonding force** | 10-100 | kN | Mechanical pressing |
| **Wafer size** | 300 | mm | Standard fab size |
| **Alignment tolerance** | ±2 | μm | Die-to-die overlay |
| **Bond strength (fracture energy)** | 2-5 | J/m² | After anneal; breakage test |
| **MTBF** | 2,500 | hours | Equipment reliability |
| **Uptime** | 94-96 | % | Scheduled maintenance 4-6%/year |
| **Equipment cost** | 2-3.5 | $M | USD millions |
| **Annual service cost** | 0.4-0.7 | $M | Maintenance, spare parts |

**Process steps:**
1. Load wafers into vacuum chamber
2. Align die-to-die (±2 μm overlay)
3. Contact under 1-5 MPa pressure at 200-300°C
4. Hold for 1-4 hours (bond formation)
5. Cool slowly (0.5-2°C/min) to room temperature
6. Unload bonded pair

---

### B.2: Suss MicroTec Fusion Bonding System

| Specification | Value | Unit | Notes |
|---|---|---|---|
| **Bonding temperature** | 800-1100 | °C | High-temp Si-Si fusion |
| **Pressure** | 1-10 | MPa | Contact pressure |
| **Vacuum** | 1-10 | Pa | Atmospheric pressure acceptable |
| **Ramp rate** | 5-10 | °C/min | Temperature ramp |
| **Hold time** | 2-4 | hours | At peak temperature |
| **Cool rate** | 5-10 | °C/min | Faster cooling than hybrid |
| **Bond strength** | >1 | J/m² | Mechanical strength after anneal |
| **Equipment cost** | 1.5-2.5 | $M | USD millions |

**Advantages over hybrid bonding:**
- Simpler wafer cleaning (RCA only, no metal patterning)
- Lower equipment cost (no vacuum chamber critical)
- **Disadvantage:** Higher temperature (~1100°C) incompatible with metal interconnect; used for memory stacking, not chiplets

---

## C. 3D Assembly & Testing Equipment

### C.1: KLA Metrology System (Defect Inspection)

| Specification | Value | Unit | Notes |
|---|---|---|---|
| **Detection capability** | 5-10 | μm | Minimum defect size detectable |
| **Throughput** | 20-50 | wafers/hour | Production speed |
| **Imaging method** | Optical + AI | — | Machine learning defect classification |
| **Defect types** | Void, bridge, delamination | — | Classifies root cause |
| **False positive rate** | <5 | % | Accuracy of classification |
| **Equipment cost** | 1-2 | $M | USD millions |
| **Uptime** | 95-97 | % | High reliability |

---

### C.2: Kulicke & Soffa Wire Bonding System

| Specification | Value | Unit | Notes |
|---|---|---|---|
| **Wire diameter** | 25-50 | μm | Gold, copper, or silver |
| **Bonding speed** | 10-15 | bonds/second | Production throughput |
| **Loop height** | ±5 | μm | Uniformity control |
| **First pass yield** | 95-98 | % | Good bond probability |
| **Bond force** | 5-50 | grams | Ultrasonic power + downforce |
| **Equipment cost** | 1-2 | $M | USD millions |
| **Process capability** | Cpk 1.0-1.2 | — | Legacy technology (lower precision) |

**Note:** Wire bonding is declining technology; included for reference only. See Chapter 7 for market analysis.

---

## D. Thermal Management Equipment & Materials

### D.1: Thermal Interface Material (TIM) Properties

| Material Type | κ (W/m·K) | Modulus (GPa) | CTE (ppm/K) | Reliability | Cost/chip |
|---|---|---|---|---|---|
| **Silicone grease** | 1-3 | 0.001 | — | Fair | $0.05 |
| **Graphite film** | 5-10 | 0.1 | 20-30 | Good | $0.20 |
| **Boron nitride epoxy** | 15-25 | 2-5 | 15-20 | Good | $0.50-1.50 |
| **Aluminum nitride** | 20-30 | 3-8 | 4-6 | Excellent | $1.50-3.00 |
| **Liquid metal** | 50-80 | — | — | Risky (leakage) | $5-10 |

---

### D.2: Thermal Management Equipment

| Equipment Type | Supplier | Specification | Cost |
|---|---|---|---|
| **Cold plate (liquid)** | Boyd, Aavid | μm channel height: 500-2000 | $100K-500K |
| **Underfill curing oven** | Ersa, BTU | 11-zone, ±2°C | $1-2M |
| **Thermal profile monitoring** | FLIR, Fluke | ±0.5°C accuracy sensors | $50-200K |
| **Pressure control system** | SMC, Festo | ±0.1 MPa uniformity | $200-400K |

---

## E. Process Control & Feedback Systems

### E.1: Machine Vision Inspection (ASMPT Integration)

| Specification | Value | Unit | Notes |
|---|---|---|---|
| **Resolution** | 2-5 | μm/pixel | Optical magnification ~10-20x |
| **FOV (Field of View)** | 10-30 | mm | Per image capture |
| **Frame rate** | 30-60 | fps | Real-time inspection |
| **Defect detection** | Bump height, solder bridges | — | AI-powered classification |
| **Feedback loop** | Real-time to print system | — | Adaptive height control |
| **False negative rate** | <1 | % | Critical for yield |
| **Inspection time** | <2 | seconds/die | Production speed requirement |

---

### E.2: Solder Paste Characterization

| Property | Specification | Measurement |
|---|---|---|
| **Particle size** | 20-35 | μm (±5% distribution) |
| **Sphericity** | >90 | % round particles |
| **Flux content** | 10-15 | % by weight |
| **Viscosity** | 800-1200 | cP @ 25°C (varies with temp) |
| **Slump resistance** | <1 | mm (gravity sag during storage) |
| **Tack time** | 4-8 | hours (workable time) |
| **Shelf life** | 3-6 | months (with refrigeration) |

---

## F. Specification Summary Table

| Equipment Category | Leader | Market Share | Est. Annual Revenue | ROIC |
|---|---|---|---|---|
| **Flip-chip bumping** | ASMPT | 45-50% | $800M-$1B | 35-40% |
| **Wafer bonding** | Amkly | 40-50% | $600M-$800M | 32-38% |
| **3D assembly** | ASMPT | 40-45% | $400M-$500M | 30-35% |
| **Metrology/Inspection** | KLA | 35-40% | $1.5B-$2B | 28-35% |
| **Wire bonding** | K&S | 50-55% | $400M-$500M | 20-25% |

---

## References & Standards

- **SEMI Standard E35:** Guide for Characterization of Semiconductor Wafer Warpage
- **SEMI Standard M1:** General Requirements for Semiconductor Equipment
- **IPC-9701:** Performance Test Methods for Area Array Solder Interconnections
- **JEDEC Standard JC-45.3:** Wafer Bond Strength Methodology
- **ISO/IEC 61340-5-1:** Protection of Electronic Devices from Electrostatic Phenomena

---

**Note:** Specifications are approximate and based on 2024 equipment. Consult actual manufacturers for current datasheets and capabilities. Equipment costs vary significantly by customization, geography, and volume commitments.
