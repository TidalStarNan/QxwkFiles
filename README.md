# 🌐 青翔未阔工作室官网

> 青翔未阔工作室的官方网站，集成了每日壁纸、一言语录、下载中心、MC 状态查询、团队成员展示等功能，全部基于静态页面构建，可部署于 GitHub Pages。

## ✨ 主要功能

- **首页**  
  - 全屏必应每日壁纸（1080P）  
  - 随机「一言」励志语录  
  - 快速导航入口：下载中心、MC 状态、关于我们、联系我们等

- **下载中心**  
  - 支持多目录选项卡（如下载、资源包、材质等）  
  - 自动拉取 GitHub 仓库指定文件夹内容，展示文件列表并提供下载

- **MC 状态**  
  - 查询任意 Minecraft 服务器的在线状态、玩家数、版本、MOTD  
  - 支持显示服务器图标与在线玩家列表

- **错误/占位页 (error.html)**  
  - 展示服务状态指示（浏览器 / Cloudflare / 服务器）  
  - 自动同步 UTC 时间  
  - 预留后续功能入口

- **关于我们 (about.html)**  
  - 按分组展示团队成员卡片（头像 + 名字 + 简介）  
  - 完美适配 PC 与移动端

## 🛠️ 使用的 API

所有接口均来自 [UAPIS](https://uapis.cn)，感谢该平台提供的免费 API 支持。

| 接口用途 | API 地址 | 备注 |
|---------|---------|------|
| 必应每日壁纸 | `https://uapis.cn/api/v1/image/bing-daily` | 默认 4K，本项目选用 `?resolution=1080` |
| 一言语录 | `https://uapis.cn/api/v1/saying` | 随机返回名言/诗词 |
| MC 服务器状态 | `https://uapis.cn/api/v1/game/minecraft/serverstatus` | 查询指定服务器信息 |
| 世界时间 | `https://uapis.cn/api/v1/misc/worldtime?city=Etc/UTC` | 用于 error 页面 UTC 时间显示 |
| GitHub 内容 API | `https://api.github.com/repos/{owner}/{repo}/contents/{path}` | 获取仓库文件列表（下载中心） |

## 🚀 部署

1. 将此仓库克隆或上传至 GitHub。
2. 在仓库设置中启用 GitHub Pages（选择 `main` 分支）。
3. 修改各页面中 `CONFIG` 对象的 `owner` 和 `repo` 为你的 GitHub 用户名与仓库名。
4. 访问 `https://你的用户名.github.io/仓库名` 即可。

---
* 青翔未阔工作室 · 静态页面 · 由 GitHub Pages 驱动*
