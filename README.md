# skills-introduction-to-github

> 我的第一个 GitHub 仓库 —— 用来练习 Git / GitHub，也是给我自己的 AI 助手（OpenClaw / 白金之星）装的 skills 存放处。

## 这个仓库要干什么

1. **学 GitHub**：把「网页点点点」升级成「命令行一条龙」，以后装软件、抄代码、存笔记都走这里。
2. **装 skills**：给 AI 助手装各种技能（skills），让助手会更多活。

## GitHub 最核心的四个概念

| 概念 | 大白话 | 对应命令 |
|---|---|---|
| **仓库 repo** | 一个项目文件夹 + 它的全部历史 | `git clone` / `git init` |
| **提交 commit** | 给文件拍一张快照 + 一句话说明 | `git add` → `git commit` |
| **分支 branch** | 平行宇宙，主线（main）之外随便试 | `git branch` / `git switch` |
| **远程 remote** | GitHub 上那个「云端副本」 | `git remote add origin <url>` |

## 每天就这几个命令

```bash
git status                    # 看现在啥状态（改了什么、有没有待提交）
git add .                     # 把改动放进「待提交区」
git commit -m "说明"          # 拍快照
git pull                      # 先拉取云端最新（开工前）
git push                      # 把本地提交推上云端（收工后）
```

一句话记忆：**开工 `pull`，干活 `add` + `commit`，收工 `push`。**

## 典型一天

```bash
cd C:/Users/bell_/Documents/GitHub/skills-introduction-to-github
git pull                                  # 开工：同步云端
# ... 改文件 / 写新文件 ...
git add .
git commit -m "feat: 新增 XXX"
git push                                  # 收工：上传
```

## 分支（安全试错用）

```bash
git switch -c feature/xxx     # 开一个新宇宙
# ... 改 ...
git add . && git commit -m "wip"
git push -u origin feature/xxx   # 推上去，发 Pull Request 合并回 main
git switch main               # 回主线
```

## 给 AI 助手装 skill（重点）

OpenClaw 支持直接从 Git 装 skill：

```bash
# 从 GitHub 仓库装（仓库根目录或子目录里有 SKILL.md）
openclaw skills install git:https://github.com/<owner>/<repo>.git

# 从 ClawHub 官方市场装
openclaw skills search "关键词"
openclaw skills install @owner/slug

# 看装没装上 / 有没有缺依赖
openclaw skills list
openclaw skills check
```

装完**重启网关**（`openclaw gateway restart`）才会生效。

> ⚠️ 第三方 skill 等于往家里装来路不明的软件，装之前先看 `SKILL.md` 里写了什么。

## 资源

- 官方中文教程：https://docs.github.com/zh
- Git 官方图解：https://git-scm.com/book/zh/v2
- OpenClaw 文档：https://docs.openclaw.ai

## License

MIT
