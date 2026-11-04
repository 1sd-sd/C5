# C5 提交成果 · skilllens（技能包体检器）

> **挑战**：C5 GitHub Repository ｜ **完成级别**：Level 全项（含 CI / CHANGELOG / CONTRIBUTING / Issue 模板）
> **仓库**：https://github.com/1sd-sd/skilllens （Public · MIT · 2 次提交 · main）
> **日期**：2026-11-04 ｜ **作者**：lishengdan

---

## 一句话

**输入**任意 `.skill` 包，**输出** 0–100 分 + 20 条检查明细 + "下一条该改什么"。离线、零依赖、可进 CI。

## 30 秒验证

```bash
git clone https://github.com/1sd-sd/skilllens.git && cd skilllens
python -m skilllens check examples/csv-insight     # → 100/100 A（实测 1.1 秒）
python -m unittest discover -s tests               # → 18 项 OK
```

## 这个目录里有什么

| 文件 | 说明 |
|---|---|
| `skilllens/` | 完整仓库（含 .git，可 `git push` 继续迭代） |
| `lishengdan_C5_repo链接.md` | 仓库地址 + 构成清单 |
| `lishengdan_C5_AI日志.md` | AI 使用骨架（完整版在仓库 AI_LOG.md） |
| `lishengdan_C5_拿来说明.md` | 6 个来源 + 拿/不拿/改的取舍 |
| `lishengdan_C5_复盘AAR.md` | R̂ vs R，3 次失败分析，3 条可复用教训 |
| `报告样例/` | **4 个真实技能包** × 3 种格式（md/html/json）的体检报告 |

## 真实回归结果（这个项目最能说明问题的部分）

| 包 | 分数 | 等级 | 主要问题 |
|---|---|---|---|
| `csv-insight`（示例，满分基准） | 100 | A | — |
| `skill-explainer`（C4 真实提交） | 83 | B | 缺 Output 段、缺 When 段 |
| `wechat-doc-mapper`（C4 真实提交） | 82 | B | 缺 Input 段 |
| `challenge-submission-checker`（作者自用） | 60 | C | description 1046 字符超上限；正文残留 TODO |
| `draft-skill`（草稿态样本） | 50 | D | 占位符 + 垃圾文件 |
| `my-skill`（低分样本） | 39 | D | 结构缺失、无代码、无示例 |

> 结论：**通过人眼评审 ≠ 结构化可执行**。这三个真实包里没有一个是"不能用"，但没有一个达到 A。

## 关键设计（为什么不是又一个关键词检查器）

1. **三态判定**：pass / fail / N/A。N/A 不进分母——否则"没引用文件"会被白扣分。
2. **红旗封顶**：密钥泄露 → 45 分，无 frontmatter → 40 分，占位符残留 → 60 分。
3. **同分契约**：同一内容在目录 / zip / 单文件三种形态下必须同分（有测试守）。
4. **零依赖**：无 PyYAML、无 requests。`clone` 下来就能跑，这是可复现性的下限。
5. **诚实的局限**：`docs/rules.md` 写了 4 条"它做不到什么"。
