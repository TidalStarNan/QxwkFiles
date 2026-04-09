# 个人作品集网站 · GitHub Pages 双页模板

这是一个基于 GitHub Pages 的轻量级静态网站模板，包含全屏图片轮播的**欢迎页**和 Windows 详细信息风格的**文件下载页**。

## ✨ 功能特点

### 🏠 欢迎页 (`index.html`)
- 全屏背景图片自动轮播（淡入淡出效果）
- 图片从仓库指定文件夹（如 `images/background`）动态读取
- 支持常见图片格式：JPG、PNG、GIF、WebP、SVG 等
- 轮播指示点，可点击切换
- 响应式设计，自适应屏幕尺寸

### 📦 下载页 (`download.html`)
- 仿 Windows 资源管理器“详细信息”表格视图
- 展示指定文件夹（如 `files/download`）内的所有文件
- 自动从文件名前缀解析日期（格式：`YY.MM.DD`），按日期倒序排列（最新在上）
- 显示文件图标、类型描述、大小和下载按钮
- 蓝绿渐变背景，界面清爽美观

## ⚠️ 注意事项
- 文件名日期格式
- 下载页面的文件必须以 YY.MM.DD 开头（如 26.01.10_文件名.pdf），系统会自动提取日期并排序，最新日期的文件会显示在最前面。

### API 速率限制
- 由于使用 GitHub API 动态获取文件夹内容，未认证请求每小时限制 60 次。对于个人或小范围使用完全足够。如需提升限制，可考虑配置 Personal Access Token（不推荐在纯静态页面中暴露）或使用 GitHub Actions 生成静态 JSON 缓存。

### 仓库可见性
- GitHub Pages 免费版要求仓库为 Public（公开），否则 API 将无法访问。如仓库为私有，需额外配置 Token（存在安全隐患，不建议）。

### 图片与文件大小
- 建议将背景图片压缩至合适尺寸（宽度 1920px 左右），文件总大小控制在合理范围，以保证加载速度。

## 🛠️ 自定义与扩展
- 更换配色：修改 download.html 中 body 的 background 渐变值。
- 调整轮播间隔：修改 index.html 中 CONFIG.switchInterval 的值（单位毫秒）。
- 增加文件类型图标：在 getFileIcon() 和 getFileTypeDescription() 函数中补充对应的扩展名映射。
