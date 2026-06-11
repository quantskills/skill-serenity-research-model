# Serenity Research Model

> Reverse-engineer Serenity's public X/Twitter research model from historical posts.

> 基于 Serenity（`@aleabitoreddit`）公开历史推文，反推出他的投资研究模型。

Language / 语言： [English](#english) | [中文](#中文)

## English

### What This Is

`serenity-research-model` is a portable agent skill for analyzing Serenity's public research behavior on X/Twitter.

It is not a copy-trading tool and it does not verify private profit claims. It turns public posts into structured research evidence:

- ticker-level public signals
- themes and subthemes
- supply-chain roles
- bottleneck claims
- evidence types
- catalysts
- risks
- quote context
- forward-return evaluation when local price data is available

The skill was built from a real Serenity MVP run and can be imported or adapted into agent environments such as Claude Code, OpenClaw, Codex-style skill systems, or other local AI agent runtimes.

### Why Serenity

Serenity became influential because his public posts often focus on under-covered AI infrastructure bottlenecks rather than only obvious mega-cap winners.

The cleaned research model shows that his strongest forward-looking thesis posts are concentrated around:

- Photonics / CPO
- InP and optical components
- AI data-center supply chains
- memory / HBM
- power and grid infrastructure
- robotics / physical AI

### What The Skill Does

The core script is:

```powershell
python .\scripts\serenity_mvp.py
```

Main commands:

```powershell
python .\scripts\serenity_mvp.py extract --posts <posts.csv> --out <out_dir>
python .\scripts\serenity_mvp.py clean --signals <signals.csv> --posts <posts.csv> --out <out_dir>
python .\scripts\serenity_mvp.py auto-review --signals <manual_review_queue.csv> --out <out_dir>
python .\scripts\serenity_mvp.py evaluate --signals <signals.csv> --prices <price_dir> --out <out_dir>
python .\scripts\serenity_mvp.py report --signals <signals.csv> --out <out_dir>
```

### Key Outputs

Typical outputs include:

- `signals.csv`
- `theme_summary.csv`
- `manual_review_queue.csv`
- `quote_relationships.csv`
- `signals_auto_reviewed.csv`
- `signals_forward_clean.csv`
- `signals_high_quality_thesis.csv`
- `signal_evaluation.csv`
- `serenity_model_report.md`

### Real MVP Reports

The first real-data MVP run produced several Chinese reports:

- `serenity_research_model_zh.md`
- `serenity_forward_research_model_zh.md`
- `serenity_high_quality_thesis_template_zh.md`
- `forward_return_recalculation.md`

These reports are run artifacts, not required runtime dependencies.

### Data Boundary

This skill only analyzes public material. It does not:

- verify Serenity's private portfolio
- prove real trading profits
- scrape private or restricted X data
- recommend trades
- treat public return claims as audited records

### Repository Hygiene

Do not bundle raw X exports, large CSVs, cloned repositories, or downloaded price files into the skill package.

Recommended to commit:

- `SKILL.md`
- `README.md`
- `scripts/`
- `references/`
- `agents/openai.yaml`
- lightweight Markdown reports

Recommended to keep outside Git:

- raw X exports
- large generated CSVs
- downloaded price histories
- cloned third-party source repositories

---

## 中文

### 这是什么

`serenity-research-model` 是一个通用 Agent 平台 Skill，用来分析 Serenity（X 账号 `@aleabitoreddit`）的公开研究行为。

它不是跟单工具，也不是用来证明 Serenity 真实赚了多少钱。它做的是把公开推文拆成结构化研究证据：

- ticker 级别公开信号
- 主题和子主题
- 供应链位置
- bottleneck / chokepoint 论点
- 证据类型
- 催化
- 风险
- 引用关系
- 如果有本地价格数据，还可以做 forward return 评估

这个 skill 已经基于 Serenity 真实公开数据跑过 MVP，可以导入或改造到 Claude Code、OpenClaw、Codex 风格 Skill 系统，以及其他本地 AI Agent 运行环境。

### 为什么是 Serenity

Serenity 的价值不在于“喊过哪些票”，而在于他的公开高质量 thesis 经常围绕 AI 基建里的供应链瓶颈，而不是只看最显眼的大市值公司。

清洗后的模型显示，他最强的前瞻研究主要集中在：

- Photonics / CPO
- InP 和光学组件
- AI 数据中心供应链
- memory / HBM
- 电力和电网基础设施
- robotics / physical AI

### 这个 Skill 能做什么

核心脚本：

```powershell
python .\scripts\serenity_mvp.py
```

主要命令：

```powershell
python .\scripts\serenity_mvp.py extract --posts <posts.csv> --out <out_dir>
python .\scripts\serenity_mvp.py clean --signals <signals.csv> --posts <posts.csv> --out <out_dir>
python .\scripts\serenity_mvp.py auto-review --signals <manual_review_queue.csv> --out <out_dir>
python .\scripts\serenity_mvp.py evaluate --signals <signals.csv> --prices <price_dir> --out <out_dir>
python .\scripts\serenity_mvp.py report --signals <signals.csv> --out <out_dir>
```

### 典型输出

常见输出包括：

- `signals.csv`
- `theme_summary.csv`
- `manual_review_queue.csv`
- `quote_relationships.csv`
- `signals_auto_reviewed.csv`
- `signals_forward_clean.csv`
- `signals_high_quality_thesis.csv`
- `signal_evaluation.csv`
- `serenity_model_report.md`

### 已完成的真实 MVP 报告

第一版真实数据 MVP 已经产出中文报告：

- `serenity_research_model_zh.md`
- `serenity_forward_research_model_zh.md`
- `serenity_high_quality_thesis_template_zh.md`
- `forward_return_recalculation.md`

这些报告是运行结果，不是 Skill 运行时必须依赖。

### 数据边界

这个 skill 只分析公开材料。它不做：

- 不验证 Serenity 私人持仓
- 不证明真实交易收益
- 不抓取私有或受限 X 数据
- 不推荐交易
- 不把公开收益声明当成审计业绩

### GitHub 上传建议

不要把原始 X 导出、大型 CSV、克隆仓库、下载价格数据打包进 Skill。

建议上传：

- `SKILL.md`
- `README.md`
- `scripts/`
- `references/`
- `agents/openai.yaml`
- 轻量 Markdown 报告

建议放在 Git 外部：

- 原始 X 导出
- 大型生成 CSV
- 下载价格数据
- 克隆的第三方仓库

### 一句话总结

`serenity-research-model` 是“白毛股神”公开研究方法的逆向工程工具。

它把公开推文里的噪声、引用和复盘剥离掉，提取真正可复用的供应链研究框架。

## License / 许可证

This project is licensed under the GNU General Public License v3.0. See [LICENSE](LICENSE).

本项目使用 GNU General Public License v3.0（GPL-3.0）协议发布，详见 [LICENSE](LICENSE)。
