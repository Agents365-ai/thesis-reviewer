# 硕士学位论文评审 (Thesis Reviewer)

[English](README.md)

系统化评审生命科学领域硕士学位论文的 AI 编程助手技能。以导师视角提供全方位、结构化的评审反馈，帮助学生在提交前改进论文质量。

## 功能特点

| 功能 | 说明 |
|------|------|
| 全方位评审 | 覆盖学术质量、写作质量、格式规范、数据与结果四大维度 |
| 两阶段流程 | Phase 1 自动深度分析 → Phase 2 交互式精修 |
| 60+ 检查项 | 从实验设计到参考文献格式，全面覆盖 |
| 结构化输出 | 正式评审意见书格式，可直接交给学生 |
| 严重程度标记 | 🔴 严重 / 🟡 需改进 / 🟢 良好，清晰的优先级 |
| 跨章一致性检查 | 研究问题↔结果、方法↔数据、引用↔文献列表 |
| 修改路线图 | 按优先级汇总所有问题，给出修改顺序建议 |
| 生命科学专业性 | 实验设计、统计分析、生物学命名等学科特有要求 |

## 多平台支持

支持所有主流 AI 编程助手平台：

| 平台 | 状态 | 说明 |
|------|------|------|
| **Claude Code** | ✅ 完整支持 | 原生 SKILL.md 格式 |
| **OpenClaw / ClawHub** | ✅ 完整支持 | `metadata.openclaw` 命名空间，依赖检测 |
| **Hermes Agent** | ✅ 完整支持 | `metadata.hermes` 命名空间，标签，分类 |
| **OpenAI Codex** | ✅ 完整支持 | `agents/openai.yaml` 配套文件 |
| **OpenCode** | ✅ 完整支持 | SKILL.md 自动发现 |
| **Pi-Mono** | ✅ 完整支持 | `metadata.pimo` 命名空间，标签 |
| **SkillsMP** | ✅ 已收录 | GitHub topics 已配置 |

## 工作流程

```
输入 .docx 文件
    │
    ▼
[预处理] markitdown 转换 → Markdown → 识别章节结构
    │
    ▼
[Phase 1: 自动深度分析]
    ├─ Step 1: 整体扫描（结构完整性、研究问题、全局印象）
    ├─ Step 2: 逐章深入分析（对照 60+ 检查项）
    ├─ Step 2b: 跨章一致性检查
    └─ Step 3: 生成初版评审报告
    │
    ▼
[Phase 2: 交互式精修]
    ├─ 逐章讨论具体问题
    ├─ 追问、调整意见、补充遗漏
    └─ 用户说"完成精修"生成最终版
    │
    ▼
[最终输出] 合并修改 → 保存最终评审意见书
```

## 前置依赖

- `markitdown` MCP — 用于将 .docx 转换为 Markdown

## 技能安装

### Claude Code

```bash
# 全局安装
git clone https://github.com/Agents365-ai/thesis-reviewer.git ~/.claude/skills/thesis-reviewer

# 项目级安装
git clone https://github.com/Agents365-ai/thesis-reviewer.git .claude/skills/thesis-reviewer
```

### OpenClaw / ClawHub

```bash
# 通过 ClawHub
clawhub install thesis-reviewer

# 手动安装
git clone https://github.com/Agents365-ai/thesis-reviewer.git ~/.openclaw/skills/thesis-reviewer

# 项目级安装
git clone https://github.com/Agents365-ai/thesis-reviewer.git skills/thesis-reviewer
```

### Hermes Agent

```bash
# 安装到 research 分类
git clone https://github.com/Agents365-ai/thesis-reviewer.git ~/.hermes/skills/research/thesis-reviewer
```

或在 `~/.hermes/config.yaml` 中添加外部目录：

```yaml
skills:
  external_dirs:
    - ~/myskills/thesis-reviewer
```

### OpenAI Codex

```bash
# 用户级安装
git clone https://github.com/Agents365-ai/thesis-reviewer.git ~/.agents/skills/thesis-reviewer

# 项目级安装
git clone https://github.com/Agents365-ai/thesis-reviewer.git .agents/skills/thesis-reviewer
```

### OpenCode

```bash
git clone https://github.com/Agents365-ai/thesis-reviewer.git ~/.opencode/skills/thesis-reviewer
```

### Pi-Mono

```bash
git clone https://github.com/Agents365-ai/thesis-reviewer.git ~/.pimo/skills/thesis-reviewer
```

### SkillsMP

```bash
skills install thesis-reviewer
```

### 安装路径汇总

| 平台 | 全局路径 | 项目路径 |
|------|----------|----------|
| Claude Code | `~/.claude/skills/thesis-reviewer/` | `.claude/skills/thesis-reviewer/` |
| OpenClaw | `~/.openclaw/skills/thesis-reviewer/` | `skills/thesis-reviewer/` |
| Hermes Agent | `~/.hermes/skills/research/thesis-reviewer/` | 通过 `external_dirs` 配置 |
| OpenAI Codex | `~/.agents/skills/thesis-reviewer/` | `.agents/skills/thesis-reviewer/` |
| OpenCode | `~/.opencode/skills/thesis-reviewer/` | — |
| Pi-Mono | `~/.pimo/skills/thesis-reviewer/` | — |

## 使用方法

直接提供论文文件：

```
帮我评审这篇硕士论文：/path/to/thesis.docx
```

或英文：

```
Review this master's thesis: /path/to/thesis.docx
```

技能将自动转换、分析并生成结构化评审报告。

## 触发关键词

- 中文：论文评审、学位论文、审阅论文、论文修改意见、硕士论文、毕业论文
- 英文：thesis review、dissertation review、thesis feedback

## 输出文件

| 文件 | 说明 |
|------|------|
| `{filename}-converted.md` | 转换后的 Markdown 文本 |
| `{filename}-review-draft.md` | Phase 1 初版评审报告 |
| `{filename}-review-final.md` | 最终评审意见书 |

## 评审维度

### 1. 学术质量
摘要、绪论/文献综述、材料与方法、结果、讨论、结论、创新性 — 包含实验设计、样本量、对照组、生物学重复等学科特有检查。

### 2. 写作质量
章节间逻辑连贯性、论证严密性（论点-论据-论证）、学术语言规范、中英文摘要质量。

### 3. 格式规范
章节完整性、图表规范（编号、标题、分辨率、三线表）、参考文献格式一致性、缩略词、生物学命名规范（基因名斜体）。

### 4. 数据与结果
图表类型选择、误差线/置信区间、统计检验方法（参数/非参数）、p 值标注、多重比较校正、图表质量（坐标轴、图例、色盲友好）、可重复性。

## 文件说明

- `SKILL.md` — **核心文件**，所有平台加载的技能指令
- `checklist.md` — 四大维度评审检查清单（SKILL.md 评审时加载）
- `output-template.md` — 评审意见书输出模板（SKILL.md 生成报告时加载）
- `agents/openai.yaml` — OpenAI Codex 专用配置
- `README.md` — 英文文档（GitHub 首页显示）
- `README_CN.md` — 本文件（中文文档）

## 已知限制

- **需要 markitdown MCP**：技能依赖 markitdown MCP 工具进行 .docx 转换。如未安装，需手动将论文转为 Markdown。
- **超长文档**：超过 8 万字的论文可能需要多轮读取。逐章分析的设计已缓解此问题。
- **格式检测**：部分格式问题（图片分辨率、页眉页脚）无法从 Markdown 转换中完全检测，需人工检查。
- **输出语言**：评审意见书使用简体中文输出，适用于中国高校学位论文评审场景。

## 许可证

MIT

## 支持作者

如果这个技能对你有帮助，欢迎支持作者：

<table>
  <tr>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/wechat-pay.png" width="180" alt="微信支付">
      <br>
      <b>微信支付</b>
    </td>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/alipay.png" width="180" alt="支付宝">
      <br>
      <b>支付宝</b>
    </td>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/buymeacoffee.png" width="180" alt="Buy Me a Coffee">
      <br>
      <b>Buy Me a Coffee</b>
    </td>
  </tr>
</table>

## 作者

**Agents365-ai**

- Bilibili: https://space.bilibili.com/441831884
- GitHub: https://github.com/Agents365-ai
