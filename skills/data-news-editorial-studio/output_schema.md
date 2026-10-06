# Data News Output Schema

本文件规定审核稿与成品的交付内容。按实际作品形态输出，不把内部过程件冒充最终成品。

## 通用审核稿

### A. 项目摘要

- 主题与作品形态
- 目标读者与发布场景
- 一句话中心判断
- 当前状态：`RESEARCH`、`DRAFT`、`NEEDS_REVIEW`、`READY` 或 `DELIVERED`

### B. 选题与叙事

- 选题价值与信息增量
- 主标题候选 3 个、副标题 1 个
- 文章结构与各模块职责
- 完整文案或用户指定深度的文案版本

### C. 数据来源总表

每条关键数据列出：

| 字段 | 内容 |
|---|---|
| data_id | 唯一编号 |
| claim | 支撑的结论 |
| value | 数值与单位 |
| period | 数据时间 |
| geography | 地域范围 |
| sample | 样本与对象 |
| definition | 统计口径 |
| source | 来源机构与原始标题 |
| published_at | 发布时间 |
| source_url | 原始链接 |
| freshness | 新鲜度状态 |
| usability | `CONFIRMED`、`NEEDS_REVIEW`、`SOURCE_CONFLICT` 或 `REJECTED` |

### D. 一图一口径映射

按图号列出结论、数据、口径、来源、是否跨来源、可比性判断和限制。不可比的数据不得被标记为 `READY`。

### E. 图表目录与单图设计卡

每张图包含：

- 图号与所属模块
- 结论式标题与口径副标题
- 图表类型与视觉母版
- 完整锁定数据
- 重点数字与编辑动作
- 来源备注
- Image-2 视觉资产需求
- 数据核验状态与视觉核验状态

### F. Visual Style Lock

完整列出画布、网格、背景、配色、字体、图表语法、插画、装饰、来源样式、参考图使用范围和禁用项。

### G. 质检结果

- 数据与口径检查
- 文案与结论检查
- 视觉一致性检查
- 尺寸、清晰度与导出检查
- 未解决问题和需要用户决定的事项

## 长图型交付规范

用户选择长图型或超长数据新闻时，本节为强制规范。

### 1. 必交成品

1. **一张完整长图母版**：优先 PNG，建议宽度 2160px，高度按内容自适应，作为 2× 高清母版。
2. **发布副本**：需要平台发布时，从母版高质量缩放为 1080px 宽；不得用发布副本反向放大生成母版。
3. **交付清单与 QA 记录**：写明尺寸、格式、文件大小、数据核验、100% 检查、200% 检查、接缝检查和视觉一致性结果。

内部 4–6 个模块和单独视觉资产属于过程件，除非用户要求，不作为最终长图分开交付。最终成品必须是一张连续图片。

### 2. 母版要求

- `format`: 默认 `PNG`；除非用户明确要求，不以有损 JPEG 作为唯一母版。
- `width`: 优先 `2160px`。
- `height`: 由正文、8–10 张图或实际内容量决定，不为凑固定高度压缩字号。
- `scale`: `2x_master`。
- `color`: 全部模块使用相同色彩空间和背景色值。
- `text`: 标题、正文、关键数字、标签和来源在最终画布中以真实文字排版后再栅格导出。
- `seams`: 无可见拼接缝、色差、边距跳变、字体跳变或内容截断。

### 3. 明确禁止的交付路径

- 不交付 Word 排版长图。
- 不把 Word 当作长图源文件或母版。
- 不采用“Word → PDF → 渲染页面 → 拼成长图 PNG”。
- **PDF 路径当前搁置**：不作为长图中间件，不作为默认交付物，也不把 PDF 页面拼接结果作为长图方案。
- 不把 4–6 张模块图、分页文件或多张截图冒充“一张完整长图”。
- 不把“已导入可画”或“可画页数正确”当成交付完成；在可画未通过正式导出与清晰度实测前，不将其列为默认生产工具。

若用户另外要求 DOCX，它是独立报告交付物，不参与长图生产。若用户以后重新要求 PDF，先把它作为独立实验项验证稳定性，再决定是否恢复相关交付规范。

### 4. 长图交付清单模板

```yaml
output_mode: long_infographic
status: READY
master:
  file: <name>_long_infographic_2x.png
  format: PNG
  width_px: 2160
  height_px: <actual>
  scale: 2x_master
publish_copy:
  file: <name>_long_infographic_1080.png
  width_px: 1080
  height_px: <actual>
  status: PROVIDED | NOT_REQUESTED
modules:
  count: <4-6 or actual>
  delivery_role: INTERNAL_ONLY
source_canvas:
  format: <actual editable format>
  status: PROVIDED | RETAINED | NOT_AVAILABLE
layout_tool:
  name: <actual tool or workflow>
  long_canvas_validation: PASS
  note: Canva is not assumed; record actual validation if used
qa:
  locked_data_check: PASS
  style_lock_check: PASS
  full_overview_check: PASS
  original_100_percent_check: PASS
  zoom_200_percent_check: PASS
  seam_check: PASS
  source_legibility_check: PASS
```

### 5. 长图 QA 证据

交付说明必须明确记录：

- 实际像素尺寸与文件格式。
- 全图概览是否存在节奏、密度或风格断裂。
- 100% 原尺寸下，标题、正文、关键数字、标签、单位和来源是否逐项清晰。
- 200% 放大下，是否出现文字锯齿、生成式错字、压缩伪影、色差或拼接缝。
- 8–10 张图或实际图表中的锁定数字是否逐图复核。
- 参考图是否仅按声明范围使用，未污染 `Visual Style Lock`。

任何一项失败，将状态改为 `NEEDS_REVIEW`、`IMAGE_DATA_VALIDATION_FAILED` 或 `VISUAL_QA_FAILED`，返工后重新导出；不得只在说明中承认问题后仍标记 `READY`。

## 其他形态的最小交付

### 一张大海报型

- 单一完整画布母版与发布副本。
- 数据来源、口径映射、Visual Style Lock 和原尺寸检查结果。
- 不拆成交付多张指标卡。

### 链接型

- 可访问链接或本地可运行成品。
- 页面结构、交互说明、数据来源和设备适配范围。
- 对关键交互、移动端阅读、加载失败和数据准确性进行实际检查。

## 文件命名

建议使用稳定、可识别的命名：

- `<topic>_long_infographic_2x.png`
- `<topic>_long_infographic_1080.png`
- `<topic>_data_sources.md` 或用户指定格式
- `<topic>_review_manifest.md`

不要用 `final_final`、`new2` 等不可追踪命名。
