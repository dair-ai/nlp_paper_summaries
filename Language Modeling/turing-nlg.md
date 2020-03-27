## Turing-NLG: A 17-billion-parameter language model by Microsoft

Turing Natural Language Generation (T-NLG) is a 17-billion-parameter language model [proposed](https://www.microsoft.com/en-us/research/blog/turing-nlg-a-17-billion-parameter-language-model-by-microsoft/) by Microsoft AI researchers. Besides being the largest known language model to date, T-NLG is a 78-layers Transformer-based language model that outperforms the previous state-of-the-art results (held by NVIDIA’s [Megatron-LM](https://github.com/NVIDIA/Megatron-LM)) on WikiText-103 perplexity. It was tested on a variety of tasks such as question answering and abstractive summarization while demonstrating desirable benefits such as zero short question capabilities and minimizing supervision, respectively. The model is made possible by a training optimization library called [DeepSpeed](https://github.com/microsoft/DeepSpeed) with ZeRO, ZeRO ([Samyam et al., 2019](https://www.microsoft.com/en-us/research/publication/zero-memory-optimization-towards-training-a-trillion-parameter-models/)) being the solution for reducing memory footprint while at the same time scaling computation.

![img txt](https://github.com/dair-ai/nlp_paper_summaries/blob/master/images/distill.png)

_Language models represented by the size of parameters (figure adopted from DistilBERT)_

T-NLG basically uses 78 Transformer layers and is trained using the same hyperparameters as Megatron-LM. Using the optimization library called DeepSpeed, the language model training time is reduced by three times. T-NLG is trained on the same data as Megraton-LM and the pre-trained version was used to test on the task of WikiTex-103 perplexity and LAMBDA next word prediction accuracy. T-NLG (17B) outperforms both OpenAI GPT-2 (1.5B) and Megatron-LM (8.3B) on both tasks.

It is interesting to see that training a language model on 17 billion parameters shows improvement in results as demonstrated in the experiments with the downstream NLP tasks (e.g. [question answering](http://nlpprogress.com/english/question_answering.html) and [abstractive summarization](http://nlpprogress.com/english/summarization.html)). As claimed by the authors, the bigger the models, the better it generalizes to perform better on downstream tasks, especially in the low-data regime. This also means that the technology stack, including libraries and hardware, used to train these enormous language models have to be optimized, which is the innovative part proposed by T-NLG. Optimal hardware setup and a reduction in model-parallelism degree allow T-NLG to be trained more efficiently with fewer GPUs (256) than the state-of-the-art at the time, Megatron-ML (1024 NVIDIA GPUs).


It will be interesting to see how Microsoft researchers apply T-NLG in production across their different products and build more fluent chatbots and digital assistants for improving customer experience.



