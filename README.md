markdown
# 运维门户仪表盘（nginx-dashboard）

这是一个基于 HTML 的多用户运维门户首页，适合部署在 NAS、本地网页或 GitHub Pages。支持密码登录、自动导航、主题切换和权限控制，适合业余爱好者快速搭建运维入口。

---

## ✨ 功能特色

- 🔐 多用户密码登录（用户名 + 密码）
- 🧭 自动导航按钮（根据用户权限生成）
- 🌙 主题切换（深色 / 浅色，自动记忆）
- 🕹️ 退出登录功能
- 📁 页面通过 iframe 加载，结构清晰
- 📱 响应式布局，适配手机和电脑

---

## 🚀 快速部署（GitHub Pages）

1. 将本项目上传到 GitHub 仓库根目录  
2. 打开仓库 → Settings → Pages  
3. Source 选择 `main` 分支，Folder 选择 `/ (root)`  
4. 保存后访问链接：  
https://your-username.github.io/nginx-dashboard/

代码

---

## 👥 默认用户配置

| 用户名 | 密码       | 可访问页面                     |
|--------|------------|--------------------------------|
| admin  | admin123   | nginx, dashboard, certbot, portainer, extra |
| li     | nginxlover | nginx, dashboard               |
| guest  | readonly   | dashboard                      |

你可以在 `index.html` 中修改用户列表和权限分配。

---

## 📁 页面结构说明

📁 nginx-dashboard/ ├── index.html ← 主入口页面 ├── nginx.html ← 示例页面 ├── dashboard.html ← 示例页面 ├── certbot.html ← 示例页面 ├── portainer.html ← 示例页面 └── extra.html ← 示例页面

代码

---

## 🛠️ 后续可扩展功能

- 页面状态检测（是否在线）
- 用户分组与权限等级
- 页面搜索与分类
- 加密存储密码（避免明文）
- 与后端服务集成（如 Docker API）

---

📄 user-loading.md（完整内容，一次性复制）
markdown
# 用户默认加载页面说明

本说明文件用于解释每个用户登录后默认加载的页面是如何控制的，适用于本项目的 `index.html` 运维门户结构。

---

## 🧠 控制逻辑概述

在 `index.html` 的 JavaScript 中，用户登录成功后会执行以下代码：

```javascript
loadPage(users[username].pages[0]);
这表示：

每个用户拥有一个页面权限列表：users[username].pages

登录后会自动加载该列表中的第一个页面（索引为 [0]）

页面通过 <iframe> 加载，文件名由页面配置决定

👥 用户配置示例
javascript
const users = {
  admin: {
    password: "admin123",
    pages: ["nginx", "dashboard", "certbot", "portainer", "extra"]
  },
  li: {
    password: "nginxlover",
    pages: ["nginx", "dashboard"]
  },
  guest: {
    password: "readonly",
    pages: ["dashboard"]
  }
};
用户名	默认加载页面	权限页面列表
admin	nginx.html	nginx, dashboard, certbot, portainer, extra
li	nginx.html	nginx, dashboard
guest	dashboard.html	dashboard
✅ 如何修改默认加载页面
只需调整 pages 数组的顺序即可。例如：

javascript
li: {
  password: "nginxlover",
  pages: ["dashboard", "nginx"]
}
这样 li 登录后将默认加载 dashboard.html。

🔧 可选扩展功能（建议）
如需更智能的默认加载行为，可考虑：

使用 localStorage 记住上次访问页面

为每个用户添加 defaultPage 字段，例如：

javascript
li: {
  password: "nginxlover",
  pages: ["nginx", "dashboard"],
  defaultPage: "dashboard"
}
然后修改加载逻辑为：

javascript
const defaultPage = users[username].defaultPage || users[username].pages[0];
loadPage(defaultPage);
📌 注意事项
所有页面文件必须存在于项目根目录

页面文件名需与配置一致（如 nginx.html）

页面权限控制仅在前端实现，非安全隔离

## 📄 许可协议

本项目为学习和个人使用而设计，无需授权即可使用和修改。

---

欢迎你 fork、改造并打造属于自己的运维门户 🚀
