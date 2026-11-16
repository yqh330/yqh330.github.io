# 留言板启用说明（Waline）

留言板前端已经改为 Waline，访客无需 GitHub 账号即可留言。由于 GitHub Pages 只能托管静态文件，留言数据需要一个独立的 Waline 服务端和数据库。

## 1. 部署服务端

1. 打开 [Waline 快速上手](https://waline.js.org/guide/get-started/)。
2. 使用 GitHub 账号登录 Vercel，按官方页面部署 Waline Server 模板。
3. 在 Vercel 项目的 Storage 中创建 Neon 数据库，并按部署向导绑定。
4. 等待部署状态变为 Ready，复制服务端域名，例如 `https://your-waline.vercel.app`。

## 2. 设置服务端环境变量

在 Vercel 项目 Settings → Environment Variables 中设置：

- `SITE_NAME` = `杨·Yaᴗngᥫᩣ · 温柔小站`
- `SITE_URL` = `https://yqh330.github.io`
- `COMMENT_AUDIT` = `true`（建议开启，留言经管理员审核后再公开）
- `SECURE_DOMAINS` = `yqh330.github.io`

**不要设置** `LOGIN=force`，否则访客会被要求登录。首次启用建议保留默认频率限制和反垃圾配置。

保存环境变量后重新部署服务端。

## 3. 连接网站前端

编辑仓库 `guestbook.html`，找到：

```js
const WALINE_SERVER_URL = "YOUR_WALINE_SERVER_URL";
```

将其替换为刚才复制的真实服务端地址，例如：

```js
const WALINE_SERVER_URL = "https://your-waline.vercel.app";
```

提交到网站分支后即可加载留言组件。

## 4. 设置管理员

部署完成后，打开：

`https://你的-waline-服务端域名/ui/register`

注册第一个管理账号。按 Waline 官方说明，首个注册用户会成为管理员。之后从服务端域名的 `/ui` 进入管理后台审核、回复和删除留言。

## 5. 验收清单

- [ ] 留言页可以正常加载
- [ ] 游客无需注册账号即可用昵称留言
- [ ] 留言提交成功
- [ ] 开启审核后，未审核留言不会公开显示
- [ ] 管理员可以审核、回复和删除留言

## 注意

- 不要把数据库密码、服务端密钥或任何管理员凭据提交到 GitHub。
- 留言内容会公开展示，请提醒访客不要填写密码、手机号等隐私信息。
- 当前网站前端已完成接入改造，但在配置真实 Waline Server URL 前，留言服务不会真正连接数据库。
- 官方文档：[快速上手](https://waline.js.org/guide/get-started/) · [服务端环境变量](https://waline.js.org/reference/server/env.html) · [安全说明](https://waline.js.org/guide/features/safety.html)
