# notes & Blog

木木和他的朋友们的 Hexo 博客源码。

## 环境

- Hexo 7.3.0
- 主题：`hexo-theme-3-hexo`
- Node.js 20+
- GitHub Pages 通过 GitHub Actions 自动构建部署

## 本地使用

```bash
npm install
npm run server
```

浏览器访问 `http://localhost:4000`。

## 构建

```bash
npm run clean
npm run build
```

构建结果生成到 `docs/`，该目录不提交到 Git；GitHub Actions 会在推送 `main` 后自动构建并部署。

## 目录

```text
source/_posts/       文章
source/about/        关于页
source/日常清单/      日常清单页
themes/3-hexo/       主题及个人配置
.github/workflows/   GitHub Pages 自动部署工作流
```

新增文章：

```bash
npx hexo new "文章标题"
```
