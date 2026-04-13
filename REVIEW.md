# Thesis Reviewer Skill — Review & Recommendations

**Review Date**: 2026-04-13
**Reviewer**: Sisyphus (OhMyOpenCode)
**Skill Version**: 3.0.0
**Research Base**: University guidelines from Stanford, MIT, Cambridge, NeurIPS/ICML/ICLR/KDD review standards, FAIR data principles, Gopen & Swan writing principles.

---

## Overall Assessment

**Rating**: Good — well-structured, production-ready for Chinese university thesis review workflows.

The 5-dimension framework, two-phase workflow, discipline modules, and output template demonstrate clear thinking. However, there are meaningful gaps when measured against international PhD standards and modern academic writing best practices.

---

## 🔴 Critical Gaps (P0 — Impact Core Review Quality)

### 1. No "Limitations" section review

Modern theses — especially in CS/AI — must have a dedicated limitations discussion. Neither `checklist.md` nor `output-template.md` reviews this. Top venues (NeurIPS, ICML, ICLR) now require a limitations section. The `discussion` checklist items do not mention limitations explicitly beyond a single item.

**Suggested addition to `checklist.md` → 讨论 section:**

- [ ] 是否包含明确的研究局限性（limitations）讨论？
- [ ] 局限性是否具体、诚实（而非仅"需要更多数据"等笼统表述）？
- [ ] 是否讨论了局限性对结论可靠性的影响？

### 2. Contribution statement clarity test missing

The skill checks *whether* innovation claims exist, but does not test their *clarity*. Research from experienced PC members at top venues confirms: **"If you cannot state your contribution in one sentence, you don't have a paper."** The checklist should verify that contributions are falsifiable and specific.

**Suggested addition to `checklist.md` → 创新性:**

- [ ] 核心贡献是否能用一句话清晰概括？（如果不能用一句话说清楚，说明贡献不聚焦）
- [ ] 创新点的描述是否具体、可验证？（避免"提出了一种新颖方法"等模糊表述）
- [ ] 创新点是否与实验结果或理论证明直接对应？

### 3. "Thin-slicing" detection for PhD theses assembled from papers

Many Chinese PhD theses are assembled from published papers. The skill does not check whether chapters are genuinely connected by a unified research program vs. "thinly sliced" (分拆式) independent studies — which is explicitly flagged as a rejection reason at top venues and a common blind review concern.

**Suggested addition to `checklist.md` → 博士论文附加检查 → 研究体系的系统性:**

- [ ] 是否存在"薄切"（thin-slicing）——将一项完整研究人为拆分成独立章节以充实论文数量？
- [ ] 如论文章节基于已发表论文，各章之间是否有跨章节的整合性讨论或统一框架？
- [ ] 是否存在章节间方法论不一致、数据集碎片化的问题？

### 4. Missing FAIR data principles check

Modern thesis standards increasingly require data to be **F**indable, **A**ccessible, **I**nteroperable, and **R**eusable. The `cs-ai.md` checks for GitHub links, but no module checks for FAIR compliance, data management plans, or long-term archiving strategies.

**Suggested addition to `checklist.md` → 维度四（数据与结果):**

- [ ] 数据是否遵循 FAIR 原则（可发现、可获取、可互操作、可复用）？
- [ ] 是否有数据管理计划或数据存储/共享策略？
- [ ] 如使用公共数据集，是否说明了许可证和使用合规性？

---

## 🟡 Significant Improvements (P1)

### 5. Missing paragraph-level writing quality rules

The writing quality checklist (`checklist.md` 维度二) covers high-level coherence but misses granular rules taught by experienced advisors:

- **One concept per paragraph** (段落单一主题原则)
- **Topic sentence first** (段首即核心观点)
- **Reader-first sentence structure** (Gopen & Swan principles: 先给读者期望的信息，再给新信息)
- **Active vs. passive voice** guidance (优先使用主动语态，仅在动作执行者不重要时用被动)

**Suggested subsection in `checklist.md` → 维度二:**

### 段落级写作规范
- [ ] 每段是否遵循"单一主题"原则（一个段落只讨论一个核心观点）？
- [ ] 段落首句是否为该段的主题句（topic sentence）？
- [ ] 句子是否遵循"已知信息→新信息"的信息流动模式？
- [ ] 是否优先使用主动语态？（仅在动作执行者不重要时使用被动语态）
- [ ] 是否存在复杂嵌套从句导致理解困难？

### 6. Figure 1 / key figure strategic review missing

Research shows that the first figure (or primary result figure) is frequently the first content readers look at after the abstract. The checklist checks figure *formatting* (三线表, 分辨率) but not whether key figures effectively communicate the core contribution.

**Suggested addition to `checklist.md` → 图表规范:**

- [ ] 论文的第一张图（Figure 1）或核心结果图是否能独立传达研究的核心发现？
- [ ] 是否有"自明性"——读者仅看图和图注即可理解主要结论？

### 7. CS/AI: Theoretical vs. Applied distinction needed

The `cs-ai.md` treats all CS/AI theses uniformly. It should differentiate review criteria by sub-field:

| Sub-field | Additional Review Focus |
|-----------|------------------------|
| **Theoretical CS** | 证明验证（proof verification）、定理正确性、引理链条完整性、符号严格性 |
| **Systems / Applied** | 基准测试设计、可扩展性分析、部署考虑、消融实验设计 |
| **HCI / User Studies** | IRB 审批、参与者人口统计学、定性编码透明度、可用性研究方法 |
| **NLP / LLM** | 计算预算报告（GPU 小时数）、碳足迹、prompt 设计说明、评估人工标注 |
| **Computer Vision** | 数据集偏见分析、数据增强策略、可视化结果解释 |

### 8. Accessibility review missing

International universities (Stanford, MIT) now require PDF accessibility — proper heading hierarchy, alt text for figures, screen reader compatibility. For students targeting international programs or joint degrees, this is increasingly important.

**Suggested addition to `checklist.md` → 维度三:**

- [ ] 文档是否遵循无障碍标准（accessible PDF）？（如适用国际学位要求）
- [ ] 图片是否有替代文本描述（alt text）？
- [ ] 标题层级是否正确嵌套（H1→H2→H3，无跳级）？

### 9. Broader Impact / Societal Implications for AI/CS

Especially for CS/AI theses, there is no check for discussing ethical implications, fairness analysis, environmental impact (compute carbon footprint), or potential misuse. ICML and NeurIPS now require broader impact statements.

**Suggested addition to `disciplines/cs-ai.md`:**

### 社会影响与伦理
- [ ] 是否讨论了研究的社会影响和伦理考量？
- [ ] 如涉及 AI 系统，是否分析了公平性/偏见（fairness / bias）问题？
- [ ] 是否评估了研究的潜在负面应用或滥用风险？
- [ ] 是否说明了计算资源消耗和环境成本（如适用）？

---

## 🟢 Minor Enhancements (P2)

### 10. International citation standards
Currently GB/T 7714 only. Add optional support for APA (psychology/social sciences), IEEE (engineering/CS), Chicago (humanities) for students targeting international submission.

### 11. Version control for interactive refinement
When users adjust/add/delete opinions during Phase 2, track these in a structured changelog (not just "record the change"). Consider a `CHANGELOG.md` section in the review output.

### 12. Checkpoint item numbering
Add ID codes to each checklist item (e.g., `CQ-01`, `WQ-01`, `FM-01`) so they can be referenced in output reports by ID. This enables traceability between checklist items and review findings.

### 13. ML-specific: Computational budget reporting
For AI/ML theses, add a check for whether computational cost (GPU hours, training budget, carbon footprint) is documented — increasingly expected by reviewers at top venues.

**Suggested addition to `disciplines/cs-ai.md`:**

- [ ] 是否报告了计算开销（GPU 类型和小时数、训练成本）？

### 14. SKILL.md length concern
At 304 lines, it approaches the limit of what an LLM can hold in active context. Consider extracting "评审原则" and "工作流程" into a separate `workflow.md` reference file. Alternatively, the auto-load references (checklist.md, disciplines/) already help by deferring most detail.

### 15. Auto-update reliability
The auto-update runs embedded in the LLM prompt as Git instructions. If the LLM doesn't execute Bash tools reliably, this silently fails. Consider moving to a pre-hook or shell script (`scripts/auto-update.sh`) that runs as a separate step.

---

## Component Scores Summary

| Component | Score | Notes |
|-----------|-------|-------|
| `SKILL.md` | 8.0/10 | Well-organized; consider extracting workflow |
| `checklist.md` | 8.5/10 | Comprehensive for China; missing limitations, FAIR data, contribution clarity |
| `output-template.md` | 9.0/10 | Professional template, clear structure |
| `disciplines/cs-ai.md` | 7.0/10 | Good baseline; misses theoretical/applied split, compute reporting, ethics |
| `disciplines/life-sciences.md` | 9.5/10 | Excellent — experimental design, statistics, nomenclature, data submission |
| `disciplines/engineering.md` | 8.5/10 | Solid simulation/measurement coverage |
| `disciplines/medicine.md` | 9.0/10 | Strong CONSORT/STROBE coverage |
| `disciplines/chemistry.md` | 8.5/10 | Good characterization standards |
| `disciplines/physics.md` | 8.5/10 | Solid error analysis coverage |
| `disciplines/social-sciences.md` | 8.5/10 | Good qualitative/quantitative distinction |
| `README.md` | 9.0/10 | Clear, thorough, good comparison tables |
| `README_CN.md` | 9.0/10 | Solid Chinese counterpart |
| Multi-platform setup | 9.5/10 | Excellent platform coverage (6 platforms) |

---

## Suggested Priority Action Plan

| Priority | Action | File(s) to Modify |
|----------|--------|-------------------|
| **P0** | Add limitations chapter review | `checklist.md` → 讨论 |
| **P0** | Add contribution clarity test (one-sentence rule) | `checklist.md` → 创新性 |
| **P0** | Add thin-slicing detection for paper-based PhDs | `checklist.md` → 博士附加检查 |
| **P0** | Add FAIR data principles | `checklist.md` → 维度四 |
| **P1** | Add paragraph-level writing rules | `checklist.md` → 维度二 |
| **P1** | Split CS/AI into sub-field sub-modules | `disciplines/cs-ai.md` |
| **P1** | Add AI/CS broader impact & ethics review | `disciplines/cs-ai.md` |
| **P1** | Add key figure strategic review | `checklist.md` → 图表规范 |
| **P2** | Add accessibility review | `checklist.md` → 维度三 |
| **P2** | Number all checklist items for reference | `checklist.md` |
| **P2** | Add computational budget reporting | `disciplines/cs-ai.md` |
| **P2** | Add international citation style support | `checklist.md` → 参考文献 |

---

## External Standards Referenced

| Standard | Source |
|----------|--------|
| Stanford ETD Guidelines | Stanford University Graduate School of Education |
| MIT Thesis Formatting | MIT Department of Electrical Engineering and Computer Science |
| Cambridge Degree Regulations | University of Cambridge Committee for Graduate Studies |
| NeurIPS Paper Checklist | NeurIPS 2026 Program Chairs |
| ICML Review Guidelines | ICML 2026 Area Chairs |
| ICLR Submission Standards | ICLR 2026 Program Committee |
| FAIR Data Principles | FORCE11 / GO FAIR Initiative |
| Gopen & Swan Writing Principles | Scientific American, "The Science of Scientific Writing" |
| "Thin-Slicing" Rejection Policy | ICML 2026 Policy Update |
| LLM Usage Disclosure | NeurIPS/ICML 2026 Ethical Guidelines |
