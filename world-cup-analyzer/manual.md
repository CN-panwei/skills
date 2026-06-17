# ⚽ World Cup Analyzer

> 一个专注世界杯赛事的 AI 分析技能，提供比分查询、积分榜、球队综合实力指数(TCR)、单场综合评分(MCR)等能力。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skill](https://img.shields.io/badge/AI-Skill-blue)]()
[![中文](https://img.shields.io/badge/lang-中文-red)]()

## ✨ 这是什么

这是一个**可直接挂载在 AI Agent 上的技能（Skill）**。当用户问起世界杯相关问题时，AI 会自动触发本技能，提供：

| 能力 | 说明 |
|------|------|
| ⚽ **实时比分** | 查询单场比赛结果、关键事件 |
| 🏆 **小组积分** | 出线形势分析、净胜球对比 |
| 📅 **赛程查询** | 今日/明日比赛时间线 |
| 🔬 **TCR 球队分析** | 百分制综合实力指数，含 6 维度拆解 |
| 🎬 **MCR 比赛评分** | 单场赛事百分制评分，含 5 维度拆解 |
| 👤 **球员数据** | 射手榜、助攻榜、表现统计 |
| ⚖️ **历史对比** | 与历届球队做横向对比 |

## 🎯 TCR / MCR 是什么

- **TCR (Team Comprehensive Rating)**：球队综合实力指数，0-100 分。基于阵容战力、近期状态、战术执行、赛果含金量、关键球员、赛程负荷 6 个维度加权。
- **MCR (Match Comprehensive Rating)**：单场综合评分，0-100 分。基于竞技质量、战术博弈、戏剧性、个人高光、赛事意义 5 个维度加权。

## 📦 包含内容

```
world-cup-analyzer/
├── SKILL.md          # 技能说明书（核心文件，给 AI Agent 读取）
├── README.md         # 项目说明（本文件）
├── LICENSE           # MIT 许可证
├── .gitignore
├── examples/         # 使用示例
│   └── sample-questions.md
└── references/       # 参考资料
    └── data-sources.md
```

## 🚀 快速开始

### 方式 1：直接喂给支持 Skills 的 AI Agent

把 `SKILL.md` 内容复制到你的 AI Agent 的系统提示词或技能库中即可。

### 方式 2：在 Coze / 扣子上传

1. 进入 Coze 技能商店
2. 选择"导入技能"
3. 上传 `SKILL.md` 和必要的元信息
4. 发布到「我的技能」

### 方式 3：在 Claude Code / Cursor 中使用

把 `SKILL.md` 放到项目根目录的 `.claude/skills/` 或 `CLAUDE.md` 同级目录，Agent 会自动读取。

## 💬 触发示例

支持中英文触发，常用提问：

- "昨晚阿根廷对法国比分多少？"
- "B 组出线形势怎么样？"
- "巴西队 TCR 多少？"
- "评价一下德国 vs 日本那场比赛"
- "这届世界杯谁最强？"
- "姆巴佩这届进球数"

更多示例见 [`examples/sample-questions.md`](./examples/sample-questions.md)。

## 📊 数据源

权威源优先，交叉验证原则：

- **FIFA 官网** fifa.com（官方数据）
- **ESPN** espn.com
- **懂球帝** dongqiudi.com
- **直播吧** zhibo8.cc
- **虎扑** hupu.com
- **SofaScore / Flashscore**（xG 数据）
- **Transfermarkt**（身价数据）

完整说明见 [`references/data-sources.md`](./references/data-sources.md)。

## ⚙️ 评分体系

### TCR 球队评分

```
TCR = 25% × 阵容战力 + 20% × 近期状态 + 20% × 战术执行
    + 15% × 赛果含金量 + 10% × 关键球员 + 10% × 赛程负荷
```

| 分数 | 标签 | 含义 |
|------|------|------|
| 90-100 | 🔥 冠军级 | 夺冠大热 |
| 80-89 | ⭐ 争冠级 | 四强候选 |
| 70-79 | 💪 淘汰赛级 | 稳定出线 |
| 55-69 | 👀 搅局者 | 出线有悬念 |
| 40-54 | 📉 陪跑级 | 出线渺茫 |
| < 40 | 🏠 观光级 | 提前准备回家 |

### MCR 比赛评分

```
MCR = 30% × 竞技质量 + 25% × 战术博弈 + 20% × 戏剧性
    + 15% × 个人高光 + 10% × 赛事意义
```

| 分数 | 标签 | 含义 |
|------|------|------|
| 90-100 | 🏆 经典 | 必看，世界杯历史留名 |
| 80-89 | 🔥 名局 | 本届最佳候选 |
| 65-79 | 👍 好球 | 值得看回放 |
| 45-64 | 👌 尚可 | 球迷可看 |
| < 45 | 💤 催眠 | 集锦都不用看 |

## 🤝 贡献

欢迎提交 PR：
- 新增数据源
- 优化评分公式
- 补充使用示例
- 修复数据冲突时的优先级规则

## 📄 许可证

MIT License - 详见 [LICENSE](./LICENSE) 文件。

## 👤 作者

由 [潘爸的第二人生](https://github.com/CN-panwei) 维护。

---

⚽ **Enjoy the World Cup!**
