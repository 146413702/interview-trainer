# 运维面试题库 · 语音模拟面试工具（Interview Trainer）

> 基于个人简历定制的运维 / DevOps 面试刷题工具：题库学习、随机小测、AI 判题、错题集、回合制聊天面试、**语音通话式模拟面试**、PWA 离线应用。

## 📌 在线体验

**https://146413702.github.io/interview-trainer/**

- 手机 Safari 打开 → 分享 → **添加到主屏幕**，即以"App"方式全屏使用（PWA）
- 首次使用语音面试需授权麦克风

## ✨ 功能特性

- **230 道面试题**：14 个分类（Linux/Shell、Git/GitLab、CI/CD、Docker、Nginx、MySQL、Redis、Spring Boot/Java、JVM、网络、监控、安全、K8s、项目综合/HR），答案可直接背诵
- **12 道 1★ 超纲加分题**：🎁 答出加分、答不出不扣分（OverlayFS、runc、eBPF、ZGC、TSDB 等真超纲题）
- **刷题打卡**：已刷/已掌握状态、打卡日历、分类掌握度可视化
- **随机小测**：从未掌握题中抽 5 题，AI 判题打分，不合格自动进错题集
- **错题集 + 历史报告**：薄弱点集中复习，每次小测/面试留档
- **模拟面试（动态题数）**：AI 面试官按临场表现调整题量（约 6~14 题，语音 30 分钟软上限）——答得好深挖加分题、连续答差提前收尾
- **文字模式**：回合制问答，AI 判题评分 + 从题库挑延伸题追问
- **语音通话模式**：AI 语音念题 → 你开口回答（讯飞流式实时转写，边说边出字）→ 手动点"说完了"确认 → AI 才接话，**AI 绝不打断表述**
- **AI 现场追问 + 一键收录**：配 AI Key 后，面试官根据你的回答现场生成追问，可一键收录为新题（自动归类 + 标记 🤖 扩展题，可删除）
- **PWA**：可安装到主屏幕、离线可用
- **数据本地持久化**：进度/错题/配置全部存 localStorage，不经过任何服务器

## 🛠 技术栈

| 模块 | 技术 |
|---|---|
| 前端 | 纯 HTML / JavaScript 单文件应用（零依赖、零构建） |
| 语音识别 | 讯飞开放平台 WebSocket 流式听写 API（实时转写） |
| 语音合成 | Web Speech API（TTS 朗读题目） |
| AI 判题/追问 | OpenAI 兼容接口（默认 DeepSeek），未配 Key 时回退内置规则引擎 |
| 数据存储 | localStorage（本地持久化） |
| PWA | manifest.json + Service Worker（离线缓存） |

## 🚀 快速开始

1. **部署**：将 `index.html` 部署到任意静态托管即可（GitHub Pages / Netlify / Nginx）
2. **配置 AI**（可选但推荐）：进入"AI 配置"填 OpenAI 兼容接口（url / key / model，如 DeepSeek）；或使用带 `#qb_ai=<base64>` 参数的一键导入链接自动写入 localStorage
3. **配置语音 Key**：进入"语音设置"填讯飞 APPID / APIKey / APISecret；或使用带 `#qb_voice=<base64>` 参数的一键导入链接
4. **手机使用**：Safari 打开 → 授权麦克风 → 添加到主屏幕 → 开测

## 📁 目录结构

```
index.html      单文件应用（全部前端逻辑 + 题库数据）
manifest.json   PWA 清单（App 名称/图标/独立窗口）
sw.js           Service Worker（离线缓存，网络优先）
icon-192.png    PWA 图标（192px）
icon-512.png    PWA 图标（512px，含 maskable）
README.md       本文档
```

## 💡 说明

- 题库根据**个人简历**（运维 / DevOps 方向，应届 · 培训机构全栈+AI 小组）与一线运维面试常考点整理
- 纯本地运行，数据不经过任何服务器；API Key 仅存于访问者浏览器 localStorage，仓库不含任何密钥明文
- 意向城市：杭州（相关面试话术已按"互联网/大厂密度高、成长优先"定制）

---

*个人求职准备工具 · 持续迭代中（v7.7）*
