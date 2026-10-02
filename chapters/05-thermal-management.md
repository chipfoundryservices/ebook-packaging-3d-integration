# Chapter 5: Thermal Management at Scale

## The Inversion: Why Thermal Failure Ends Chiplet Viability

When you integrate multiple chiplets into a single package, thermal density increases exponentially. A 500W AI accelerator dissipating power across 100mm² creates thermal conditions that passive air cooling cannot handle.

The catastrophic failures:

1. **Thermal throttling** — Junction temperature exceeds safe limits (120-125°C), forcing frequency/voltage reduction, losing 20-30% performance mid-workload
2. **Electromigration acceleration** — Temperature increases 40°C → MTTF (mean time to failure) decreases 100x, turning 10-year component into 1-month reliability disaster
3. **Thermal cycling fatigue** — Rapid temperature swings (boot, workload start, thermal shutdown) cause solder joint cracking and mechanical failure
4. **Bondline voiding** — Thermal stress at chiplet interfaces causes trapped gas expansion and delamination (combined with void nucleation from Chapter 3)
5. **Material degradation** — TIM (thermal interface material) cross-links and hardens over time; thermal conductivity decreases 30-40% over 5 years of operation

**The company that solves thermal management at the chiplet integration level controls the next decade of AI accelerator design.**

This is why NVIDIA spent billions optimizing thermal paths for H100. This is why TSMC's CoWoS (Chip-on-Wafer-on-Substrate) dominates AI packaging. This is why thermal materials suppliers (Dow, Henkel, Indium) command supply-chain pricing power.

---

## Part I: Thermal Interface Materials (TIMs)

### The Physics of Heat Transfer Through Bondlines

Heat flows from a high-temperature source (chiplet junction) through multiple resistive layers:

$$T_{\text{junction}} = T_{\text{ambient}} + P \cdot R_{\text{total}}$$

where $R_{\text{total}}$ is the sum of all thermal resistances:

$$R_{\text{total}} = R_{\text{die-to-substrate}} + R_{\text{substrate}} + R_{\text{substrate-to-lid}} + R_{\text{lid-to-heatsink}} + R_{\text{heatsink-to-air}}$$

For a 500W chip with ambient 25°C and max safe junction temperature 120°C:

$$120°C = 25°C + 500W \times R_{\text{total}}$$
$$R_{\text{total}} = \frac{95°C}{500W} = 0.19 \text{ K/W}$$

**This is extremely aggressive.** Typical packaging achieves R_total = 0.25-0.35 K/W. To hit 0.19 K/W requires:
- Die-to-substrate TIM layer: 0.02 K/W (not 0.05 K/W)
- Substrate thermal conductivity: copper-heavy design
- Liquid cooling integration (air cooling alone cannot achieve 0.19 K/W)

### TIM Materials & Thermal Conductivity

Thermal conductivity (κ) measures how quickly heat flows through material:

$$Q = \kappa \cdot A \cdot \frac{\Delta T}{d}$$

where:
- $Q$ = heat flow (watts)
- $\kappa$ = thermal conductivity (W/m·K)
- $A$ = cross-sectional area (m²)
- $\Delta T$ = temperature difference
- $d$ = material thickness (bondline thickness)

| TIM Material | κ (W/m·K) | Form Factor | Reliability | Cost ($/chip) | Status |
|---|---|---|---|---|---|
| **Air gap** | 0.026 | None | Poor (voids form) | $0 | Baseline only |
| **Silicone grease** | 1-3 | Paste, pump-able | Fair (pump-out over time) | $0.05-0.10 | Legacy (mobile SoCs) |
| **Graphite-filled epoxy** | 5-10 | Pre-applied film | Good (stable over 7 years) | $0.20-0.50 | Mid-range packages |
| **Boron nitride filled** | 15-25 | Film or slurry | Good (higher modulus) | $0.50-1.50 | Advanced packages |
| **Aluminum nitride (AlN)** | 20-30 | Ceramic particles in polymer | Excellent (high CTE match to Si) | $1.50-3.00 | Premium packages |
| **Liquid metal** | 50-80 | Flowing thermal fluid | Excellent (highest κ) | $5-10 | Exotic (some Intel, Apple) |

**The trade-off:** Higher thermal conductivity materials are:
- More expensive (5x-100x vs. baseline)
- Harder to process (require controlled application, curing)
- Mechanistically riskier (liquid metals can leak; AlN particles can separate)

### Bondline Thickness & Thermal Resistance

For a TIM layer with thickness $d$:

$$R_{\text{TIM}} = \frac{d}{\kappa \cdot A}$$

**Example:** 500W chip, 100mm² area, AlN TIM (κ = 25 W/m·K):

If $d = 50 \text{ μm}$ (0.05 mm):
$$R_{\text{TIM}} = \frac{0.00005 \text{ m}}{25 \text{ W/m·K} \times 0.01 \text{ m}^2} = 0.0002 \text{ K/W}$$

If $d = 200 \text{ μm}$ (loose tolerance printing):
$$R_{\text{TIM}} = \frac{0.0002 \text{ m}}{25 \text{ W/m·K} \times 0.01 \text{ m}^2} = 0.0008 \text{ K/W}$$

**The difference:** 0.0008 vs. 0.0002 K/W is 4x worse thermal resistance. For a 500W package, this translates to:

$$\Delta T_{\text{penalty}} = 500W \times (0.0008 - 0.0002) \text{ K/W} = 0.3°C$$

Doesn't sound like much, but:
- Chiplet 1 is at 120°C (target)
- Chiplet 2, 300 μm away, experiences 0.3°C hotter → 120.3°C
- With multiple chiplets and variance, peak temperature can reach 125-130°C
- Thermal throttling activates; performance drops 20%+

**Critical manufacturing requirement:** TIM bondline uniformity must be **±20 μm (±40% variation)** to maintain thermal consistency across chiplet.

This is why equipment precision matters: solder paste printing (Chapter 2) and underfill application must achieve tight tolerances.

---

## Part II: Multi-Path Heat Dissipation & System Thermal Design

### The Thermal Resistance Hierarchy

For a 500W AI accelerator, heat dissipation pathways are:

| Pathway | R (K/W) | Power (W) | Junction Temp Rise (°C) | Notes |
|---|---|---|---|---|
| **Primary: Die → Substrate → Heatsink → Air** | 0.10-0.15 | 450W | 45-67°C | Dominant path (passive cooling) |
| **Secondary: Die → Solder → PCB → Air** | 0.25-0.30 | 30-50W | 7.5-15°C | Solder ball interconnect path |
| **Tertiary: Die (side) → Underfill → Case → Convection** | 0.30-0.40 | 10-20W | 3-8°C | Minor, radiation + convection |

**Total R_total ≈ 0.15-0.20 K/W (parallel combination of above paths)**

### Liquid Cooling Integration

For AI data center applications (NVIDIA H100, next-gen TPU), **passive air cooling is insufficient.** Liquid cooling becomes mandatory.

**Cold plate design:**

```
┌─────────────────────────────────┐
│   Liquid Inlet (5-15°C water)   │
├─────────────────────────────────┤
│  ▓▓▓ Microchannel Array ▓▓▓     │  Width: 2-5 mm
│  ▓▓ (100-500 μm tall) ▓▓        │  Depth: 500-2000 μm
│  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓     │
├─────────────────────────────────┤
│   Liquid Outlet (25-30°C return) │
└─────────────────────────────────┘
```

**Heat transfer coefficient in microchannels:**

For turbulent flow (Re = 5,000-10,000):

$$h = 0.023 \cdot Re^{0.8} \cdot Pr^{0.4} \cdot \frac{\kappa}{D_h}$$

where:
- $Re$ = Reynolds number (flow turbulence)
- $Pr$ ≈ 5 (Prandtl number for water)
- $D_h$ ≈ 1 mm (hydraulic diameter of microchannel)
- $\kappa$ ≈ 0.6 W/m·K (water thermal conductivity)

$$h \approx 50,000-100,000 \text{ W/m}^2\text{·K}$$

Thermal resistance with liquid cooling:

$$R_{\text{liquid}} = \frac{1}{h \cdot A} = \frac{1}{75,000 \text{ W/m}^2\text{·K} \times 0.01 \text{ m}^2} ≈ 0.0013 \text{ K/W}$$

This is **150x lower** than air-cooled passive design.

**For 500W chip:**
- Air cooled: T_j = 25°C + 500W × 0.18 K/W = 115°C
- Liquid cooled: T_j = 25°C + 500W × 0.008 K/W = 29°C

**This explains why NVIDIA H100 requires direct liquid cooling.**

### Pumping Power & System Trade-offs

Liquid cooling introduces parasitic power loss from pump overhead:

$$P_{\text{pump}} = \Delta P \cdot Q_{\text{flow}}$$

where:
- $\Delta P$ = pressure drop across cold plate (50-200 kPa)
- $Q_{\text{flow}}$ = flow rate (10-50 liters/minute for 500W)

$$P_{\text{pump}} = 100 \text{ kPa} \times 25 \text{ L/min} = 100 \text{ kPa} \times \frac{0.4167 \text{ L/s}}{1000} ≈ 42 W$$

**Thermal efficiency penalty:** 42W pump power = 42W additional heat into the liquid loop (closed-loop system). This increases system cooling load by 8%, partially offsetting the 150x benefit.

**Real-world tradeoff:**
- Passive cooling: 500W thermal load on heatsink, air cooler energy cost ~$20-50/month (electricity)
- Liquid cooling: (500W + 42W) × efficiency + liquid circulation pump → $30-60/month (net similar cost for large data centers)

---

## Part III: Case Studies—Real Thermal Constraints

### NVIDIA H100: 700W Thermal Design

NVIDIA's H100 GPU dissipates up to 700W, making passive cooling impossible.

**Thermal design solution:**

1. **Front-side: Direct-to-die liquid cold plate** (mounted on GPU die)
   - Microchannel design, 5°C inlet water
   - Removes 600W directly from GPU junction
   - Achieves die-to-water resistance ≈ 0.002 K/W

2. **Memory thermal management:**
   - HBM (high-bandwidth memory) stacked on GPU
   - Interfaces via micro-bumps (Chapter 2)
   - TIM layer (AlN, κ = 25 W/m·K, d = 20 μm)
   - R_TIM = 0.00008 K/W (extremely tight control)

3. **Substrate backside cooling:**
   - Secondary cold plate on GPU substrate
   - Removes waste heat from IO dies, power delivery circuits
   - Removes 50-100W

**Result:**
- Junction temperature ≤ 85°C under sustained 700W load (with 10°C ambient water temp)
- Memory temperature ≤ 75°C (tighter thermal design)
- Packaging cost: +$100-200 per GPU (vs. air-cooled baseline) for liquid integration

### TSMC CoWoS (Chip-on-Wafer-on-Substrate): HBM Integration

TSMC's CoWoS technology stacks HBM memory directly on top of GPU logic using:

1. **Wafer bonding** (Chapter 3: hybrid bonding)
   - 10 μm copper-to-copper pads
   - Solder-free (no underfill required)
   - Extremely low thermal resistance at bond interface

2. **Through-silicon vias (TSVs)** for vertical thermal pathways
   - 50 μm diameter, 100-200 μm spacing
   - Copper-filled (κ_copper = 400 W/m·K)
   - Enable direct heat extraction from HBM to substrate

3. **Substrate thermal design**
   - Heavy copper substrate (500+ μm copper layers)
   - Thermal vias connecting die-attach layer to backside heatsink
   - R_substrate ≈ 0.005 K/W (vs. 0.02 K/W for standard organic substrates)

**Thermal performance:**
- HBM on GPU (stacked): 2-3°C temperature delta vs. separate packages
- Saves ~$50-100 per package (no separate HBM module)
- Enables 200+ GB/s GPU-to-HBM bandwidth (thermal coupling improves electrical coupling)

**Yield impact:** CoWoS stacking adds ~5-10% defect rate (bonding voids, TSV opens). This is more than offset by bandwidth and thermal gains.

### Apple M-series & A-series: Chiplet Integration Thermal Strategy

Apple's recent SoCs (M3, A17) use chiplets with aggressive thermal co-design:

| Chiplet Type | Power (W) | Thermal Strategy | R_total (K/W) |
|---|---|---|---|
| **Performance cores** | 20-30W | High-density underfill + Graphite-filled TIM | 0.15 |
| **Efficiency cores** | 5-10W | Standard TIM | 0.25 |
| **GPU cores** | 15-20W | TIM + passive substrate spreading | 0.20 |
| **Memory controller** | 2-3W | Substrate-level thermal distribution | 0.40 |

**System-level strategy:**
- Performance and GPU cores are thermally co-located → share heatspreader
- Efficiency cores positioned away from hot zone → lower local temperature
- Substrate designed with heavy copper under performance zone
- Dynamic thermal management (DTM) algorithm throttles performance cores when T > 105°C

**Result:** System thermal design achieves 0.18 K/W (comparable to NVIDIA's design, but without liquid cooling).

---

## Part IV: Material Supply Chain & Equipment Moats

### TIM Material Suppliers & Qualification

Only 3-4 suppliers globally can provide advanced TIM formulations qualified for chiplet integration:

| Supplier | Primary Product | κ Range | Qualification Timeline | Market Share |
|---|---|---|---|---|
| **Dow Corning** | Silicone-based TIM, AlN particles | 2-8 W/m·K | 12-18 months | 40-50% |
| **Henkel** | Epoxy-based, boron nitride | 5-15 W/m·K | 12-18 months | 30-40% |
| **3M** | Micro-structured films | 1-5 W/m·K | 9-12 months | 15-20% |
| **Indium Corporation** | Specialty pastes, thermal greases | 0.5-3 W/m·K | 6-9 months | 5-10% |

**Qualification is a 12-18 month process:**
1. Materials testing (thermal cycle reliability: −40°C to +125°C, 500+ cycles)
2. Process integration (compatibility with underfill, solder)
3. Thermal performance validation (customer-specific test vehicles)
4. Reliability approval (long-term aging tests, electromigration coupling effects)

**Result:** Once a fab qualifies a TIM material, switching costs are astronomical ($20-50M in re-qualification).

### Equipment for TIM Application & Control

Precise TIM bondline thickness requires automated equipment:

| Equipment | Supplier | Precision | Cost | Application |
|---|---|---|---|---|
| **Dispense systems** | Nordson, Musashi | ±10-20 μm | $500K-$1M | Paste dispensing, underfill |
| **Curing ovens** | Ersa, BTU | ±2°C uniformity | $1-2M | Thermal profile control |
| **Thermal monitoring** | Fluke, FLIR | ±0.5°C accuracy | $50-200K | Real-time temperature sensing |
| **Pressure control** | SMC, Festo | ±0.1 MPa | $200-400K | Uniform bondline thickness |

**Total equipment investment for TIM line:** $3-5M per fab

This is why **ASMPT's integrated systems** (dispense + cure + monitor + pressure) command pricing power—they bundle all these functions.

---

## Part V: Capital Allocation & TIM Supply Scarcity

### The Thermal Materials Shortage (2024-2027)

As chiplet adoption accelerates, TIM demand grows exponentially:

| Year | Estimated TIM Demand (MT/year) | Market Value | YoY Growth |
|---|---|---|---|
| 2023 | 5,000 MT | $200M | — |
| 2024 | 7,500 MT | $300M | +50% |
| 2025 | 12,000 MT | $500M | +60% |
| 2026 | 18,000 MT | $750M | +50% |

**Constraint:** Current TIM manufacturing capacity is ~8,000 MT/year (across Dow, Henkel, 3M).

**Result:** Supply shortage 2024-2026, driving prices up 30-50% for premium formulations.

### Margin Expansion for TIM Suppliers

TIM material gross margins are typically 45-55%. During supply shortage (2024-2026), margins expand to 60-70%:

**Dow Corning thermal materials business:**
- Revenue 2023: ~$200M (estimate)
- Revenue 2026: ~$500M (projected)
- Gross margin: 45% → 65% (shortage pricing)
- Operating margin: ~30-35% (significant operating leverage)

**Capital allocation implication:** Specialty chemical suppliers (Dow, Henkel) will show outsized profitability 2024-2027 due to TIM supply constraints.

### Equipment Suppliers Benefiting

Equipment suppliers who can integrate TIM application with thermal monitoring (ASMPT, Amkly, Onto Innovation) will:
- Capture service revenue from TIM supply chain integration ($500K-$1M annually per tool)
- Gain stickiness as customers optimize TIM application for their processes
- Build moat through process IP (how to dispense, cure, monitor AlN TIM without voids)

---

## Summary: Thermal Management as the Final Frontier

Thermal management is the **limiting factor** for advanced chiplet integration:

| Aspect | Physics Challenge | Competitive Moat | Equipment/Material Impact |
|---|---|---|---|
| **TIM Bondline** | <50 μm thickness, ±20 μm tolerance | Dow/Henkel supply lock-in (12-18 month qualification) | ASMPT dispense + cure integration (+$1M equipment) |
| **Liquid Cooling** | Microchannel design, pump control, water chemistry | Only NVIDIA/TSMC have figured this out (3-5 year head start) | Custom cold plate suppliers, pump makers |
| **CTE Mismatch** | Thermal stress management across multiple chiplets | Material selection (AlN vs. boron nitride) affects MTBF | TIM suppliers; substrate designers |
| **System Thermal Design** | Multiple heat paths (die, substrate, case, external) | R_total ≤ 0.19 K/W for 500W packages | Heatsink design (Boyd, Laird), thermal simulation (Ansys) |
| **Supply Constraints** | 12,000+ MT/year TIM demand vs. 8,000 MT capacity | Shortage 2024-2027, price +30-50% | Dow, Henkel margin expansion; ASMPT service revenue |

**Capital allocation thesis:** Thermal management creates a **3-5 year supply shortage** that benefits:
1. **TIM suppliers** (Dow, Henkel) — 60-70% gross margins through 2027
2. **Equipment integrators** (ASMPT) — Service revenue from TIM optimization
3. **Specialty chemical companies** — Boron nitride, AlN particle suppliers

This is the **hidden profit opportunity** that most investors miss while focusing on TSMC and NVIDIA.

---

**Next: [Chapter 6: 3D NAND Stack Assembly & Reliability](#chapters-06)**
