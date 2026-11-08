# Midjourney Prompt Writer

[中文](#中文) · [English](#english)

An independent Codex skill for writing Midjourney **image-generation** prompts. It turns a visual idea or brief into a ready-to-copy English prompt, a matching Chinese prompt, and separate parameter advice. It also works when you provide an image as a content or style reference. It does not generate images, edit existing images, or write video prompts. This project is not affiliated with Midjourney.

## 中文

### 适合谁、什么时候用

- **设计师与产品人员：**将视觉方向、构图和必须保留的细节整理成可测试的提示词。
- **内容创作者与营销人员：**为海报、社交内容或概念图确定画面，再按实际出图快速调整。
- **初学者：**只提供一个想法，也能得到明确的画面描述，而不必先学习提示词术语。

适用于从文字想法生图、结合内容或风格参考图生图、优化已有 Midjourney 提示词，以及比较多个视觉方向。首版不处理修改现有图片或生成视频。

### 与直接让 Codex 写提示词的区别

直接对话也可能得到优秀的提示词。这个 skill 固定了你的工作习惯：每次提供英文和中文两版、将参数单独列出、按 Midjourney 官方写词原则取舍画面细节，并在调整已有结果时聚焦实际偏差。你无需每次重新解释这些偏好。它提高的是**输出一致性和迭代效率**，不能保证 Midjourney 一次生成理想图片。

### 安装到 Codex

将整个 `skills/midjourney-prompt-writer` 文件夹放入个人 Codex skills 目录。下面的命令在全新安装时使用；更新现有安装时，先核对本地改动，再替换该文件夹。

**macOS / Linux**（需要 Git）：

```bash
git clone https://github.com/Roqi-zhang/midjourney-prompt-writer.git
mkdir -p ~/.codex/skills
cp -R midjourney-prompt-writer/skills/midjourney-prompt-writer ~/.codex/skills/
```

**Windows PowerShell**（需要 Git）：

```powershell
git clone https://github.com/Roqi-zhang/midjourney-prompt-writer.git
New-Item -ItemType Directory -Force "$HOME\.codex\skills" | Out-Null
Copy-Item -Recurse "midjourney-prompt-writer\skills\midjourney-prompt-writer" "$HOME\.codex\skills\"
```

安装后开启一个新的 Codex 对话。此 skill 默认允许自动调用；直接说“帮我写一条 Midjourney 提示词”或“优化这条 MJ 提示词”，无需输入 skill 名称。Codex 根据请求与 skill 描述选择是否调用，自动匹配并非绝对保证；需要明确指定时可使用 `$midjourney-prompt-writer`。

### 怎样描述需求

说明你想看到什么、图片用途，以及不能变的关键视觉细节即可。媒介、环境、光线、颜色、情绪和构图有明确要求时再补充；有参考图时说明主要借鉴内容还是风格。没有这些细节也可以从一个简短想法开始。

**输入示例：**“帮我写 Midjourney 提示词：雨后的城市街角，一只橘猫坐在亮着灯的小书店门前，温暖的彩铅插画，竖版海报。”

**输出示例：**

> **English prompt**
>
> Colored pencil illustration of an orange cat sitting outside a warmly lit corner bookshop after rain, reflections on the city pavement, cozy evening mood, vertical poster composition
>
> **中文提示词**
>
> 彩铅插画：雨后城市街角，一只橘猫坐在亮着暖光的书店门前，路面映出倒影，温馨的傍晚氛围，竖版海报构图
>
> **理想参数**
>
> `--ar 4:5`：为竖版海报留出更合适的画面比例。其他设置先保持默认，再根据第一轮出图调整。

将英文提示词复制到 Midjourney，按需要把参数建议附在末尾。中文版本用于核对画面意图。出图后告诉 Codex 具体偏差，例如“猫太小、书店灯光不明显”，它会针对这些问题调整提示词。参考图用于引导创作，不能保证精确复刻。

### 更新与来源

在克隆的仓库中运行 `git pull` 获取新版，再将 `skills/midjourney-prompt-writer` 文件夹复制到个人 skills 目录，开启新对话。参数及模型兼容性可能变化；skill 会在提出版本相关建议时核对官方文档。写词原则来自 [Prompt Basics](https://docs.midjourney.com/hc/en-us/articles/32023408776205-Prompt-Basics)、[Art of Prompting](https://docs.midjourney.com/hc/en-us/articles/32835253061645-Art-of-Prompting)、[Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts) 与 [Style Reference](https://docs.midjourney.com/hc/en-us/articles/32180011136653-Style-Reference)。参数依据为官方 [Parameter List](https://docs.midjourney.com/hc/en-us/articles/32859204029709-Parameter-List)。

## English

### Who it is for and when to use it

- **Designers and product teams:** turn visual direction, composition, and essential details into prompts that can be tested.
- **Creators and marketers:** develop images for posters, social content, and concepts, then revise them against generated results.
- **Beginners:** start with a rough idea without learning prompt jargon first.

Use it for text-to-image creation, creation with content or style references, prompt refinement, or comparing visual directions. The first release does not cover editing an existing image or generating video.

### How it differs from a direct Codex request

Codex can already write a good prompt in an ordinary conversation. This skill makes your preferred workflow repeatable: English and Chinese versions every time, parameters in a separate section, selective visual detail based on Midjourney's official guidance, and focused revisions when an image misses the target. It improves consistency and iteration speed; it does not guarantee a perfect image on the first try.

### Install for Codex

Copy the entire `skills/midjourney-prompt-writer` directory into your personal Codex skills directory. The commands above cover macOS, Linux, and Windows. They assume a fresh install; review local changes before replacing an existing copy. Start a new Codex conversation after installation.

Ask naturally, for example: “Write a Midjourney prompt for a rainy city bookshop poster” or “Refine this MJ prompt.” The skill allows automatic invocation; Codex decides whether a request matches its description, so automatic selection is not an absolute guarantee. Use `$midjourney-prompt-writer` when you need to invoke it explicitly.

### Input, output, and iteration

Describe the desired subject, purpose, and any non-negotiable details. Add medium, environment, light, palette, mood, or composition only when they matter. If you attach a reference image, say whether its content or style is the main guide. The skill returns an **English prompt**, a faithful **Chinese prompt**, and separate **ideal parameter recommendations** with reasons. Copy the English prompt into Midjourney and append any parameters you choose to use. After generating, report concrete mismatches so Codex can revise the relevant wording.

The Chinese example above shows the full output format. Reference images guide new creations rather than guarantee exact reproduction. For updates, pull the repository and replace the installed skill folder, then start a new conversation. The official Midjourney sources are linked in the Chinese section above.

## License

MIT. See [LICENSE](LICENSE).
