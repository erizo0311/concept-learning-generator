# Concept Learning Generator · 概念学习资料生成器

> 📚 **作业 1：用 AI 构建个人概念学习资料生成 Skill**
>
> 这是一个用于「深入理解一个新概念」的个人学习仓库。它把「如何学习一个陌生概念」沉淀成一个**可复用的 Skill**，只要是新概念，都能用它自动生成一套结构化的学习资料。

---

## 一、仓库用途

本仓库有两个用途：

1. **存放一个项目级 Skill**（`concept-learning-generator`）：能接收任意新概念，自动生成「学习目标 → 核心问题 → 结构化解释 → 应用案例 → 概念辨析 → 自测题 → 参考来源」7 大模块的学习材料。
2. **存放用该 Skill 生成的样例学习资料**：针对 **Agent、大模型的上下文、Skill** 三个概念，各生成了一份 HTML 学习页 + 一份三概念关系图。

> 它不是一次性任务，而是一套**可积累、可复用**的知识生产工具。

---

## 二、仓库结构

```
concept-learning-generator/
├── .workbuddy/
│   └── skills/
│       └── concept-learning-generator/   ← 项目级 Skill 存放处
│           └── SKILL.md                  ← Skill 定义（元数据 + 规范）
├── learning-materials/                   ← 生成的样例学习资料
│   ├── agent.html                        → 概念：Agent（智能体）
│   ├── llm-context.html                  → 概念：大模型的上下文
│   ├── skill.html                        → 概念：Skill（技能）
│   └── concept-relationship.md           → 三概念关系说明（含 Mermaid）
├── README.md                             ← 本文件
└── .gitignore                            ← 排除敏感文件
```

---

## 三、Skill 存放路径

- **Skill 名**：`concept-learning-generator`
- **路径**：`.workbuddy/skills/concept-learning-generator/SKILL.md`
- **类型**：项目级 Skill（本项目专用，跟随仓库走）

---

## 四、如何在 WorkBuddy 中调用它

### 方式 1：自然语言触发
在 WorkBuddy 中打开本仓库，直接说：

```
用 concept-learning-generator 学一下「大模型的上下文」
```

或更完整地指明定制项：

```
概念：Skill
背景：我想理解它和"一次性提示词"有什么区别
难度：进阶
```

WorkBuddy 会自动读取 `.workbuddy/skills/concept-learning-generator/SKILL.md`，把其中定义的
**适用场景 / 输入 / 生成步骤 / 输出结构 / 来源要求 / 自检要求** 注入执行，产出对应学习资料。

### 方式 2：明确指定概念（可换任意概念）
因为是通用 Skill，你也可以换成学别的概念，例如：

```
用 concept-learning-generator 学一下「Transformer」
用 concept-learning-generator 学一下「决策树」
```

流程完全复用，无需修改 Skill。

---

## 五、已生成哪些学习资料

| 文件 | 概念 | 覆盖模块 |
|------|------|---------|
| `learning-materials/agent.html` | Agent（智能体） | 目标/核心问题/解释/案例/辨析/自测/来源 ✅ |
| `learning-materials/llm-context.html` | 大模型的上下文 | 目标/核心问题/解释/案例/辨析/自测/来源 ✅ |
| `learning-materials/skill.html` | Skill（技能） | 目标/核心问题/解释/案例/辨析/自测/来源 ✅ |
| `learning-materials/concept-relationship.md` | 三概念关系 | 关系图 + 两大重点（上下文→Agent，Skill 沉淀知识）✅ |

每一份学习资料都包含作业要求的 5 项要素：
**①个人解释 ②核心机制/组成 ③具体应用场景 ④易混淆问题/使用边界 ⑤可核查来源链接**。

---

## 六、人工核查与修改记录

> 本仓库内容在 AI 生成基础上进行了**人工阅读、理解与核查**，说明如下（也体现了作业对"资料真实、非照搬"的要求）：

| 项目 | AI 生成 | 人工核查 / 修改 |
|------|:---:|------|
| **SKILL.md** | ✅ 起草骨架 | 人工改写为「通用、可复用」设计：明确强调"能接收任意新概念，而非一次性提示词"；补充了「资料来源硬性规定」和「自检清单」。 |
| **agent.html** | ✅ 生成初稿 | 人工核实：Workflow vs Agent 区别参考 Anthropic 官方文章；Agent 循环、组成、边界做了人工重述与校订；来源逐条打开验证真实。 |
| **llm-context.html** | ✅ 生成初稿 | 人工核实：长上下文"中间易丢"结论匹配《Lost in the Middle》论文；明确区分"上下文 vs 长期记忆"；来源逐条验证。 |
| **skill.html** | ✅ 生成初稿 | 人工核实：Skill 的组成、加载机制、与提示词/工具/上下文的辨析做了人工梳理；来源逐条验证（WorkBuddy 官方文档、Anthropic）。 |
| **concept-relationship.md** | ✅ 生成初稿 | 人工重绘 Mermaid 关系图；重点补足「上下文如何影响 Agent」与「Skill 如何沉淀任务知识」两块；表格内容人工整理。 |

**核查原则**：
- ✅ **来源真实**：所有引用链接均已逐条打开核实（Anthropic 官方博客、arXiv 论文页、WorkBuddy 官方文档），**未使用任何被拦截或伪造的链接**。
- ✅ **内容原创**：概念解释均以「我理解的一句话 + 结构化拆解」方式重述，**未整段照搬 AI 对话原文**。
- ✅ **结构完整**：七份资料全部满足作业要求的 5 项要素与 Skill 的 7 大模块。

---

## 七、安全说明

- 本仓库**不含**任何 API Key、密码、令牌或个人隐私信息。
- `.gitignore` 已排除常见敏感文件与目录（见下）。

---

## 八、环境与复现

- **运行环境**：WorkBuddy（项目级 Skill 由 WorkBuddy 加载执行）。
- **依赖**：SKILL.md 本身无需额外安装；如需把 HTML 打开预览，任意浏览器即可。
- **版本控制**：Git + GitHub，主分支 `main`。

---

© 2026 erizo0311 · 个人作业 1 · 概念学习资料生成器
