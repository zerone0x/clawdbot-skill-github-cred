---
name: github-cred
description: Analyze GitHub user contribution quality. Evaluates owned repos, external contributions, output quality, and social influence. Triggers on "github cred", "含金量", "analyze github".
author: zerone0x
version: 1.0.0
---

# GitHub Cred — 含金量分析

分析 GitHub 用户的开源贡献含金量。

## 触发词

- `github cred <username>`
- `分析 <username> 的 GitHub`
- `<username> 含金量`

---

## 四层评分体系

### Tier 0 — 自有高星项目 (30%)

| 指标 | 计分 |
|------|------|
| 拥有 ≥10k⭐ 项目 | +30 |
| 拥有 ≥5k⭐ 项目 | +20 |
| 拥有 ≥1k⭐ 项目 | +10 |

*Cap: 30分。自己造轮子 > 给别人贡献*

### Tier 1 — 外部高星项目贡献 (30%)

| 指标 | 计分 |
|------|------|
| ≥100k⭐ 项目 merged PR | +4/PR |
| ≥10k⭐ 项目 merged PR | +2/PR |
| ≥1k⭐ 项目 merged PR | +1/PR |
| 非 trivial (>20 lines) | ×1.5 |

*Cap: 30分*

### Tier 2 — 产出质量 (20%)

| 指标 | 计分 |
|------|------|
| Merge rate ≥70% | +10 |
| Merge rate ≥50% | +7 |
| 代码占比 ≥80% | +5 |
| 项目多样性 ≥10 repos | +5 |

*Cap: 20分*

### Tier 3 — 社区影响力 (20%)

| 指标 | 计分 |
|------|------|
| ≥5k followers | +20 |
| ≥2k followers | +15 |
| ≥1k followers | +12 |
| ≥500 followers | +8 |
| ≥200 followers | +5 |
| ≥100 followers | +3 |
| <100 followers | +1 |

---

## 评级

| 等级 | 分数 | 描述 |
|------|------|------|
| S | 95+ | 传奇 — 顶级项目作者 + 核心贡献者 + 大V |
| A+ | 85-94 | 大神 — 高星项目作者 或 顶级项目贡献者 |
| A | 70-84 | 资深 — 有实质贡献的活跃开发者 |
| B | 50-69 | 活跃 — 稳定贡献者 |
| C | 30-49 | 入门 — 有贡献但不深入 |
| D | <30 | 新手 |

---

## 输出格式

```
📊 GitHub Cred: @username

🏆 XX/100 (等级)

▸ Tier 0 自有项目 (XX/30)
  👑 repo1 ⭐XXk

▸ Tier 1 外部贡献 (XX/30)
  🔨 org/repo ⭐XXk × N PRs

▸ Tier 2 产出质量 (XX/20)
  📈 Merge rate XX% | 代码占比 XX%

▸ Tier 3 社区影响 (XX/20)
  👥 X,XXX followers
```

---

## 两条路到 A+

- **作者路线** — 造一个 10k+ stars 项目
- **贡献者路线** — 深耕多个顶级项目（100k+ stars）

混合型最强。
