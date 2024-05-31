---
"title:": "Train Flat, then Compress: Sharpness-Aware Minimization Learns More Compressible Models"
citekey: naTrainFlatThen2022
authors: Clara Na, Sanket Vaibhav Mehta, Emma Strubell
year: 2022
doi:
---

# Train Flat, Then Compress: Sharpness-Aware Minimization Learns More Compressible Models

## Abstract
Model compression by way of parameter pruning, quantization, or distillation has recently gained popularity as an approach for reducing the computational requirements of modern deep neural network models for NLP. Inspired by prior works suggesting a connection between simpler, more generalizable models and those that lie within wider loss basins, we hypothesize that optimizing for flat minima should lead to simpler parameterizations and thus more compressible models. We propose to combine sharpness-aware minimization (SAM) with various task-specific model compression methods, including iterative magnitude pruning (IMP), structured pruning with a distillation objective, and post-training dynamic quantization. Empirically, we show that optimizing for flatter minima consistently leads to greater compressibility of parameters compared to vanilla Adam when fine-tuning BERT models, with little to no loss in accuracy on the GLUE text classification and SQuAD question answering benchmarks. Moreover, SAM finds superior winning tickets during IMP that 1) are amenable to vanilla Adam optimization, and 2) transfer more effectively across tasks.

## Notes

An adapted loss function looks for minima that have a flat area around them, meaning that the solution should be more "robust" in some way. This has previously known to be good for generalization, and this paper shows that it is also very good for compression.

*Related work on flatness and generalization:*
>Prior work has investigated the connection between flat minima and generalization (i.e., the gap between training accuracy and holdout set accuracy), starting with Hochreiter and Schmidhuber (1997).

## #research_questions

- Would it help to combine this with [[movement pruning]]? I still consider it to be a superior method to [[IMP]], so any time I see [[IMP]] being used, I tend to think [[movement pruning]] should also be considered.
- The [[sharpness-aware loss function]] seems to be a nice concept in general, which makes me think that there may be more benefits to it other than compressibility. How about generalizability, transferability, etc?
	- This is partially answered in the related work section, where several works talk about improved generalizability.
- Given the above, why aren't we using the [[sharpness-aware loss function]] more frequently? What are its major drawbacks?