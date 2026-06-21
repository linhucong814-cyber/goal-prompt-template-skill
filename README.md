# Goal Prompt Template Skill

一个用于 Codex 的提示词优化 skill。它可以把一句粗略目标、中文想法或一句话需求，整理成可直接交给 Codex、agent 或 `/goal` 执行的最终提示词。

## 功能

- 将一句话目标优化成结构清晰的 agent prompt
- 自动整理适合 `/goal` 使用的长期任务提示词
- 明确任务目标、背景、范围、约束、交付物和完成标准
- 尽量少问问题，只有信息真正阻塞执行时才最多提出 3 个关键问题
- 对检查、调试、修复、重构、UI review 等任务自动加入审批闸门：检查完成之后制定修复方案并向我汇报，在批准后执行

## 适用场景

- 优化提问
- 一句话达成目的
- 自动翻译成 agent 提示词
- 生成可复制的 `/goal` 任务模板
- 把模糊想法变成可执行任务
- 减少 agent 来回追问，提高首次执行质量

## 安装

克隆仓库后，将 skill 复制到 Codex 的 skills 目录，并确保目标目录名是 `goal-prompt-template`：

```bash
git clone https://github.com/linhucong814-cyber/goal-prompt-template-skill.git
mkdir -p ~/.codex/skills
cp -R goal-prompt-template-skill ~/.codex/skills/goal-prompt-template
```

如果 Codex 已经打开，安装后建议重启 Codex 或开启新线程，让 skill 列表刷新。

## 使用方法

在 Codex 中显式调用：

```text
$goal-prompt-template 检查首页移动端排版问题并生成可执行修复任务
```

也可以这样写：

```text
Use $goal-prompt-template 把“做一个可以自动整理会议纪要的工具”变成最终可执行提示词
```

生成 `/goal` 任务：

```text
$goal-prompt-template 帮我写 /goal：把这个网站做一次完整 UI 检查并输出修复方案
```

## 输出特点

这个 skill 会优先输出可直接复制执行的最终提示词，而不是再让另一个 AI 去“帮你写提示词”。它会基于用户原始目标补全合理背景和执行标准，并把非阻塞信息作为假设写入提示词中。

当信息不足但仍可继续时，它会继续生成暂定提示词。当信息缺失会导致执行不安全、不可验证或方向完全不同，它才会先提出最多 3 个关键问题。

## 文件结构

```text
goal-prompt-template/
├── SKILL.md
└── agents/
    └── openai.yaml
```

## License

MIT License
