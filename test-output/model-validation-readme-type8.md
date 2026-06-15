# Model Validation & Overfitting Detection

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License">
  <img src="https://img.shields.io/badge/type-Science-indigo" alt="Type: Science">
  <img src="https://img.shields.io/badge/validation_layers-5-purple" alt="5 Validation Layers">
  <img src="https://img.shields.io/badge/red_flags-6-critical" alt="6 Red Flags">
</p>

> **你的模型回测看起来很好。但上线就崩。**
>
> 回测好 ≠ 模型好。Model Validation 用 5 层系统化协议告诉你：模型是真的学到了信号，还是记住了噪声。

---

## 安装

```bash
npx skills add model-validation
```

触发：

> "帮我看下这个模型有没有过拟合"
> "validate 这个预测模型"
> "跑一下学习曲线和 ablation"

---

## 5 层验证协议

每层回答一个不同的问题。

### Layer 1: Walk-Forward Backtesting

**问题：模型在未见过的数据上表现如何？**

```
工作流：
1. 按时间切分（时序数据绝不随机打乱）
2. Train [0:t], predict t+1, slide forward
3. 最少 40% 训练，60% 测试
4. 对比 ≥3 个 baseline: Random, Simple Heuristic, Naive
5. 输出：命中率均值、误差分布、逐期变化曲线
```

> **关键约束：时序数据随机打乱 = 数据泄露。这是最常见的过拟合来源。**

---

### Layer 2: Statistical Significance

**问题：模型的表现是统计显著的，还是碰运气？**

```
H₀: 模型 = random / baseline
检验：二项检验（命中数），大样本用正态近似
阈值：p < 0.05 显著，p < 0.01 非常显著
注意：测试多个模型时需做多重检验校正
```

---

### Layer 3: Learning Curve

**问题：给模型更多数据，它会变得更好吗？**

```
工作流：
1. 在 [25%, 50%, 75%, 100%] 训练数据上训练
2. 在固定 holdout 上测试
3. 画出 performance vs training size 曲线

健康信号：单调提升，逐渐趋于平稳
过拟合信号：平台期 或 下降
```

```
Performance
    │
    │     ╭───────  ← 健康：平稳
    │    ╱
    │   ╱
    │  ╱
    │ ╱
    └───────────────── Training size

Performance
    │
    │   ╱╲
    │  ╱  ╲________  ← 过拟合：先升后降
    │ ╱
    │╱
    └───────────────── Training size
```

---

### Layer 4: Component Ablation

**问题：模型的每个组件都有用吗？还是有的在帮倒忙？**

```
一次去掉一个组件，重新归一化权重：

组件去掉后 → 性能提升  → 🚨 HARMFUL（过拟合组件）
组件去掉后 → 性能不变  → 🗑️  DEAD WEIGHT（可以删）
组件去掉后 → 性能下降  → ✅  USEFUL（保留）
```

---

### Layer 5: Stability & Sensitivity

**问题：模型稳定吗？还是换了参数就变了？**

```
稳定性测试：
- 同一训练数据跑 10 次
- 统计唯一输出数量
- 高方差（>30% 唯一）= 随机性主导信号

敏感性测试：
- 每个权重 ±0.1
- 测最大输出变化
- 高敏感（delta > 0.05）= 过拟合到特定参数值
```

---

## 6 条红线

**命中任意一条 = 很可能过拟合：**

| # | 红线 | 为什么可怕 |
|---|------|-----------|
| 1 | 模型**差于**简单 baseline | 你的复杂模型连简单规则都打不过 |
| 2 | p > 0.05 vs random | 统计上不显著——可能只是运气 |
| 3 | 学习曲线随数据增加而下降 | 更多数据 = 更差 —— 过拟合的经典信号 |
| 4 | 去掉某个组件后**性能提升** | 这个组件正在伤害模型 |
| 5 | 权重敏感性 delta > 0.05 | 微小参数变化就导致输出剧烈变化 |
| 6 | 预测稳定性 < 50% | 同一输入多次预测结果都不一样 |

---

## 实现铁律

```
❌ NEVER random-shuffle time-series（制造 look-ahead bias）
❌ NEVER report in-sample score as model performance
❌ NEVER tune hyperparameters on test set
✅ ALWAYS save raw results separate from analysis output
✅ ALWAYS compare against random baseline before claiming success
```

---

## 真实对话示例

```
User: "validate 我的股票预测模型，训练集上准确率 78%"

Agent: "Running 5-layer validation protocol on your model...

Layer 1 (Walk-Forward Backtesting):
→ 训练集 40% (2018-2020), 测试集 60% (2020-2024)
→ Out-of-sample 准确率：58% (vs 78% in-sample)
→ ⚠️ 20% 的 in-sample vs out-of-sample 差距 — 显著

Layer 2 (Statistical Significance):
→ vs random baseline: p = 0.12
→ ❌ 不显著（p > 0.05）— 模型可能不比随机好

Layer 3 (Learning Curve):
→ 25% data: 62% | 50%: 60% | 75%: 57% | 100%: 58%
→ ❌ 数据越多 → 性能越差 — 过拟合经典信号

Layer 4 (Component Ablation):
→ 移除 sentiment 组件后性能提升 +3%
→ ❌ sentiment 组件在伤害模型

Layer 5 (Stability):
→ 10 次运行产生 7 个不同的预测结果
→ ❌ 稳定性 30% — 远低于 50% 阈值

总结：🚨 模型高度过拟合。3 条红线命中（p>0.05、学习曲线下降、组件有害）。
建议：减少特征数量，从最简单的 5 个核心特征重新开始。"
```

---

## 它不做什么

- **不帮你调参** — 只告诉你模型是否有效，不帮你找最优参数
- **不替代领域知识** — 统计检验通过 ≠ 经济意义上有效
- **不保证预测未来** — 验证通过只说明历史规律可能延续，不保证未来不变

---

## License

MIT
