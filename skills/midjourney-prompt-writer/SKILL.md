---
name: midjourney-prompt-writer
description: Write or refine Midjourney image-generation prompts from an idea, visual brief, or reference image. Use when the user asks for a Midjourney or MJ prompt, including Chinese requests such as “写 Midjourney 提示词” or “优化 MJ 提示词”.
---

# Midjourney Prompt Writer

Turn the user's visual intent into an image prompt they can use immediately. This skill covers generating images with or without reference images. It does not cover editing an existing image or generating video.

## Write the image

- Describe the desired final image, not a conversation with Midjourney or a list of editing commands. Keep the prompt concise while retaining details essential to the user's intent.
- Choose precise visual words. Specify counts when the number of subjects matters. Prefer positive descriptions of what should appear; handle genuine exclusions through the separate parameter recommendation when supported.
- Select only useful details from subject, medium, setting, lighting, color, mood, and composition. Avoid adding stock camera jargon, decorative adjectives, or invented constraints.
- Treat an attached image as visual guidance. Use the user's intent to decide which content or style cues matter. Describe the desired final image in full rather than saying “make this image look like…”. Do not promise an exact copy.
- Preserve explicit constraints and established choices during revisions. When the user shares a generation result, identify the visual mismatch and change the relevant words instead of rewriting unrelated parts.
- Ask only when a missing fact would materially change the creative direction; otherwise make a sensible choice and deliver a usable prompt. Provide multiple directions only when requested.

## Deliver every time

Use these three distinct sections, in this order:

1. **English prompt** — ready-to-copy English image description, with no Midjourney parameter syntax.
2. **中文提示词** — a faithful Chinese rendering of the same visual intent, also without parameter syntax.
3. **理想参数** — a small set of context-specific, concrete Midjourney parameter suggestions with values where applicable and a one-sentence reason for each. If no additional parameter is useful, state that the default settings are the recommendation and why. Never silently append parameters to either prompt.

Choose parameters for the user's intended image and delivery surface, rather than applying a fixed preset. Check the current official [Parameter List](https://docs.midjourney.com/hc/en-us/articles/32859204029709-Parameter-List) and linked parameter/version pages before recommending version-sensitive syntax, values, or compatibility. If current documentation is unavailable, avoid unverified version-specific claims and say what could not be checked. Keep reference-image setup outside the text prompt; when relevant, briefly explain which reference role to choose in the parameter section.

## Source principles

- [Prompt Basics](https://docs.midjourney.com/hc/en-us/articles/32023408776205-Prompt-Basics): concise descriptions, precise words and counts, positive framing, and detail according to desired control.
- [Art of Prompting](https://docs.midjourney.com/hc/en-us/articles/32835253061645-Art-of-Prompting): medium, era, emotion, color, and setting are useful choices, not a mandatory checklist.
- [Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts) and [Style Reference](https://docs.midjourney.com/hc/en-us/articles/32180011136653-Style-Reference): references guide content or style; the text still describes the final image.
