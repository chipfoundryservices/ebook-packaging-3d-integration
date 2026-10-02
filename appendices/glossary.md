# Glossary: Advanced Packaging & 3D Integration

## A

**ALE (Atomic Layer Etch):** Self-limiting etch process that removes material one atomic layer at a time, achieving sub-nanometer precision without lattice damage. See Chapter 5 of *Etch: The Sub-Nanometer Chisel*.

**Aspect Ratio:** The ratio of vertical height to horizontal width in a trench or via structure. High aspect ratio (>100:1) is challenging for etch and assembly processes.

**ASMPT (ASM Pacific Technology):** Leading flip-chip packaging equipment supplier. Manufactures Datapace systems for bump printing, reflow, underfill, and inspection. ~45-50% market share in flip-chip bumping. See Chapter 7.

## B

**Backside Power Delivery Network (bPDN):** Advanced power delivery architecture where power is routed through the back of the die rather than the front metal layers, reducing voltage drop and enabling higher current delivery at lower resistance.

**Barrier Layer (in TSVs):** Thin layer (TaN, Ti, or TiN) deposited before copper electroplating to prevent copper diffusion into adjacent materials. Typical thickness: 50-100 nm.

**Bindline:** See TIM (Thermal Interface Material).

**Bohm Velocity:** In plasma physics, the minimum velocity at which ions can exit the plasma sheath. Critical for ion energy distribution calculations in RIE chambers. See Chapter 2 of *Etch*.

**Bonding (wafer-to-wafer):** Process of physically joining two wafers through fusion bonding, oxide bonding, or hybrid bonding. See Chapter 3.

**Boron Nitride (BN):** High-thermal-conductivity ceramic material used in advanced TIM formulations. Thermal conductivity 15-25 W/m·K.

**Bump (Solder Bump):** Spherical or near-spherical ball of solder deposited on die pads for flip-chip interconnection. See Chapter 2.

## C

**Capex (Capital Expenditure):** Large capital investment in equipment or infrastructure. In semiconductors, typically refers to fab, lithography, etch, or packaging equipment purchases. See Chapter 8 for capex cycle dynamics.

**CCP (Capacitively Coupled Plasma):** Plasma source in which RF energy is applied to electrode plates facing the plasma chamber. Lower plasma density than ICP. See Chapter 2 of *Etch*.

**Chiplet:** Small silicon die (50-200 mm²) manufactured at a specific process node and integrated with other chiplets into a single package. See Chapter 1.

**CoWoS (Chip-on-Wafer-on-Substrate):** TSMC's advanced 2.5D/3D stacking technology combining chiplets with HBM memory using hybrid bonding and TSVs. See Chapter 5.

**CTE (Coefficient of Thermal Expansion):** Measure of how much a material expands per unit temperature change. Units: ppm/K (parts per million per Kelvin).

**Copper Electromigration:** Atomic diffusion of copper under high current density and elevated temperature, leading to void nucleation and open circuits. See Chapter 6.

**Cpk (Process Capability Index):** Statistical measure of manufacturing process precision. Cpk = 1.67 means process is capable; Cpk = 1.8+ is excellent; Cpk = 1.2 is marginal. ASMPT achieves Cpk 1.8; competitors typically 1.2.

## D

**Datapace:** ASMPT's flagship integrated flip-chip packaging platform. Combines bump printing, reflow, underfill, and inspection. See Chapter 7.

**Defect (in packaging):** Any departure from specification: void in underfill, solder bridge, bump height out of tolerance, delamination, etc.

**Debye Length:** Characteristic distance over which electric fields are shielded by surrounding charges in plasma. Typical value in semiconductor processing plasmas: 1-100 micrometers.

**Die Attach:** Process of bonding a bare die (chip) to the substrate or package base using adhesive, solder, or direct bonding.

## E

**Electromigration (EM):** Atomic movement in metals under high current density, driven by electron wind force. Causes device failure by creating voids or hillocks. See Chapter 2 and Chapter 6.

**EMIB (Embedded Multi-die Interconnect Bridge):** Intel's proprietary chiplet interconnect technology using micro-bump substrates. See Chapter 4.

**Epoxy (in underfill):** Organic polymer resin used as base material for underfill formulations. Provides mechanical support and stress relief for solder bumps.

## F

**Flip-Chip:** Die attachment method where die pads are bonded directly to substrate pads via solder bumps, with the die face down. See Chapter 2.

**Flux (in solder paste):** Organic solvent component of solder paste that removes oxide layers during reflow and enables wetting. Comprises 10-15% by weight of solder paste.

**Fluorocarbon (in etch chemistry):** Molecular compounds containing fluorine and carbon (e.g., CF₄, C₄F₈, CHF₃) used in RIE processes to etch silicon and related materials. See Chapter 3 of *Etch*.

**Fusion Bonding:** Direct bonding of silicon wafers through van der Waals forces and high-temperature diffusion, without intermediate adhesive. See Chapter 3.

## G

**GAAFET (Gate-All-Around FET):** Advanced transistor architecture where gate surrounds channel on all sides, enabling better electrostatic control at sub-3nm nodes. Requires selective etch of SiGe channels. See Chapter 6 of *Etch*.

**Gross Margin:** Gross profit as percentage of revenue. In semiconductor equipment: typically 45-50% for hardware, 60-70% for service.

## H

**HBM (High-Bandwidth Memory):** Advanced memory technology with 1000+ GB/s bandwidth, achieved through 3D stacking and hybrid bonding with compute dies. See Chapter 5.

**Heat Capacity (C):** Amount of energy required to raise temperature of material by 1°C. Units: J/g·K or cal/g·°C.

**Henkel:** Major supplier of underfill and TIM materials for semiconductor packaging. ~30-40% market share in advanced underfill.

**Hybrid Bonding:** Simultaneous bonding of metal (copper) and dielectric (SiO₂) layers between two wafers. See Chapter 3.

## I

**ICP (Inductively Coupled Plasma):** Plasma source in which RF energy couples through a coil above the chamber, creating high plasma density. Used in advanced RIE and etch systems. See Chapter 2 of *Etch*.

**Indium Corporation:** Specialty materials supplier for solder alloys, thermal pastes, and flux formulations for advanced packaging.

**Interconnect (chiplet):** Signal path connecting two chiplets, typically through micro-bumps, bonded pads, or substrate traces. See Chapter 4.

## J

**Junction Temperature (Tj):** Operating temperature of semiconductor die during use. Limited by reliability constraints; typically <120-125°C maximum.

## K

**KLA Corporation:** Leading supplier of process control, metrology, and inspection equipment for semiconductor manufacturing. ~40% market share in advanced inspection.

**Kirkendall Void:** Void formed at interface between two metals due to differential diffusion rates. Affects reliability of bonded interfaces and solder joints.

## L

**Lam Research:** Leading supplier of plasma etch and deposition equipment. Dominates advanced RIE market with Kiyo and Sensei platform systems. See Chapter 7 of *Etch*.

**Latency:** Signal propagation time from source to destination, typically measured in nanoseconds. Critical for chiplet interconnect performance. See Chapter 4.

**Liquid Metal (TIM):** Advanced thermal interface material with exceptional thermal conductivity (50-80 W/m·K) but reliability concerns (potential leakage).

## M

**Machine Vision (in packaging):** Optical inspection system that images printed bumps, bonded areas, or underfill to detect defects and measure geometry.

**Martensite:** Phase of steel or other materials with high hardness and low ductility, formed during rapid cooling. Relevant to thermal cycling-induced cracking.

**Microelectronic-Grade Materials:** Specialty chemicals and materials formulated to semiconductor purity standards (ppb-level contaminants). Required for advanced packaging.

**Micro-Bump:** Solder bump with diameter <50 micrometers, used in fine-pitch flip-chip and chiplet interconnects. See Chapter 2.

**MTTF (Mean Time To Failure):** Average time a component operates before failure. Calculated from Black's equation for electromigration or Coffin-Manson for thermal cycling.

## N

**NAND Flash:** Nonvolatile memory technology storing charge in floating gates. Dominant memory type for data storage. See Chapter 6 for 3D NAND stacking.

**Nanosheet:** Ultra-thin silicon layer (5-10 nm) used as channel material in advanced FET architectures. Selective etch of SiGe beneath nanosheet is critical for GAAFET fabrication.

## O

**Onto Innovation:** Packaging and semiconductor process control equipment supplier. ~10-15% market share in advanced metrology and yield optimization.

**Oxidation:** Formation of oxide layer on material surface through exposure to oxygen. Can degrade bonding and etch performance if not controlled.

## P

**Passivation (in etch):** Deposition of thin polymer layer on trench sidewalls to protect them from further etching. Critical for high-aspect-ratio etch and selectivity control. See Chapter 3 of *Etch*.

**Peel Strength:** Mechanical force required to separate two bonded layers, measured in N/mm or pli (pounds per linear inch). Typically 5-20 N/mm for advanced packaging bonds.

**Polyimide:** High-temperature organic polymer used in advanced substrates and dielectrics. Better thermal stability than standard epoxy.

**Process Capability (Cpk):** See Cpk.

**Pulsed DC (in electroplating):** Electroplating technique using alternating current pulses rather than continuous current, enabling better control of plating uniformity and reduced void formation.

## R

**Rayleigh Criterion:** Optical resolution limit defined as wavelength divided by 2×NA (numerical aperture). Fundamental limit for optical lithography. See Chapter 3 of *Lithography*.

**RIE (Reactive Ion Etching):** Plasma-based etching process combining ion sputtering with chemical etch reactions. See Chapter 2 of *Etch*.

**ROIC (Return on Invested Capital):** Net profit divided by capital employed. Measure of business efficiency. Equipment suppliers: 35-42%; foundries: 15-22%.

## S

**SAC (Solder Alloy Composition):** Lead-free solder alloy, typically Sn/Ag/Cu at 96/3/1 weight ratio. Melting point ~217°C. See Chapter 2.

**Selectivity (in etch):** Ratio of etch rate for target material to etch rate for masking material. High selectivity prevents undercut and enables precise pattern transfer. See Chapter 3 of *Etch*.

**Service Revenue:** Recurring revenue from equipment maintenance, consumables, process support, and upgrade kits. 30-40% of initial equipment cost annually; 60-70% gross margin.

**SiGe (Silicon-Germanium):** Binary alloy of silicon and germanium used for channel or source/drain materials in advanced FETs. Selective etch of SiGe beneath Si/SiGe nanosheets is critical. See Chapter 6 of *Etch*.

**Signal Integrity:** Quality of analog or digital signals during transmission through interconnects. Degraded by impedance mismatch, crosstalk, and reflections.

**Squeegee (in printing):** Polyurethane or plastic blade used to force solder paste through stencil apertures during flip-chip printing.

**Stencil Printing:** Process of applying solder paste through laser-cut stencil onto substrate pads. See Chapter 2.

**Stress-Induced Void (SIV):** Void formation in metal films due to mechanical stress, even without current flow. Relevant to TSV reliability under CTE mismatch stress.

## T

**Thermal Conductivity (κ):** Rate of heat flow through material per unit temperature gradient. Units: W/m·K. Higher κ = better heat dissipation.

**Thermal Cycling:** Repeated temperature swings (e.g., −40°C to +125°C) that induce mechanical stress and fatigue in packaging materials and solder joints.

**TIM (Thermal Interface Material):** Material layer between die and heatspreader providing thermal conductivity path. Typical κ = 2-80 W/m·K depending on formulation. See Chapter 5.

**TSV (Through-Silicon Via):** Vertical copper-filled conductor passing through entire silicon wafer, enabling 3D interconnection and heat extraction in stacked die or 3D NAND. See Chapter 6.

**Tungsten (W):** Refractory metal used for interconnect plugs and contacts. High melting point (3,422°C), high density, low thermal expansion.

## U

**UCIe (Universal Chiplet Interconnect Express):** Open-source, standardized chiplet interconnect standard supporting 32 Gb/s per lane with latency <5 ns. See Chapter 4.

**Underfill:** Low-viscosity epoxy resin dispensed under flip-chip die to provide mechanical support, stress relief, and environmental protection for solder bumps. See Chapter 2.

## V

**Via (through-substrate):** Conductive hole through substrate or PCB enabling electrical connection between layers. See TSV for through-silicon versions.

**Void (in solder/underfill):** Air pocket or unfilled region in solder joint or underfill material. Reduces mechanical strength and thermal conductivity, degrading reliability.

## W

**Wafer Bonding:** Process of joining two wafers using physical forces (pressure, temperature) and chemical bonding (oxide bonding, metal diffusion). See Chapter 3.

**Warpage:** Distortion of wafer from flat due to residual stress, CTE mismatch, or mechanical deformation. See Chapter 6.

**Wire Bonding:** Legacy interconnect method using ultrasonic or thermal energy to bond thin gold/copper wires from die pads to substrate pads. See Chapter 7 for market analysis.

## Y

**Yield (in manufacturing):** Percentage of manufactured parts that meet specifications. High yield = lower cost per working unit. See Chapter 6 for yield learning curves in 3D NAND.

## Z

**Young's Modulus (E):** Stiffness of material under elastic deformation. Units: GPa. Silicon E ≈ 130 GPa; solder E ≈ 30-50 GPa; underfill E ≈ 3-10 GPa.

---

**Cross-References:**
- For plasma physics terms: See *Etch: The Sub-Nanometer Chisel* (Book 4)
- For lithography terms: See *Lithography: Photomasks, Optics, and the EUV Monopoly* (Book 3)
- For foundry economics: See *Foundry: Fab Economics and the Manufacturing Paradox* (Book 2)
- For device physics: See *Chip: Crystalline Silicon and the Industrial Moat* (Book 1)
