# INSTALL（给 agent 看的安装说明）

你（agent）收到这条指令，说明用户要把 exam-answer 技能装到你这里。照下面做。

## 1. 取仓库

优先 GitHub：

    git clone https://github.com/petra1218/exam-answer.git

或（国内网络）GitCode：

    git clone https://gitcode.com/petra1218/exam-answer.git

也支持 npx skills add petra1218/exam-answer（只认 GitHub 地址）。实测注意：它的 79 个 agent 支持列表里没有 WorkBuddy，会把技能装到项目内的 .agents/skills/，WorkBuddy 读不到；WorkBuddy 请走上面的克隆复制方式。非交互安装需加 --agent <名称> -y，例如 --agent universal -y。

## 2. 复制技能目录

把仓库根目录下的 SKILL.md、references/、README.md、CHANGELOG.md、LICENSE 复制到你的技能目录下的 exam-answer/ 文件夹。结构：

    <技能目录>/exam-answer/
      SKILL.md
      references/
      INSTALL.md（本文件，可不复制）
      README.md
      CHANGELOG.md
      LICENSE
      .gitignore（可不复制）

各 agent 的技能目录：

| agent | 技能目录 | 状态 |
|---|---|---|
| WorkBuddy (Windows) | C:\Users\<用户名>\.workbuddy\skills\ | 已验证 |
| WorkBuddy (macOS/Linux) | ~/.workbuddy/skills/ | 已验证（路径规则同上） |
| Claude Code | ~/.claude/skills/ | 未验证 |
| Cursor | ~/.cursor/skills/ | 未验证 |
| 其他 | 查该 agent 的技能目录文档 | 未验证 |

没有技能目录机制的 agent：把 SKILL.md 和 references/ 的内容作为系统提示词或项目规范文件加载，效果等同。

## 3. 运行自检

装完后对用户执行一次技能的"自检"指令（见 SKILL.md 指令一）。自检通过（或明确报出缺什么、怎么补）即安装成功。

## 4. 报告

向用户报告：版本号、自检结论、你的技能目录路径。如果第 1 步克隆失败，换 GitCode 地址重试一次；两个都失败就把缺什么告诉用户。

## 已验证环境

- Windows 11 + WorkBuddy（本仓库发布时实测）。
- 其他环境未验证，装完以自检结果为准。
