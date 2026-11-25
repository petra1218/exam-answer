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
        题型模板.md
        计算题写法.md
        计算命令.md
        复利系数表.md
        答案册规范.md
        故障排查.md
      INSTALL.md（本文件，可不复制）
      README.md
      CHANGELOG.md
      LICENSE
      .gitignore（可不复制）

各 agent 的技能目录：

| agent | 技能目录 | 状态 |
|---|---|---|
| WorkBuddy | ~/.workbuddy/skills/（各平台同一写法） | 可用 |
| Claude Code | ~/.claude/skills/ | 未测 |
| Cursor | ~/.cursor/skills/ | 未测 |
| 其他 | 查该 agent 的技能目录文档 | 未测 |

没有技能目录机制的 agent：把 SKILL.md 和 references/ 的内容作为系统提示词或项目规范文件加载，效果等同。

## 3. 运行自检

装完后对用户执行一次技能的"自检"指令（见 SKILL.md 指令一）。自检单独开一个会话，不要和开考共用；它只读每门课的导览，不读课件，不报字符数。自检通过（或明确报出缺什么、怎么补）即安装成功。想抽查课件是否读得全，用"深度自检"。

可选：提示用户可以设"本人情况"，用于"结合本企业或本项目"的题。三种给法见 SKILL.md 指令二第 3 步——贴文字、发一份个人材料（报名表、简历、项目经历说明，Word、PDF、图片都行）、或更新已有内容。材料只在会话里读，不上传、不入库。读不了按故障排查第 12 条降级。别在安装时就追问，用户需要时再说。

## 4. 报告

向用户报告：版本号、自检结论、你的技能目录路径。如果第 1 步克隆失败，换 GitCode 地址重试一次；两个都失败就把缺什么告诉用户。

## 环境说明

- 本仓库在 Windows 上的 WorkBuddy 里跑通过；其他 agent 与系统未单独测，装完以自检结果为准。
