# lishengdan_C5_repo链接

**仓库**：https://github.com/1sd-sd/skilllens （Public，MIT，main 分支）

**一句话**：输入一个 `.skill` 包，输出 0–100 分 + 20 条检查明细 + "下一条该改什么"；离线、零依赖、可进 CI。

**为什么是这个项目**：C4 阶段我一共写了 4 个技能包，全部通过人眼评审。但把其中三个丢进 skilllens 跑，最高只有 83 分——**"人觉得还行"和"结构上真的能用"是两件事**。这个工具就是把那件事变成可机器判定的东西。

## 5 分钟跑起来（实测 1.1 秒）

```bash
git clone https://github.com/1sd-sd/skilllens.git
cd skilllens
python -m skilllens check examples/csv-insight     # → 100/100 A
python -m skilllens check examples --out reports   # 批量 + 三份报告
python -m unittest discover -s tests -v            # 18 项自测
```

只需要 Python 3.9+，**不装任何依赖**（无 PyYAML、无 requests）。

## 仓库构成

| 要素 | 状态 |
|---|---|
| README（含快速开始/示例/结构/评分算法） | ✅ |
| LICENSE（MIT） | ✅ |
| .gitignore | ✅ |
| AI_LOG.md（8 个小节，含两次真 bug 的排查过程） | ✅ |
| ATTRIBUTION.md（6 个来源 + 拿/不拿/改的取舍） | ✅ |
| CHANGELOG.md（1.0.0 / 1.1.0 / 1.1.1） | ✅ |
| CONTRIBUTING.md + Issue 模板 | ✅ |
| CI（GitHub Actions：3.9/3.11/3.13 × Ubuntu/Windows） | ✅ |
| 测试（18 项 unittest，含 dir/zip 同分契约） | ✅ |
| 文档（docs/rules.md：20 条规则的阈值 + 4 条已知局限） | ✅ |
| 示例（3 个包：A 级 / 草稿态 / 低分） | ✅ |
