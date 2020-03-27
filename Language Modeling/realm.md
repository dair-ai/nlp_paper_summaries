## REALM: Retrieval-Augmented Language Model Pre-Training

REALM is a large-scale neural-based retrieval approach that makes use of a corpus of textual knowledge to pre-train a language model in an unsupervised manner (Guu et al., 2020). This approach essentially aims to capture knowledge in a more interpretable way by exposing the model to world knowledge that is used for training and predictions via backpropagation. Tasks approached and evaluated using REALM include open-domain question answering benchmarks. Besides the improvements in the accuracy of the model, other benefits include the modularity and interpretability components.

When training language models, current methods implicitly store the knowledge learned in the parameters of the neural network. This means that it is difficult to say what and where exactly this knowledge is stored. It also means that the more knowledge you want to capture the bigger the networks and the more compute and space are required. REALM offers a way to augment language models by explicitly exposing the model to world knowledge which it can refer to during inference.

During the pre-training of the language model, a neural retrieval module is applied. This neural knowledge retrieval is trained to retrieve useful knowledge from a corpus such as Wikipedia. Then that knowledge is passed on to the knowledge auto-encoder that then predicts the original value of a [MASK] token where masked language model (MLM) is employed as the pretraining task. In essence, the knowledge retriever and the knowledge augmented encoder are jointly trained in an unsupervised way via said task (depicted left of the figure below). The language model is trained is such a way that the knowledge retriever is rewarded if it improves the language model’s perplexity or penalized if it’s uninformative. Once the parameters of both those components have been trained, the fine-tuning process takes in supervised examples that allow for fine-tuning on a downstream task (depicted right of the figure below).

![img txt](https://github.com/dair-ai/nlp_paper_summaries/blob/master/images/realm.png)

_(Guu et al., 2020)_

Open-QA was used for fine-tuning the model where the objective is to produce the answer in the form of a string. REALM outperforms all other previous methods while providing some interpretability due to the way the model is exposed to external knowledge.
