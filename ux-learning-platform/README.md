# UX 学习助手（MVP）

这是一个无需构建工具的静态 Web 应用：知识内容保存在 `data/knowledge.json`，前端功能在 `assets/app.js`，样式在 `assets/styles.css`。

## 本地运行

请从本目录启动静态服务器（不要直接双击 `index.html`，因为浏览器会限制读取 JSON）：

```powershell
python -m http.server 8080
```

然后打开 `http://localhost:8080`。

## 数据与认证说明

- 知识库：`data/knowledge.json`，可直接添加分类、知识点、练习题和案例。
- Demo 登录：注册信息、盐化后的密码验证值、会话、收藏与学习数据只保存在该浏览器的 `localStorage`；密码不会以明文保存。
- 这是可完整演示登录流程的前端 MVP，不适合生产账号系统。生产环境应将认证和学习数据迁移至受管认证与数据库服务（例如 Supabase Auth + Postgres），由服务端使用 HTTPS、行级访问控制、邮件验证和密码重置机制管理。

## Netlify 部署

1. 将本目录上传到新的 GitHub 仓库；
2. 在 Netlify 选择“Add new site → Import an existing project”；
3. 选择仓库，发布目录填写 `.`，无需 Build command；
4. 部署完成后，Netlify 会生成公开 HTTPS 地址。

仓库内的 `netlify.toml` 已提供基础安全响应头配置。
