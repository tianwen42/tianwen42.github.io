# notes & Blog

木木和他的朋友们的 Hexo 博客源码。

## 环境

- Hexo 7.3.0
- 主题：`hexo-theme-3-hexo`
- Node.js 20+
- GitHub Pages 发布目录：`docs/`

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

构建结果会生成到 `docs/`，GitHub Pages 的发布源应设置为：

```text
Branch: main
Folder: /docs
```

## 目录

```text
source/_posts/       文章
source/about/        关于页
source/日常清单/      日常清单页
themes/3-hexo/       主题及个人配置
docs/                Hexo 生成的静态站点
```

新增文章：

```bash
npx hexo new "文章标题"
```
