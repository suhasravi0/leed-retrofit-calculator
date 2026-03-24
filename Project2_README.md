# LEED v4.1 Retrofit Savings Calculator

**An open-source Excel tool that models energy savings, water savings, and projected LEED point achievement for commercial building retrofits — built on ASHRAE 90.1-2019 baselines and EPA WaterSense standards.**

---

## Overview

This calculator was built to turn the LEED GA credential into a demonstrated, practical skill. You input a building's current systems and proposed retrofit measures — the tool calculates annual energy savings (kBtu and $), water savings (gallons and $), and estimates LEED v4.1 BD+C points earned by credit category, projecting the certification level automatically.

The sample data models **Casa Cortile, Arlington, TX** — an 8,500 sq ft commercial office building targeted for LEED v4.1 Gold certification.

---

## Workbook Structure

| Tab | What It Does |
|-----|-------------|
| **Inputs** | All editable parameters — building info, current systems, proposed retrofit measures |
| **Energy Savings** | ASHRAE 90.1-2019 energy savings by measure: HVAC, lighting, envelope, solar |
| **Water Savings** | EPA WaterSense fixture-by-fixture water savings calculation |
| **LEED Points** | Credit-by-credit LEED v4.1 BD+C point estimator with auto certification level |
| **Summary Report** | Auto-generated one-page retrofit recommendation report |

---

## How to Use

1. Open the workbook and navigate to the **Inputs** tab
2. Update the **amber cells** with your building's information (all other cells are formulas)
3. Set Yes/No for each retrofit measure in Section 3
4. Navigate to **Summary Report** for a complete one-page results overview
5. Check **LEED Points** tab for the credit-by-credit breakdown

> **Amber cells = input fields. All other cells are formulas — do not overwrite them.**

---

## Methodology

### Energy Savings

| Measure | Calculation Basis |
|---------|------------------|
| HVAC upgrade | Savings = baseline HVAC energy × (1 − current SEER / proposed SEER); HVAC = 40% of commercial energy per ASHRAE 90.1 |
| LED lighting | Savings = (baseline LPD − proposed LPD) × sq ft × annual occupancy hours; baseline per ASHRAE 90.1 Table 9.6.1 |
| Roof insulation | Savings based on U-value improvement ratio; envelope = 10% of total energy |
| Window upgrade | Savings = baseline window load × (proposed U-factor / baseline U-factor) |
| Solar PV | Generation = system kW × 1,460 hours/yr (NREL PVWatts, DFW: 4.0 peak sun hrs/day) |

### Water Savings

| Fixture | Basis |
|---------|-------|
| Toilets | 3 uses/person/day × occupants × 260 workdays × (current − WaterSense gpf) |
| Urinals | 2 uses/person/day × 50% occupancy × 260 workdays × (current − WaterSense gpf) |
| Lavatory faucets | 3 uses × 0.5 min/use × occupants × 260 workdays × flow reduction |
| Kitchen faucets | 15 min/day × occupants × 260 workdays × flow reduction |

All water fixtures benchmarked against EPA WaterSense maximum flow rates.

### LEED v4.1 Points

Points are estimated across six credit categories under BD+C New Construction & Major Renovation:

- **Sustainable Sites (SS)** — heat island, rainwater, light pollution
- **Water Efficiency (WE)** — indoor water use reduction; scaled by % savings
- **Energy & Atmosphere (EA)** — optimize energy performance (up to 18 pts); renewable energy
- **Materials & Resources (MR)** — construction waste, low-emitting materials
- **Indoor Environmental Quality (EQ)** — thermal comfort, lighting quality, daylight
- **Innovation + Regional Priority** — LEED AP credit, DFW regional priorities

Certification thresholds per USGBC LEED v4.1:

| Level | Points Required |
|-------|----------------|
| Certified | 40–49 |
| Silver | 50–59 |
| **Gold** | **60–79** |
| Platinum | 80+ |

---

## Sample Output — Casa Cortile, Arlington TX

| Metric | Result |
|--------|--------|
| Annual energy savings | $2,335/yr |
| Annual water savings | ~$890/yr |
| Total annual savings | ~$3,225/yr |
| Energy reduction | ~31% |
| Water reduction | ~38% |
| Estimated LEED points | 63 |
| Projected certification | **GOLD** |

---

## Skills Demonstrated

| Skill | Where Applied |
|-------|--------------|
| LEED v4.1 credit structure | LEED Points tab — credit-by-credit estimation |
| ASHRAE 90.1-2019 compliance | Energy Savings methodology |
| EPA WaterSense standards | Water Savings methodology |
| Sustainable building analysis | Summary Report — combined savings and certification |
| Advanced Excel (cross-sheet formulas, conditional logic) | All tabs |
| Quantitative building performance modeling | Energy and water calculations |

---

## Data Sources & References

- **ASHRAE 90.1-2019** — Energy Standard for Buildings Except Low-Rise Residential Buildings
  - §6: HVAC systems; Table 9.6.1: Lighting power density; §5.5: Envelope prescriptive path
- **EPA WaterSense** — [epa.gov/watersense](https://www.epa.gov/watersense) — fixture flow rate specifications
- **USGBC LEED v4.1 BD+C** — [usgbc.org/leed](https://www.usgbc.org/leed) — credit categories and point thresholds
- **NREL PVWatts Calculator** — [pvwatts.nrel.gov](https://pvwatts.nrel.gov) — DFW solar irradiance baseline (4.0 peak sun hrs/day)
- **Dallas-Fort Worth utility rates** — Oncor / Atmos Energy 2024 average tariff rates

---

## Limitations & Assumptions

- Energy calculations are simplified estimates for early design-phase decision support, not engineered energy models (which require EnergyPlus or eQUEST whole-building simulation)
- LEED point estimates are based on threshold logic — actual certification requires full documentation submission to USGBC
- Single electricity rate assumed (no time-of-use tariff modeling)
- Water calculations assume 260 occupied workdays/year; adjust for different occupancy patterns
- Solar generation assumes standard south-facing roof orientation at 20° tilt; actual yield varies with shading and orientation

---

## Author

**Suhas Ravi, CMIT, LEED GA**  
MS Construction Management | University of Texas at Arlington (Dec 2026)  
[linkedin.com/in/suhasravi](https://linkedin.com/in/suhasravi)

---

## License

MIT — free to use, adapt, and extend for educational and professional purposes. If you use this for an actual project, verify all assumptions against current ASHRAE, EPA, and USGBC documentation.
