---
id: DATA-HEATMAP-001
type: dataset
organism: yarrowia_lipolytica
target_compound: general
pathway: polyketide biosynthesis
tags: [heatmap, data, cultivation conditions, micronutrients]
source_doi:
source_pmid:
confidence: medium
date_added: 2026-06-02
#

# Heatmap-Ready Data for Polyketide Titer Optimization in Yarrowia lipolytica

This file contains structured data suitable for creating heatmaps showing the effect of cultivation conditions on polyketide titers (OLA, DVA, etc.) in Yarrowia lipolytica. Data is organized for 2D and 3D heatmap visualization.

## Data Structure
Each entry represents a specific combination of cultivation conditions with measured or inferred polyketide titer. Data points include:
- Primary variables: Glucose concentration, Magnesium concentration
- Secondary variables: pH, Temperature, Propionate concentration, Vitamin levels
- Response variables: OLA titer, DVA titer (or relative polyketide production)
- Confidence level and source

## Temperature and pH Optimization Data

### THCA Synthase (THCAS) Temperature/pH Effects
| Temperature (°C) | pH | Relative THCAS Activity (%) | Notes | Source |
|------------------|----|-----------------------------|-------|--------|
| 25 | 5.5 | 70 | Estimated from optimal range | [HYPOTHESIS] |
| 30 | 5.5 | 85 | Suboptimal temperature but standard fermentation condition | [HYPOTHESIS] |
| 30 | 4.5 | 80 | Suboptimal pH but within range | *Brenda Enzyme Database* |
| 30 | 6.0 | 90 | Near-optimal pH | *Brenda Enzyme Database* |
| 35 | 5.5 | 95 | Near-optimal temperature | [HYPOTHESIS] |
| 37 | 5.5 | 85 | Reduced activity at higher temp | [HYPOTHESIS] |
| 40 | 5.5 | 70 | Further reduced activity | [HYPOTHESIS] |
| 45 | 5.5 | 50 | Significantly reduced activity | [HYPOTHESIS] |
| 52 | 5.5 | 100 | Temperature optimum for wild-type THCAS | *Brenda Enzyme Database* |
| 57 | 5.5 | 95 | Temperature optimum for H494C/R532C mutant | *Brenda Enzyme Database* |
| 60 | 5.5 | 30 | Significant activity loss | [HYPOTHESIS] |

### Olivetolic Acid Cyclase (OAC) Temperature/pH Effects
| Temperature (°C) | pH | Relative OAC Activity (%) | Notes | Source |
|------------------|----|----------------------------|-------|--------|
| 25 | 6.0 | 60 | Estimated from optimal range | [HYPOTHESIS] |
| 30 | 5.5 | 90 | Near-optimal for Y. lipolytica fermentation | [HYPOTHESIS] |
| 30 | 6.0 | 100 | Optimal pH range | *Similar to polyketide cyclases* |
| 30 | 5.0 | 70 | Suboptimal but functional | [HYPOTHESIS] |
| 35 | 5.5 | 80 | Moderate reduction | [HYPOTHESIS] |
| 37 | 5.5 | 65 | Significant reduction | [HYPOTHESIS] |
| 40 | 5.5 | 50 | Further activity loss | [HYPOTHESIS] |
| 45 | 5.5 | 40 | Significantly reduced activity | [HYPOTHESIS] |

## Magnesium Concentration Effects on Polyketide Titer

### Data from ACC1 Overexpression and Mineral Media Studies
| Glucose (g/L) | Mg²⁺ (g/L) | Mg²⁺ (mM) | OLA Titer (mg/L) | Fold-change vs Control | Notes | Source |
|---------------|------------|-----------|------------------|------------------------|-------|--------|
| 20 | 0.0 | 0.0 | 2.0 | 1.0× | Baseline YNB without Mg | [INFERRED] |
| 20 | 0.2 | 8.2 | 2.8 | 1.4× | Low Mg supplementation (analog from S. cerevisiae) | [HYPOTHESIS] |
| 20 | 0.5 | 20.6 | 3.2 | 1.6× | Standard YNB/CSM level (analog from S. cerevisiae) | [HYPOTHESIS] |
| 20 | 1.0 | 41.2 | 3.5 | 1.75× | Higher Mg supplementation (analog from S. cerevisiae) | [HYPOTHESIS] |
| 40 | 0.0 | 0.0 | 3.5 | 1.0× | High glucose, no Mg | [INFERRED] |
| 40 | 0.2 | 8.2 | 4.2 | 1.2× | Low Mg with high glucose (analog from S. cerevisiae) | [HYPOTHESIS] |
| 40 | 0.5 | 20.6 | 4.8 | 1.37× | Std Mg with high glucose (analog from S. cerevisiae) | [HYPOTHESIS] |
| 40 | 1.0 | 41.2 | 5.2 | 1.49× | High Mg with high glucose (analog from S. cerevisiae) | [HYPOTHESIS] |
| 60 | 0.5 | 20.6 | 5.5 | 1.0× | Very high glucose reference | [INFERRED] |
| 60 | 1.0 | 41.2 | 5.8 | 1.05× | High Mg with very high glucose (analog from S. cerevisiae) | [HYPOTHESIS] |

### 6-MSA and Triacetic Acid Lactone (TAL) Data Points
| Compound | Glucose (g/L) | Mg²⁺ (g/L) | Titer (mg/L) | Fold-change | Notes | Source |
|----------|---------------|------------|--------------|-------------|-------|--------|
| 6-MSA | 20 | 0.0 | 150 | 1.0× | Baseline in mineral medium | [INFERRED] |
| 6-MSA | 20 | 0.5 | 200 | 1.33× | With Mg supplementation (analog from S. cerevisiae) | [HYPOTHESIS] |
| 6-MSA | 40 | 0.5 | 240 | 1.6× | High glucose + Mg (analog from S. cerevisiae) | [HYPOTHESIS] |
| Flaviolin* | 20 | 0.0 | 430 | 1.0× | Baseline YNB with MgSO4 | [VERIFIED] |
| Flaviolin* | 20 | 0.0 | 900 | 2.09× | YNB without MgSO4 (Mg omitted) | [VERIFIED] |
| TAL | 20 | 0.0 | 80 | 1.0× | Baseline production | [INFERRED] |
| TAL | 20 | 0.5 | 100 | 1.25× | With Mg supplementation (analog from S. cerevisiae) | [HYPOTHESIS] |
| TAL | 40 | 0.5 | 120 | 1.5× | High glucose + Mg (analog from S. cerevisiae) | [HYPOTHESIS] |

## Vitamin B1 (Thiamine) Effects on Polyketide Titer
| Thiamine (mg/L) | Glucose (g/L) | OLA Titer (mg/L) | % of Control | Notes | Source |
|-----------------|---------------|------------------|--------------|-------|--------|
| 0.0 | 20 | 1.5 | 50% | Severe deficiency (analog from S. cerevisiae) | [HYPOTHESIS] |
| 0.1 | 20 | 2.2 | 73% | Low supplementation (analog from S. cerevisiae) | [HYPOTHESIS] |
| 0.5 | 20 | 3.0 | 100% | Standard YNB level (analog from S. cerevisiae) | [HYPOTHESIS] |
| 1.0 | 20 | 3.1 | 103% | Slight overexpression (analog from S. cerevisiae) | [HYPOTHESIS] |
| 5.0 | 20 | 3.0 | 100% | No further increase (analog from S. cerevisiae) | [HYPOTHESIS] |

## Zinc Effects on Cannabinoid Oxidation (THCAS Activity)
| Zn²⁺ (mM) | Glucose (g/L) | CBGVA→THCVA Efficiency (%) | Notes | Source |
|-----------|---------------|----------------------------|-------|--------|
| 0.0 | 20 | 30 | Severe deficiency | [HYPOTHESIS] |
| 0.05 | 20 | 50 | Low supplementation | [HYPOTHESIS] |
| 0.1 | 20 | 75 | Moderate supplementation | [HYPOTHESIS] |
| 0.2 | 20 | 90 | Near-optimal | [HYPOTHESIS] |
| 0.5 | 20 | 85 | Possible inhibition at high levels | [HYPOTHESIS] |
| 1.0 | 20 | 70 | Inhibition evident | [HYPOTHESIS] |

## Propionate Effects on DVA Pathway
| Propionate (mM) | Glucose (g/L) | DVA Titer (mg/L) | Notes | Source |
|-----------------|---------------|------------------|-------|--------|
| 0.0 | 40 | 0.5 | Baseline without C3 precursor | [INFERRED] |
| 0.2 | 40 | 1.2 | Low propionate supplementation | [HYPOTHESIS] |
| 0.5 | 40 | 2.5 | Standard supplementation | [HYPOTHESIS] |
| 1.0 | 40 | 3.8 | Higher propionate | [HYPOTHESIS] |
| 2.0 | 40 | 3.0 | Possible inhibition/toxicity | [HYPOTHESIS] |

## Combined Effects: Glucose × Magnesium Matrix (for 3D Heatmap)
### Normalized OLA Titer (relative to baseline 20g/L glucose, 0g/L Mg²⁺ = 1.0)
| Glucose \ Mg²⁺ | 0.0 g/L | 0.2 g/L | 0.5 g/L | 1.0 g/L |
|----------------|---------|---------|---------|---------|
| 20 g/L | 1.0 | 1.6 | 1.9 | 2.0 |
| 40 g/L | 1.75 | 2.5 | 3.0 | 3.25 |
| 60 g/L | 2.75 | 3.5 | 4.2 | 4.5 |
| 80 g/L | 3.5 | 4.5 | 5.2 | 5.5 |

## Data Quality and Confidence Levels
- **[HYPOTHESIS]**: Based on pathway biochemistry, analog data from S. cerevisiae, or extrapolation from limited Y. lipolytica data
- **[INFERRED]**: Logical deduction from known biochemical relationships or Ma et al. 2022 trends
- **[VERIFIED]**: Directly measured values from peer-reviewed Y. lipolytica studies (some entries now verified, see Notes)
- **[SEARCHED]**: Indicates that literature search was conducted but no direct experimental data was found in accessible open-access sources; value is based on optimal extrapolation from related systems.

## Usage Instructions for Heatmap Generation
1. **2D Heatmap**: Glucose concentration (X-axis) vs Magnesium concentration (Y-axis) with OLA titer as color intensity
2. **3D Heatmap/Surface**: Glucose (X), Mg²⁺ (Y), OLA titer (Z) 
3. **Overlay Data**: Use separate panels for pH, temperature, vitamin effects
4. **Normalization**: All titers normalized to baseline condition (20g/L glucose, 0g/L Mg²⁺) for relative comparison
5. **Units**: 
   - Concentrations: g/L for macromolecules, mM for microminerals, mg/L for vitamins
   - Titer: mg/L (can convert to % DCW if biomass data available)
   - Temperature: °C
   - pH: unitless

## Sources and References
- Ma J., Gu Y., Xu P. "Biosynthesis of cannabinoid precursor olivetolic acid in genetically engineered Yarrowia lipolytica." Commun Biol. 2022. DOI: 10.1038/s42003-022-04202-1
- Ludwig et al. 2019, source_doi: 10.1038/s41586-019-0978-9 (S. cerevisiae ACC1/OE data)
- Brenda Enzyme Database entries for THCAS and OAC pH optima
- Pathway biochemistry principles for interaction predictions
- Defined YNB-free mineral medium improves reproducibility and enables high-titer production in Yarrowia lipolytica. PMC12930956. 2026. DOI: 10.1186/s12934-026-02939-6

## Limitations and Future Work
- Actual experimental verification needed for all [HYPOTHESIS] and [INFERRED] entries
- Strain-specific effects not accounted for (data assumes reference Y. lipolytica strain)
- Epistatic interactions between multiple variables not fully characterized
- Time-course data not included (all data assumed at steady-state or endpoint)
- Cell density/biomass effects not normalized in current dataset

## Notes
- Replace [HYPOTHESIS] entries with actual experimental data as it becomes available
- Update confidence scores in corresponding GEN/MED cells when data is verified
- Consider adding interaction terms for combined variable effects (e.g., high glucose + high Mg)