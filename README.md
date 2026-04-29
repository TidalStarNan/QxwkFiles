# 🌐 青翔未阔工作室官网

&gt; 青翔未阔工作室的官方网站，集成了每日壁纸、一言语录、GitHub 下载中心、MC 服务器状态查询、团队成员展示等功能，全部基于静态页面构建，可部署于 GitHub Pages。

## ✨ 主要功能

### 🏠 首页 (`index.html`)
- **全屏必应每日壁纸**：自动加载 1080P 必应每日一图，加载失败时自动降级为占位图
- **随机「一言」**：每次访问随机展示一条励志语录（支持作者与出处显示）

### 📦 下载中心 (`download.html`)
- **多目录标签页**：支持切换不同文件夹（如"一中整合包下载"、"未定文件夹"等）
- **自动拉取文件列表**：通过 GitHub API 读取指定仓库目录，自动生成文件列表
- **智能文件信息**：自动识别文件名中的日期、文件类型、大小，支持排序与图标展示
- **一键下载**：直接调用 GitHub `download_url` 进行下载

### 🎮 MC 服务器状态 (`mc-status.html`)
- **双 API 冗余查询**：优先使用 `mcsrvstat.us`，失败自动切换至 `minecraft-serverhub.com`
- **详细信息展示**：在线状态、当前玩家数 / 最大玩家数、游戏版本、服务器图标
- **MOTD 渲染**：支持彩色 MOTD 的 HTML 渲染与纯文本回退
- **在线玩家列表**：展示当前在线玩家昵称标签

### 👥 关于我们 (`about.html`)
- **成员卡片**：在线获取成员头像（WeAvatar）
- **响应式布局**：完美适配 PC 与移动端

### 🛠️ 错误 / 占位页 (`error.html`)
- **服务状态指示**：可视化展示浏览器、Cloudflare、服务器三层状态
- **UTC 实时时间**：通过 `timeapi.io` 同步并持续刷新 UTC 时间

## 🔌 使用的 API 与服务

| 接口用途 | API 地址 | 备注 |
|---------|---------|------|
| 必应每日壁纸 | `https://uapis.cn/api/v1/image/bing-daily?resolution=1080` | 首页全屏背景图 |
| 一言语录 | `https://v1.hitokoto.cn/` | 首页随机语录 |
| MC 服务器状态 (主) | `https://api.mcsrvstat.us/3/{host}` | Java 版服务器查询 |
| MC 服务器状态 (备) | `https://minecraft-serverhub.com/api/ping?host={host}&platform=java` | 失败时自动切换 |
| UTC 时间同步 | `https://timeapi.io/api/Time/current/zone?timeZone=UTC` | error 页面实时时钟 |
| GitHub 内容 API | `https://api.github.com/repos/{owner}/{repo}/contents/{path}` | 下载中心拉取文件列表 |
| 头像服务 | `https://weavatar.com/avatar/{hash}?s=400` | 团队成员头像 |

## 🚀 部署指南

1. **Fork / 上传仓库**：将代码上传至你的 GitHub 仓库。
2. **启用 GitHub Pages**：在仓库 **Settings → Pages** 中选择 `main` 分支作为源。
3. **配置下载中心**：打开 `download.html`，修改 `CONFIG` 对象中的 `owner` 和 `repo` 为你自己的 GitHub 用户名与仓库名：
4. **访问站点**：打开 https://你的用户名.github.io/仓库名 即可访问。