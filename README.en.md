# Goal Prompt Template

Turn a short goal into an executable agent prompt. When the user explicitly asks to execute the task, define the scope and acceptance criteria, complete the authorized work, and verify the outcome.

[中文](README.md) · [Skill instructions](SKILL.md) · [Illustrated setup guide in Chinese](docs/personalization.md) · [Release notes](docs/releases/v1.1.0.md)

## Install

Clone into an unused user skill directory:

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/linhucong814-cyber/goal-prompt-template-skill.git ~/.agents/skills/goal-prompt-template
```

To update that checkout, run `git -C ~/.agents/skills/goal-prompt-template pull --ff-only`. Avoid installing the same skill in multiple discovery directories. Restart Codex if changes do not appear.

## Use

Ask `$goal-prompt-template` to write a prompt, or explicitly ask it to complete your task using best practices. Prompt-only requests return a copyable prompt. Execution requests continue through verification and delivery within the existing authorization.

The illustrated Chinese guide shows how to add preferences in Settings → Personalization → Codex instructions. Installing the skill and adding a preference are separate steps.

[MIT License](LICENSE). Local discovery follows the [official skill documentation](https://learn.chatgpt.com/docs/build-skills).
