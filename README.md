# Medical Paper X-Ray

A medical/biomedical fork of [Wang-auspicious/paper-xray](https://github.com/Wang-auspicious/paper-xray). It keeps the original project's core idea — deep reading instead of abstract paraphrase, skeptical appraisal, and Markdown/interactive HTML delivery — but replaces the computer-science-specific framework with clinical epidemiology, evidence-based medicine, biostatistics, causal inference, and medical research methodology.

## What it asks instead

Medical Paper X-Ray focuses on the questions that determine whether a biomedical paper is actually believable and useful:

- What is the exact clinical/biological question and estimand?
- What strength of causal, diagnostic, or predictive claim does the design permit?
- Do registry, protocol, SAP, supplement, peer-review history, and publication agree?
- What are the absolute effects, not only relative effects and p-values?
- How much clinically meaningful benefit or harm is still compatible with the confidence interval?
- How do missing data, multiplicity, subgroup analysis, time zero, analysis populations, and model choices affect the conclusion?
- Are harms treated as seriously as efficacy?
- Who does the result apply to, and who was effectively excluded from the evidence?
- What did this paper actually change when placed back into the full evidence chain?

Supported study types include randomized trials, non-randomized comparative effectiveness studies and target-trial emulations, cohorts/case-control/cross-sectional studies, diagnostic accuracy studies, prediction models and medical AI, systematic reviews/meta-analyses, guidelines, case series, translational/animal/in-vitro work, biomarkers/omics/genetics, health economics, and qualitative/mixed-methods research.

## Not a defensive reviewer

The goal is the **strongest defensible conclusion**, not the safest-sounding conclusion. The skill explicitly avoids boilerplate such as “more research is needed” when a sharper judgment is possible.

When supported by evidence, it can directly call out outcome switching, data-driven analyses, spin, post-hoc rationalization, or claims that exceed the registered analysis. Methodological constraints remain strict: association is not silently upgraded to causation, hazard ratios are not rewritten as cumulative risk ratios, reporting completeness is not confused with low risk of bias, and a single RCT is not casually assigned a GRADE certainty rating.

Three forced steps make the appraisal harder to game:

1. **Claim ledger** — identify the 3–7 load-bearing claims and settle them one by one.
2. **Independent numerical audit** — recompute key effects, denominators, absolute differences, NNT/NNH, and spot-check CIs/tests when the paper exposes enough data.
3. **Red-team pass** — identify the strongest alternative explanation, the hidden assumption most likely to overturn the conclusion, and the authors' best evidence against that critique.

## Reporting quality ≠ risk of bias ≠ certainty of evidence

The skill keeps these layers separate. Current examples include CONSORT 2025/SPIRIT 2025 for randomized-trial reporting/protocols, RoB 2 for randomized-trial bias, ROBINS-I V2 for non-randomized intervention studies, STARD/STARD-AI plus QUADAS-3 for diagnostic accuracy, and TRIPOD+AI plus PROBAST+AI for prediction models. It verifies current tool versions when network access is available rather than treating old checklists as timeless.

## Usage

Install `SKILL.md` as `medical-paper-xray` together with `references/medical-methods-router.md` and `references/calibration-log.md`.

```text
/medical-paper-xray /path/to/paper.pdf clinical
/medical-paper-xray 10.xxxx/xxxxx methods
/medical-paper-xray PMID:12345678 journal-club html
```

Modes:

- `clinical`: absolute effects, harms, patient-important outcomes, applicability, and practice relevance.
- `methods`: design, estimand, statistics, causal inference, bias, registry/protocol/SAP, reproducibility.
- `journal-club`: adds 8–12 likely questions with answers plus three high-value discussion points.

The original `references/figure-kit.html` remains useful for the HTML branch. Legacy CS demos may remain in the fork for provenance, but they are not part of the medical skill specification.

## License and attribution

The upstream project is MIT licensed. This fork retains attribution while substantially rewriting the methodology for biomedical research appraisal.
