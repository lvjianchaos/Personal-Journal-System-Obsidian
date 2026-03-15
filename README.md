# Personal Journal System（Obsidian）

一个基于 Obsidian 的个人日志与复盘系统，覆盖：
- 日记（Daily）
- 周回顾（Weekly）
- 月回顾（Monthly）
- 季度回顾（Quarterly）
- 年度回顾（Yearly）

系统通过 **Templater + Journals + Dataview + Tracker/Chart** 实现自动生成、聚合回顾与可视化统计。

---

## 目录结构

```text
Attachments/
Journal/
  01 Daily/
  02 Weekly/
  03 Monthly/
  04 Quarterly/
  05 Yearly/
Notes/
Templates/
  Daily Note Template.md
  Weekly Note Template.md
  Monthly Note Template.md
  Quarterly Note Template.md
  Yearly Note Template.md
  New Note Template.md
  log Templates/
    log highlight.md
```

> 当前仓库里可能只存在已使用的目录（如 `01 Daily`）。其余目录会在创建对应日志时自动出现。

---

## 核心思路

1. 使用 **Journals 插件**按日期周期创建日志文件。
2. 使用 **Templater 模板**注入 frontmatter、查询块、回顾结构。
3. 使用 **Dataview**汇总任务、高亮、历史同日记录。
4. 使用 **Tracker / Charts**生成评分与习惯可视化。

---

## 已配置插件

### 社区插件（已在仓库配置中声明）
- templater-obsidian
- dataview
- journals
- callout-manager
- obsidian-charts
- heatmap-calendar
- obsidian-tracker
- contribution-graph
- obsidian-style-settings
- obsidian-minimal-settings

### 常用核心插件（建议保持开启）
- File explorer / Search / Backlinks / Graph
- Daily notes / Templates / Command palette
- Outline / Bookmarks / Page preview

---

## 快速开始

1. 安装 Obsidian。
2. 选择 **Open folder as vault**，打开本仓库根目录。
3. 打开设置，确认社区插件可用并启用（若首次打开需允许第三方插件）。
4. 在 Journals 中使用对应命令创建周期日志：
   - `Journal Daily`
   - `Journal Weekly`
   - `Journal Monthly`
   - `Journal Quarterly`
   - `Journal Yearly`

---

## 文件命名与路径规则（Journals）

- Daily：`Journal/01 Daily/YYYY/MM/YYYY-MM-DD.md`
- Weekly：`Journal/02 Weekly/YYYY/MM/YYYY-Www.md`
- Monthly：`Journal/03 Monthly/YYYY/YYYY-MM.md`
- Quarterly：`Journal/04 Quarterly/YYYY/YYYY-QX.md`
- Yearly：`Journal/05 Yearly/YYYY.md`

对应模板位于 `Templates/` 目录。

---

## 每日记录建议流程

1. 早晨创建当日日记，填写 `Plan Pages`。
2. 白天持续记录任务、学习与事件。
3. 晚间填写 `Evening Review`，补全：
   - `#log/day-review`
   - `#memos/good`
   - `#memos/difficult`
   - `#memos/different`
4. 在有代表性的条目打上 `#log/highlight`，供周/月/季/年汇总。

---

## Frontmatter 指标说明（Daily）

常用统计字段：
- `log-sleep-hours`：睡眠时长
- `log-sleep-rating`：睡眠质量评分
- `log-learn-hours`：学习时长
- `log-learn-rating`：学习状态评分
- `log-healthy-eating`：饮食健康评分
- `log-day-rating`：当天总体评分

这些字段会被周/月/季/年的统计模块读取。

---

## 推荐使用习惯

- 所有任务统一保留 `#task` 标签，方便 Dataview 聚合。
- 高亮条目统一使用 `#log/highlight`。
- 个人想法沉淀到 `Notes/`，再通过链接回链到日志。
- 图片与截图放在 `Attachments/`，避免日志目录膨胀。

---

## 可自行扩展

- 在 `Templates/New Note Template.md` 增加你的默认元数据。
- 在 `Templates/log Templates/log highlight.md` 调整高亮记录格式。
- 新增更多习惯字段，并在 Tracker 查询中补充 `searchTarget`。

---

## 版本管理建议

建议结合 Git 定期提交：

- 每日或每周一次提交
- 提交前检查是否包含敏感信息（截图、隐私文本）

---

## License

仅供个人知识管理与日志记录参考。可按需私有化使用与修改。
