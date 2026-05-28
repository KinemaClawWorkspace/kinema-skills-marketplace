# KinemaClaw Skills Marketplace

私有 Claude Code Skill 集合索引。所有 skill 代码维护在各自仓库中，本仓库仅作为 marketplace 聚合入口。

## 包含的 Skill

| Skill | 说明 |
|-------|------|
| [kinema-tdd-injector](https://github.com/KinemaClawWorkspace/kinema-tdd-injector) | TDD 方法论注入器，为仓库生成定制版 CLAUDE.md（三阶测试体系、conftest 分层、覆盖率门槛） |
| [kinema-task-management](https://github.com/KinemaClawWorkspace/kinema-task-management) | AI Agent 维护的个人任务追踪系统，支持每日报告、主动推送、任务回溯 |
| [alist-cli](https://github.com/KinemaClawWorkspace/alist-cli) | AList 文件管理 CLI，支持 upload/download/list/mkdir/rm/mv/search/url |
| [kinema-skill-making-pipeline](https://github.com/KinemaClawWorkspace/kinema-skill-making-pipeline) | KinemaClaw Skill 开发与发布规范 |
| [kinema-concept-research](https://github.com/KinemaClawWorkspace/kinema-concept-research) | 概念研究 — 多语言关键词、多引擎交叉验证、多维度搜索 |
| [searxng-search-cli](https://github.com/KinemaClawWorkspace/searxng-search-cli) | 自托管 SearXNG 搜索引擎 CLI，聚合 200+ 搜索引擎 |

## 安装

### 1. 添加 Marketplace

在 Claude Code 中运行：

```
/plugin marketplace add https://github.com/KinemaClawWorkspace/kinema-skills-marketplace
```

### 2. 安装 Skill

```
/plugin install <skill-name>@kinema-skills-marketplace
```

示例：

```
/plugin install kinema-tdd-injector@kinema-skills-marketplace
/plugin install alist-cli@kinema-skills-marketplace
/plugin install searxng-search-cli@kinema-skills-marketplace
```

### 3. 查看已安装的 Skill

```
/plugin list
```

## 新增 Skill

在本仓库的 `.claude-plugin/marketplace.json` 的 `plugins` 数组中添加条目：

```json
{
  "name": "new-skill-name",
  "displayName": "New Skill Display Name",
  "description": "Skill 描述",
  "source": {
    "source": "github",
    "repo": "KinemaClawWorkspace/new-skill-repo"
  },
  "strict": false
}
```

提交并推送即可生效。

## 仓库结构

```
kinema-skills-marketplace/
├── .claude-plugin/
│   └── marketplace.json   ← Marketplace 索引文件
└── README.md
```

## 许可

[GNU General Public License v3.0](LICENSE)