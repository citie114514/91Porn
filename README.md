# 💀 RickBait — 经典钓鱼整蛊页面

> 假装成人网站，点开直接骷髅跳舞一小时 🕺

一个纯前端整蛊恶作剧页面。**无任何真实色情内容、无恶意代码、无追踪、无广告。**  
页面伪装成常见的「成人网站」风格，朋友点击进入并尝试播放视频时，会自动跳转到 / 播放：

- 🎵 **魔性骷髅跳舞 1 小时纯享版**

仅用于朋友间玩笑、整活、整蛊，**禁止用于任何恶意用途**。

---

## ✨ 功能特性

- 🎭 仿钓鱼网站视觉风格（仅界面，**无任何不良内容**）
- 🎬 点击「我已满 18 岁」→ 骷髅跳舞 1 小时
- 🎞️ 原生 HTML5 `<video>` 播放器，自动加载 GitHub Release 视频
- 🌌 粒子连线背景 + 噪点纹理，沉浸感拉满
- 📱 移动端 / 桌面端自适应
- 🧩 纯静态 HTML + CSS + JS，**无后端、无采集、无隐私获取**，可直接部署

## 🚀 快速开始

### 方式一：本地预览

```bash
git clone https://github.com/citie114514/91Porn.git
cd 91Porn
# 直接用浏览器打开 index.html 即可
```

> 也可使用任意静态服务器，例如 `python3 -m http.server 8000`。

### 方式二：部署到 GitHub Pages

1. **Fork** 本项目到你自己的 GitHub 账号
2. 进入仓库 **Settings → Pages**
3. **Source** 选择 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`
4. 等待 1–2 分钟，即可获得公开整蛊链接：`https://<你的用户名>.github.io/<仓库名>/`
5. 把链接发给朋友，等待爆笑（或绝交）现场 😏

> 仓库已内置 [`.github/workflows/static.yml`](./.github/workflows/static.yml)，push 到 `main` 会自动部署。

## ⚙️ 配置说明

页面会从 GitHub Release 拉取视频文件。打开 [`index.html`](./index.html)，修改顶部 `CONFIG` 区块即可：

```javascript
var CONFIG = {
  repo:  "citie114514/91Porn",   // 你的仓库（owner/repo）
  tag:    "latest",                // Release 标签，latest 表示最新
  token: "",                       // 公开仓库留空即可
  exts:   [".mp4",".m4v",".webm",".mov",".mkv"]
};
```

### 上传视频

1. 在你的仓库页面点击 **Releases → Draft a new release**
2. 填写 Tag（如 `1.0.0`），发布 Release
3. 在 Assets 中拖入你的 `.mp4` 文件并发布

### ⚠️ 关于 Token（重要）

| 场景 | 是否需要 Token |
|------|----------------|
| 仓库 **公开**（Public） | ❌ **不需要**，匿名调用即可（限速 60 次/小时/IP，对整蛊页面足够） |
| 仓库 **私有**（Private） | ✅ 需要，但**不要直接写在前端代码里** |

> **安全提醒**：把 GitHub Personal Access Token 写在客户端 HTML 中，等于把它公开给所有访客——任何人按 F12 就能拿到你的 Token 并盗用。私有仓库请通过后端代理（如 Cloudflare Workers / Vercel Functions）转发请求。

## 🛠️ 技术栈

- HTML5 + CSS3（CSS 变量、backdrop-filter、grid/flex）
- 原生 JavaScript（无任何依赖、无构建步骤）
- Canvas 2D 粒子动画
- GitHub REST API（拉取 Release Assets）

## 📁 项目结构

```
.
├── index.html                  # 唯一页面（HTML + CSS + JS 内联）
├── .github/workflows/static.yml  # GitHub Pages 自动部署
├── LICENSE
└── README.md
```

## 🧩 Bug 修复记录（本次优化）

- ✅ 仓库名由 `RickBait` 更新为 `91Porn`（已重命名）
- ✅ 移除不可靠的 `window.close()` 调用，未成年选项改为引导离开
- ✅ 移除会误触关页的 `Esc` 全局快捷键
- ✅ 自定义控制栏精简为原生 `<video controls>`，减少兼容性问题
- ✅ 自动播放策略改为先静音播放 → 尝试取消静音，符合浏览器策略
- ✅ 弹窗在移动端小屏下不再溢出

## 📜 免责声明

本项目**仅用于娱乐、整蛊、玩笑**。

- ❌ 不含任何色情、暴力、违法内容
- ❌ 不收集任何用户信息
- ❌ 不用于诈骗、勒索、恶意骚扰
- ✅ 使用本项目的任何后果由使用者自行承担

作者不对滥用本项目造成的任何法律责任或人际关系破裂负责。请确保在双方都能接受的范围内使用 😄

## 📄 License

[MIT](./LICENSE)
