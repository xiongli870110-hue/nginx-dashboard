以下是整合后的 README.md 文件，包含所有内容，结构清晰，适合一键复制到 GitHub 仓库。内容已优化，确保简洁、易读，涵盖原始文档和 user-loading.md 的全部信息。
markdown# 运维门户仪表盘（nginx-dashboard）

一个基于 HTML 的多用户运维门户首页，适合部署在 NAS、本地网页或 GitHub Pages。支持多用户密码登录、动态导航、主题切换和权限控制，适合业余爱好者快速搭建运维入口。

---

## ✨ 功能特色

- 🔐 **多用户密码登录**：支持用户名和密码验证
- 🧭 **动态导航**：根据用户权限自动生成导航按钮
- 🌙 **主题切换**：支持深色/浅色模式，自动记忆用户选择
- 🕹️ **退出登录**：一键退出，安全便捷
- 📁 **页面加载**：通过 iframe 加载页面，结构清晰
- 📱 **响应式布局**：适配手机、平板和电脑

---

## 🚀 快速部署

### 方法 1：GitHub Pages 部署
1. 将项目上传至 GitHub 仓库
2. 进入仓库 → **Settings** → **Pages**
3. 设置 **Source** 为 `main` 分支，**Folder** 为 `/ (root)`
4. 保存后访问：`https://your-username.github.io/nginx-dashboard/`

### 方法 2：本地或 NAS 部署
1. 将项目文件放置在本地或 NAS 的 Web 服务器目录
2. 通过浏览器访问 `index.html`

---

## 👥 默认用户配置

| 用户名 | 密码       | 默认页面        | 可访问页面                     |
|--------|------------|----------------|--------------------------------|
| admin  | admin123   | nginx.html     | nginx, dashboard, certbot, portainer, extra |
| li     | nginxlover | nginx.html     | nginx, dashboard               |
| guest  | readonly   | dashboard.html | dashboard                      |

> **修改用户配置**：编辑 `index.html` 中的 `users` 对象，调整用户名、密码或页面权限。

### 用户页面加载逻辑
- 每个用户有独立的页面权限列表 `users[username].pages`
- 登录后默认加载列表中的第一个页面（`pages[0]`）
- 示例代码：
  ```javascript
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
  // 加载逻辑
  loadPage(users[username].pages[0]);

修改默认页面：调整 pages 数组顺序，例如：
javascriptli: {
  password: "nginxlover",
  pages: ["dashboard", "nginx"] // 默认加载 dashboard.html
}

可选扩展：支持更智能的加载行为：

使用 localStorage 记住用户上次访问页面
为用户添加 defaultPage 字段：
javascriptli: {
  password: "nginxlover",
  pages: ["nginx", "dashboard"],
  defaultPage: "dashboard"
}
// 加载逻辑
const defaultPage = users[username].defaultPage || users[username].pages[0];
loadPage(defaultPage);





📁 项目结构
textnginx-dashboard/
├── index.html        # 主入口页面
├── nginx.html        # 示例页面
├── dashboard.html    # 示例页面
├── certbot.html      # 示例页面
├── portainer.html    # 示例页面
└── extra.html        # 示例页面

注意：页面文件名需与 users.pages 配置一致，且文件必须存在于项目根目录。


🛠️ 可扩展功能

页面状态检测：检查页面是否在线
用户分组：支持权限等级管理
页面搜索：实现页面搜索与分类
密码加密：避免明文存储密码
后端集成：对接 Docker API 或其他服务
智能加载：记住用户上次访问页面或指定默认页面


📌 注意事项

页面权限控制仅在前端实现，非安全隔离，生产环境建议加强后端验证
确保所有页面文件存在并与配置一致
项目适合学习和个人使用，无需授权即可自由修改


📄 许可协议
本项目为学习和个人使用设计，欢迎 fork、改造并打造属于自己的运维门户 🚀

部署你的运维仪表盘，享受高效管理！
text### 说明
- **整合完整**：合并了原始 `README.md` 和 `user-loading.md` 的所有内容，确保信息无遗漏。
- **结构清晰**：使用 Markdown 表格、列表、代码块和分隔线，优化可读性。
- **一键复制**：内容格式规范，直接复制即可用于 GitHub 仓库的 `README.md`。
- **精简优化**：删除冗余表述，保留核心信息，突出部署步骤、用户配置和扩展功能。
- **时间戳无关**：未包含与时间戳相关的内容，专注于项目说明。

如果需要进一步调整或添加特定内容，请告诉我！2秒快速模式能直接下载吗我无法直接提供文件的下载链接，因为我只能以文本形式返回内容。不过，我可以帮你将整理好的 README.md 内容以最便捷的方式提供，方便你复制并保存为文件，或者我可以指导你如何快速生成并下载文件。
方案 1：手动保存 README.md


复制以下完整 README.md 内容：
markdown# 运维门户仪表盘（nginx-dashboard）

一个基于 HTML 的多用户运维门户首页，适合部署在 NAS、本地网页或 GitHub Pages。支持多用户密码登录、动态导航、主题切换和权限控制，适合业余爱好者快速搭建运维入口。

---

## ✨ 功能特色

- 🔐 **多用户密码登录**：支持用户名和密码验证
- 🧭 **动态导航**：根据用户权限自动生成导航按钮
- 🌙 **主题切换**：支持深色/浅色模式，自动记忆用户选择
- 🕹️ **退出登录**：一键退出，安全便捷
- 📁 **页面加载**：通过 iframe 加载页面，结构清晰
- 📱 **响应式布局**：适配手机、平板和电脑

---

## 🚀 快速部署

### 方法 1：GitHub Pages 部署
1. 将项目上传至 GitHub 仓库
2. 进入仓库 → **Settings** → **Pages**
3. 设置 **Source** 为 `main` 分支，**Folder** 为 `/ (root)`
4. 保存后访问：`https://your-username.github.io/nginx-dashboard/`

### 方法 2：本地或 NAS 部署
1. 将项目文件放置在本地或 NAS 的 Web 服务器目录
2. 通过浏览器访问 `index.html`

---

## 👥 默认用户配置

| 用户名 | 密码       | 默认页面        | 可访问页面                     |
|--------|------------|----------------|--------------------------------|
| admin  | admin123   | nginx.html     | nginx, dashboard, certbot, portainer, extra |
| li     | nginxlover | nginx.html     | nginx, dashboard               |
| guest  | readonly   | dashboard.html | dashboard                      |

> **修改用户配置**：编辑 `index.html` 中的 `users` 对象，调整用户名、密码或页面权限。

### 用户页面加载逻辑
- 每个用户有独立的页面权限列表 `users[username].pages`
- 登录后默认加载列表中的第一个页面（`pages[0]`）
- 示例代码：
  ```javascript
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
  // 加载逻辑
  loadPage(users[username].pages[0]);

修改默认页面：调整 pages 数组顺序，例如：
javascriptli: {
  password: "nginxlover",
  pages: ["dashboard", "nginx"] // 默认加载 dashboard.html
}

可选扩展：支持更智能的加载行为：

使用 localStorage 记住用户上次访问页面
为用户添加 defaultPage 字段：
javascriptli: {
  password: "nginxlover",
  pages: ["nginx", "dashboard"],
  defaultPage: "dashboard"
}
// 加载逻辑
const defaultPage = users[username].defaultPage || users[username].pages[0];
loadPage(defaultPage);





📁 项目结构
textnginx-dashboard/
├── index.html        # 主入口页面
├── nginx.html        # 示例页面
├── dashboard.html    # 示例页面
├── certbot.html      # 示例页面
├── portainer.html    # 示例页面
└── extra.html        # 示例页面

注意：页面文件名需与 users.pages 配置一致，且文件必须存在于项目根目录。


🛠️ 可扩展功能

页面状态检测：检查页面是否在线
用户分组：支持权限等级管理
页面搜索：实现页面搜索与分类
密码加密：避免明文存储密码
后端集成：对接 Docker API 或其他服务
智能加载：记住用户上次访问页面或指定默认页面


📌 注意事项

页面权限控制仅在前端实现，非安全隔离，生产环境建议加强后端验证
确保所有页面文件存在并与配置一致
项目适合学习和个人使用，无需授权即可自由修改


📄 许可协议
本项目为学习和个人使用设计，欢迎 fork、改造并打造属于自己的运维门户 🚀

部署你的运维仪表盘，享受高效管理！



打开文本编辑器（如 Notepad、VS Code 或任何代码编辑器）


粘贴内容，保存为 README.md 文件（确保文件扩展名为 .md）


将文件放入你的项目目录或直接上传到 GitHub 仓库


方案 2：快速生成并下载
如果你想直接生成文件并下载，可以使用以下方法：

在线工具：

访问在线 Markdown 编辑器，如 Dillinger 或 StackEdit
复制上述 README.md 内容并粘贴到编辑器
使用编辑器的导出功能，下载为 README.md 文件


GitHub 仓库：

创建或进入你的 GitHub 仓库
点击 Add file → Create new file
命名为 README.md，粘贴上述内容
提交后，GitHub 会自动保存，仓库页面会显示该文件
下载整个仓库（点击仓库的 Code 按钮 → Download ZIP）



方案 3：自动化脚本（可选）
如果你熟悉命令行，可以使用脚本快速生成文件：


打开终端（Windows: CMD/PowerShell; macOS/Linux: Terminal）


运行以下命令：
bashecho '# 运维门户仪表盘（nginx-dashboard）

一个基于 HTML 的多用户运维门户首页，适合部署在 NAS、本地网页或 GitHub Pages。支持多用户密码登录、动态导航、主题切换和权限控制，适合业余爱好者快速搭建运维入口。

---

## ✨ 功能特色

- 🔐 **多用户密码登录**：支持用户名和密码验证
- 🧭 **动态导航**：根据用户权限自动生成导航按钮
- 🌙 **主题切换**：支持深色/浅色模式，自动记忆用户选择
- 🕹️ **退出登录**：一键退出，安全便捷
- 📁 **页面加载**：通过 iframe 加载页面，结构清晰
- 📱 **响应式布局**：适配手机、平板和电脑

---

## 🚀 快速部署

### 方法 1：GitHub Pages 部署
1. 将项目上传至 GitHub 仓库
2. 进入仓库 → **Settings** → **Pages**
3. 设置 **Source** 为 `main` 分支，**Folder** 为 `/ (root)`
4. 保存后访问：`https://your-username.github.io/nginx-dashboard/`

### 方法 2：本地或 NAS 部署
1. 将项目文件放置在本地或 NAS 的 Web 服务器目录
2. 通过浏览器访问 `index.html`

---

## 👥 默认用户配置

| 用户名 | 密码       | 默认页面        | 可访问页面                     |
|--------|------------|----------------|--------------------------------|
| admin  | admin123   | nginx.html     | nginx, dashboard, certbot, portainer, extra |
| li     | nginxlover | nginx.html     | nginx, dashboard               |
| guest  | readonly   | dashboard.html | dashboard                      |

> **修改用户配置**：编辑 `index.html` 中的 `users` 对象，调整用户名、密码或页面权限。

### 用户页面加载逻辑
- 每个用户有独立的页面权限列表 `users[username].pages`
- 登录后默认加载列表中的第一个页面（`pages[0]`）
- 示例代码：
  ```javascript
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
  // 加载逻辑
  loadPage(users[username].pages[0]);

修改默认页面：调整 pages 数组顺序，例如：
javascriptli: {
  password: "nginxlover",
  pages: ["dashboard", "nginx"] // 默认加载 dashboard.html
}

可选扩展：支持更智能的加载行为：

使用 localStorage 记住用户上次访问页面
为用户添加 defaultPage 字段：
javascriptli: {
  password: "nginxlover",
  pages: ["nginx", "dashboard"],
  defaultPage: "dashboard"
}
// 加载逻辑
const defaultPage = users[username].defaultPage || users[username].pages[0];
loadPage(defaultPage);





📁 项目结构
textnginx-dashboard/
├── index.html        # 主入口页面
├── nginx.html        # 示例页面
├── dashboard.html    # 示例页面
├── certbot.html      # 示例页面
├── portainer.html    # 示例页面
└── extra.html        # 示例页面

注意：页面文件名需与 users.pages 配置一致，且文件必须存在于项目根目录。


🛠️ 可扩展功能

页面状态检测：检查页面是否在线
用户分组：支持权限等级管理
页面搜索：实现页面搜索与分类
密码加密：避免明文存储密码
后端集成：对接 Docker API 或其他服务
智能加载：记住用户上次访问页面或指定默认页面


📌 注意事项

页面权限控制仅在前端实现，非安全隔离，生产环境建议加强后端验证
确保所有页面文件存在并与配置一致
项目适合学习和个人使用，无需授权即可自由修改


📄 许可协议
本项目为学习和个人使用设计，欢迎 fork、改造并打造属于自己的运维门户 🚀
