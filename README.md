# 季度复盘分析 skill

当前封装：**步骤一 · 数据分析**。步骤二“总结分析”后续单独制作。

## 下载与阅读

- [下载完整安装包 ZIP](quarterly-product-review-skills.zip)：包含完整 skill 目录、流程 HTML、使用说明、指标规则与只读汇总脚本。
- [流程可视化 HTML](step-1-workflow.html)：点击 Raw / Download 下载到本地，用浏览器打开。支持离线流程切换、公式查阅和交付自查。
- [详细使用说明](usage.md)

## 安装

下载完整安装包并解压，把包内 `skills/quarterly-data-analysis` 整个文件夹复制到 `~/.codex/skills/`。如已有同名 skill，先备份比较，不直接覆盖。刷新技能列表或重新启动 Codex 后搜索“数据分析”。

本仓库通过 ZIP 保留安装目录结构，安装时使用 ZIP 内的 skill 文件夹。请勿仅下载一份 SKILL.md 替代完整目录。

## 使用

提供季度分析模板 XLSX 和运营季度复盘 XLSX，发送：

> 使用 $quarterly-data-analysis 按步骤一填写这款季度复盘表，另存数据填写稿，保留原件；问题、方案及总结留空。核对本款全部 SKC、当前商品信息和首图加五张商品图，完成数据和图片显示核验后给我文件。

## 安装包内容

```text
quarterly-product-review-skills/
├── README.md
├── docs/
│   ├── step-1-workflow.html
│   └── usage.md
└── skills/quarterly-data-analysis/
    ├── SKILL.md
    ├── agents/openai.yaml
    ├── references/data-contract.md
    ├── references/wps-images.md
    └── scripts/aggregate.py
```

执行需要正常网页访问、表格编辑/渲染能力及 WPS 或目标应用。辅助脚本需要 Python3 + openpyxl，仅做只读汇总；它不是无人值守的整表填充程序。

## 已确认的关键规则

父级及 SKC 比例均由总分子÷总分母计算；视频完播率=完播次数÷对应视频可见次数。图片默认沿用全部广告口径（含视频），A+共用全部广告转化率，并明确非独立效果。目标严格比较：图片CTR>0.5%、视频CTR>0.7%、CVR>5%、5秒率>8%、完播率>24%、ACOS<25%、ROI>4倍。缺失用“—”且不标色。

交付保持模板和分析栏空白，另存文件；六张图片须在 WPS/目标应用中实际打开核验。本公开仓库不含真实运营报表、商品素材或凭据。
