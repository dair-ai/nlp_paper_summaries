## ELECTRA: Pre-training Text Encoders as Discriminators Rather Than Generators

[Clark et al. (2020)](https://openreview.net/forum?id=r1xMH1BtvB) propose a more sample-efficient pretraining task called replaced token detection for training a language model that is more efficient than masked language modeling (MLM) pretraining methods such as BERT. The model, coined ELECTRA, and its contextualized representations outperform those of BERT ([Devlin et al., 2019](https://arxiv.org/abs/1810.04805)) and XLNET ([Yang et al., 2019](https://arxiv.org/abs/1906.08237)) on the same data and model size. The method particularly works well on the low-compute regime. This is an effort to build smaller and cheaper language models.

In essence, the model proposes a new pre-training task called replaced token detection in which the model is trained to distinguish the real input tokens from generated replacements. First, some tokens from the input are corrupted and replaced by samples from a generator network, typically a small MLM. This means that the generator part of the model (shown in the figure below) learns to predict the original identities of the corrupted tokens. The network is then pre-trained as a discriminator that aims to predict whether each token is an original or a replacement, i.e. replaced token prediction. This differs from the use of just the MLM task which trains the network to instead predict the original identities of the corrupted tokens.

![img txt](https://github.com/dair-ai/nlp_paper_summaries/blob/master/images/electra.png)

_ELECTRA — (Clark et al., 2020)_


The main advantages of this new pre-training task are that it is more computationally and parameter efficient as all the input is considered and after pre-training only the discriminator is fine-tuned for downstream tasks, while the generator is left out. This means that we don’t need to worry about the discrepancy of the [MASK] token during fine-tuning as is the case with the original BERT model. This particular model is shown to be effective for language representation learning and requiring less compute than other methods such as GPT and [XLNet](https://medium.com/dair-ai/xlnet-outperforms-bert-on-several-nlp-tasks-9ec867bb563b). It could pave the way for building smaller and more effective models that optimize for pre-training.
