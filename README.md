# 即梦 / Seedance 写实剧情片丝滑转场 Skill

把粗略的剧情短片构想，扩写成可直接用于即梦、Seedance 或同类视频生成模型的高密度中文提示词。

这个 Skill 从真实可感的生活场景和人物动作出发，通过视觉收束、遮挡或图形匹配，把镜头自然带入更宏大的电影场景。它强调生活段的写实感、人物和动作连续性，以及宏景揭示后的叙事余韵，适合制作带有剧情感的一镜到底式短片转场。

## 能做什么

- 将一句剧情或场景构想扩写为可复制的视频生成提示词
- 设计 match cut、遮挡切换、纹理接管、粒子升格等转场
- 明确时间轴、镜头路径、速度曲线和隐藏切点
- 锁定人物、手部、服装和道具，减少身份漂移
- 保留前段的生活质感，并把后段提升为电影级摄影语言
- 自动补充与方案相关的负面约束
- 支持单条转场、首尾帧方案和连续转场链

## 示例请求

```text
使用 $generate-seedance-smooth-transition-prompts，把“咖啡杯中的奶泡旋涡转成海上台风云眼”写成 8 秒、9:16 的即梦丝滑转场提示词。
```

## 安装

你可以直接让 Codex 的 `$skill-installer` 从本 GitHub 仓库安装，也可以手动把整个仓库目录复制到个人或项目的 `.agents/skills/` 目录中。

安装后，在提示词中使用：

```text
$generate-seedance-smooth-transition-prompts
```

Codex 也可以在用户请求与 Skill 描述匹配时自动调用它。

## 文件结构

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── transition-framework.md
```

## 说明

这是社区创作的提示词工作流，不隶属于或代表即梦、Seedance、字节跳动或 OpenAI。不同模型版本的生成结果可能不同，建议结合实际素材迭代提示词。

## License

[MIT](LICENSE)
