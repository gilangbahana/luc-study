# Localised Uniform Conditioning (LUC) in Estimating Recoverable Resources in Porphyry Copper Deposits: A Comparative Study of Geostatistical Methods

## Introduction
### The Problem
Traditional kriging smooths grade variability at the SMU scale — leading to unreliable recoverable resource estimates and suboptimal mine planning.
- Accurate estimation of recoverable resources is fundamental to economically viable mining projects.
- Mining is conducted at the Selective Mining Unit (SMU) scale — not sample scale.
- Linear methods (e.g. Ordinary Kriging) often produce over-smoothed block estimates.
- Localised Uniform Conditioning (LUC) provides a non-linear approach that refines grade estimation at the SMU scale.

### Study Aims
- Compare  LUC accuracy vs. kriging in the panel and ground truth
- Assess  Impact of SMU size on anamorphosis (r value)
- Benchmark  LUC vs. conditional simulation (SGS & TBS)
- Quantify  Economic impact of each estimation technique
- Evaluate  LUC sensitivity to nugget effect parameters

## LUC Theory — Change of Support & Workflow
### Change of Support Concept
- As support increases (Point → SMU → Panel): mean stays constant, variance decreases, histogram becomes more symmetric.
- Dispersion variance (Krige's Relation): σ²(v|V) = σ²(o|V) − γ̄(v,v)
- Global change of support: does not spatially locate resources.
- Local change of support (LUC): approximates the spatial position of grade classes.

### LUC Workflow (6 Steps)
- Panel Grade Estimation (Ordinary Kriging)
- DGM Fitting: Normal Score Transform + Hermite Polynomials
- Change of Support: compute r (SMU) and R (Panel)
- Grade Transformation: convert estimates to Gaussian space
- Tonnage & Metal above cut-off via bivariate Gaussian
- Localisation — rank SMUs by OK grade, assign UC grades

## Dataset & Exploratory Data Analysis
### Key Observations
- Both datasets show nearly identical statistics: confirming exploration data is representative.
- Both distributions are positively skewed: Normal Score Transform required for LUC/simulation.
- Declustering unnecessary: uniform grid sampling confirmed by declustering window test.
- r = 0.7821 (SMU-point correlation); Gaussian variogram nugget ~43%, range ~200 m.
<img width="3047" height="893" alt="dataset" src="https://github.com/user-attachments/assets/d4857fdb-4cab-41d5-b522-56bfc20de82d" />

## Estimation & Simulation Parameters
<img width="3095" height="1308" alt="estimation parameter" src="https://github.com/user-attachments/assets/2666907c-9c98-4b70-9ca3-970534c894f2" />

## Results — LUC vs. Linear Kriging
<img width="1278" height="630" alt="results 1" src="https://github.com/user-attachments/assets/6fb70c8b-63f3-4385-8860-92bf28c231c8" />
Plan view comparison of the panel kriging (a), the direct kriged to SMU (b), the LUC (c), and the ground truth (d).

## Results — LUC vs. Linear Kriging (cont..)
<img width="3127" height="1145" alt="results 2" src="https://github.com/user-attachments/assets/d8df4952-ef31-4cb9-8214-cb17ef1d257c" />

## Sensitivity Analysis — SMU Size & Discretisation Points
### Discretisation Point Findings
- Impact of SMU size on grade-tonnage curve is negligible, curves for all SMU sizes nearly overlap.
- This holds regardless of whether discretisation density is uniform (5×5×1) or proportional to SMU size.
- Exception: using a SINGLE discretisation point (point estimate) causes slight grade overestimation.
- Therefore, multiple discretisation points per block are always recommended for LUC.
- Practical implication: SMU size choice is driven by mining selectivity, not by statistical accuracy concerns.
<img width="1716" height="989" alt="sens  analysis" src="https://github.com/user-attachments/assets/40fdbcd7-54d4-4100-886f-a62302fdc232" />
As SMU size increases → variance decreases (change-of-support principle confirmed)

## Results — LUC vs. Conditional Simulation (TBS & SGS)
- LUC (+1%) outperforms all methods in matching ground truth at 1% cut-off.
- Simulations (SGS/TBS) offer risk quantification through multiple realisations.
- Kriging methods severely underestimate high-grade zones (smoothing effect).
- At 0% cut-off, all methods are within 3–4% of ground truth — differences emerge at higher cut-offs.
<img width="3074" height="1072" alt="results 3" src="https://github.com/user-attachments/assets/ea588965-d09e-4241-814a-84ebe7dcba0c" />
Ground truth = grade control kriging | Exploration data spacing = 40×40 m

## Economic Implications — Revenue vs. Drilling Cost
- LUC achieves comparable net benefit to ground truth while using only 90 drillholes vs. 1,200.
- Drilling cost savings: $234,000 (dense) vs. $17,550 (sparse) — over 13× reduction.
- Kriging using sparse data severely underestimates revenue — $6M+ difference vs. LUC.
- Optimal strategy: sparse exploration + LUC = low cost, high accuracy.
<img width="3007" height="576" alt="results 4 table" src="https://github.com/user-attachments/assets/f8e18249-01e3-4119-b511-b3f5026e6e51" />
<img width="1815" height="940" alt="results 4 graph" src="https://github.com/user-attachments/assets/7c36d4f3-ecee-4aeb-8911-b7c8ff65132e" />
Assumptions: $9,757/t Cu price, 82% recovery rate

## NPV Analysis — Impact of Mining Direction
- N–S direction consistently generates higher NPV than E–W across ALL estimation methods.
- Highest grades are concentrated in the NE corner — starting there and mining south maximises early cash flow.
- All estimation methods agree on optimal mining direction — robust finding.
- DCF principle: high-grade areas mined early are worth more due to time value of money.
- LUC NPV ($57.9M) closely matches ground truth ($60.4M) in N–S direction.
<img width="2046" height="1121" alt="results 5 graph" src="https://github.com/user-attachments/assets/ce8d2c28-104c-40d6-8f37-0f5dd182390b" />
Assumptions: Cu @ $9,757/t | Recovery: 82% | Discount: 10% | Total volume = 432,000 m³ | Mining rate = 43,200 m³/year | LoM = 10 years

## LUC Sensitivity — Impact of Nugget Effect
### Scenario 1: Zero Nugget
- Well-defined spatial continuity
  - Hermite polynomial fits perfectly
  - High support correction (r = 0.985)
  - LUC closely matches ground truth

### Scenario 2: High nugget (50%)
- Erratic spatial behaviour
  - Hermite polynomial struggles to fit
  - Low support correction (r = 0.710)
  - LUC significantly deviates from ground truth

### Conclusion: LUC is best suited for deposits with low nugget effects (e.g. porphyry copper). High nugget effects impair support correction and hermite polynomial fitting, consider alternative methods.

## Conclusions & Recommendations
- LUC outperforms kriging — at the SMU scale — significantly reduces smoothing effect and better reflects true grade distribution.
- LUC matches ground truth — with only 1% metal difference at 1% cut-off using sparse (40×40 m) exploration data.
- Economic advantage — sparse drilling + LUC = $13× lower drilling costs with comparable net benefit to dense sampling.
- Mining direction matters — N–S mining from the NE high-grade zone consistently maximises NPV across all methods.
- Nugget effect is critical — LUC performs best with low nugget effects. High nugget (>50%) impairs hermite polynomial fitting and lowers support correction.

## Presentation Deck
[MSC Thesis - Localised Uniform Conditioning.pdf](https://github.com/user-attachments/files/28317246/MSC.Thesis.-.Localised.Uniform.Conditioning.pdf)

