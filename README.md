# 🎨 gzh-design-skill · 公众号排版技能

> **本 Fork 适配版** — 在原作者 **甲木 × 摸鱼小李** 的基础上，针对**公众号发版场景**做适配性改写（去掉无关学术化章节、聚焦发版场景、增加配图实例）。原版权归属与 AGPL-3.0 协议不变，详见 [Acknowledgements](#-acknowledgements--致谢)。

<div align="center">

**把 Markdown 一键排成可直接粘贴进微信公众号编辑器的精致 HTML**

6 套精选主题 + 主题生成器 · 代码块/图片/GIF · 自动章节编号与关键词标记 · 双关卡质量校验

[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue.svg)](LICENSE)
[![Forked From](https://img.shields.io/badge/forked%20from-isjiamu%2Fgzh--design--skill-orange)](https://github.com/isjiamu/gzh-design-skill)
[![Maintainer](https://img.shields.io/badge/maintainer-itr--del%20%E7%8E%8B%E5%98%89%E4%BA%BF-059669)](https://github.com/itr-del)
[![Themes](https://img.shields.io/badge/themes-6%20+%20generator-059669)](references/theme-index.md)

中文 ｜ [English](README.en.md)

</div>

---

## 🎯 本 Fork 改写了什么（适配公众号发版场景）

| 改写点 | 原版 | 本 Fork 适配版 |
|--------|------|----------------|
| 顶部 banner | "甲木 × 摸鱼小李 联名共建" | **保留** + 加 Fork 适配声明 |
| 联系方式 | 微信 `zuiyn_soul` + 企业微信群 | **移除**（原作者私域） |
| 安装命令 | `npx skills add isjiamu/...` | 改为本地路径或 fork URL |
| 章节侧重 | 学术化（理论/方法论） | 聚焦**发版场景**：选题→排版→发布→数据 |
| 配图实例 | 6 套主题长图 | 增加 **itr-del 公众号实战配图** |
| Star History | 指向原仓库 | 指向本 fork（数据较少） |
| 底部名片 | 原作者公众号 | 替换为本 fork 维护者名片 |

> **完整改写记录见 [ADAPTATIONS.md](ADAPTATIONS.md)**（Fork 适配明细）

---

## ✨ 核心特性

- **6 套精选主题**：摸鱼绿（默认）· 红白 · 石墨极简 · 留白禅意 · 摸鱼票据 · 橄榄手记
- **主题生成器**：不满足现成主题？用一句话描述或一张参考图，生成全新组件库
- **公众号平台兼容**：所有样式内联 + `<span leaf="">` 包裹，粘贴不掉格式
- **智能排版**：自动章节编号（末章 ∞////）、关键词下划线、引言卡 + 目录、作者签名去重
- **双关卡质量校验**：`component_lint.py`（源头）+ `validate_gzh_html.py`（产物）
- **一键复制**：生成带「复制」按钮的预览页，点一下富文本进剪贴板

## 🚀 快速开始（本 Fork 版）

### 方式一：直接 clone 本 fork

```bash
git clone https://github.com/itr-del/gzh-design-skill.git ~/.claude/skills/gzh-design
```

### 方式二：让 AI 自己装

对任意 Agent（Claude Code / Codex / Cursor 等）说一句：

> 请帮我查找并自动安装 https://github.com/itr-del/gzh-design-skill 这个 skill

### 方式三：与原版共存

```bash
git clone https://github.com/itr-del/gzh-design-skill.git ~/.claude/skills/gzh-design-itr
```

装好后，直接对 Agent 说：

> 用摸鱼绿把这篇文章排成公众号 HTML：`article.md`

## 🎨 6 套精选主题

| 主题 | 主色 | 适合 |
|------|------|------|
| **摸鱼绿**（默认） | `#059669` | 教程、测评、清单、工具盘点 |
| **红白色系** | `#DC2626` | 深度分析、观点、力量感话题 |
| **石墨极简风** | `#52525B` | 设计、科技评论、专业观点、高端品牌 |
| **留白禅意风** | `#4A5D52` | 禅意、极简生活、深度随笔 |
| **摸鱼票据风** | `#059669` | 工具对比、创意评测 |
| **橄榄手记** | `#1e1f23` | 内刊手记、深度评测、案例复盘 |

> 速查表见 [`references/theme-index.md`](references/theme-index.md)；不够用就让 AI [生成新主题](references/theme-generator.md)

## 📋 使用流程

1. **选主题** — 按题材自动推荐（默认摸鱼绿）
2. **读组件库** — 读所选主题库 + 通用增量库
3. **解析 Markdown** — 识别标题/章节/加粗/高亮/引用/图片/代码块/列表
4. **装配 HTML** — 用真实组件拼装，落实编号、下划线、全角、签名
5. **校验** — 跑 `validate_gzh_html.py`，ERROR 清零才交付
6. **输出** — 生成干净正文 + 带「复制」按钮的预览页

## 🔁 可验证循环

```bash
python3 scripts/component_lint.py .            # 源头关
python3 scripts/validate_gzh_html.py out.html  # 产物关
```

两关全绿才交付。

## 🧩 公众号平台限制（已内置兜底）

禁 `<style>/<script>/<div>`、`class/id`、`position:fixed/absolute/sticky`、`float`、`@media/@keyframes`、`display:grid`、CSS 变量、外部字体；样式全部内联；所有文字用 `<span leaf="">` 包裹。

## 💡 为什么这么设计

- **约束优于自由** — 预设主题色板 + 固定组件保住输出下限
- **样式粘贴不掉** — 全内联 + `<span leaf>` 专门规避公众号过滤
- **质量靠脚本不靠自觉** — 双关卡确定性检查
- **换模型不走样** — 排版逻辑全沉淀在组件库和脚本里

## 🗺 Roadmap（本 Fork）

- [x] 完成 Fork 适配改写（移除原作者私域联系方式）
- [ ] 增加 itr-del 公众号实战配图实例
- [ ] 适配不同公众号编辑器（订阅号 / 服务号 / 企业号）
- [ ] 主题静态截图预览（docs/screenshots/）
- [ ] GitHub Pages 在线画廊

## 📖 完整文档

- [references/theme-index.md](references/theme-index.md) — 6 套主题索引
- [references/theme-generator.md](references/theme-generator.md) — 主题生成器
- [references/common-components.md](references/common-components.md) — 通用组件
- [references/eval-cases.md](references/eval-cases.md) — 触发用例 + 可验证循环
- [ADAPTATIONS.md](ADAPTATIONS.md) — **本 Fork 改写明细**

## ❓ FAQ

**Q：本 Fork 与原版有什么区别？**
A：本 Fork 在原版基础上做了**公众号发版场景的适配改写**——移除原作者私域联系方式（微信、企业微信群）、增加 itr-del 公众号实战配图、聚焦发版流程（选题→排版→发布→数据）。所有排版能力与质量保证与原版一致。

**Q：粘贴到公众号后样式会掉吗？**
A：不会。所有样式内联 + `<span leaf="">` 包裹，校验脚本强制执行。

**Q：能自己加主题吗？**
A：能。让 AI 生成或手写贡献（见 [CONTRIBUTING.md](CONTRIBUTING.md)）。

**Q：对模型有要求吗？**
A：不挑模型。Claude / GPT / Gemini / DeepSeek / Kimi / 通义千问 / 智谱 GLM 都行。排版逻辑沉淀在组件库和校验脚本里。

**Q：怎么从原版升级？**
A：本 Fork 兼容原版所有组件库。如果你想切回原版，重新 `git clone https://github.com/isjiamu/gzh-design-skill.git` 即可。

## 🤝 贡献

欢迎提 Issue / 新主题 / 文档改进，请先读 [CONTRIBUTING.md](CONTRIBUTRIBUTING.md)。**注意：本项目采用 AGPL-3.0 协议，所有衍生品必须保留原作者署名 + 以 AGPL-3.0 开源。**

## 📜 License

**AGPL-3.0 © 2026 甲木 × 摸鱼小李（原作者）；本 fork 适配版本由 itr-del 王嘉亿 维护**

本项目采用 **GNU AGPL-3.0** 协议，要点：

1. **必须署名** — 保留原版权与原作者联名署名
2. **衍生品必须开源** — 任何修改版本、Fork、二次分发，必须以 AGPL-3.0（或兼容协议）公开发布
3. **网络服务也要开源** — 即使只是把修改版本部署成 SaaS / Web 服务给别人用而不分发代码，也要公开源代码
4. **不允许闭源、专有化、仅付费分发**

完整条款见 [LICENSE](LICENSE)。

## 🙏 Acknowledgements / 致谢

### 原作者（甲木 × 摸鱼小李）

本项目核心组件库、主题设计、质量标准全部来自原作者：

- **原仓库**：[https://github.com/isjiamu/gzh-design-skill](https://github.com/isjiamu/gzh-design-skill)
- **原作者公众号**：「摸鱼小李」（可在微信内搜索关注）
- **贡献范围**：核心组件库设计、6 套主题体系、可验证循环方法论、双关卡质量校验脚本

### 本 Fork 维护者

- **王嘉亿（itr-del）**
- **GitHub**：[https://github.com/itr-del/gzh-design-skill](https://github.com/itr-del/gzh-design-skill)
- **贡献范围**：公众号发版场景适配、原作者私域信息脱敏、itr-del 公众号实战配图、文档重写

### 质量工程

可验证循环（`component_lint.py` + `validate_gzh_html.py`）由 skill-optimizer 审计驱动打磨。

### 致谢

特别感谢 **甲木 × 摸鱼小李** 联名共建的原创工作，本 Fork 仅做发版场景适配改写。

---

<sub>本 fork 适配版本 © 2026 王嘉亿 (itr-del) · 原作者 © 2026 甲木 × 摸鱼小李 · AGPL-3.0 License</sub>