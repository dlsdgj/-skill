# 结构标注

Claude Code 技能：对文章进行**原位结构化标注**，直接在原文中用彩色 HTML 标签标识每个段落的结构功能，插入缺失的结构元素，并附加论证骨架图和结构完整度评估。

## 功能概述

- **原位标注**：修改原文件，不创建新文件，标注围绕原文展开
- **文体自适应**：自动识别科研报道、政策评论、思想史等多种文体，选用对应标注体系
- **彩色标签**：用内联 HTML span 标签标注段落结构功能（发现、结论、思想突破、概念演变等 30+ 标签）
- **补缺失元素**：用 Obsidian callout 插入原文缺失的结构元素（隐含假设、研究局限、反面论证等）
- **论证骨架图**：Mermaid 流程图重构全文论证逻辑链
- **结构完整度评估**：逐项检视各结构类型的覆盖情况
- **双语翻译**：为英文原文添加中文翻译（普通段落格式）

## 触发方式

在 Claude Code 对话中发送：

```
/结构标注 Clippings/某文章.md
```

或任何包含以下关键词的请求：
- "结构标注" / "标注文章结构"
- "用颜色标记" / "结构化标识"
- "分析文章结构"

## 支持的文体

| 文体 | 示例 | 特有标签 |
|------|------|----------|
| 科研报道 | 实证研究新闻（自然科学+社会科学） | 发现、结论、方法、证据、因果机制、调节效应 |
| 政策评论/Op-Ed | 政策分析、智库报告、立法评论 | 核心论点、政策内容、政治分析、方案建议 |
| 思想史 | 哲学史、概念谱系学、观念演变 | 历史节点、思想立场、思想辩论、概念演变、思想突破 |

## 输出结构

标注后的文件包含：

1. **📋 结构标识图例** — 彩色标签速查表
2. **逐段标注** — 标签 span + 中文分析注释（blockquote）
3. **缺失元素 Callout** — 隐含假设、研究局限、概念定义等补充
4. **🧩 全文论证骨架** — Mermaid 流程图
5. **🧩 结构完整度评估** — 覆盖度评估表
6. **🧩 总结** — 3-5 个要点总结

## 标注示例

```markdown
<span style="background:#FFD700; color:#333; ...">💡 思想突破</span>
<span style="background:#E74C3C; color:#fff; ...">🏛️ 思想立场</span>

Nietzsche pulls the rug on the projects of his predecessors...

> "Pulls the rug"是一个生动的隐喻——前人的哲学工程被视为站在一块
> 可以被瞬间抽走的地毯上。三个关键词的递进：abstract logic →
> elaborate metaphysics → God is dead。
```

## 效果展示

### 结构标注前的 Obsidian 阅读视图

![标注效果概览](images/annotation-example-1.png)

### 结构标注后:

![论证骨架图](images/annotation-example-2.png)

## 文件结构

```
结构标注/
├── skill.md                    # 主技能定义（工作流程 + 标注格式规范）
└── references/
    ├── categories.md           # 文体×标签矩阵（30+ 标签的颜色/含义/触发条件）
    └── html-templates.md       # HTML 模板速查（标签、图例、Callout、Mermaid）
```

## 安装

将 `结构标注/` 文件夹放入你的 Obsidian vault 的 `.claude/skills/` 目录：

```
你的Vault/
└── .claude/
    └── skills/
        └── 结构标注/
            ├── skill.md
            └── references/
                ├── categories.md
                └── html-templates.md
```

重启 Claude Code 或重新加载技能即可使用。

## 依赖

- Claude Code（claude.ai/code）
- Obsidian（用于阅读模式下渲染彩色标签和 Callout）

## 许可

本技能为个人知识管理工具，可自由修改和分发。
