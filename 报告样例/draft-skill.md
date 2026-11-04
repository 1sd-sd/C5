# 技能体检报告 · draft-skill

> skilllens · 2026-11-04 14:24 · 输入 `examples\draft-skill`

## 结论：**50 / 100 · D 级 · FAIL**

还不算一个技能，只是一个想法

## 四维得分

| 维度 | 得分 | 进度 | 未通过 |
|---|---|---|---|
| 触发力（D1） | 14/25 | `███████████░░░░░░░░░` 56% | TRG003, TRG004 |
| 结构（D2） | 20/20 | `████████████████████` 100% | — |
| 可执行（D3） | 0/24 | `░░░░░░░░░░░░░░░░░░░░` 0% | EXE001, EXE003, EXE004, EXE005 |
| 可维护（D4） | 13/25 | `██████████░░░░░░░░░░` 52% | MNT003, MNT004, MNT005 |

## 先改这 5 条

1. **[EXE001] 有代码块或 scripts/** —— 证据：既没有代码块也没有 scripts/，执行细节全靠脑补
   → 怎么改：把关键命令写成 ```bash 块
2. **[EXE003] 输入契约明确** —— 证据：Input 段过于笼统（5 字符，无格式/示例）
   → 怎么改：给出输入格式/字段/示例
3. **[MNT004] 无占位符残留** —— 证据：SKILL.md 仍含占位符：TODO
   → 怎么改：删掉 TODO/待补充 并写实
4. **[TRG003] description 长度 80–1024 字符** —— 证据：description 仅 28 字符（< 80，模型很难判断何时触发）
   → 怎么改：把'做什么+什么时候用+输入输出'压进 80–500 字
5. **[TRG004] description 含触发语与用户原话** —— 证据：description 只描述功能，没有'什么时候用'的触发语
   → 怎么改：加 '适用于/Use when …' 并抄 2 条用户会说的话

## 其余待改项

- [EXE004] 输出契约明确：Output 段没说清产出物的格式 → 给出产出格式与样例
- [EXE005] 有失败路径说明：没有失败路径说明（输入不合规时怎么办） → 补一段'输入不合规时怎么办'
- [MNT003] 有 examples/demo：没有 examples/ 或 demo，别人不知道怎么验证它好用 → 加一个最小可跑示例
- [MNT005] 无垃圾文件：夹带垃圾文件：~$meeting.docx → 打包前删除 ~$/tmp/.DS_Store

## 通过的检查

- ✅ [TRG001] frontmatter 可解析且含 name/description：name='draft-skill', description 28 字符
- ✅ [TRG002] name 为 kebab-case 且与目录名一致：draft-skill
- ✅ [STR001] 有 What/Purpose 段：有 What/Purpose 段
- ✅ [STR002] 有 When to use 段：有 When 段
- ✅ [STR003] 有 Input 与 Output 段：Input/Output 段齐全
- ✅ [STR004] Steps 至少 3 条：3 条步骤
- ✅ [STR005] 说明所需工具/运行时：有 Tools/依赖段
- ✅ [MNT001] SKILL.md ≤ 500 行：33 行
- ✅ [MNT002] 体积分层合理：0KB
- ✅ [MNT006] 无明文密钥：未发现明文密钥

---

分数算法：每条规则有固定权重，按维度归一化；4 条红旗（密钥/无 frontmatter/占位符）会封顶总分。详见 `docs/rules.md`。
