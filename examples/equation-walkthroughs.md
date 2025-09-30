# Equation Walkthroughs

## Example 1: Baseline Defensive Profile

Given:
- 5 axioms → σ_a = 1/(1+5)=0.1667
- χ_e = 0.80
- Average CTI growth factor term e^{-δ \overline{Ṫ(CTI)}} with δ=0.7, average rate factor = 0.9 → contributes ≈ 0.9
- F_p = 0.6
- α=1.1, β=1.0, ζ=0.8

Compute KII:
KII ≈ (0.1667)^{1.1} * (0.80)^{1.0} * 0.9 * (0.6)^{0.8}

Breakdown:
(0.1667)^{1.1} ≈ 0.144
(0.6)^{0.8} ≈ 0.664
Multiply: 0.144 * 0.80 * 0.9 * 0.664 ≈ 0.0687

Result: KII ≈ 0.069 (weak – suggests over-axiomatized)

Refinement: Drop to 4 axioms: σ_a=1/5=0.2 → (0.2)^{1.1} ≈ 0.179
New KII ≈ 0.179*0.80*0.9*0.664 ≈ 0.085 → ~24% improvement.

## Example 2: Harvest Efficiency Impact

Let Ψ_Δ = 12 (abstract), KII = 0.30, β=1.2, γ=1.4

Compute KII^γ = 0.30^{1.4} ≈ 0.184
Denominator = 12 + 1.2*0.184 ≈ 12 + 0.2208 = 12.2208
η_h ≈ 12 / 12.2208 ≈ 0.982

Interpretation: Low KII gives attacker nearly full conversion. Target raising KII to 0.6:

0.6^{1.4} ≈ 0.495
Denominator = 12 + 1.2*0.495 ≈ 12 + 0.594 = 12.594
η_h ≈ 0.953 (still high). Reduce Ψ_Δ via Predictive Throttle (batching) to 6:

New denominator (KII=0.6): 6 + 0.594 = 6.594
η_h ≈ 6 / 6.594 = 0.91 → combined KII + Ψ_Δ reduction more meaningful.

## Example 3: Drift Accumulation Control

Parameters:
γ_crypt = 0.08, χ = 0.5, μ=0.9, ν=0.6

Case A: ω_v=2, J_d=1
Net additive term: χ - μ ω_v - ν J_d = 0.5 - 0.9*2 - 0.6*1 = 0.5 - 1.8 - 0.6 = -1.9 (negative → stable)

Case B: ω_v=0.5, J_d=0
Term = 0.5 - 0.9*0.5 = 0.5 - 0.45 = 0.05 (positive → drift exponential growth)

Lesson: Minimal journaling + low validation flips stability.

## Example 4: Backscatter Tuning

ξ = 0.3
Attacker Δκ choices:

| Δκ | R_b |
|----|-----|
| 1 | 1 - e^{-0.3} ≈ 0.26 |
| 3 | 1 - e^{-0.9} ≈ 0.59 |
| 5 | 1 - e^{-1.5} ≈ 0.78 |

If defender manipulates attacker to overshoot to Δκ=5, 78% of injected entropy reflected.

## Example 5: Fork Penalty

κ_safe=2, IMT=6, κ_fork=5, ω=1.2

Overshoot = (5 - 2)/(6 - 2)=3/4=0.75
Penalty factor = (1 - 0.75)^{1.2} = (0.25)^{1.2} ≈ 0.25^{1} * 0.25^{0.2} ≈ 0.25 * 0.758 ≈ 0.189
KII_eff = 0.7 * 0.189 ≈ 0.132 → catastrophic. Reintegration needed.

## Example 6: Sector Fidelity Decay

ρ=0.02, C_s=1.5 → (1 - C_s) negative? Cap C_s contribution: use max(0, 1 - C_s).

Effective decay exponent: ρ * max(0, 1 - 1.5)=0 → no decay while high redundancy sustained.

If C_s drops to 0.4:
Exponent = 0.02*(1-0.4)=0.012
After 100 time units: F_s=F_s0 e^{-1.2} ≈ 0.30 F_s0 (significant loss)

## Example 7: Event Probability

λ₀=0.01, Ψ_Δ=8, KII=0.5, C_s=1.2, Δt=10

Rate = λ₀ Ψ_Δ /(KII C_s) = 0.01*8/(0.5*1.2)=0.08/0.6=0.1333
P ≈ 1 - e^{-0.1333*10}=1 - e^{-1.333}=1 - 0.263 ≈ 0.737

Improve KII to 0.7 and C_s to 1.8:
Rate = 0.08/(0.7*1.8)=0.08/1.26=0.0635
P ≈ 1 - e^{-0.635}=1 - 0.530 = 0.470

Drop Ψ_Δ to 5 simultaneously:
Rate=0.05/(1.26)=0.0397 → P=1 - e^{-0.397}=0.329

## Example 8: Optimization of Predictive Throttle

a=0.015, b=1.2
ν_b* = sqrt(b/a)= sqrt(1.2/0.015)= sqrt(80)=8.944 updates / cycle
Round to 9. Over-updating to 15 or under to 4 both raise harvest exposure.

## Example 9: Ethical Integrity Projection

KII_0=0.6, ω_drift=0.25, σ_a χ_e = 0.20
Exponent = -(0.25 - 0.20)= -0.05 → KII(T)=0.6 e^{-0.05}=0.57 after unit time.

Improve σ_a χ_e to 0.27:
Exponent = -(0.25 - 0.27)= +0.02 → slight growth KII(T)=0.612

## Example 10: Composite Defense Efficacy

Assume:
KII=0.65, C_s=1.4, η_h=0.9, D_norm=0.3, IOL=0.8*IOL_opt, VDI=0.5*VDI_tol

DEI = (0.65*1.4*(1-0.9)*(1-0.3)) / ((1+0.8)(1+0.5))
= (0.91*0.1*0.7)/(1.8*1.5)= (0.0637)/(2.7)=0.0236 low

Reduce η_h to 0.6, D_norm to 0.15:
Numerator: 0.91*(0.4)*(0.85)=0.3094
DEI=0.3094/2.7=0.1147 → ~5x improvement.

## Interpretation Summary Table
| Adjustment | Effect | Primary Lever |
|------------|--------|---------------|
| Reduce axiom count | ↑σ_a | Kernel refinement |
| Increase χ_e | Slows KII decay | Ethical ritual |
| Raise C_s | Lowers event probability | Validation coordination |
| Paradox training | ↑F_p, lowers yield | Guid. Paradox Integration |
| Optimize ν_b | Minimizes jitter | Predictive Throttle |
| Increase R_b | Deters complex injections | Backscatter prep |

Use these examples to calibrate campaigns or simulations.