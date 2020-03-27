## Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer

Text-to-Text Transformer is a method that brings together all the lessons learned and recent improvements from NLP transfer learning models into one unified framework called Text-to-Text Transfer Transformer (T5 for short)([Raffel et al., 2019](https://arxiv.org/abs/1910.10683)).

This work proposes that most NLP tasks can be formulated in a text-to-text format, suggesting that both the inputs and outputs are texts, which is the case for a variety of NLP tasks. The authors claim that this “framework provides a consistent training objective both for pre-training and fine-tuning”. T5 is essentially an encoder-decoder Transformer that applies various improvements in particular to the attention components of the model. The model was pre-trained on a newly released dataset called [Colossal Clean Crawled Corpus](https://www.tensorflow.org/datasets/catalog/c4) and achieved SOTA results on NLP tasks such as summarization, question answering, and text classification.

This work proposes a unified approach that can allow ease of analysis of transfer learning for NLP approaches. This has been a challenge as current methods have different objectives and training procedures and are difficult to compare. T5 allows experimentation of different datasets, tasks, objectives for better understanding the limits, efficiency, and effectiveness of transfer learning for NLP models and how they scale in terms of data and modeling.

![img txt](https://github.com/dair-ai/nlp_paper_summaries/blob/master/images/t5.png)

In the future, authors aim to build language-agnostic models, cheaper models that achieve stronger performance, improved knowledge extraction through smarter and efficient pretraining tasks, among other strategies.
