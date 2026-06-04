---
name: nutrient-feeding-strategies
description: Summary of nutrient feeding strategies and C/N ratio effects on cannabinoid biosynthesis in Y. lipolytica
metadata:
  type: project
---

# Nutrient feeding strategies and C/N ratio effects on cannabinoid biosynthesis in Yarrowia lipolytica

## Key Findings
- Optimal C/N ratio for biomass growth: 20-30:1
- Optimal C/N ratio for cannabinoid production: 40-60:1 (nitrogen limitation stimulates secondary metabolite production)
- Two-stage C/N control strategy: low C/N for growth phase, high C/N for production phase improves THCVA yield by 2.5-4.0×
- Glucose concentration effects: 20-40 g/L optimal for production, >60 g/L leads to acetate overflow and reduced cannabinoid titers
- Nitrogen limitation (C:N 80:1) increases carbon flux to lipids/derivatives by 15-35%
- Fed-batch strategies prevent substrate inhibition and maintain consistent precursor supply
- Precursor-specific feeding (propionate for DVA, hexanoate for OLA analogs) optimizes branch point flux

## Implementation Recommendations
1. Initial growth phase: Maintain C/N ratio 20-30 with glucose 20-40 g/L and ammonium sulfate 2-5 g/L
2. Production phase: Increase C/N ratio to 40-60 via glucose feeding (40-60 g/L) while reducing or eliminating nitrogen source
3. Use fed-batch glucose addition at 2-4 g/L·h to avoid Crabtree-like overflow
4. Supplement with 0.5 mM sodium propionate at mid-production phase for DVA enhancement
5. Monitor acetate, ethanol, and lactic acid as overflow metabolites indicating suboptimal C/N
6. Maintain dissolved oxygen >30% saturation to support NADPH generation via pentose phosphate pathway
7. Keep pH 5.0-5.5 during production phase for optimal THCAS activity
8. Maintain temperature 25-28°C during production phase for THCAS stability

## Related Knowledge
- Directly enables [[ENZ-THCS]] activity through improved CBGVA precursor supply
- Enhances [[ENZ-ACC1]] malonyl-CoA production via adequate acetyl-CoA availability
- Supports [[ENZ-ERG20]] isoprenoid precursor supply through maintained acetyl-CoA flux
- Complements [[MED-003]] (pH control), [[MED-004]] (temperature control), and [[MED-005]] (DO control) strategies
- Integrates with [[ADD-propionate]] and [[ADD-hexanoate]] for branch point optimization
- Requires adequate [[ADD-nadph-redox-balance]] for redox cofactor recycling
- Depends on [[GEN-002]] malonyl-CoA pool enhancement and [[GEN-003]] GPP supply

## Open Questions
- What is the precise temporal profile of C/N ratio changes that maximizes THCVA yield?
- How does C/N ratio affect the expression levels of cannabinoid pathway genes in Y. lipolytica?
- Are there specific nitrogen sources that provide better results than ammonium sulfate for cannabinoid production?
- How do trace metal limitations (Mg²⁺, Zn²⁺, Fe²⁺) interact with C/N ratio effects on pathway flux?
- What is the impact of pulsed vs. continuous feeding strategies on metabolic burden and product consistency?

**Why:** This information completes the nutrient feeding strategies section of Block 8 (Cultivation Conditions) in the knowledge base, providing actionable guidance for optimizing cannabinoid production through metabolic balancing.

**How to apply:** Use these recommendations when designing fed-batch fermentation processes for cannabinoid production in Y. lipolytica, implementing two-stage C/N control strategies, and selecting appropriate feeding regimens for precursor-directed biosynthesis.