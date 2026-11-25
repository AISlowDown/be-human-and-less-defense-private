# Be Human and Less Defense

面向中英文学术写作的语言与证据校准 skill。适用于论文、学位论文、审稿回复和科研申请，帮助减少空泛措辞、重复句式和不必要的防御性表述，同时保留作者风格、技术内容、数据、引用与必要限制。

An academic-writing skill for English and Chinese prose. It reduces formulaic language and unnecessary defensive wording while preserving scientific meaning, evidence, citations, and the author's voice.

## 主要用法 / Workflow

- **从结果起草**：先核实数据与主张，直接生成清楚、具体、有证据支持的表述。
- **润色已有文本**：先列逐项修改表，收到作者决定后再应用；用户明确要求直接编辑时遵照执行。
- **长文稿**：按章节审阅，保留跨章节术语、数字和引用的一致性。
- **与看图说话大师配合**：`results` 负责科学解释，本 skill 负责从第一稿开始的学术表达。

This workflow does not invent results, strengthen unsupported claims, remove necessary uncertainty, or promise to evade AI-use disclosure requirements.

## 安装 / Installation

本仓库公开可访问，无需申请仓库权限。仓库名沿用历史的 `-private` 后缀，但安装目录及调用名仍为 `be-human-and-less-defense`。

```bash
git clone https://github.com/AISlowDown/be-human-and-less-defense-private.git \
  ~/.codex/skills/be-human-and-less-defense
```

若目标目录已存在，请先对比或备份现有版本。也可把本仓库文件复制到支持 `SKILL.md` 的其他代理环境的技能目录。

This repository is publicly accessible. The `-private` suffix is historical. Keep the installed directory name `be-human-and-less-defense` so sibling skills can resolve it.

## 示例 / Examples

```text
使用 $be-human-and-less-defense 检查这段 Results。
保留数字、引文和必要限制，先给逐项修改建议。

Use $be-human-and-less-defense to draft a concise explanation of these results.
State the comparison and evidence directly without adding unsupported claims.
```

## 文件 / Files

| 文件 | 用途 |
| --- | --- |
| `SKILL.md` | 完整写作与修改规则 / Main instructions |
| `references/proposals.md` | 修改建议表及示例 / Edit-proposal guidance |
| `LICENSE` | 原有许可与来源声明 / Existing license and attribution |

`SKILL.md` 已内嵌“学术直说”的核心规则。同级 `plain-academic-writing` 是可选的扩展参考；单独安装本 skill 不依赖它。配套分析 skill 见 [Result Explainer / 看图说话大师](https://github.com/AISlowDown/results)。

## 来源与许可 / Attribution and License

保留原有 [LICENSE](LICENSE)：MIT，Copyright (c) 2026 AIScientists-Dev。源文件注明其基于 [blader/humanizer](https://github.com/blader/humanizer) 并吸收 [ARMS](https://github.com/koaeraser/ARMS) 的相关规范。

This repository preserves the installed skill snapshot and its existing attribution. The original MIT notice is retained without assigning new authorship.
