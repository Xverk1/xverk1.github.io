仓库概览

这是一个基于 Hexo 的静态博客站点（根目录使用 `hexo`、依赖在 `package.json`），主题由 `next` 提供（通过依赖引入）。主要内容放在 `source/` 下，文章位于 `source/_posts/`。

**Quick Overview**
- **Framework**: Hexo (see `package.json`, `hexo` v7.3 in this repo).
- **Theme**: configured via `theme: next` in `_config.yml` and theme options in `_config.next.yml`.
- **Content**: posts in `source/_posts/`, pages under `source/<page>/index.md`.

**Where To Look (key files)**
- **Config**: `_config.yml` — 全站 URL、permalink、theme、渲染/插件开关等。
- **Theme config**: `_config.next.yml` — NexT 主题大量视觉与功能开关（scheme、sidebar、menu、toc、post_meta 等）。
- **Scripts / deps**: `package.json` — 常用命令 `npm run server`, `npm run build`, `npm run deploy`。
- **Scaffolds**: `scaffolds/` — 新建文章/页面模板（`post.md`, `page.md`, `draft.md`）。
- **Content**: `source/_posts/`（文章）、`source/about/index.md` 等页面。

**Common Commands**
- **本地开发**: `npm run server`  （运行 Hexo 本地服务器）
- **生成静态文件**: `npm run build` （等同 `hexo generate`）
- **清理**: `npm run clean` （`hexo clean`）
- **部署**: `npm run deploy` （`hexo deploy`；注意：`_config.yml` 中 `deploy.type` 为空时需先配置）

**Content conventions and examples (project-specific)**
- **Front-matter**: 使用 YAML front-matter，常见字段见 `scaffolds/post.md`：`title`, `date`, `tags`。
- **文章目录与永久链接**: `permalink: :year/:month/:day/:title/`（见 `_config.yml`），发布后的 URL 遵循该规则。
- **Post asset folder**: `post_asset_folder: true`（在 `_config.yml`）。示例：`source/_posts/electric.md` 中的 `![](123.png)` 意味着图片应放在与文章同名的资源文件夹或者同目录下（Hexo 的 post asset 约定）。
- **Markdown 渲染**: 使用 `hexo-renderer-marked`，`marked` 配置项（如 `prependRoot`, `postAsset`）可影响图片路径解析。

**Patterns, gotchas & integration points**
- **Theme is dependency-managed**: `hexo-theme-next` 在 `package.json` 中；仓库中没有内置 `themes/next/`，修改主题模板需把主题复制到 `themes/` 或在 `package.json` 中改为本地主题。
- **配置分离**: 站点级配置在 `_config.yml`，主题级配置在 `_config.next.yml`。常见变更（菜单、侧边栏、scheme）都在 `_config.next.yml`。
- **投稿/编辑流程**: 修改文章直接编辑 `source/_posts/*.md` 或使用 Hexo 命令 `hexo new post "title"`（会使用 `scaffolds/post.md`）。
- **部署未配置**: 仓库 `deploy.type` 留空；CI/部署前需在 `_config.yml` 或 CI 环境中配置对应 deploy 插件（例如 `hexo-deployer-git`）。

**Examples from repo**
- `source/_posts/electric.md` — 简短示例，展示 front-matter、内联图片引用与引用块用法。
- `scaffolds/post.md` — 新文章模板，说明必须的 front-matter 字段。

如果这些说明有遗漏或你希望我把某些团队惯例写得更严格（例如 commit message、分支策略、CI 配置示例），告诉我具体要补充的部分，我会立刻更新这份文件。

---

请审阅这份初稿：我可以根据你的反馈合并现有团队规则，或把更多细节（CI、部署示例、常见 PR 模板）补充进来。
