# Requirements Document

## Introduction

`xh2580.github.io` 是一个部署在 GitHub Pages 上的个人博客与作品展示站点。站点采用纯静态 HTML/CSS/JS 实现，包含首页、博客文章列表与详情、作品展示、关于我四个核心模块。内容通过文件方式管理，作者直接编写 Markdown 或 HTML 文件并提交到仓库，站点构建或运行时读取这些文件完成渲染。

站点目标用户为访问该站点的访客（读者、潜在合作者），以及作为内容作者的站点所有者。

## Glossary

- **站点（Site）**：部署在 GitHub Pages 上的静态网站整体。
- **访客（Visitor）**：通过浏览器访问站点的读者或潜在合作者。
- **作者（Author）**：站点所有者，负责编写和维护站点内容。
- **博客文章（Post）**：以文件形式存在、包含标题、日期、正文等字段的内容条目。
- **作品（Project）**：作者展示的已完成或进行中的项目，包含名称、描述、链接等字段。
- **首页（Home）**：站点的入口页面，展示站点概览与最新内容。
- **关于我（About）**：介绍作者身份、经历与联系方式信息的页面。

## Requirements

### 1. 首页

**User Story:** AS 访客, I want 打开站点时看到清晰的站点概览与最新内容, so that 快速了解作者和站点价值。

#### Acceptance Criteria

1. WHEN 访客访问站点根路径，站点 SHALL 展示首页内容。
2. WHEN 首页加载完成，首页 SHALL 展示作者简介、最新 3 篇文章摘要和最新 3 个作品卡片。
3. WHEN 访客点击首页的"全部文章"入口，站点 SHALL 跳转到博客文章列表页。
4. WHEN 访客点击首页的"全部作品"入口，站点 SHALL 跳转到作品展示页。
5. IF 首页某个内容模块没有数据，该模块 SHALL 显示友好的空状态提示，站点 SHALL 保持页面正常渲染。

### 2. 导航栏

**User Story:** AS 访客, I want 在站点任意页面通过统一导航栏切换模块, so that 快速定位所需内容。

#### Acceptance Criteria

1. WHEN 任意页面加载完成，站点 SHALL 在页面顶部显示包含"首页、博客、作品、关于我"四个入口的导航栏。
2. WHEN 访客处于某个模块页面，导航栏 SHALL 高亮当前所在模块的入口。
3. WHEN 访客点击导航栏中的入口链接，站点 SHALL 跳转到对应模块页面。

### 3. 博客文章列表

**User Story:** AS 访客, I want 浏览所有博客文章并按发布时间排序, so that 查阅作者的历史文章。

#### Acceptance Criteria

1. WHEN 访客访问博客列表路径，站点 SHALL 展示全部文章的列表。
2. WHEN 列表渲染完成，站点 SHALL 按发布时间从新到旧对文章排序。
3. WHEN 文章超过 10 篇，站点 SHALL 提供分页能力，每页展示 10 篇。
4. WHEN 访客点击某篇文章的标题，站点 SHALL 跳转到该文章的详情页。
5. IF 博客列表为空，站点 SHALL 显示"暂无文章"的空状态提示。

### 4. 博客文章详情

**User Story:** AS 访客, I want 阅读单篇文章的完整正文, so that 获取文章内容。

#### Acceptance Criteria

1. WHEN 访客访问某篇文章的详情路径，站点 SHALL 展示该文章的标题、发布日期与完整正文。
2. WHEN 文章详情渲染完成，站点 SHALL 将 Markdown 格式的正文渲染为可读的 HTML 排版。
3. WHEN 正文包含代码块，站点 SHALL 以等宽字体和合适的语法高亮展示代码块。
4. WHEN 正文包含标题层级，站点 SHALL 展示清晰的标题层级结构。
5. IF 文章详情路径对应的文件不存在，站点 SHALL 显示 404 页面提示内容不存在，页面 SHALL 提供返回博客列表的入口。

### 5. 作品展示

**User Story:** AS 访客, I want 浏览作者的作品列表并访问作品详情或外部链接, so that 了解作者的能力与成果。

#### Acceptance Criteria

1. WHEN 访客访问作品展示路径，站点 SHALL 展示全部作品的卡片列表。
2. WHEN 作品卡片渲染完成，卡片 SHALL 展示作品名称、描述、技术标签以及外链地址。
3. WHEN 访客点击作品卡片，站点 SHALL 在新标签页打开作品的外部链接。
4. IF 作品列表为空，站点 SHALL 显示"暂无作品"的空状态提示。

### 6. 关于我

**User Story:** AS 访客, I want 查看作者的个人介绍、技能与联系方式, so that 判断是否与作者合作或联系。

#### Acceptance Criteria

1. WHEN 访客访问关于我路径，站点 SHALL 展示作者的个人介绍段落。
2. WHEN 关于我页面渲染完成，页面 SHALL 展示技能标签列表。
3. WHEN 关于我页面包含联系方式，页面 SHALL 展示邮箱、社交链接等联系信息，站点 SHALL 以新标签页打开社交链接。

### 7. 内容文件管理

**User Story:** AS 作者, I want 通过添加或修改文件来发布内容, so that 无需后台即可更新站点。

#### Acceptance Criteria

1. WHEN 作者在内容目录中新增一个 Markdown 格式的博客文章文件，站点 SHALL 将该文章纳入文章列表与详情渲染。
2. WHEN 作者在内容目录中新增一个作品数据文件，站点 SHALL 将该作品纳入作品展示页。
3. WHEN 作者修改某个内容文件，站点 SHALL 在重新部署或刷新后展示更新后的内容。
4. WHEN 作者修改站点首页与关于我页面，站点 SHALL 展示对应更新内容。
5. WHILE 文章正文使用 Markdown 编写，站点 SHALL 支持标题、段落、列表、引用、代码块、图片与链接的基础 Markdown 语法。

### 8. 移动端适配

**User Story:** AS 访客, I want 在手机和平板等小屏设备上正常浏览站点, so that 随时随地访问内容。

#### Acceptance Criteria

1. WHEN 站点在视口宽度小于等于 768px 的设备上渲染，站点 SHALL 采用单列布局。
2. WHEN 视口宽度大于 768px，站点 SHALL 采用多列或更宽的布局展示内容。
3. WHILE 站点在任何视口宽度下，正文文本、图片与代码块 SHALL 不发生横向溢出。

### 9. 性能与可访问性

**User Story:** AS 访客, I want 页面快速加载且内容可被辅助技术读取, so that 获得良好的浏览体验。

#### Acceptance Criteria

1. WHEN 页面首次加载，站点 SHALL 将首屏 CSS 内联或以其他方式避免阻塞渲染。
2. WHEN 访客使用键盘导航，站点 SHALL 支持通过 Tab 键遍历所有可交互元素。
3. WHEN 页面包含图片，图片 SHALL 提供描述性 alt 文本。
4. WHEN 页面渲染完成，正文文字与背景 SHALL 满足足够颜色对比度，便于阅读。
5. IF 页面包含动态内容加载，站点 SHALL 提供加载中或降级状态，页面 SHALL 不因加载失败而出现空白。

### 10. 部署与可维护性

**User Story:** AS 作者, I want 站点能够被自动部署并易于维护, so that 聚焦内容创作。

#### Acceptance Criteria

1. WHEN 作者将内容提交到仓库 main 分支，GitHub Actions SHALL 自动构建并部署站点到 GitHub Pages。
2. WHEN 构建过程执行，构建脚本 SHALL 读取内容文件并生成对应的静态页面。
3. WHEN 站点部署完成，站点 SHALL 可通过 `https://xh2580.github.io` 访问。
4. WHEN 作者维护站点，内容文件与页面模板 SHALL 分离存放，作者 SHALL 只需修改内容目录即可更新页面。
