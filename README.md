# 季度复盘分析 skill

包含两个独立 skill：**步骤一 · 数据填充（原名“数据分析”）** 与 **步骤二 · 总结分析**。步骤二按2026-10-16确认的V6思路封装，2026-10-17发布。

| 区分 | 步骤一：数据填充 | 步骤二：总结分析 |
| --- | --- | --- |
| 技能标识 | `$quarterly-data-analysis`（保持已安装名称） | `$quarterly-summary-analysis` |
| 输入 | 空模板 + 运营季度复盘原始XLSX | 用户补好对标、视频截图的数据填写稿 + 匹配退货报告；有A+截图一并分析 |
| 工作 | 核对父级/SKC数据、线上6张商品图、当前商品信息、指标颜色 | 比较本款/对标图片与A+、分析视频指标和画面、填写问题/方案/总结 |
| 输出 | 数据填写稿；分析栏空白 | 完整分析稿；数据、布局和嵌入图片保留 |
| 不负责 | 不写视觉问题和优化方案 | 不代替步骤一重算或覆盖已确认数据 |

**步骤一已经安装的用户，只安装新增的 `quarterly-summary-analysis` 文件夹即可，不要覆盖步骤一。** 本次没有更改步骤一技能内容，也没有自动安装步骤二到本机。

## 步骤二快速入口

- [步骤二流程可视化 HTML](step-2-workflow.html)：下载后用浏览器打开，离线可读，可勾选交付检查。
- [总结分析 skill完整目录（ZIP内）](quarterly-summary-analysis.zip)
- [步骤二详细使用说明](step-2-usage.md)
- [仅步骤二安装包 ZIP](quarterly-summary-analysis.zip)
- [两步完整安装包 ZIP](quarterly-product-review-skills.zip)

> 使用 $quarterly-summary-analysis 按步骤二分析这份已补图的数据填写稿和匹配退货报告，参考表内双方图片与A+截图，按已确认格式另存完整分析稿，保留原数据和嵌入图片。

## 下载与阅读

- [下载完整安装包 ZIP](quarterly-product-review-skills.zip)：包含完整 skill 目录、流程 HTML、使用说明、指标规则与只读汇总脚本。
- [流程可视化 HTML](step-1-workflow.html)：点击 Raw / Download 下载到本地，用浏览器打开。支持离线流程切换、公式查阅和交付自查。
- [详细使用说明](usage.md)

## 安装步骤一（未安装时）

下载完整安装包并解压，把包内 `skills/quarterly-data-analysis` 整个文件夹复制到 `~/.codex/skills/`。如已有同名 skill，先备份比较，不直接覆盖。刷新技能列表或重新启动 Codex 后搜索“数据分析”。

本仓库通过ZIP保留完整skills目录，安装时复制包内完整skill文件夹。请勿仅下载一份 SKILL.md 替代完整目录。

## 使用

提供季度分析模板 XLSX 和运营季度复盘 XLSX，发送：

> 使用 $quarterly-data-analysis 按步骤一填写这款季度复盘表，另存数据填写稿，保留原件；问题、方案及总结留空。核对本款全部 SKC、当前商品信息和首图加五张商品图，完成数据和图片显示核验后给我文件。

## 安装包内容

```text
quarterly-product-review-skills/
├── README.md
├── docs/
│   ├── step-1-workflow.html
│   ├── usage.md
│   ├── step-2-workflow.html
│   └── step-2-usage.md
└── skills/
    ├── quarterly-data-analysis/       步骤一，保留原版
    └── quarterly-summary-analysis/    步骤二，新增
        ├── SKILL.md
        ├── agents/openai.yaml
        ├── references/workbook-contract.md
        ├── references/approved-example.md
        └── scripts/audit_preservation.py
```

执行需要正常网页访问、表格编辑/渲染能力及 WPS 或目标应用。辅助脚本需要 Python3 + openpyxl，仅做只读汇总；它不是无人值守的整表填充程序。

## 已确认的关键规则

父级及 SKC 比例均由总分子÷总分母计算；视频完播率=完播次数÷对应视频可见次数。图片默认沿用全部广告口径（含视频），A+共用全部广告转化率，并明确非独立效果。目标严格比较：图片CTR>0.5%、视频CTR>0.7%、CVR>5%、5秒率>8%、完播率>24%、ACOS<25%、ROI>4倍。缺失用“—”且不标色。

步骤一交付保持分析栏空白；步骤二填写分析但保留原数据及用户补图。所有图片须在 WPS/目标应用中实际打开核验。本公开仓库不含真实运营报表、商品素材、私人路径或凭据。
