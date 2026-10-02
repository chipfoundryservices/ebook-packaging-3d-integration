# Knowledge Base Links & Cross-References

## A. ChipFoundryServices 5-Book Series Integration

### A.1: Book 1 — "Chip: Crystalline Silicon and the Industrial Moat"

**Chapters with direct relevance to Book 5:**

| Book 5 Topic | Book 1 Reference | Connection |
|---|---|---|
| Chiplet architecture | Ch. 3: Device scaling limits | Why monolithic scaling is dead; chiplets are alternative |
| Gate-all-around (GAAFET) | Ch. 2: Transistor physics | GAAFET requires selective SiGe etch (downstream of lithography) |
| Silicon properties | Ch. 1: Crystalline Si fundamentals | CTE (2.6 ppm/K), Young's modulus (130 GPa) underpin stress analysis |
| Power density | Ch. 4: Interconnect challenges | Junction temperature constraints drive thermal management requirements |

**Cross-reference:** Book 5, Chapter 1 (Death of Moore's Law) references Book 1's analysis of transistor scaling cost curves.

---

### A.2: Book 2 — "Foundry: Fab Economics and the Manufacturing Paradox"

**Chapters with direct relevance to Book 5:**

| Book 5 Topic | Book 2 Reference | Connection |
|---|---|---|
| TSMC's role in chiplets | Ch. 2: Foundry scale & cost | TSMC's CoWoS packaging platform is critical for HBM integration |
| Capex cycle dynamics | Ch. 3: Fab investment cycles | Packaging capex (2024-2028) parallels foundry capex timing |
| Yield learning curves | Ch. 5: Yield and ramp curves | 3D NAND stacking follows same S-curve yield profile as new nodes |
| Capital intensity | Ch. 6: Equipment ROI | Packaging equipment ($8-12M per line) vs. foundry equipment ($50-200M) |

**Cross-reference:** Book 5, Chapter 6 (3D NAND Stacking) models yield learning curves identical to Book 2's foundry ramp analysis.

---

### A.3: Book 3 — "Lithography: Photomasks, Optics, and the EUV Monopoly"

**Chapters with direct relevance to Book 5:**

| Book 5 Topic | Book 3 Reference | Connection |
|---|---|---|
| Pattern printing | Ch. 2: EUV optics | EUV exposure on substrate before flip-chip assembly requires pattern generation on interconnect layers |
| Resolution limits | Ch. 3: Rayleigh criterion | 2D scaling hits optical limit (~22nm in 2018); packaging is necessary next frontier |
| Equipment cycles | Ch. 5: EUV capex peaks | Lithography capex peaked 2023-2024; packaging capex rises 2024-2028 (complementary cycles) |
| Mask costs | Ch. 4: Photomask complexity | Advanced substrate manufacturing requires multi-layer photolithography ($1-2M per mask set) |

**Cross-reference:** Book 5, Chapter 4 (Chiplet Interconnects) discusses why substrate lithography becomes critical as interconnect density increases.

---

### A.4: Book 4 — "Etch: The Sub-Nanometer Chisel"

**Chapters with direct relevance to Book 5:**

| Book 5 Topic | Book 4 Reference | Connection |
|---|---|---|
| 3D NAND etch | Ch. 4: Extreme aspect ratio | 100:1+ aspect ratio etching (NAND channels) feeds into 3D stacking |
| Atomic layer etch (ALE) | Ch. 5: ALE self-limiting chemistry | ALE enables selective removal of SiGe nanosheet layers (GAAFET prep) |
| Thermal constraints | Ch. 2: Plasma temperature | Etch chamber temperatures <100°C to prevent thermal damage; downstream packaging must handle higher thermal loads |
| Equipment moats | Ch. 7: Lam Research dominance | Lam's plasma expertise complementary to (not competing with) packaging equipment suppliers |

**Cross-reference:** Book 5, Chapter 6 (3D NAND Assembly) references etch as the bottleneck for achieving 100:1 aspect ratio channels before packaging integration.

---

## B. 110-Asset Portfolio Integration

### B.1: Equipment Suppliers (Direct Book 5 Exposure)

**Tier 1: Overweight (2024-2027)**

| Company | Ticker | Book 5 Role | Chapters |
|---|---|---|---|
| **ASMPT** | ASMPT | Flip-chip bumping ecosystem | Ch. 2, 7, 8 |
| **Amkly** | Private (IPO pending) | Wafer bonding dominance | Ch. 3, 7, 8 |
| **Onto Innovation** | ONTO | Process control & metrology | Ch. 2, 5, 6, 8 |

**Tier 2: Hold (Stable)**

| Company | Ticker | Book 5 Role | Chapters |
|---|---|---|---|
| **Lam Research** | LRCX | Etch equipment (upstream) | Ch. 6 (3D NAND etch) |
| **KLA Corporation** | KLAC | Inspection & metrology | Ch. 2, 5, 6 |

**Tier 3: Reduce (Structural Decline)**

| Company | Ticker | Book 5 Role | Chapters |
|---|---|---|---|
| **Kulicke & Soffa** | K&S | Wire bonding (legacy) | Ch. 7 (declining market) |

---

### B.2: Foundries & Manufacturers (Indirect Book 5 Exposure)

**Chiplet Adopters:**

| Company | Ticker | Book 5 Relevance | Chapters |
|---|---|---|---|
| **TSMC** | TSM | CoWoS packaging platform | Ch. 4, 5, 6 |
| **Samsung** | SSNLF | 3D NAND stacking, chiplet roadmap | Ch. 6, 8 |
| **Intel** | INTC | Arrow Lake/Lunar Lake chiplets | Ch. 1, 4 |
| **AMD** | AMD | Ryzen/EPYC chiplet architecture | Ch. 1, 4 |

---

### B.3: Materials Suppliers (Specialty Chemicals)

**TIM & Underfill Suppliers:**

| Company | Exposure | Book 5 Chapters | Rationale |
|---|---|---|---|
| **Dow Chemical** | Thermal materials division | Ch. 5, 8 | TIM shortage 2024-2027 → margin expansion |
| **Henkel AG** | Adhesives & underfill | Ch. 5, 8 | Underfill formulation IP; 12-18 month qualification lock-in |
| **Indium Corporation** | Solder alloys & paste | Ch. 2, 8 | Specialty solder chemistry for advanced bumping |

---

## C. Key Research Papers & Standards

### C.1: Thermal Management & Reliability

- **Sheng, K.** (2015). "Challenges in wide bandgap semiconductor power electronics." *IEEE IEDM Technical Digest*, 1.1.1-1.1.9.
  - References: Chapter 5 thermal physics
  
- **Bhatti, M., et al.** (2012). "Thermal interface materials—A review of state-of-the-art." *Journal of Electronic Materials*, 40(5), 858-876.
  - References: Chapter 5 TIM materials

- **Manley, J.** (2002). "Solder joint fatigue under thermal cycling." *IPC Technical Review*, 26(4).
  - References: Chapter 2 and Chapter 6 Coffin-Manson modeling

---

### C.2: 3D Integration & Bonding

- **Tezzaron Semiconductor.** (2015). "Through-silicon vias and 3D assembly fundamentals." *White Paper*.
  - References: Chapter 6 TSV reliability

- **MIT Lincoln Laboratory.** (2019). "Hybrid bonding for chiplet integration." *Microelectronics Journal*, 85.
  - References: Chapter 3 and Chapter 4 chiplet integration

---

### C.3: Plasma Physics & Etch (Referenced from Book 4)

- **Lieberman, M.A., Lichtenberg, A.J.** (2005). *Principles of Plasma Discharges and Materials Processing*. 2nd Ed., Wiley.
  - References: Chapter 2 of *Etch* (Book 4); underpins plasma-based etching constraints on downstream packaging

---

### C.4: Equipment & Process Control Standards

- **SEMI E35-0706.** Guide for Characterization of Semiconductor Wafer Warpage.
  - References: Chapter 6 warpage calculations

- **SEMI M1-0302.** General Requirement for Semiconductor Equipment.
  - References: Chapter 7 equipment reliability specs

- **IPC-9701.** Performance Test Methods for Area Array Solder Interconnections.
  - References: Chapter 2 bump reliability, Chapter 5 thermal cycling

- **JEDEC JC-45.3.** Wafer Bond Strength Methodology.
  - References: Chapter 3 hybrid bonding strength specifications

---

## D. ChipFoundryServices Knowledge Base Articles

### D.1: Semiconductor Equipment Ecosystem

**Article:** "Semiconductor Equipment Market Dynamics: From Lithography to Packaging"
- Summarizes capex cycles across lithography (Book 3), etch (Book 4), and packaging (Book 5)
- Located: https://www.chipfoundryservices.com/knowledge-base/equipment-cycles

**Article:** "3D NAND Stacking: The Capital Allocation Opportunity"
- Deep dive on 3D NAND capex cycles and equipment supplier positioning
- References: Chapter 6 of Book 5

---

### D.2: Capital Allocation Frameworks

**Article:** "The 110-Asset Semiconductor Infrastructure Model"
- Maps all 110 assets to competitive moats, ROIC, and market cycles
- Integrates Books 1-5 into unified capital allocation framework
- Located: https://www.chipfoundryservices.com/knowledge-base/110-asset-model

**Article:** "Chiplet Architecture & Equipment Demand: A 5-7 Year Outlook"
- Forecasts equipment demand based on chiplet adoption roadmaps (Apple, AMD, Intel)
- References: Chapters 1, 4, 8 of Book 5

---

### D.3: Competitive Intelligence

**Article:** "ASMPT vs. Amkly: Equipment Moat Comparison"
- Direct competitive analysis of packaging equipment leaders
- References: Chapter 7 of Book 5

**Article:** "Wafer Bonding as Strategic Moat: Amkly's Market Position"
- Deep dive on hybrid bonding technology lock-in and service revenue durability
- References: Chapters 3, 7 of Book 5

---

## E. External Industry Resources

### E.1: Semiconductor Industry Association (SIA)

- **Factbook:** Annual semiconductor industry statistics
- Relevant sections: Equipment capex trends, equipment supplier market share

---

### E.2: SEMI (Semiconductor Equipment and Materials International)

- **Standards Database:** SEMI E standards (equipment), SEMI M standards (manufacturing)
- Key standards referenced: E35 (warpage), M1 (equipment reliability), M13 (equipment safety)

---

### E.3: IPC (Association Connecting Electronics Industries)

- **IPC-9701:** Solder interconnection reliability
- **IPC-6016:** Connectivity systems for electronic equipment

---

### E.4: JEDEC (Joint Electron Device Engineering Council)

- **JC-45:** Microelectronic Assembly and Interconnection Society standards
- **JC-45.3:** Wafer bonding specifications

---

## F. Investment Research & Market Reports

### F.1: Market Size Estimates (Book 5 Context)

| Market | 2024E Size | 2028E Size | CAGR | Source |
|---|---|---|---|---|
| Flip-chip bumping equipment | $2.5B | $3.8B | 11% | Industry estimates |
| Wafer bonding equipment | $1.8B | $3.2B | 15% | Industry estimates |
| 3D NAND capex equipment | $8B | $12B | 10% | Industry estimates |
| Chiplet packaging total | $12B | $22B | 16% | CAGR 2024-2028 |

---

### F.2: Competitive Rankings (Gartner-style Analysis)

**Flip-Chip Equipment Magic Quadrant:**
- **Leaders:** ASMPT (visionary, execution)
- **Challengers:** Amkly (niche leader in bonding), FINETECH (precision)
- **Visionaries:** None (market mature, incremental innovation)
- **Niche Players:** Solder paste suppliers (Henkel, Dow)

---

## G. Companion Materials to Book 5

### G.1: Interactive Tools

**Capital Allocation Calculator:** Input equipment supplier financials; calculates ROIC, service margin impact, capex cycle timing
- Located: https://www.chipfoundryservices.com/tools/equipment-roic-calculator
- References: Chapter 8 ROIC analysis

**Chiplet Roadmap Tracker:** Timeline of chiplet adoption (Apple, AMD, Intel, Microsoft)
- Forecasts equipment demand 3-5 years out
- Located: https://www.chipfoundryservices.com/tools/chiplet-roadmap

---

### G.2: Video Explainers

**"Why Packaging Is the Next Semiconductor Capex Cycle"** (15 min)
- High-level overview of Book 5's thesis
- References: Chapters 1, 4, 8

**"ASMPT Equipment Ecosystem Deep Dive"** (25 min)
- Technical walkthrough of Datapace integration strategy
- References: Chapter 7

---

## H. Author's Recommended Reading Sequence

**For Capital Allocators:**
1. Read Book 5: Chapters 1, 8 (skip deep physics if time-constrained)
2. Read 110-Asset Model (chipfoundryservices.com KB)
3. Read Chapter 7 (ASMPT competitive analysis)
4. Reference Appendices as needed for specifications

**For Engineers/Technical Professionals:**
1. Read Book 5: All chapters in order (Chapters 1-8)
2. Study Appendices (glossary, math, specs)
3. Cross-reference to Books 1-4 for upstream/downstream context

**For Portfolio Managers:**
1. Read Chapter 8 (capital allocation playbook)
2. Skim Chapters 1, 4, 6 (markets and capex cycles)
3. Use Appendix F (competitive rankings, market size estimates)
4. Reference ROIC analysis (Chapter 7) quarterly as equipment supplier earnings arrive

---

## I. Document Version & Updates

**Book 5 Version:** 1.0 (Complete Manuscript)  
**Last Updated:** October 2, 2026  
**Next Review:** Q1 2027 (update capex forecasts, equipment supplier performance)

**Feedback & Corrections:** Submit to research@chipfoundryservices.com

---

**End of Appendices**

See the main chapters for detailed analysis. All four books (and this Book 5) available on GitHub:
https://github.com/chipfoundryservices/
