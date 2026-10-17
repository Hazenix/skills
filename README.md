# 我的 Agent Skills

把实际使用中沉淀下来的 Skill 放在一个入口：模拟面试、个人编码与架构习惯、新电脑初始化，以及开发流程工具。

每个 Skill 在独立仓库中维护。点击下面的仓库名查看说明和最新内容；上方带箭头的目录是 Git submodule，可以跳转到对应仓库的已收录版本。

## 我的 Skills

| 仓库 | 用途 | Skill 入口 |
| --- | --- | --- |
| [backend-interview-simulator](https://github.com/Hazehacker/backend-interview-simulator) | Java / Go / C++ 后端模拟面试，支持不同求职阶段、面试官风格、简历与 JD、追问和评估反馈 | [SKILL.md](https://github.com/Hazehacker/backend-interview-simulator/blob/main/SKILL.md) |
| [ai-dev-interview-simulator](https://github.com/Hazehacker/ai-dev-interview-simulator) | AI 应用开发模拟面试，覆盖 LLM、Agent、RAG、MCP 等方向 | [SKILL.md](https://github.com/Hazehacker/ai-dev-interview-simulator/blob/main/SKILL.md) |
| [code-like-me](https://github.com/Hazehacker/code-like-me) | 将我的编码习惯、架构取舍和 Review 经验沉淀为可复用的判断方法 | [SKILL.md](https://github.com/Hazehacker/code-like-me/blob/codex/publish-skill/SKILL.md) |
| [init-new-computer](https://github.com/Hazehacker/init-new-computer) | 初始化新 Mac：环境盘点、配置备份、开发工具安装、个人设置迁移和运行验证 | [skills/init-new-computer/SKILL.md](https://github.com/Hazehacker/init-new-computer/blob/main/skills/init-new-computer/SKILL.md) |

## Fork 的技能集合

| 仓库 | 用途 | 上游 |
| --- | --- | --- |
| [superpowers-bzh](https://github.com/Hazehacker/superpowers-bzh) | 覆盖需求梳理、计划、开发、调试、代码审查和验证的技能集合，具体技能位于 `skills/` | [obra/superpowers](https://github.com/obra/superpowers) |

## 怎么用

只想用某一个 Skill，直接进入对应仓库，按它的说明安装。`init-new-computer` 的入口在子目录，`superpowers-bzh` 是一整套技能，安装方式以各仓库说明为准。

需要把所有仓库一起下载到本地：

```bash
git clone --recurse-submodules https://github.com/Hazehacker/skills.git
cd skills
```

如果已经普通克隆了总仓库，补拉子模块：

```bash
git submodule update --init --recursive
```

这一步只下载仓库，不会自动安装技能或执行其中的脚本。

## 版本与维护

子模块记录的是具体 commit。各子仓库发布新提交后，这里的目录不会自动跳到最新版；README 中的仓库链接始终可以访问各仓库的当前默认分支。

拉取总仓库已经收录的版本：

```bash
git pull --ff-only
git submodule update --init --recursive
```

维护这个导航仓库时，更新到 `.gitmodules` 指定分支的最新提交，再检查改动：

```bash
git submodule update --init --remote
git diff --submodule=log
```

确认后，提交发生变化的子模块路径即可。当前 `code-like-me` 跟踪 `codex/publish-skill`，其余子模块跟踪 `main`。

新增 Skill 时，用 `git submodule add -b <分支名> <仓库地址> <目录名>` 添加引用，并在上方表格补充用途与入口；将 `.gitmodules`、新子模块路径和 `README.md` 一起提交。

本仓库仅收录已公开的 Skill 仓库。各子仓库的作者、许可证和使用说明以其自身内容为准。
