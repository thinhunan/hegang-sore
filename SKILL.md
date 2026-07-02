---
name: hegang-score
slug: hegang-score
version: 1.0.0
description: Apply He Gang's six-methodology investment framework—value gear model, fan analysis, industry/company scoring, fund selection, financial reports, and gold pricing—for structured investment analysis.
metadata:
  requires:
    bins: []
---

## When to Use

User asks for investment analysis using 何刚方法论, or mentions: 财富齿轮、扇面模型、价值三象限、何三点、公司打分、基金三步法、财报三维度、黄金价格分析、行业/公司/基金/财报/黄金分析.

Source material: [references/赠品《何刚投资方法论》.pdf](references/赠品《何刚投资方法论》.pdf)

## Quick Reference

| Topic | File |
|-------|------|
| Ch1 价值投资（财富齿轮 + 扇面模型） | [references/ch01-value-investing.md](references/ch01-value-investing.md) |
| Ch2 行业分析（何三点 + 案例） | [references/ch02-industry-analysis.md](references/ch02-industry-analysis.md) |
| Ch3 公司分析（三维度 + 量化打分） | [references/ch03-company-analysis.md](references/ch03-company-analysis.md) |
| Ch4 基金分析（三因素 + 三步法） | [references/ch04-fund-analysis.md](references/ch04-fund-analysis.md) |
| Ch5 财报分析（框架 + 三维度） | [references/ch05-financial-report.md](references/ch05-financial-report.md) |
| Ch6 黄金价格（四大因素） | [references/ch06-gold-price.md](references/ch06-gold-price.md) |
| 公司量化评分表 | [templates/company-score-sheet.md](templates/company-score-sheet.md) |
| 综合分析报告模板 | [templates/investment-analysis-report.md](templates/investment-analysis-report.md) |
| 申万行业分类 | [references/sw-industry.md](references/sw-industry.md) |
| 使用示例 | [examples.md](examples.md) |

## Core Rules

### 1. Route by Asset Type

| 用户意图 | 方法论 | 必读 |
|---------|--------|------|
| 宏观/选股方向/该不该投 | 扇面模型（政策→宏观→基本面） | ch01 |
| 行业赛道判断 | 何三点（规模→链条→竞争） | ch02 |
| 个股/公司价值 | 三维度打分（行业→管理→运营） | ch03 + score sheet |
| 选基金 | 三因素 + 三步法 | ch04 |
| 读财报 | 五部分框架 + 三维度 | ch05 |
| 黄金/贵金属配置 | 四大需求因素 | ch06 |

### 2. Layered Analysis Order

完整投资决策必须自上而下：**政策面指方向 → 宏观面看环境 → 基本面选标的**。不可跳过上层直接给买卖建议。

### 3. Quantify Company Value

公司分析必须输出量化评分（满分 10，三维度各 10 分折算后取均分）。均分 **< 8 分** 从价值投资角度不建议投资。使用 [templates/company-score-sheet.md](templates/company-score-sheet.md)。

### 4. Data Freshness

方法论中的案例数据（如家电、证券、寒武纪等）可能过时。分析时须标注数据日期，并主动获取最新行情/财报（可用 `finance-data-source` 或 `tushare-data` skill）。

### 5. No Direct Trade Advice

输出分析框架与判断依据，不做具体买卖指令。结尾注明：不构成投资建议，决策权在用户。

### 6. Output Format

综合分析使用 [templates/investment-analysis-report.md](templates/investment-analysis-report.md)。单项分析按对应章节结构输出，保留何刚原文的关键模型名称。

## Workflow

```
1. 识别分析对象（宏观/行业/公司/基金/财报/黄金）
2. 读取对应 reference 章节
3. 获取最新数据（如需要）
4. 按模型逐步分析，引用评分标准
5. 输出结构化报告 + 核心结论（3 句话以内）
```

## Traps

| Trap | Fix |
|------|-----|
| 只看财务数据忽略行业/政策 | 先跑扇面模型再深入基本面 |
| 行业好但选了产业链末端公司 | 先何三点定价值点，再选公司 |
| 基金只看去年收益 | 看年化平均收益 + 从业年限 |
| 财报只看利润表 | 权益→经营→现金三维度缺一不可 |
| 用旧案例数据当现状 | 标注时效，拉取最新数据 |
