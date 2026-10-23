# A/B Testing — Designing the Data-Generating Process

## Objective

I wanted to see how the way data is generated (randomized experiment versus observational comparison) changes what we can conclude about a treatment effect, and how to size a study so it can detect that effect.

## Methodology

- Loaded the LaLonde NSW job training experiment (445 people: 185 trainees and 260 controls) and computed the experimental ATE.
- Simulated an observational comparison group to show selection bias, and split the gap as: Observational ATE = True ATE + Selection Bias.
- Ran a permutation test with 9,999 shuffles on the ATE.
- Computed a bootstrap BCa 95% confidence interval for the ATE.
- Ran a power analysis: the power of this study, and the sample size needed for three dollar effects.
- Applied the same tests to the Cookie Cats mobile game A/B test (90,189 players, gate at level 30 or 40, Day-1 retention).
- Wrote a sample-size function, `n_needed()`, checked it against the power analysis, and used it to size a rerun of Cookie Cats.

## Key Findings

**NSW job training**
- Trainees earned $1,794.34 more than controls.
- Permutation test: p = 0.0046.
- Bootstrap BCa 95% CI: $575.18 to $3,262.37.
- The simulated comparison group gave an ATE of $1,794.34.

**Cookie Cats**
- Day-1 retention differed by 0.59 percentage points (p = 0.0059).
- A rerun would need 111,192 players per group.
