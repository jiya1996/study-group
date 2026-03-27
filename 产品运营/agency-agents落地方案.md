# agency-agents 自媒体运营落地方案

> 基于 agency-agents + 小登能力，构建双账号内容生产线

---

## 一、需求对齐

### 账号一：小何学AI
- 内容：AI 实战日记 + 小白方法论
- 来源：日常学 AI 用 AI 的真实经历
- 需要：素材收集、选题、初稿

### 账号二：投资心理观
- 内容：心理陷阱 + 大师心理模型 + 个人日记
- 来源：投资心理学知识 + 个人投资心理记录
- 需要：案例研究、初稿、选题库

---

## 二、Agent 角色配置

### 🎨 内容写作 Agent（核心）

| Agent | 用途 |
|-------|------|
| **Content Writer** | 生成公众号初稿（投资心理观） |
| **Technical Writer** | 写小何学AI的方法论文章 |
| **Researcher** | 研究投资心理学案例、KOL观点 |
| **Storyteller** | 把复杂概念写成故事 |

### 🔍 信息搜集 Agent

| Agent | 用途 |
|-------|------|
| **News Analyst** | 追踪 AI 行业动态 |
| **Financial Analyst** | 追踪金融科技新闻 |
| **Trend Spotter** | 发现 GitHub/HackerNews 热门 |

---

## 三、工作流设计

### 工作流 A：小何学AI 内容生产

```
你日常用AI ↓
    ↓
灵感捕手（素材收集）↓
    ↓
创作筛选器（21:00自动）↓
    ↓
Content Writer 生成初稿↓
    ↓
你修改打磨 ↓
    ↓
发布公众号
```

### 工作流 B：投资心理观 内容生产

```
选题库（12+心理偏差）↓
    ↓
Researcher 搜集案例↓
    ↓
Storyteller 生成初稿↓
    ↓
你修改打磨↓
    ↓
发布公众号
```

---

## 四、具体配置

### 4.1 安装 agency-agents

```bash
cd /root/.openclaw/workspace/skills
git clone https://github.com/msitarzewski/agency-agents.git
```

### 4.2 配置小登的 Agent 角色

在对话中让小登扮演特定角色：
- "用 Content Writer 的风格帮我写一篇..."
- "用 Researcher 的方式查一下..."

### 4.3 定时任务（可选）

| 时间 | 任务 | 内容 |
|------|------|------|
| 21:00 | 创作筛选 | 筛选次日选题 |
| 手动 | 初稿生成 | 根据素材生成初稿 |

---

## 五、工具联动

| 工具 | 用途 |
|------|------|
| 小登（我） | 整体协调 + 复杂内容生成 |
| agency-agents | 专业化 Agent 角色 |
| GitHub Trending | 项目素材来源 |
| 定时推送 | 资讯汇总 |

---

## 六、执行步骤

### 第一步：安装 agency-agents
```bash
git clone https://github.com/msitarzewski/agency-agents.git
```

### 第二步：配置角色 prompt
让小登扮演 Content Writer / Researcher / Storyteller

### 第三步：测试生成
- 用小何学AI素材测试生成方法论文
- 用投资心理观选题测试生成案例文

### 第四步：嵌入工作流
配合灵感捕手 + 创作筛选器形成完整生产线

---

## 七、预期效果

| 场景 | 效果 |
|------|------|
| 你日常发灵感 | 自动分类存入素材库 |
| 需要写文章 | 触发 Agent 生成初稿 |
| 资讯推送 | 自动追踪 + 汇总 |

---

*需要我帮你安装 agency-agents 并配置吗？*