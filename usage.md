# 安装与使用

## 安装

下载本仓库内的 `quarterly-product-review-skills.zip` 完整安装包并解压，将 `skills/quarterly-data-analysis` 整个文件夹复制到 Codex 的 `~/.codex/skills/` 中。若已存在同名 skill，先备份并比较版本，不直接覆盖。刷新技能列表或重新启动 Codex 后，搜索中文名“数据分析”。实际刷新方式取决于当前客户端。

也可以把完整安装包提供给 Codex，并说：“解压并安装包内 skills/quarterly-data-analysis 目录下的数据分析 skill。”仓库根目录以 ZIP 保存完整目录。

skill 本身无需独立服务。执行时需要：可读取 XLSX 的运行时、电子表格编辑/渲染能力、正常网页访问能力、用于图片最终显示核验的 WPS 或目标表格应用。Codex 环境应使用已安装的 spreadsheets skill；辅助汇总脚本需要 Python 3 和 openpyxl。不能访问页面或目标应用时，应说明未核验项。

## 开始一次任务

附上两个文件，复制以下提示：

> 使用 $quarterly-data-analysis 按步骤一填写这款季度复盘表。模板：[模板路径]；运营源表：[源表路径]。另存数据填写稿，保留原件；问题、方案及总结留空。核对本款全部 SKC、当前线上商品信息和首图加五张图，完成数据和图片显示核验后给我文件。

同一聊天中连续处理时，可继续提供下一款模板和源表；为避免上下文不明确，新聊天请明确说“步骤一数据填写”。

## 你会收到什么

`{父ASIN}-{SPU}-季度视觉分析-数据填写稿.xlsx`，以及缺失素材或源表差异说明。若同名已存在会另存新版本。视频截图、A+素材和分析文本不属于本步骤，后续补齐再进入总结分析。

## 可视化 HTML

下载仓库根目录的 `step-1-workflow.html`（安装包内位于 docs/） 并用 Chrome/Safari 打开。无需联网或安装前端依赖。点击流程步骤可查看输入、处理和检查；指标表、异常分支与交付检查可直接展开阅读，可打印为 PDF。GitHub 文件预览显示源码属于正常情况；本包没有启用 GitHub Pages。

## 辅助脚本（可选）

```bash
python3 skills/quarterly-data-analysis/scripts/aggregate.py input.xlsx --parent B0EXAMPLE01 --sales-header 广告销售额
```

销售额列名必须来自当前原表真实表头；脚本不猜第50列。输出 JSON 中 null 对应展示“—”，不是零。脚本不采集图片、不改表、不替代与源汇总核对，也不会自动处理真实重复区间。

## 验收

核对父ASIN、SPU、全部SKC；总金额与源明细；比例用合计计算；视频完播以视频可见次数为分母；严格阈值和倍数ROI；六张图真实显示；所有步骤二分析区留空；来源和采集日期已记录；原件未修改。
