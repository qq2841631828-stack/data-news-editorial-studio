# 数据新闻编辑工作室

`data-news-editorial-studio` 是用于 Codex 的中文数据新闻 Skill，当前版本为 **3.0.0**。

它把选题、来源核验、叙事、图表设计、视觉生产和交付检查组织为一个可复用流程。支持连续长图、单张大海报以及网页/H5 形式；交互产品需要另行落实和验证网页实现。

## 在另一台电脑安装

在已安装 Codex 的电脑上，把本仓库的 GitHub 链接发给 Codex：

```text
请使用 skill-installer，从这个 GitHub 仓库安装
skills/data-news-editorial-studio 目录中的 Skill：
https://github.com/qq2841631828-stack/data-news-editorial-studio
```

Skill Installer 支持从 GitHub 仓库及子目录安装。安装完成后，确认技能列表出现 `data-news-editorial-studio`；如果没有出现，重启 Codex 再检查。私有仓库需要新电脑上的账号具备读取权限。

如果电脑上已经存在同名 Skill，请先比较版本并保留备份，再决定更新，避免覆盖个人修改。

也可以手动下载或克隆本仓库，将 **整个** `skills/data-news-editorial-studio` 文件夹复制到当前 Codex 版本识别的个人技能目录。新版本官方文档列出 `~/.agents/skills`；部分安装环境使用 `$CODEX_HOME/skills`，默认通常为 `~/.codex/skills`。以该电脑的实际配置和识别结果为准。

官方说明：[Build skills](https://learn.chatgpt.com/docs/build-skills)。

## 使用示例

```text
使用 data-news-editorial-studio，围绕我提供的主题和资料，
先核验数据来源并形成中心判断，再制作一张完整的高清数据新闻长图。
```

```text
使用 data-news-editorial-studio，审核这份数据新闻的统计口径、
数据时效、来源可追溯性、叙事结构和图表表达，列出需要修正的内容。
```

## 核心规则

- 先明确中心判断，再安排文案和图表；区分来源事实、计算结果与编辑推断。
- 每张图采用明确且可比较的统计口径，核心数据必须可追溯。
- 当前现象优先使用近 1–2 年数据；官方数据滞后时说明实际年份与发布时间。
- 视觉制作先锁定全篇风格；数字、单位、年份和来源逐项核验。
- 长图最终为一张连续图片，优先使用 2160px 宽母版，并完成概览、100% 和 200% 检查。
- 长图不使用 Word 排版；PDF 和 Canva 不作为默认长图生产路径。

## 能力依赖

这份 Skill 提供工作方法，不会随安装自动开通外部工具或服务。

- 资料研究需要可用的网页检索、来源访问或用户提供的资料。
- 原版视觉流程指定使用 **Image-2**。若运行环境无法提供或确认这个模型，应明确报告并暂停依赖它的视觉生成，不能静默改用其他模型。
- 正式长图需要支持真实文字、精确定位、连续画布和高清 PNG 导出的工具或渲染流程。
- 网页/H5 成品需要实际的开发、预览和交互验证能力。

## 文件

```text
skills/data-news-editorial-studio/
├── SKILL.md          # 触发规则、工作流与验收条件
├── visual_rules.md   # 视觉规则与长图高清生产规范
└── output_schema.md  # 审核稿、成品与 QA 交付规范
```

三个技能文件完整保留原版 v3.0.0 内容，配套文件使用相对路径引用，无本机绝对路径依赖。
