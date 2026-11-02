# 制作知识卡片（文章 → 原子卡片） · Knowledge Card Maker

> 把粘贴的文章或 .md/.txt 文件提炼成 5-8 张原子知识卡片，每张含标题、核心知识、简明解释、例子或自测题

![License](https://img.shields.io/badge/license-MIT-5a6b4f)
![Type](https://img.shields.io/badge/type-Agent%20Skill-4a6b7c)
![Platform](https://img.shields.io/badge/platform-WorkBuddy%20%7C%20Claude%20Code-b8935a)

## 它解决什么问题

读完一篇文章，感觉懂了，一周后什么都不剩。原因是没有把「文章的结构」重组成「你的结构」。

这个 skill 把一段连贯的文章拆成 5–8 张**原子卡片**，每张只承载一个知识点，用固定四段结构表达，便于复习、归档与二次创作。

## 卡片结构

```markdown
## 卡片 N｜<标题>

**核心知识**：一句话说清这个知识点
**简明解释**：2-3 句，讲清为什么成立
**例子 / 自测**：一个具体场景，或一个能自测的问题
```

## 七步流程

1. 确认输入（粘贴文本，或 `.md` / `.txt` 文件）
2. 通读，标出所有候选知识点
3. 合并同质内容，删掉重复
4. 压缩到 5–8 张，按逻辑顺序排序
5. 按原文体裁调整抽卡重点（论述文抽论点、教程抽步骤、案例抽因果）
6. 逐张撰写
7. 自检后输出

## 质量红线

- 每张卡片必须**脱离原文也能读懂**
- 一张卡片只讲一件事，讲两件就拆开
- 不写「很重要」「值得深思」这类空转结论
- 数字、专有名词、出处必须与原文一致，不确定就标注
- 5–8 张是硬区间：3 张说明抽得太粗，12 张说明没有合并

## 能力边界（会明确告知）

| 支持 | 不支持 |
|---|---|
| 粘贴纯文本 | 网页抓取 |
| `.md` / `.txt` 文件 | PDF / Word / 图片 OCR |
| 输出 Markdown | Anki 导出、图形界面 |

## 相关仓库

- [`article-to-knowledge-cards`](https://github.com/px-pangu/article-to-knowledge-cards) — 同一思路的增强版，带 `app/` 可视化与测试用例
- [`wechat-deposit`](https://github.com/px-pangu/wechat-deposit) — 面向微信聊天内容的卡片化

## 目录结构

```
knowledge-card-maker/
├─ SKILL.md      用途 · 边界 · 七步流程 · 质量红线 · 输出格式 · 完整示例
└─ agents/       子代理配置
```

## 许可

MIT © 2026 px-pangu


## 安装

把本仓库整个目录放进 Agent 的 skills 目录即可，目录名保持仓库名：

```bash
# WorkBuddy
git clone https://github.com/px-pangu/knowledge-card-maker.git ~/.workbuddy/skills/knowledge-card-maker

# Claude Code
git clone https://github.com/px-pangu/knowledge-card-maker.git ~/.claude/skills/knowledge-card-maker
```

装好后在对话里说一句相关的话就会自动触发，也可以用 `@knowledge-card-maker` 显式点名。

