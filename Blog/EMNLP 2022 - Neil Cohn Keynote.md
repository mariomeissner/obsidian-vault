---
draft: false
title: EMNLP 2022 - Neil Cohn's Keynote
date: '2022-12-10'
tags: [research, nlp]
---

This post summarizes the keynote speech given by [[Neil Cohn]] at [[EMNLP-2022]]. He addressed the need to treat visual language as a first class language citizen. First, he showed how visual language shares many of the same properties that our spoken and written languages share, such as grammar, structure, and clear distinctions among the visual languages of different countries. He concluded with the announcement that he is working on releasing a large-scale visual language dataset based on comics from a large variety of countries with detailed annotations that can be used to further study the properties of visual languages. I especially liked his overview of how visual language fits into the broader scope of language in general. See below for details.

## Visual Language as a first class citizen
Cohn started his keynote by showcasing how comics have structured grammar and distinct properties among countries. First, he drew parallels between language grammars and comic structure.

![](/Images/cohn_graphic_grammar.jpeg)

In this example, an embedded clause is contained in the narrative, and both the main storyline and the embedded storyline work well by themselves. This kind of structure is analogous to embedded clauses in natural languages.

![](cohn_grammar_tree.jpeg)

Here, the syntax tree for the graphic narrative is shown.

Further, graphic language such as comics does require a learning and acquisition stage, as it was shown that highly illiterate groups are not able to understand graphic structures such as comics. This acquisition is in a sense akin to natural language learning.

Finally, graphic language is different among regions, some exhibiting unique properties in their narrative and style, again resembling natural language. For example, Asian and especially Japanese Comics (Manga) show much more frequent close-up scenes such as face-only or eyes-only, while American-style comics show full-frame scenes with a higher frequency.

## Cohn's Language Model
Graphic language fits into Cohn's proposed high-level model as a first-class component along written, spoken and body language, and consume similar grammatical structures to map to the same conceptual space.

![](cohn_model.jpeg)

## The Comics Dataset
His works involves annotating and releasing [datasets](https://dataverse.nl/dataset.xhtml?persistentId=doi:10.34894/LWMZ7G) to enable graphic language research. He announced that a new, larger scale dataset is on the works and may be released in the following months / years.

The talk convinced me about the need to incorporate graphic language as a first-class member of NLP, and should be considered in future multi-modality research alongside sign-language, body language and other kinds of visual information.