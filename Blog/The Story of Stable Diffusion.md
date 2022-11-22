---
title: The Story of Stable Diffusion
date: '2022-10-01'
tags: []
draft: false
summary: A brief summary of my exploration of stable-diffusion-based ML models
---

## Introduction

[[Stable Diffusion]] is a novel image synthesis approach that took the world by surprise and made [big news](https://arstechnica.com/information-technology/2022/09/with-stable-diffusion-you-may-never-believe-what-you-see-online-again/) not only due to its surprising results, but also thanks to being completely open source, as opposed to the recently released alternatives.

- Dalle
- Dalle 2?
- Much smaller size than Dalle (compare parameters?)

## Negative Impact
>others [aren't happy about it](https://twitter.com/arvalis/status/1558623545374023680?s=20&t=iIj1KeOeVDYRwjdQfzAerQ), and society at large still seems largely unaware of the rapidly evolving tech revolution taking place through communities on Twitter, Discord, and Github. Image synthesis arguably brings implications as big as the invention of the camera—or perhaps the creation of visual art itself. Even our sense of history [might be at stake](https://www.fastcompany.com/90549441/how-to-prevent-deepfakes), depending on how things shake out. Either way, Stable Diffusion is leading a new wave of deep learning creative tools that are poised to revolutionize the creation of visual media.

>As a result, Stable Diffusion has absorbed the styles of many living artists, and some of them have [spoken out](https://twitter.com/arvalis/status/1558632898336501761) forcefully against the practice. More on that below.

>As hinted above, Stable Diffusion's public release has [raised alarm bells](https://bakztfuture.substack.com/p/statement-on-stable-diffusion) among people who fear its cultural and economic impact. Unlike DALL-E 2, Stable Diffusion's training data (the "weights") are available for anyone to use without any hard restrictions. The official Stable Diffusion release (and DreamStudio) includes automatic "NSFW" filters (nudity) and an invisible tracking watermark embedded in the images, but these restrictions can [easily be circumvented](https://www.reddit.com/r/StableDiffusion/comments/wv2nw0/tutorial_how_to_remove_the_safety_filter_in_5/) in the open source code. This means Stable Diffusion can be used to create images that OpenAI currently blocks with DALL-E 2: propaganda, violent imagery, pornography, images that potentially violate corporate copyright, celebrity deepfakes, and more.

>(https://bakztfuture.substack.com/p/statement-on-stable-diffusion)
>Personally, I don’t think Emad’s intentions are purely utilitarian. I think it is really interesting that Emad does have commercial intentions through his company - Stability AI. Although I will give them credit for releasing their core model completely to open source, his own company does not tolerate offensive generations themselves - yet, they released a model which is capable of doing so completely uncontrolled at a mass scale. My personal opinion is that he may not necessarily be a true utilitarian. I feel like he’s just more willing to make that scale of a trade off at the expense of everyone else for his company’s market dominance, controversial hype, and financial gain.


## History
- Emad Mostaque: London-based former hedge fund manager whose aim is to bring novel applications of deep learning to the masses through his company, Stability AI
- the roots of modern image synthesis date back [to 2014](https://www.foldl.me/uploads/2015/conditional-gans-face-generation/paper.pdf), and Stable Diffusion wasn't the first image synthesis model (ISM) to make waves this year.
- In April 2022, OpenAI announced [DALL-E 2](https://openai.com/dall-e-2/), which shocked social media with its ability to transform a scene written in words (called a “prompt”)
- Not long after DALL-E 2, [Google](https://imagen.research.google/) and [Meta](https://about.fb.com/news/2022/07/metas-new-ai-research-tool-turns-ideas-into-art/) announced their own text-to-image AI models. [MidJourney](https://www.howtogeek.com/823337/how-to-create-synthetic-ai-art-with-midjourney/), available as a Discord server since March 2022 and open to the public a few months later, charges for access and achieves similar effects but with a more painterly and illustrative quality as the default.
- Then there's Stable Diffusion. On August 22, Stability AI [released](https://stability.ai/blog/stable-diffusion-public-release) its open source image generation model that arguably matches DALL-E 2 in quality. It also launched its own commercial website, called [DreamStudio](https://beta.dreamstudio.ai/), that sells access to compute time for generating images with Stable Diffusion. Unlike DALL-E 2, anyone can use it, and since the Stable Diffusion code is open source, projects can build off it with few restrictions.

## How it works
>Broadly speaking, most of the recent wave of ISMs use a technique called [latent diffusion](https://arxiv.org/abs/2112.10752). Basically, the model learns to recognize familiar shapes in a field of pure noise, then gradually brings those elements into focus if they match the words in the prompt.
>During the training process, the model associates words with images thanks to a technique called [CLIP](https://openai.com/blog/clip/) (Contrastive Language–Image Pre-training), which was invented by OpenAI and announced just last year.

## Technical Details

## Spin-Offs
https://multimodal.art/news/1-week-of-stable-diffusion
https://github.com/topics/stable-diffusion?o=desc&s=stars
https://github.com/nateraw/stable-diffusion-videos
https://github.com/torrinworx/Cozy-Auto-Texture

What are these?
https://paperswithcode.com/paper/dreambooth-fine-tuning-text-to-image
https://github.com/XavierXiao/Dreambooth-Stable-Diffusion
https://paperswithcode.com/paper/text-to-mesh-without-3d-supervision-using

## Prompt Engineering
> At the moment, Stable Diffusion doesn't care if a person has three arms, two heads, or six fingers on each hand, so unless you're a wizard at crafting the text prompts necessary to generate great results (which AI artists sometimes call "prompt engineering"), you'll probably need to generate lots of images and cherry-pick the best ones. Keep in mind that the more a prompt matches captions for [known images in the data set](https://rom1504.github.io/clip-retrieval/?back=https%3A%2F%2Fknn5.laion.ai&index=laion5B&useMclip=false), the more likely you'll get the result you want. In the future, it's likely that models will improve enough to reduce the need for cherry-picking—or some kind of internal filter will do the picking for you.

## The Future
> Stable Diffusion and [other models](https://github.com/THUDM/CogVideo) are already starting to take on dynamic video generation and [manipulation](https://www.reddit.com/r/MachineLearning/comments/wmypmh/a_demo_of_stable_diffusion_a_texttoimage_model/), so expect photorealistic video generation via text prompts before too long. From there, it's logical to extend these capabilities to audio and [music](https://openai.com/blog/jukebox/), [real-time video games](https://twitter.com/benjedwards/status/1300252019534462977?s=20&t=u1vh9HqkMZ-2AeiwGYHPtg), and 3D VR experiences. Soon, advanced AI may do most of the creative heavy lifting with just a few suggestions. Imagine unlimited entertainment generated in real-time, on demand. "I expect it to be fully multi-modal," said Mostaque, "so you can create anything you can imagine, like the Star Trek holodeck experience."