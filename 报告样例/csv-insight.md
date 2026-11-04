# 技能体检报告 · csv-insight

> skilllens · 2026-11-04 14:24 · 输入 `examples\csv-insight`

## 结论：**100 / 100 · A 级 · PASS**

可以直接发布

## 四维得分

| 维度 | 得分 | 进度 | 未通过 |
|---|---|---|---|
| 触发力（D1） | 25/25 | `████████████████████` 100% | — |
| 结构（D2） | 20/20 | `████████████████████` 100% | — |
| 可执行（D3） | 30/30 | `████████████████████` 100% | — |
| 可维护（D4） | 25/25 | `████████████████████` 100% | — |

## 通过的检查

- ✅ [TRG001] frontmatter 可解析且含 name/description：name='csv-insight', description 214 字符
- ✅ [TRG002] name 为 kebab-case 且与目录名一致：csv-insight
- ✅ [TRG003] description 长度 80–1024 字符：214 字符
- ✅ [TRG004] description 含触发语与用户原话：含触发线索 ['适用于', '用于'] + 引号示例
- ✅ [STR001] 有 What/Purpose 段：有 What/Purpose 段
- ✅ [STR002] 有 When to use 段：有 When 段
- ✅ [STR003] 有 Input 与 Output 段：Input/Output 段齐全
- ✅ [STR004] Steps 至少 3 条：5 条步骤
- ✅ [STR005] 说明所需工具/运行时：有 Tools/依赖段
- ✅ [EXE001] 有代码块或 scripts/：2 个代码块
- ✅ [EXE002] 引用的本地文件都存在：4 处引用全部存在
- ✅ [EXE003] 输入契约明确：Input 段 249 字符，含格式或示例
- ✅ [EXE004] 输出契约明确：Output 段给出格式/模板
- ✅ [EXE005] 有失败路径说明：提到失败/边界处理
- ✅ [MNT001] SKILL.md ≤ 500 行：80 行
- ✅ [MNT002] 体积分层合理：2KB
- ✅ [MNT003] 有 examples/demo：有 examples/demo
- ✅ [MNT004] 无占位符残留：无占位符
- ✅ [MNT005] 无垃圾文件：无垃圾文件
- ✅ [MNT006] 无明文密钥：未发现明文密钥

---

分数算法：每条规则有固定权重，按维度归一化；4 条红旗（密钥/无 frontmatter/占位符）会封顶总分。详见 `docs/rules.md`。
