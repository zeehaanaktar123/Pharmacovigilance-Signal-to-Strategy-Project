# Signal-to-Strategy: A Pharmacovigilance Case Study on Semaglutide and the Suicidality Signal

A complete, end-to-end pharmacovigilance (PV) project that walks a single real-world safety signal — post-marketing reports of suicidal ideation/self-injury with **semaglutide** (Ozempic / Wegovy / Rybelsus) — through the full signal lifecycle: **detection → validation → benefit-risk assessment → risk management planning**.

The project is built entirely on real, cited data (published FAERS/WHO VigiBase studies, SELECT and STEP randomized trial results, EMA PRAC and FDA regulatory decisions) rather than simulated numbers, so the conclusions can be checked against what regulators actually decided on this exact issue.

> **Disclaimer:** This is a student/portfolio project, not a regulatory submission. It has not been reviewed by a Qualified Person for Pharmacovigilance (QPPV) or any regulatory authority. Where figures are real and cited, this is noted; where a number was reconstructed to reproduce a published statistic, or a judgment call (e.g. MCDA weights) was made by the author for demonstration purposes, this is flagged explicitly in the relevant document.

---

## Why this project

Most PV portfolio projects rely on toy or simulated data. This one deliberately picks a signal that is:

- **Real and recent** — first flagged by the Icelandic Medicines Agency in July 2023, formally reviewed by EMA's PRAC (concluded April 2024), and revisited by the FDA in its January 2026 labeling decision.
- **Genuinely contested** — independent FAERS and WHO VigiBase analyses disagree with each other, including a direct contradiction in direction for "suicide attempt" (ROR 0.16 vs. 1.39).
- **Fully documented** — every case count, trial result, and regulatory date in this repo is traceable to a published source, so the project's own conclusions can be sanity-checked against real regulatory outcomes.

## What I did

I ran a single safety signal through all four stages of the PV value chain that a Head of PV / QPPV would expect to see, and produced one deliverable per stage plus a synthesis document:

1. **Signal Detection** — Built a no-code disproportionality analysis (2×2 contingency tables) using published FAERS/WHO VigiBase case counts for the MedDRA terms under the "Suicide/Self-Injury" SMQ. Calculated PRR, ROR, 95% confidence intervals, and chi-square by hand/formula, and applied standard signal thresholds (Evans criteria for PRR, lower-CI-bound test for ROR).
<img width="1387" height="642" alt="image" src="https://github.com/user-attachments/assets/523f9e64-c7cc-415d-825e-3db5c0a46366" />


2. **Signal Validation** — Took the statistically flagged/borderline terms from Phase 1 and assessed them against the **CIOMS Working Group VIII** framework: biological plausibility, confounding by indication, dechallenge/rechallenge evidence, temporal association, and cross-database concordance.
<img width="597" height="647" alt="image" src="https://github.com/user-attachments/assets/67dda9a7-0c1c-4666-a414-c584de73a998" />


3. **Benefit-Risk Assessment** — Weighed the validated risk against semaglutide's real, high-certainty cardiometabolic benefit data (the SELECT and STEP 1 randomized trials) using a **Multi-Criteria Decision Analysis (MCDA)**, informed by the BRAT and PrOACT-URL frameworks, including an explicit sensitivity analysis on the weighting assumptions.
<img width="730" height="716" alt="image" src="https://github.com/user-attachments/assets/0b5ff87c-5bf0-4c2a-98ce-167587d67fdd" />
<img width="767" height="732" alt="image" src="https://github.com/user-attachments/assets/d38007e7-8081-497e-9772-46aeb7b78244" />


4. **Risk Management Plan** — Wrote an RMP in **EU GVP Module V** structure (Safety Specification, Pharmacovigilance Plan, Risk Minimization Measures, Effectiveness Evaluation), clearly separating real/current regulatory requirements from the additional monitoring activities I'm proposing to close the evidence gaps found in Phase 2.
<img width="581" height="752" alt="image" src="https://github.com/user-attachments/assets/eb6f6c33-c3b3-484b-92f9-37868c13a4ff" />


5. **Executive Summary** — A one-document synthesis of all four phases, written for a reader who won't read the full underlying analysis, ending in a single conditional recommendation.
<img width="710" height="761" alt="Screenshot 2026-09-16 155143" src="https://github.com/user-attachments/assets/e815b3ac-7527-4734-b87a-b277ed535011" />


## How I did it

- **Methodology, not memorization.** Each phase uses the actual industry-standard framework for that stage of PV work (Evans/CIOMS thresholds → CIOMS WG VIII → MCDA/BRAT/PrOACT-URL → GVP Module V) rather than an ad-hoc approach, so the project mirrors how this work is actually structured in industry.
- **Real data, transparently sourced.** All case counts and trial results are drawn from published, cited literature (e.g. Noordam et al., *JAMA Network Open* 2024; Chukwuma et al., FAERS-based comparative analysis, 2025–26; the SELECT and STEP 1 trials) and real regulatory records (EMA PRAC outcome statement, FDA labeling actions). Where live database access wasn't available to me and a figure had to be reconstructed to reproduce a published statistic, or where data simply doesn't exist for a term, that is labeled in the worksheet rather than presented as a computed result.
- **Disagreement treated as signal, not noise.** FAERS and WHO VigiBase disagree with each other on more than one term. Rather than picking the source that supports a conclusion, the project treats the discrepancy itself as the central analytical finding and discusses why it happens (database, comparator, and population differences).
- **Judgment calls made explicit.** The Benefit-Risk MCDA weights are illustrative, assigned by me for demonstration, not elicited from clinicians or patients — this is stated on the document itself, along with a sensitivity analysis showing how the conclusion moves if those weights change.
- **Checked against reality.** Every phase's conclusion is compared against what regulators actually did with this same signal (EMA PRAC, April 2024; FDA labeling update, January 2026), so the project's independent analysis can be validated against real-world outcomes instead of just asserting its own correctness.

## Repository contents

| File | Phase | Format | Contents |
|---|---|---|---|
| `faers_signal_worksheet.xlsx` | 1 — Signal Detection | Excel | Raw case counts, 2×2 tables, PRR/ROR/chi-square formulas, published benchmarks, signal-threshold logic |
| `signal_validation_memo.docx` | 2 — Signal Validation | Word | CIOMS WG VIII assessment: plausibility, confounding, dechallenge/rechallenge, temporality, cross-database comparison, regulatory timeline |
| `benefit_risk_assessment.docx` | 3 — Benefit-Risk Assessment | Word | MCDA scoring against SELECT/STEP trial data, weighted scoring table, sensitivity analysis |
| `risk_management_plan.docx` | 4 — Risk Management Plan | Word | GVP Module V safety specification, PV plan, risk minimization measures, effectiveness KPIs |
| `executive_summary.docx` | Synthesis | Word | Cross-phase findings table and final recommendation, written for a reader who won't open the other four documents |

## Key finding

No new regulatory restriction is warranted on the evidence assembled here — a conclusion that independently reproduces EMA PRAC's April 2024 review and the FDA's January 2026 labeling decision. The cardiometabolic benefit case is large and rests on high-certainty randomized trial evidence; the suicidality signal is modest, statistically inconsistent between FAERS and VigiBase, and substantially confounded by the elevated baseline psychiatric risk of the treated population. The recommendation is conditional, not absolute: it depends on closing specific evidence gaps (confounding by indication, incomplete dechallenge/rechallenge linkage, no long-term psychiatric outcome data) through the additional monitoring proposed in Phase 4.

## Frameworks referenced

- Evans/PRR and ROR disproportionality thresholds (used by UK MHRA, EMA EudraVigilance screening)
- CIOMS Working Group VIII signal validation framework
- Multi-Criteria Decision Analysis (MCDA), informed by BRAT and PrOACT-URL
- EU GVP Module V (Risk Management Plan structure)

## Limitations

- This is a portfolio/demonstration project, not a regulatory submission, and has not been reviewed by a QPPV or any regulator.
- Two of the five MedDRA terms in scope (Intentional self-injury, Self-injurious ideation) have no retrievable case-count data — this is reported as an evidence gap, not a negative finding.
- Live querying of the FAERS Public Dashboard was not available during this project; all case counts are drawn from previously published, peer-reviewed literature.
- Benefit-Risk MCDA weights are illustrative and were not elicited from clinicians, patients, or regulators.
- No formal statistical adjustment for confounding by indication (e.g. propensity matching) was performed.

## Author

**Munshi Zeehaan Aktar**

---

*This repository is for educational/portfolio purposes and does not constitute medical, regulatory, or clinical advice. Labeling and regulatory positions referenced here reflect the project's research dates and should be re-verified against current sources before any real-world use.*
