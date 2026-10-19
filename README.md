# Goal Prompt Template

把一句话目标整理成可执行提示词。明确要求“你来执行最佳实践”时，先理清任务，再完成已授权的工作。

[MIT](LICENSE) · [技能规则](SKILL.md) · [图文设置教程](docs/personalization.md) · [更新公告](docs/releases/v1.1.0.md) · [English](README.en.md)

## 两种用法

| 你的要求 | 技能会做什么 |
| --- | --- |
| 帮我优化提示词、写模板、生成 `/goal` 提示词 | 输出可复制的最终提示词 |
| 帮我完成这件事，你来执行最佳实践 | 明确目标和完成标准，执行已授权任务，验证并交付 |

信息不阻塞时采用合理假设。只有缺失信息影响正确执行或授权范围时才追问，最多三个问题。检查或修复任务尚未授权修改时，会先提交方案；已经授权的操作按约定继续。

## 安装

在终端运行以下命令，将技能克隆到当前官方文档列出的用户技能目录。目标目录需为空或不存在。

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/linhucong814-cyber/goal-prompt-template-skill.git ~/.agents/skills/goal-prompt-template
```

更新通过上述方式安装的技能：

```bash
git -C ~/.agents/skills/goal-prompt-template pull --ff-only
```

已有 `~/.codex/skills/goal-prompt-template` 安装的用户，先确认自己的 Codex 能发现该目录，再选择保留或迁移；避免重复安装同名技能。更新后若未显示，重启 Codex。

## 直接调用

只生成提示词：

```text
$goal-prompt-template 把“做一个自动整理会议纪要的工具”变成可执行提示词。
```

执行任务：

```text
$goal-prompt-template 帮我给这个开源项目补齐安装教程和使用示例，你来执行最佳实践。完成后检查文档链接。
```

生成长期任务的提示词：

```text
$goal-prompt-template 帮我写 /goal：检查这个网站的移动端体验，给出修复方案，等我批准后修改。
```

## 使用技巧：添加到“个性化”

安装后进入 **设置 → 个性化 → 自定义指令 → Codex 指令**，添加使用偏好。

![在个性化中打开 Codex 指令](docs/images/codex-personalization-entry.png)

![填写两个技能的使用习惯](docs/images/codex-custom-instructions.png)

截图由维护者提供，具体界面随版本变化。推荐指令和操作说明见 [完整教程](docs/personalization.md)，也可直接复制 [个性化指令示例](examples/personalization.txt)。该示例同时使用 [自然语气](https://github.com/linhucong814-cyber/lieflat-less-ai-tone)，需要另行安装。

## 本次更新

- 新增明确授权后的执行模式，保留提示词和 `/goal` 模板。
- 结合已有授权判断是否需要审批，减少同一范围内的重复确认。
- 补齐中文技能说明、两张设置截图、可复制指令和发布包。

详见 [v1.1.0 发布公告](docs/releases/v1.1.0.md)。

## 文件与许可

`SKILL.md` 是技能规则入口，`agents/openai.yaml` 提供界面说明。`docs/` 和 `examples/` 供使用者查阅。

技能安装与指令机制参考 [OpenAI 官方技能文档](https://learn.chatgpt.com/docs/build-skills) 和 [AGENTS.md 指南](https://learn.chatgpt.com/docs/agent-configuration/agents-md)。

[MIT License](LICENSE)。
