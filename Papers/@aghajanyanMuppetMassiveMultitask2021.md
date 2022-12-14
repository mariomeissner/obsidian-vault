---
title: Muppet: Massive Multi-task Representations with Pre-Finetuning
citekey: aghajanyanMuppetMassiveMultitask2021
authors: Armen Aghajanyan, Anchit Gupta, Akshat Shrivastava, Xilun Chen, Luke Zettlemoyer, Sonal Gupta
year: 2021
doi: 
---

# Muppet: Massive Multi-task Representations with Pre-Finetuning
([Open in Zotero](zotero://select/items/@aghajanyanMuppetMassiveMultitask2021))

## Abstract
We propose pre-finetuning, an additional large-scale learning stage between language model pre-training and fine-tuning. Pre-finetuning is massively multi-task learning (around 50 datasets, over 4.8 million total labeled examples), and is designed to encourage learning of representations that generalize better to many different tasks. We show that pre-finetuning consistently improves performance for pretrained discriminators (e.g.~RoBERTa) and generation models (e.g.~BART) on a wide range of tasks (sentence prediction, commonsense reasoning, MRC, etc.), while also significantly improving sample efficiency during fine-tuning. We also show that large-scale multi-tasking is crucial; pre-finetuning can hurt performance when few tasks are used up until a critical point (usually above 15) after which performance improves linearly in the number of tasks.

## Notes
