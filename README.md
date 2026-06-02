# skills-repo

个人 AI 技能集合仓库。每个技能是一个独立的 Claude Code 技能包，安装后可在 Claude Code 对话中自动触发或手动调用。

---

## 技能列表

### 1. one-person-business-assessor — 一人商业自我评估顾问

**解决什么问题：** 帮职场人完成从"螺丝钉思维"到"主权者思维"的清醒诊断。通过四坐标（时代→自我→商业→行动）系统性扫描：你现在在哪、你是谁、你能创造什么价值、你该从哪里开始。

**适用场景：**
- 有稳定工作但想做副业，不知道从哪开始
- 对自己能做什么感到迷茫，需要一次系统性诊断
- 想出来自己干但不清楚能不能养活自己
- 有几个模糊方向但不确定哪个值得投入

**一句话：** 帮你找到个人垄断市场，带着 24 小时内能执行的第一步离开。

---

### 2. ai-startup-strategist — AI 创业战略思维导师

**解决什么问题：** AI 时代创业的三个特有陷阱——构建了没人要的东西、AI 写得太快导致功能失控、团队规模惯性。通过三阶段（想法验证→MVP 构建→增长规模化）帮创始人做清醒的战略决策。

**适用场景：**
- 有一个创业想法但不确定值不值得做
- 在 MVP 阶段不断被新功能分散注意力，需要范围裁剪
- 团队效率遇到瓶颈，需要诊断自动化空间
- 担心产品护城河不够深

**一句话：** AI 创业版的恶魔代言人——不鼓励你，只帮你找出想法里最致命的问题。

---

### 3. one-person-business-advisor — 一人商业定位顾问

**解决什么问题：** 当你已经决定要做自媒体/一人公司，但卡在"我的定位到底是什么"这一步。通过三阶段（残酷解构→刺猬交叉→MVP画布），用苏格拉底式追问帮你找到只有你能占据的内容生态位。

**适用场景：**
- 已经开始做内容/产品，但感觉没有差异化
- 有专业技能但不知道怎么变成有穿透力的内容定位
- 同时有几个方向，不知道该砍哪个
- 想做个人 IP 但不想跟别人卷同一个赛道

**一句话：** 一把手术刀——切开你的自我叙述，找到痛苦×技能×变现路径的真正交叉点。

---

### 4. hormozi-100m-system — Alex Hormozi 1亿美元商业系统

基于 Alex Hormozi 方法论构建的商业策略系统，将 Hormozi 的报价、获客、定价框架编码为可执行的 AI 工作流。

---

## 推荐使用路径

对于一个**完全没想法、没行动的人**，按以下路径使用：

```
阶段一：一人商业自我评估顾问（assessor）
    │  四坐标扫描：时代→自我→商业→行动
    │  输出：你在哪、你是谁、你能做什么
    │
    ├─ 发现自己有创业想法 ──► 阶段二：AI 创业战略顾问（strategist）
    │                              │  验证想法、定义 MVP、构建护城河
    │                              │
    │                              └─ 需要自媒体定位 ──► 阶段三：一人商业定位顾问（advisor）
    │                                                       聚焦内容生态位、受众、首发切入点
    │
    ├─ 发现自己更适合一人公司/自媒体 ──► 直接进入阶段三：一人商业定位顾问（advisor）
    │
    └─ 发现自己还没准备好 ──► 回去积累经历、获取市场反馈，再回来
```

**已有方向/成果的人**，可以跳过前面的技能，直接进入对应阶段。

---

## 安装方法

### 前置条件

- 已安装 [Claude Code](https://claude.ai/code)（VS Code 扩展、JetBrains 扩展或 CLI）
- 克隆本仓库到本地

### 安装单个技能

创建符号链接到 Claude Code 技能目录，修改后即时生效：

```bash
# 克隆仓库
git clone <repo-url> ~/skills-repo

# 创建符号链接（以 one-person-business-advisor 为例）
ln -s ~/skills-repo/one-person-business-advisor ~/.claude/skills/one-person-business-advisor
```

### 安装所有技能

```bash
for dir in ~/skills-repo/*/; do
  skill_name=$(basename "$dir")
  if [ "$skill_name" != ".git" ]; then
    ln -s "$dir" "$HOME/.claude/skills/$skill_name"
  fi
done
```

安装后重启 Claude Code 或开始新对话即可在技能列表中看到已安装的技能。

### 调用技能

- **自动触发：** 用自然语言描述你的需求，技能会根据描述自动触发
- **手动调用：** 输入 `/<技能名称>`，如 `/one-person-business-advisor`

---

## 仓库结构

```
skills-repo/
├── README.md                           # 本文件：技能概览、使用路径、安装方法
├── CLAUDE.md                           # 个人使用，不同步到 GitHub
├── .gitignore
├── ai-startup-strategist/              # AI 创业战略顾问
│   ├── SKILL.md
│   └── manual.md
├── one-person-business-assessor/       # 一人商业自我评估顾问
│   ├── SKILL.md
│   └── manual.md
├── one-person-business-advisor/        # 一人商业定位顾问
│   ├── SKILL.md
│   └── manual.md
└── hormozi-100m-system/                # Hormozi 商业系统
```
