# Budvest 产品设计笔记

> 整理：小登

---

## 三阶段 Agent 架构

来自 Anthropic 的研究：长时间运行的 Agent 需要三阶段分离设计

### 架构图

```
Planner (规划) ──→ Generator (生成) ──→ Evaluator (评估)
     ↓                ↓                    ↓
   任务拆解        心理陪伴回应         质量评估
```

### 各阶段职责

| Agent | 职责 |
|-------|------|
| **Planner** | 分析用户状态、识别情绪信号、规划干预策略 |
| **Generator** | 生成心理陪伴回复（话术、助推建议） |
| **Evaluator** | 独立评估回复质量，确保不偏不倚 |

---

## 核心设计原则

### 1. 分离评估 (Separate Evaluation)

**问题**：Agent 评估自己的工作总是偏乐观

**解决**：让独立的 Evaluator 来评估，而不是自己评自己

**评估维度**（参考 Anthropic 前端设计评测标准）：

| 维度 | 含义 |
|------|------|
| **共情准确度** | 是否准确识别用户情绪？ |
| **助推有效性** | 建议是否能引导用户理性决策？ |
| **话术自然度** | 回复是否自然、不说教？ |
| **风险提示** | 是否适当提示风险、不夸大收益？ |

---

### 2. Context Reset

**问题**：模型在长对话中会"上下文焦虑"，过早收尾

**解决**：定期清空上下文，给 Agent 干净起点

**实现方式**：
- 每隔 N 轮对话或 N 分钟，重置 context
- 通过结构化 artifact 传递状态（当前进度、用户画像、待办事项）

---

### 3. 任务分解 (Decomposition)

**问题**：复杂任务容易让 Agent"跑偏"

**解决**：拆分成可管理的小任务

**Budvest 示例**：
```
用户：我想加仓
  ↓
Planner 分析：用户处于什么情绪？什么偏误风险？
  ↓
Generator：根据情绪类型，选择合适的干预话术
  ↓
Evaluator：这话术是否合适？有没有过度乐观？
```

---

## 参考来源

- [Anthropic: Harness design for long-running apps](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- [Anthropic: Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)

---

*持续更新中...*