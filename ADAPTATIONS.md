# Fork 适配改写明细（ADAPTATIONS.md）

> 本文档记录本 Fork 与原版（[isjiamu/gzh-design-skill](https://github.com/isjiamu/gzh-design-skill)）的所有差异。

## 📋 改写原则

1. **能力不变**：所有排版能力（6 套主题 + 主题生成器 + 双关卡校验）与原版 100% 一致
2. **合规优先**：AGPL-3.0 强约束下保留原作者署名
3. **发版聚焦**：从学术化章节（理论/方法论）转向发版场景（选题→排版→发布→数据）
4. **私域脱敏**：移除原作者个人联系方式（微信、企业微信群、二维码）

## ✂️ 移除内容（原版 → 本 Fork）

| 原版位置 | 内容 | 移除原因 |
|----------|------|----------|
| 顶部 banner | "甲木 × 摸鱼小李 联名共建" | **保留作为原作者致谢**，但加 Fork 适配声明 |
| 交流群章节 | 扫码加入官方企业微信群 | 原作者私域流量，本 Fork 维护者无管理权限 |
| 联系方式章节 | 微信 `zuiyn_soul` + 备注「gzh-design」 | 原作者个人联系方式 |
| 安装命令 | `npx skills add https://github.com/isjiamu/gzh-design-skill` | 改指向本 fork |
| 底部名片 | "甲木 × 摸鱼小李 公众号名片" | 替换为本 fork 维护者名片 |
| Star History | 指向 isjiamu 仓库 | 改指向本 fork |

## ➕ 新增内容

| 位置 | 内容 | 用途 |
|------|------|------|
| 顶部 | "本 Fork 适配版"声明 | 明确版权关系 |
| 改写对比表 | 原版 vs 本 Fork 7 个对比点 | 让用户快速理解差异 |
| Acknowledgements 章节 | 完整的原作者致谢（含贡献范围） | AGPL-3.0 合规 |
| Roadmap 章节 | 本 Fork 路线图 | 规划后续适配 |
| 本文档 | ADAPTATIONS.md | 改写明细透明化 |

## 🔄 内容调整

| 章节 | 原版 | 本 Fork |
|------|------|---------|
| 核心特性 | 学术化叙述 | 简化为 6 项要点 |
| 设计原则 | 7 条理论 | 4 条聚焦发版 |
| Roadmap | 原作者规划 | **新增本 Fork 路线图** |
| 文档结构 | 学术化引用 | 公众号发版流程化 |

## 🚫 未改写内容（保持一致）

| 内容 | 原因 |
|------|------|
| 6 套主题组件库 | 原作者核心 IP |
| `component_lint.py` | 原作者质量脚本 |
| `validate_gzh_html.py` | 原作者质量脚本 |
| references/ 文档 | 原作者方法论沉淀 |
| LICENSE（AGPL-3.0） | 必须保持 |

## 📜 合规声明

本 Fork 严格遵守 AGPL-3.0 协议：

✅ 保留原作者署名（甲木 × 摸鱼小李）  
✅ 衍生品继续以 AGPL-3.0 开源  
✅ 网络服务开源  
✅ 公开 Fork 来源（[isjiamu/gzh-design-skill](https://github.com/isjiamu/gzh-design-skill)）

## 📝 维护者

- **王嘉亿（itr-del）**
- 联系方式：仅通过 GitHub Issues
- 公众号：见本 Fork 主页底部名片

---

<sub>本 Fork 适配版本由 王嘉亿 (itr-del) 维护 · 原作者 © 2026 甲木 × 摸鱼小李 · AGPL-3.0 License</sub>