# Medical Methods Router

这不是机械评分表，而是 `medical-paper-xray` 在识别研究设计后要优先检查的“承重问题”。

> 重要：报告规范（reporting guideline）、偏倚风险工具（risk-of-bias tool）和证据确定性框架不是一回事。网络可用时，从官方来源核对最新版本与适用范围。

## 1. 随机对照试验（RCT）

优先资料：registry → protocol → SAP → supplement → main paper。

关键问题：
- sequence generation 与 allocation concealment；
- superiority / non-inferiority / equivalence；
- blinding 对 co-intervention、依从性和 outcome assessment 的影响；
- ITT / mITT / PP / as-treated；
- primary outcome、timepoint、estimand；
- protocol deviations 与 intercurrent events；
- missing outcomes；
- multiplicity、interim analysis、stopping rules；
- harms；
- 选择性报告。

报告规范：CONSORT 2025（及与具体设计匹配的 extension）；若能获得 protocol，同时用 SPIRIT 2025 对计划方法做结构化核对。
偏倚思路：RoB 2 的 outcome/result-level 思路。报告规范只检查“有没有报告清楚”，不要拿 CONSORT/SPIRIT 代替偏倚判断。

### 非劣试验额外检查
- margin 的临床依据和历史证据；
- constancy / assay sensitivity；
- ITT 与 PP 是否一致；
- cross-over / nonadherence 是否把结果推向“看起来相似”；
- 结论是 non-inferior，而非 automatically equivalent/superior。

### 集群随机
- randomization unit 与 analysis unit 是否一致；
- ICC/设计效应；
- cluster recruitment 是否发生在知道分组之后；
- cluster 数量是否过少导致不稳定。

### 交叉试验
- carry-over；
- washout；
- period effect；
- 结局是否可逆且疾病状态稳定。

## 2. 非随机干预 / 比较效果 / 目标试验模拟

先写“目标试验”七要素：eligibility、treatment strategies、assignment procedure、time zero、follow-up、outcome、causal contrast/analysis。

关键问题：
- eligibility、treatment assignment、follow-up 起点是否对齐；
- confounders 是否在治疗前测量；
- immortal time；
- prevalent user vs new user；
- active comparator 是否合理；
- positivity；
- informative censoring；
- time-varying confounding；
- propensity score / weighting / matching 的 balance 与 weight diagnostics；
- negative controls / quantitative bias analysis / sensitivity to unmeasured confounding。

偏倚思路：可优先参考 ROBINS-I V2（2025 年 11 月发布修订草案，仍可能继续调整）；使用时记录具体版本日期。若需要与既有系统综述或历史评价保持可比，可同时说明旧版 ROBINS-I 的差异，但不要机械沿用旧域。

## 3. 队列 / 病例对照 / 横断面 / 病因研究

关键问题：
- sampling frame 与 selection；
- exposure ascertainment；
- reverse causation；
- confounding；
- outcome ascertainment；
- missing data；
- time-varying exposure；
- overadjustment（把 mediator 当 confounder）；
- collider adjustment；
- multiple comparisons；
- 绝对风险与人群基线风险。

报告规范示例：STROBE / RECORD（常规数据时）。

病例对照额外：control selection、matching 后分析、recall bias。
横断面额外：时间顺序通常无法确定，避免因果语句。

## 4. 诊断准确性研究

先明确：target condition、index test、reference standard、intended use、threshold、clinical pathway。

关键问题：
- consecutive/random sampling vs case-control enrichment；
- spectrum / selection bias；
- index test 与 reference standard 是否互盲；
- partial/differential verification；
- threshold 是否预先指定；
- indeterminate results 如何处理；
- sensitivity/specificity 的 CI；
- prevalence 与 PPV/NPV；
- 每 1000 人 TP/FP/TN/FN；
- 是否改善 patient-important outcomes，而不只是 accuracy。

报告规范：一般诊断准确性研究用 STARD 2015；AI 诊断准确性研究叠加 STARD-AI 2025。
偏倚框架：优先 QUADAS-3（2026 当前版本）；只有为复现旧综述或比较历史结果时才回到 QUADAS-2/QUADAS-C，并明确原因。

## 5. 预后 / 临床预测模型 / 医学 AI

先区分：model development、internal validation、external validation、model updating、impact study。

关键问题：
- target population、prediction time、horizon、outcome definition；
- predictor measurement 是否在 prediction time 可得；
- leakage；
- missing predictor handling；
- sample size / effective events；
- overfitting 与 shrinkage/penalization；
- bootstrap/CV 是否正确嵌套 preprocessing 和 feature selection；
- discrimination：AUROC/C-index 等；
- calibration：intercept/slope/plot/observed-expected；
- overall performance：Brier 等；
- decision curve / net benefit；
- external validation 的 geography/time/site/device shift；
- subgroup/fairness 需要有数据才能评价；
- 与简单临床基线模型是否公平比较。

报告规范：TRIPOD+AI 2024 已取代 TRIPOD 2015，适用于回归或机器学习预测模型；按场景叠加 cluster 等扩展。
偏倚/质量框架：优先 PROBAST+AI 2025；它把 model development 与 model evaluation 分开审。不要把 TRIPOD+AI 的报告完整性当成模型低偏倚。

## 6. 系统综述 / Meta-analysis

优先资料：protocol/PROSPERO → search strategy → study list → risk-of-bias assessments → analysis code/data（若有）。

关键问题：
- question 与 eligibility 是否预先指定；
- databases、dates、language、grey literature；
- full search string 可复现性；
- dual screening/data extraction；
- 重复 cohort / companion reports；
- effect measure harmonization；
- fixed/common vs random effects；
- τ² estimator 与 CI method；
- clinical/statistical heterogeneity；
- prediction interval（适用时）；
- small-study effects / publication bias；
- sensitivity excluding high-risk studies；
- certainty of evidence 要按 outcome 评估。

报告规范示例：PRISMA 及对应 extension。
综述本身偏倚：ROBIS 等。
证据确定性：需要时使用 GRADE 的思想，不要把单篇文章和整个 body of evidence 混为一谈。

### Network meta-analysis
额外检查：
- transitivity；
- direct vs indirect evidence；
- incoherence/inconsistency；
- network geometry；
- ranking uncertainty，避免把 SUCRA/排名当确定事实。

## 7. 临床实践指南

关键问题：
- panel composition 与 conflicts；
- systematic review 是否支持每条 recommendation；
- evidence-to-decision 过程；
- recommendation strength 与 certainty 是否对应；
- patient values/preferences、resources、equity、feasibility；
- 更新机制与发布日期。

报告/评价框架示例：RIGHT、AGREE 系列。不要只凭“指南来自大机构”判断可靠性。

## 8. 病例报告 / 病例系列

用途通常是信号生成，不是效应量估计。

关键问题：
- case definition；
- 时间线；
- alternative explanations；
- dechallenge/rechallenge（若涉及药物）；
- reporting completeness；
- denominator 缺失意味着不能估 incidence/risk；
- 不从一例推治疗效果。

报告规范示例：CARE。

## 9. 基础 / 动物 / 体外 / 转化研究

关键问题：
- biological vs technical replicates；
- randomization/blinding；
- sample size justification；
- batch effects；
- exclusion/outlier rules；
- multiplicity；
- reagent/cell-line validation；
- animal model 与 human disease 的对应关系；
- 机制链中哪些环节只在模型里成立；
- 是否有 independent replication。

动物报告规范示例：ARRIVE。

## 10. 生物标志物 / 组学 / 遗传关联

关键问题：
- pre-analytic handling；
- batch correction；
- multiple testing / FDR；
- winner's curse；
- population stratification；
- discovery vs replication cohort；
- cutoff derivation vs validation；
- incremental value over clinical predictors；
- clinical utility beyond association。

## 11. 健康经济学

关键问题：
- analysis perspective；
- time horizon；
- comparator；
- costs 与 outcome（QALY 等）来源；
- discounting；
- ICER；
- model structure；
- parameter uncertainty；
- probabilistic sensitivity analysis；
- structural/scenario sensitivity；
- willingness-to-pay threshold；
- sponsor assumptions。

报告规范示例：CHEERS。

## 12. 定性研究 / 混合方法

关键问题：
- sampling strategy；
- reflexivity；
- data saturation 的定义与证据；
- coding / triangulation；
- negative cases；
- context transferability；
- 定量与定性部分如何真正整合，而不是并排报告。

报告规范示例：COREQ / SRQR。
