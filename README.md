# 即梦 / Seedance 2.5 剧情片提示词 Skill

用户只写一两句剧情想法，这个 Skill 把它扩写成一组可直接用于 Seedance 2.5（即梦）的专业提示词：按戏剧节拍拆成多条片段，依次生成后即可剪成一部短片。

写法遵循火山方舟《Doubao Seedance 2.5 提示词指南》和官方 sd25-pe Skill。官方 sd25-pe 负责把一条提示词优化到位；本 Skill 侧重它不覆盖的部分：把故事拆成多段、全组统一角色与素材设定、用视频延长和首帧把片段接起来。

## 能做什么

- 把简单想法补全为有起承转合的故事，保留用户写下的人物、地点、物件和台词
- 拆成多条可单独提交、可拼接的片段，写清景别、运镜、站位、表演和光影
- 像摄影指导一样选配全组共用的机身、胶片和镜头组，把器材写成可见效果，并为每个镜头选焦段
- 把用户的风格拆成色彩、光线、质感、镜头特性和运动五个维度，落到每个镜头
- 为每段选择生成方式：参考生成、向后延长上一段、或用上一段尾帧作首帧
- 用固定的角色名、外观句和风格句锁定跨片段的人物与画风
- 按官方格式写对白（`{台词}`）、音效（`<>`）和配乐（`()`），规避意外字幕、配乐漏出和眼睛发光
- 支持 @参考图/视频/音频映射、首尾帧、关键帧、宫格分镜和视频无缝转场
- 可选丝滑转场模块：从日常画面无缝进入宏景、回忆或梦境

不适用于纯图片提示词，或与视频生成无关的剧本写作。

## 示例请求

```text
女孩在雨夜便利店等一个不会来的人。
```

```text
古装短剧，三段：将军出征前和妻子告别，@图片1 是将军，@图片2 是妻子，要有对白。
```

## 安装

Skill 的目录名需要与 `SKILL.md` 中的 `name` 一致，请克隆到名为 `seedance-story-prompts` 的目录。

**Claude Code**

```bash
git clone https://github.com/ogen35/seedance-story-prompts.git ~/.claude/skills/seedance-story-prompts
```

使用 `/seedance-story-prompts` 调用；请求与 Skill 描述匹配时也会自动调用。

**Codex**

让 `$skill-installer` 从本仓库安装，或手动克隆到个人或项目的 `.agents/skills/seedance-story-prompts`。使用 `$seedance-story-prompts` 调用。

## 文件结构

```text
.
├── SKILL.md                      # 工作流、输出结构、审计
├── agents/
│   └── openai.yaml               # Codex 界面元数据
├── references/
│   ├── story-example.md          # 完整输出示例
│   ├── prompt-craft.md           # 景别、运镜、表演、光影、声音、失败模式
│   ├── cinematography.md         # 机身、胶片、镜头组、焦段、特种拍摄、风格拆解
│   ├── assets-and-continuity.md  # 素材映射、延长、首尾帧、关键帧、无缝转场
│   └── smooth-transition.md      # 可选：丝滑转场模块
└── evals/
    ├── evals.json                # 输出质量评测用例
    └── trigger-evals.json        # 触发边界评测用例
```

## 说明

这是社区创作的提示词工作流，不隶属于或代表即梦、Seedance、字节跳动、OpenAI 或 Anthropic。Skill 中的能力数字（单段 30 秒、最多 50 份参考素材等）取自 2026 年 10 月的官方指南，模型更新后请以平台实际为准，并结合生成结果迭代提示词。

## License

[MIT](LICENSE)
