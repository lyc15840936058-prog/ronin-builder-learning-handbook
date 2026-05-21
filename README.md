# 小岛学堂 · 网站文件说明（给 Codex 看）

## 这个项目是什么
一个**纯静态网页**(单页应用),无后端、无数据库、无构建步骤。
直接把这些文件原样部署到任何静态托管(Vercel / Netlify / GitHub Pages)即可,**不需要 npm install、不需要 build**。

## 文件构成（只有 2 个,缺一不可）
- `index.html` —— 主页面(单页应用,内含 10 个内联页面 + 导航)
- `island-3d.html` —— "3D 视觉岛"页面,被 index.html 通过 iframe 加载

⚠️ **关键:这两个文件必须放在同一目录、一起部署。** index.html 用相对路径 `island-3d.html` 引用 3D 岛,少了它,3D 那一页会空白。

## 技术说明
- 纯 HTML/CSS/JS,无依赖、无打包工具。
- 3D 岛运行时从公共 CDN 加载 Three.js(已内置多源容错,联网即可)。
- 无需任何环境变量、API key、配置文件。

## 部署期望
- 部署根目录 = 含这两个文件的目录。
- 入口文件 = `index.html`。
- Vercel 识别为 "Other / 静态站点" 即可,无需框架预设、无构建命令、无 output 目录设置。
