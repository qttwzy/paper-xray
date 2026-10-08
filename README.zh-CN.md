# Medical Paper X-Ray

这是对 [Wang-auspicious/paper-xray](https://github.com/Wang-auspicious/paper-xray) 的医学论文专用改造方案，保留原项目“深读而非摘要复述、怀疑式审读、MD/HTML 双交付”的核心思想，把计算机科学论文的分析框架替换为临床流行病学、循证医学、生物统计和医学研究方法框架。

## 它和原版最重要的区别

原版 Paper X-Ray 的核心问题是“这个方法为什么这样设计、哪个模块真正承重”。医学版把核心问题换成：

- 研究问题和 estimand 到底是什么；
- 研究设计允许多强的因果/诊断/预测结论；
- primary endpoint、注册记录、protocol、SAP 与发表稿是否一致；
- 相对效应背后的绝对获益/伤害有多大；
- 置信区间允许哪些临床上重要的可能性；
- 失访、多重性、亚组、缺失数据、分析集如何影响结论；
- 安全性是否与 efficacy 被同等认真地报告；
- 结果对真实患者是否可推广；
- 单篇论文放回整条证据链后究竟改变了什么。

## 支持的研究类型

RCT、非随机干预与真实世界比较效果、队列/病例对照/横断面、诊断准确性、预测模型/医学 AI、系统综述/meta-analysis、临床指南、病例系列、基础/动物/转化、生物标志物与组学、健康经济学、定性/混合方法。

## 三层审读，避免常见误区

1. **报告质量**：CONSORT / STROBE / PRISMA / STARD / TRIPOD 等回答“有没有把该报告的信息写清楚”。
2. **偏倚风险**：RoB 2 / ROBINS-I / QUADAS / PROBAST 等思想回答“这个具体结果可能偏到什么程度”。
3. **证据确定性与临床决策**：在足够的 evidence body 上再使用类似 GRADE 的框架；不会给单篇 RCT 随手贴“GRADE 高质量”。

## 设计取向：不做“过度防御型”论文解读

这个 fork 的目标不是输出最安全、最圆滑的评论，而是输出**最强的可辩护判断**。新版明确禁止用“仅供参考”“仍需更多研究”“存在一定局限”这类套话替代分析。

如果注册记录、protocol/SAP、审稿历史或统计结果支持更强判断，可以直接写：outcome switching、data-driven analysis、spin、post hoc rationalization、结论超过数据支持范围。与此同时，因果推断、效应指标解释、缺失数据、偏倚方向等方法学约束仍严格保留——那是准确性，不是“合规”。

新版还增加三个强制步骤：
- **核心主张台账**：只抓 3–7 个真正承重的 claim，逐条结算证据；
- **独立数值审计**：能从论文数字重算的 primary result、绝对效应、NNT/NNH、分母和 CI 就自己重算；
- **Red-team 反方测试**：强制找最可能推翻主结论的隐藏假设、替代解释和不同分析选择，再看作者最强的反证是什么。

## 安装

把本目录中的 `SKILL.md` 安装为 `medical-paper-xray`，并保留 `references/medical-methods-router.md` 与 `references/calibration-log.md`。

示例：

```text
/medical-paper-xray /path/to/paper.pdf clinical
/medical-paper-xray 10.xxxx/xxxxx methods
/medical-paper-xray PMID:12345678 journal-club html
```

模式：
- `clinical`：临床意义、绝对效应、安全性、外部有效性优先。
- `methods`：研究设计、estimand、统计、偏倚、registry/protocol/SAP 优先。
- `journal-club`：额外生成最可能被追问的问题和讨论点。

## Fork 后建议的仓库改动

- 用本版本 `SKILL.md` 替换上游 `SKILL.md`；
- 增加 `references/medical-methods-router.md`；
- 保留 `references/calibration-log.md`，只记录可泛化的阅读与输出偏好；
- 原 `references/figure-kit.html` 可以继续保留，HTML 分支仍有价值；
- 原来的 CS demo 建议移到 `archive/upstream-demos/` 或删除，避免 Agent 把 DINO/Transformer 示例当医学默认范式；
- `references/SKILL.en.md` 建议删除：医学版主 skill 已按用户语言自动输出，避免维护两套超长 prompt 发生漂移；
- 更新 README 并保留上游 MIT License 与 attribution。

## 许可与来源

上游 Paper X-Ray 使用 MIT License。这个改造保留来源说明，并在医学研究方法部分进行了专门重构。
