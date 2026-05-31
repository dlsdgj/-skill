# HTML 模板速查

## 一、内联标签

### 单个标签
```html
<span style="background:{HEX}; color:{TEXT}; padding:1px 6px; border-radius:3px; font-weight:bold; font-size:0.85em;">{EMOJI} {名称}</span>
```

### 并列标签（同一段落多个结构功能）
```html
<span style="background:{HEX1}; color:{TEXT1}; padding:1px 6px; border-radius:3px; font-weight:bold; font-size:0.85em;">{EMOJI1} {名称1}</span> <span style="background:{HEX2}; color:{TEXT2}; padding:1px 6px; border-radius:3px; font-weight:bold; font-size:0.85em;">{EMOJI2} {名称2}</span>
```

### 扩展标签（需要附加说明时）
```html
<span style="background:{HEX}; color:{TEXT}; padding:1px 6px; border-radius:3px; font-weight:bold; font-size:0.85em;">{EMOJI} {名称}（{简短补充}）</span>
```

例：`⚙️ 方法（数据来源）`、`🧩 结论（不可逆性）`、`⚖️ 调节效应（首次出现）`

## 二、图例表

在文档开头插入。样式：标准 Markdown 表格，标签列使用 HTML span。

```markdown
## 📋 结构标识图例（{文体名称}版）

| 标识 | 颜色 | 含义 |
|------|------|------|
| {EMOJI} {名称} | <span style="background:{HEX}; color:{TEXT}; padding:0 5px; border-radius:3px; font-weight:bold;">{颜色名称}</span> | {一句话含义} |
```

图例表按标签在文中的重要程度排序，最核心的标签排在最前面。表后接 `> [!tip] 阅读提示` 简要说明文体特征。

## 三、Callout 类型

### 插入缺失假设
```markdown
> [!warning] 💡 隐含假设
> **该研究/论证隐含了一个关键假设：[具体内容]。** [为什么这个假设重要/可能被质疑]。
```

### 插入研究局限
```markdown
> [!warning] ⚠️ 研究局限
> **原文未明确讨论的局限：**
> 1. **[局限名称]**：[具体说明]
> 2. **[局限名称]**：[具体说明]
```

### 插入概念定义
```markdown
> [!info] 📐 缺失元素：关键概念定义
> 本文使用"[术语]"但未给出正式定义。补充如下：
> - **[术语]**：[定义]，通常指 [操作标准]
```

### 插入反面论证
```markdown
> [!question] 🏛️ 缺失元素：[具体缺失内容]
> [补充的反面视角或其他解释]
```

### 插入结构对比
```markdown
> [!info] ⚔️ 辩论结构对比（补充）
> 
> | 维度 | 甲方 | 乙方 |
> |------|-----|-----|
> | 核心主张 | ... | ... |
```

### 阅读提示（图例表后）
```markdown
> [!tip] 阅读提示
> 本文是一篇**{文体名称}**。标注适用于全文。
```

## 四、Mermaid 节点样式

### 基础节点格式
```
A["{EMOJI} {标签}<br>{节点描述}"]
```

### 高亮关键节点（在 flowchart 末尾）
```
style X fill:{HEX},color:{TEXT}
```

- 核心结论节点：fill:#FF6B6B,color:#fff
- 思想突破节点：fill:#FFD700,color:#333
- 概念区分节点：fill:#0984E3,color:#fff
- 缺失/隐含节点：虚线边框（用 `-.->` 箭头）

### 箭头类型
- 逻辑推进：`-->`
- 隐含关系/未检验路径：`-.->`
- 标签（可选）：`-->|"标签文字"|`

## 五、结构完整度评估表

```markdown
## 🧩 结构完整度评估

| 结构类型 | 原文覆盖 | 点评 |
|----------|----------|------|
| {EMOJI} {名称} | ✅/⚠️/❌ | {一句话} |
```

覆盖度标记：
- ✅ 充足：原文有多处明确体现
- ⚠️ 部分/弱：有提及但不充分
- ❌ 缺失：原文完全没有

## 六、总结 Callout

```markdown
> [!summary] 总结
> [3-5 个要点，突出本文最独特的结构特征]
```

总结的典型角度：
- 本文的核心论证结构是什么（线性因果？范式转换？概念谱系？）
- 最重要的 1-2 个结构发现（如"调节效应是主线""研究者主动管理预期"）
- 最关键的缺失元素
- 如果有多篇对比，可简要提及本文在系列中的位置

## 七、跨文体对比表（可选）

```markdown
## 🧩 N篇文章结构类型对比

| 维度 | 文章1 | 文章2 | 文章3 |
|------|-------|-------|-------|
| 文章类型 | ... | ... | ... |
| 核心论证结构 | ... | ... | ... |
| 独特结构 | ... | ... | ... |
| 关键缺失 | ... | ... | ... |
```

## 八、段落间距

段落之间使用**单个空行**自然分隔，不使用 `---` 分隔线（YAML frontmatter 的 `---` 边界符除外）。翻译段落紧跟在英文原文之后，之间不留多余空行。

## 九、内联 callout 注释（引述内部分析）

分析研究者引述的内部结构时，使用缩进的 blockquote：
```markdown
> 引述内部分析：
> - <span style="...">标签</span> "[引语片段]"——[分析]
> - <span style="...">标签</span> "[引语片段]"——[分析]
```
