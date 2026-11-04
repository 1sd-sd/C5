# lishengdan_C5_拿来说明

> 完整版：[skilllens/ATTRIBUTION.md](https://github.com/1sd-sd/skilllens/blob/main/ATTRIBUTION.md)

## 拿了什么（6 个来源）

| 来源 | 拿的部分 | 我怎么改的 |
|---|---|---|
| Anthropic Agent Skills 规范 | frontmatter 语义、kebab-case、description ≤ 1024、SKILL.md ≤ 500 行的分层加载 | 把"规范建议"拆成可机器判定的 2 条规则（触发语 + 引号原话数量 ≥ 2） |
| skill-creator（Anthropic 内置） | "description 要写清 what + when + 用户原话"；metadata → body → references 三层 | 作为 D1 维度的全部依据 |
| ESLint 自定义规则模型 | `rule id + 固定权重 + 证据 + fix` 的输出形态 | 加了 N/A 语义（ESLint 没有）与红旗封顶 |
| Ruff / golangci-lint | 退出码 0/1/2 供 CI 判断 | 加 3 = 读取错误，区分"不合格"和"跑不起来" |
| 自己 C4 的 `challenge-submission-checker` | 空壳检测、垃圾文件、密钥泄露的实现经验 | 重写为独立规则，去掉对 C4 目录结构的耦合 |
| 《程序员修炼之道》broken windows | "占位符残留"这条规则的动机 | 从"建议清理"升级为"封顶 60 分" |

## 明确没拿

- **LLM 语义评审**：会让工具依赖 API key，破坏"clone 下来就能跑"。改放到 C6 的 Web 版做可选层。
- **完整 YAML 解析器**：只支持 frontmatter 子集。
- **别人的评分量表**：0–100 + 等级更利于设 CI 阈值。

## 我加的、别人没有的

1. **N/A 语义**：没有引用文件时不因"引用完整性"扣分。
2. **红旗封顶**：总分 85 但包里有 API key 是荒谬的，因此密钥命中直接封顶 45。
3. **同分契约**：同一内容在"目录 / zip / 单文件"三种形态下必须同分（有测试守）。
