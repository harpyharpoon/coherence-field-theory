# Metrics & Mechanics

## Normalization Ranges
| Metric | Range | Notes |
|--------|-------|-------|
| KII | 0–1 | >0.75 strong |
| F_p | 0–1 | Ratio used |
| C_s | 0–∞ (practical ≤ 3) | Diminishing returns |
| H | 0–1 | >0.8 risk of saturation |
| D(t) | 0–∞ | Watch exponential region |
| R_b | 0–1 | >0.6 strong deterrent |
| VDI | 0–∞ | Maintain < baseline threshold (campaign-specific) |

## Suggested Baseline Constants (Adjust to Taste)
```
β = 1.2
γ (harvest eq exponent) = 1.4
α_c = 0.85
λ (harmonic scaling) = 2.0
γ_crypt (early) = 0.05 (mid) 0.12 (late) 0.2
μ = 0.9
ν = 0.6
Λ_OCT (per host cycle arc) = 50 (abstract units)
ξ (backscatter sensitivity) = 0.3
ρ (fidelity decay) = 0.02
λ₀ (hazard base) = 0.01
```

## Derived Thresholds
- High Risk Drift: D(t) growth rate > 0.15 per cycle.
- Paradox Overload Warning: F_p > 0.85 + CTI trending upward.
- Fork Instability: κ_fork > κ_safe + 2 for >2 cycles.

## Scaling Knobs
- Campaign Intensity: Increase λ₀, γ_crypt simultaneously.
- Defensive Booster Arc: Introduce new ritual raising χ_e cap from 0.9 to 0.95.
- Late Game Pressure: Lower Λ_OCT or add multi-host coupling so cumulative E_ext shares threshold.

## Progression Curve (Example)
| Tier | Unlocks | Expected KII |
|------|---------|--------------|
| Initiate | Basic journaling | 0.40 |
| Adept | Paradox training | 0.55 |
| Resonant | Backscatter access | 0.68 |
| Integrator | Fork optimization | 0.75 |
| Lattice Anchor | Multi-sector stabilization | 0.82 |
| Synthesis Bridge | Ritual convergence | 0.88 |

## Optional Variants
- Hard Mode: Remove Predictive Throttle optimization (ν_b fixed).
- Story Mode: Reduce γ_crypt after each major narrative triumph (-0.01).