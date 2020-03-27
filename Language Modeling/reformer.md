## Reformer: The Efficient Transformer

[Transformer models](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html) efficiently extend the context window that helps to improve language understanding while at the same time requiring less computation and speeding up training via a self-attention mechanism. However, as you keep increasing the context window to even larger sizes at some point the Transformer becomes impractical due to the number of comparisons it has to perform and its memory requirements. Thus, it may only be possible to apply the Transformer model to limited text sizes and to generate short statements or pieces of music.

To address some of the limitations identified in the Transformer model, [Kitaev et al. (2020)](https://arxiv.org/abs/2001.04451) propose an efficient variant of a Transformer model called [Reformer](https://ai.googleblog.com/2020/01/reformer-efficient-transformer.html). The two main objectives are to allow for longer context by reducing the complexity of the attention mechanism and to reduce memory footprint.

To achieve both requirements, Reformer first uses locality-sensitive-hashing ([LSH](https://en.wikipedia.org/wiki/Locality-sensitive_hashing)) to group similar vectors together and creates segments out of them, which enable parallel processing. The attention is then applied to these smaller segments and corresponding neighbouring parts — this is what reduces the computational load.

Secondly, memory efficiency is accomplished using [reversible layers](https://arxiv.org/abs/1707.04585) that allow the input of each layer to be recomputed on-demand (as opposed to storing it in memory) while training. This is a simple technique that avoids the model of the need to store the activations of each layer in memory, which is very expensive when the context window is too large and you are working with multiple layers that you need to backpropagate through — typically the case with a Transformer model. The way it works is that the activations (input) coming from the last layer are used to recover the activations in the intermediate layer. This is made possible by simply running the network in reverse which is achievable through the subtraction of the activations that were applied at each layer, depicted as part “c” in the figure below. Part “b” shows that two sets of activations need to be defined to be able to achieve the recovery of activations. Part “a” is referring to the standard transformation applied to inputs that go through a layer as applied in residual networks.

![img txt](https://github.com/dair-ai/nlp_paper_summaries/blob/master/images/reformer.png)

_(Nikita et al., 2020)_

Applications, where the Reformer is beneficial involve those that depend on large-context data such as in image generation and for generating long and coherent sequences.
