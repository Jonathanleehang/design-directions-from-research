# Design Directions From Research

一个面向 Codex、Claude Code、WorkBuddy 等支持 Agent Skills 标准的产品设计方向生成 skill。

它把产品调研报告、竞品分析、用户痛点和设计机会转化为 3 套可比较的产品设计方向，再根据用户选择深化为产品定义、结构与流程、形态/CMF、交互、验证计划和效果图提示词。

## 核心特点

- 先整理证据地图和设计挑战，再开始方案发散
- 默认生成 3 套策略不同的方向，而不是 3 个换名字的方案
- 方向 A 偏问题解决，方向 B 偏体验重构，方向 C 偏差异化探索
- 关键主张区分 `[事实]`、`[观察]`、`[推断]` 和 `[待验证]`
- 先输出方向卡，等待用户选择后再展开完整方案
- 支持方案融合、重新发散、评分比较和被否决方向记录
- 支持工业设计、消费品、家电、数码产品、包装和产品体验概念
- 没有图像生成工具时，仍可输出可直接使用的图像生成提示词

## 安装

### 通用 Agent Skills 安装器

```bash
npx skills add Jonathanleehang/design-directions-from-research -g
```

### Codex

```bash
git clone https://github.com/Jonathanleehang/design-directions-from-research.git \
  ~/.codex/skills/design-directions-from-research
```

### Claude Code

```bash
git clone https://github.com/Jonathanleehang/design-directions-from-research.git \
  ~/.claude/skills/design-directions-from-research
```

### WorkBuddy

优先使用 WorkBuddy 支持的 Agent Skills/GitHub 安装入口。如果当前版本没有 GitHub 安装入口，将仓库目录复制到 WorkBuddy 配置的 skills 目录，并确保 `SKILL.md` 位于 skill 根目录，同时保留 `references/` 子目录。

不同平台的技能目录可能不同；本仓库不依赖某一个平台的专属运行时命令。

## 使用示例

先准备一个调研报告，例如：

```text
调研报告-桌面空气净化器.md
竞品对比表-桌面空气净化器.md
来源记录-桌面空气净化器.csv
```

然后提出：

```text
根据当前文件夹里的桌面空气净化器调研，生成 3 套有明显差异的工业设计方向，重点考虑噪音、清洁维护、桌面占用和年轻用户的视觉偏好。
```

方向预览后，可以继续：

```text
深化方案 B，保留它的低噪音交互和可维护结构，并生成一份适合出效果图的完整设计说明。
```

也可以：

```text
融合方案 A 和 C，但优先控制成本，先列出冲突点、舍弃内容和需要验证的假设。
```

## 推荐输入

- 产品调研报告或竞品分析报告
- 竞品对比表和来源记录
- 用户评论、访谈摘要或问卷结果
- 硬件/元件清单、尺寸、成本和工艺约束
- 品牌调性、渠道、法规或专利边界
- 已经否决的方向和设计决策记录

## 输出

- 方向轮：3 套方向卡，可保存为 `方向轮-<日期>.md`
- 详细方案：`方案-<方案名>.md`
- 设计决策：`design-decisions.md`
- 效果图生成提示词和一致性/禁止项
- 方案验证计划和风险清单

## 工作边界

这是概念探索工具，不是 CAD、工程设计、成本核算、专利检索或可制造性证明工具。效果图只表达设计意图，不能证明尺寸、材料、性能或装配关系已经成立。涉及工程、法规、知识产权和量产时，必须另行验证。

## 参考项目

本项目的流程设计参考了公开 GitHub 项目的通用思路，包括：

- [product-design-three-views](https://github.com/Gayaya999/product-design-three-views)：设计语言、设计状态和多视图一致性
- [zero-to-design](https://github.com/mitaraifail/zero-to-design)：分阶段设计流程、方向轮和反馈迭代
- [design-workflow](https://github.com/jrbrugger/design-workflow)：研究、机会定义、概念选择和设计验证闸门
- [product-teardown-skill](https://github.com/yanliudesign/product-teardown-skill)：证据优先和可行动机会

本仓库没有复制上述项目的代码、图片或专有内容。

## 许可证

MIT License。详见 [LICENSE](LICENSE)。
