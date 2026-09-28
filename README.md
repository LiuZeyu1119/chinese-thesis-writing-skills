# 中文工科硕士论文写作 Skills

用于起草、重组和精修中文工科硕士论文的两个写作技能，适用于支持 `SKILL.md` 的 AI 助手。以下安装与调用示例面向 Codex。

**从自己的研究材料出发写作，而不是套写参考论文。** 以“研究问题—技术机制—对应证据”组织论证，保留公式、数据、引用、必要假设和实际研究状态。

## 两个技能怎么选

| Skill | 适用任务 | 核心内容 |
|---|---|---|
| [`engineering-thesis-writing-zh`](skills/engineering-thesis-writing-zh/SKILL.md) | 不绑定学校的中文工科硕士论文写作 | 摘要、绪论、方法、实验、结论的论证职责；凝练的学术表达 |
| [`bjtu-master-thesis-writing-zh`](skills/bjtu-master-thesis-writing-zh/SKILL.md) | 北京交通大学工科硕士论文 | 在研究写作基础上区分学硕/专硕规范，并组织学校要求、参考论文经验和作者要求 |

两个技能可以分别安装，不互相依赖。北交大论文优先使用专用版，其他院校优先使用通用版并提供相应学校规范；不必让两个技能同时改同一段。

## 主要能力

- 从研究目标、方法、代码说明、推导及实验材料起草正文。
- 建立摘要、研究内容、方法章节、实验与结论之间的对应关系。
- 将验证结果放在其支持的贡献附近，不把“完成实验”凑成方法创新。
- 精简重复解释和对话式表达，保留必要技术条件与贡献归属。
- 将调试、启动命令和归档细节移至附录或作者记录。
- 核对中英文摘要的贡献、数值及研究状态；按需检查导出页面。

这些技能提供写作指导，不自带 LaTeX 编译器、PDF 原文、实验数据或文献数据库，也不保证论文通过评审。材料不足时列出具体待补项，不编造结果、引用或统计结论。

## 安装

### 在 Codex 中安装

将下面的请求发送给具有 skill 安装能力的 Codex：

```text
请从 GitHub 仓库 LiuZeyu1119/chinese-thesis-writing-skills 安装：
skills/engineering-thesis-writing-zh
skills/bjtu-master-thesis-writing-zh
保留已经存在的同名技能，若需要替换先说明差异。
```

### 使用 Codex 自带安装脚本

如果本机存在 `.system/skill-installer`，可运行：

```bash
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo LiuZeyu1119/chinese-thesis-writing-skills \
  --path skills/engineering-thesis-writing-zh skills/bjtu-master-thesis-writing-zh
```

安装器遇到已有同名目录会停止，避免直接覆盖个人修改。缺少该安装器时，可克隆仓库，将所需技能的完整目录放入客户端使用的 skills 目录；复制前检查是否已有同名目录。

## 使用示例

### 通用论文精修

```text
使用 $engineering-thesis-writing-zh，根据我的研究材料精修方法章。
明确每个模块的输入、处理机制、数学表达和输出用途。
保留公式、数据、引用和必要假设，删除重复解释与对话式表达。
直接交付修改后的正文，待确认问题单独列出。
```

### 北交大论文写作

```text
使用 $bjtu-master-thesis-writing-zh，按北京交通大学硕士论文规范修改摘要。
根据本研究实际贡献组织创新点，每项紧接属于该贡献的验证结果。
不要从参考论文复制句子，不把基础版本结果写成完整方法的验证。
学位类别、学院要求或材料不明确时，先指出会影响本次修改的事项。
```

创新点数量由实际研究和作者要求决定，“三个创新点”不是对所有硕士论文的统一要求。

## 目录

```text
skills/
├── engineering-thesis-writing-zh/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
│       ├── sample-analysis.md
│       ├── abstract-patterns.md
│       └── revision-examples.md
└── bjtu-master-thesis-writing-zh/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
        ├── bjtu-requirements.md
        └── writing-methods.md
```

## 规范与资料来源

北交大要求核验日期为 **2026-09-27**，来源及条款定位见 [规范记录](skills/bjtu-master-thesis-writing-zh/references/bjtu-requirements.md)。学校入口仍链接不同年份的规范和模板，核验日期不代表文件发布年份；提交前应核对学院、学位类别及最新要求。

写作经验来自三篇工科硕士论文的结构与语言分析，题名和物理页定位见 [样本分析](skills/engineering-thesis-writing-zh/references/sample-analysis.md)。仓库只包含写作规则与分析摘要，不分发原论文、学校模板、个人论文或实验材料。

本项目为独立整理，非北京交通大学官方项目，也不代表学校或参考论文作者背书。资料归属见 [NOTICE](NOTICE.md)。

## 许可证与反馈

本仓库原创技能指令和说明采用 [MIT License](LICENSE)。链接的学校文件、参考论文及第三方资料仍适用各自权利与条款。

欢迎通过 Issues 或 Pull Requests 提交可核验的规范更新、论证改进与语言修订。涉及院校要求时请给出官方来源、适用对象和日期；请勿上传含个人信息或未获授权的论文全文与实验数据。
