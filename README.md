# 杨·Yaᴗngᥫᩣ · 温柔小站

一个使用原生 HTML、CSS 和 JavaScript 构建的响应式个人网站，采用自然背景与液态玻璃视觉主题。

🌐 **在线访问：** https://yqh330.github.io/

## 页面结构

- `index.html` — 网站首页
- `about.html` — 关于我
- `projects.html` — 项目展示
- `guestbook.html` — 留言板（Waline，支持免账号留言）
- `contact.html` — 联系方式
- `404.html` — 自定义错误页面
- `assets/css/style.css` — 全站样式
- `assets/js/main.js` — 导航交互与页脚年份
- `tools/stock-calculator.html` — 股票交易计算器

## 留言板启用

留言板前端使用 Waline，访客无需 GitHub 账号即可留言。需要先部署 Waline Server 并连接数据库，再将服务端地址填入 `guestbook.html`。详细步骤见 [`docs/WALINE-SETUP.md`](docs/WALINE-SETUP.md)。

## 部署

使用 GitHub Pages：Settings → Pages → Deploy from a branch，选择 `main` 分支和 `/(root)` 目录。

---

Made with care.
