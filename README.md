<div align="center">

<img src="https://raw.githubusercontent.com/xh2580/xh2580.github.io/main/assets/logo.svg" width="120" height="120" style="border-radius: 50%;" />

# xh2580 的个人站点

**个人博客与作品展示站**

记录技术成长、分享开源项目与生活思考

<br>

[![](https://img.shields.io/badge/访问站点-6366f1?style=for-the-badge)](https://xh2580.github.io/)
[![](https://img.shields.io/badge/GitHub-333?style=for-the-badge&logo=github&logoColor=white)](https://github.com/xh2580/xh2580.github.io)

</div>

---

## 关于本站

| 图标 | 说明 |
|:---:|------|
| 首页 | 站点概览、最新博客与作品入口 |
| 博客 | 技术文章、项目笔记与日常思考 |
| 作品 | 开源项目与开发实践展示 |
| 关于我 | 个人介绍、技能标签与联系方式 |

## 技术栈

- **纯静态**：HTML / CSS / JS，无构建工具，无需后端
- **文件式管理**：内容以文件方式直接维护，提交即可更新
- **免费托管**：部署在 GitHub Pages，零成本维护

## 机器人崽崽使用教程

[机器人崽崽使用教程](docs/机器人崽崽使用教程.md) — 涵盖 ck 绑定、米游社签到、体力查询、uid 管理、抽卡/充值记录、角色面板排行等常用指令。

## 本地预览

```bash
python3 -m http.server 8080
```

浏览器访问 <http://localhost:8080> 即可预览。

## 站点结构

```
xh2580.github.io/
├── index.html      # 单页站点（首页、博客、作品、关于我）
├── assets/
│   └── logo.svg    # 站点 Logo
└── README.md
```

## 部署方式

将代码推送到 `main` 分支，GitHub Pages 会自动部署：

```bash
git add .
git commit -m "update site"
git push origin main
```

部署完成后访问 <https://xh2580.github.io>。

## 如何更新内容

- **修改博客文章**：编辑 `index.html` 中的博客区块内容
- **修改作品展示**：编辑 `index.html` 中的作品区块内容
- **修改个人介绍**：编辑 `index.html` 中的关于我区块内容

修改后提交推送即可，无需其他操作。

---

<div align="center">

Made with 🔥 and ❤️ by **xh2580**

</div>
