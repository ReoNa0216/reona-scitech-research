# ReoNa 科学与技术调研

**reona-scitech-research** 是面向科学与技术研究的 Agent Skill，将文献、补充材料和技术资料转化为有依据的研究判断、方法比较与图文报告。

An Agent Skill for evidence-grounded research across experimental science, computational methods, and engineering systems. The instructions and writing defaults are primarily in Chinese.

## 适用范围

覆盖生命科学、生物医学、药学、化学、材料、AI、计算与计算生物学，以及硬件、自动化和机械。按研究任务选择工作方式：

| 研究任务 | 重点 |
|---|---|
| 机制与证据梳理 | 支持证据、竞争解释、适用条件与未决问题 |
| 实验与干预方法 | 核心原理、操作方法、资源可得性与验证设计 |
| 计算与模型比较 | 数据、基线、评价协议、泛化范围与复现条件 |
| 硬件与工程系统 | 功能、接口、工作范围、集成与系统测试 |

跨领域任务可组合这些方式。机制综述可以以证据关系收尾，方法和系统研究可以进一步形成实施建议。以文本诠释、历史论证、规范判断或纯形式证明为主的任务，应采用相应领域的方法。

## 工作流程

1. **建立问题与约束**：识别目标、研究对象、评价尺度和已有资源，核对当前流程与最新决定。
2. **建立文献版图**：寻找代表研究、成熟方法、近期改进和关键争议，结合领域判断来源质量。
3. **精读证据**：核读正文、Methods、图表和决定性补充材料，记录条件、分析单位、基线与出处。
4. **协同补件**：盘点已有资料；缺件清单包含文献或资源标识、具体附件、用途、下载入口和保存位置；补入后核验并更新状态。
5. **形成判断**：区分原文结果、作者解释与拟议组合，说明适用条件、复现要求及关键权衡。
6. **图文交付**：按对象选择结构、机制、流程、架构或结果图；独立通读语言；需要 PDF 时完成渲染和版式检查。
7. **接续与清理**：记录待讨论问题，维护当前成果与引用，按授权清理废弃文件并保留原始资料和重建依赖。

根据用户任务选择所需流程和交付，使用所在环境的检索、绘图、渲染与执行工具。实验、模型运行和设备操作按本次授权开展。

## 安装与调用

在支持 Agent Skills 的工具中，将本仓库作为一个 skill 目录使用，入口为 [SKILL.md](SKILL.md)。

Codex 的个人 skill 默认位于 `~/.codex/skills/`，可以运行：

```sh
git clone https://github.com/ReoNa0216/reona-scitech-research.git "$HOME/.codex/skills/reona-scitech-research"
```

如果设置了 `CODEX_HOME`，将目标路径改为该目录下的 `skills/reona-scitech-research`。已有同名目录时先检查其内容，避免覆盖本地修改。

在新会话中显式调用：

```text
请使用 $reona-scitech-research，调研以下问题：……
目标与已有条件：……
希望重点比较：……
需要的交付：简短判断／文献比较／图文报告／PDF。
```

也可以直接指定局部任务，例如补读 SI、审计候选方案或调整报告版式。UI 配置保留默认的自动发现方式。

## 使用示例

- **机制研究**：梳理某种细胞状态变化的竞争性机制，比较干预证据、模型差异与尚未解决的问题。
- **药学与材料**：比较不同递送或检测策略，核查完整制备流程、表征方法、作用条件和重复使用负担。
- **AI 与计算生物学**：比较预测模型，重点检查数据独立性、划分与预处理、基线公平性、外部验证和代码复现条件。
- **硬件与自动化**：比较自动操作或测量系统，检查机械与电气接口、控制时序、工作范围、集成资源和真实负载测试。

## 表达与 PDF 默认偏好

- 术语采用领域惯用且读者易懂的表达；必要时保留英文，专用缩写首次解释，常用符号按读者背景处理。
- 图示随对象选择，精确结构、数据和工程细节使用可靠来源及可控工具核对。
- 直接说明结论、证据和实际权衡；正文能独立阅读，避免反复防御与改稿过程叙述。
- 中文 PDF 默认宋体正文与粗体、黑体标题，引号匹配字体；检查表格孤字、分页、图注与符号，渲染后逐页查看。

以上偏好均可由本次用户要求或模板覆盖。具体领域细则按需启用。

## 文件结构

```text
SKILL.md
agents/openai.yaml
references/
  research-and-evidence.md
  fulltext-and-si.md
  writing-and-figures.md
  pdf-delivery.md
  handoff-and-cleanup.md
```

[研究与证据](references/research-and-evidence.md)提供分任务核查；其余参考分别说明[补件](references/fulltext-and-si.md)、[文字与图解](references/writing-and-figures.md)、[PDF](references/pdf-delivery.md)和[接续清理](references/handoff-and-cleanup.md)。

修改后应检查名称和 UI 配置、内部链接以及典型任务的处理方式。结构检查通过与实际研究效果分别评价，使用中出现的问题可通过 Issue 或 Pull Request 反馈。

## 许可证

[MIT](LICENSE) · Copyright (c) 2026 ReoNa0216
