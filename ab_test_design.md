# A/B Test: paymentChange

## Case Description

You are a product analyst in a mobile app with a freemium model.  
The product offers a subscription (price = 400) and one-time purchases.

An experiment was conducted to reduce the subscription price from 400 to 160 for new users (50/50 split).

The goal is to evaluate the impact on conversion and revenue.

---

## 1. Business Understanding

| Checklist Item | Status | Comment |
|----------------|--------|--------|
| Problem defined | ✓ | High price may reduce conversion |
| Hypothesis formulated | ✓ | Lower price → higher conversion |
| Impact on key metric understood | ✓ | Expect strong conversion growth |
| Economic impact considered | ✓ | Risk of ARPU decrease |
| Risks identified | ✓ | Revenue loss, logging issues, parallel tests |
| Limitations defined | ✓ | New users only, no historical calibration |
| A/B test necessity justified | ✓ | Need causal inference |
| Experiment type defined | ✓ | User-level randomization |
| Success criteria defined | ✓ | Conversion growth without revenue damage |
| Action plan defined | ✓ | Rollout / extend / reject |

---

## 2. Experiment Design Validation

| Checklist Item | Status | Comment |
|----------------|--------|--------|
| Group balance checked | ✓ | No imbalance detected |
| SRM check | ✓ | No SRM |
| Cross-group contamination | ✓ | ~0.003% overlap |
| Parallel experiments impact | ✓ | Negligible |

---

## 3. Metrics

| Metric Type | Metric | Description |
|------------|--------|------------|
| Primary | Conversion | Share of users who subscribed |
| Guardrail | ARPU | Revenue per user |
| Guardrail | ARPPU | Revenue per paying user |
| Informational | Activity | User engagement |

---

## 4. Results

### Conversion

| Group | Value |
|------|------|
| Old | ~19.9% |
| New | ~49.9% |

Change: +30 p.p.  
Statistical significance: YES (p < 0.05)

---

### ARPU

| Group | Value |
|------|------|
| Old | ~309 |
| New | ~225 |

Change: -27%  
Statistical significance: NO (p = 0.67)

---

## 5. Interpretation

- Conversion significantly increased  
- ARPU decreased in absolute terms  
- However, ARPU difference is not statistically significant  

This indicates a **trade-off between growth and monetization** with uncertainty in revenue impact.

---

## 6. Final Decision

The experiment should **not be rolled out immediately**.

Reason:
- Strong positive effect on conversion  
- Potential risk of revenue decline  
- No statistical confirmation of ARPU drop  

---

## 7. Next Steps

- Extend experiment duration  
- Perform deeper analysis (LTV, segmentation)  
- Validate ARPU impact  

---

## 8. Project Structure

- `data/` — datasets  
- `notebooks/` — analysis  
- `docs/` — experiment design  
