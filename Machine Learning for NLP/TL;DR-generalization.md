## UNDERSTANDING DEEP LEARNING REQUIRES RETHINKING GENERALIZATION
**TL;DR (Insights, Learnings, Observations and questions)**

### Insights:
The paper is on understanding generalization error (difference between in-sample and out- sample error) and seeks to question the applicability of traditional generalizability metrics like VC dimension, Rademacher complexity and Uniform stability when applied to deep neural networks, in this case, CNN’s. The main argument being are these metrics robust enough to understand the complex nature of generalization in neural networks ?

The CNN models were able to learn with ~0 training error even after randomizing the labels and picture pixels. This experiment suggests that that learning models memorize the data and their ability to learn is questionable since there is no inherent correlation between the pictures and labels (labels and pixels are randomized). The authors also claim that the explicit regularization is important yet a non-critical factor affecting generalization error. This claim is corroborated by experiments run by them (fig2 a and b of the paper) using methods like data augmentation, L2 (weight decay), drop out and batch normalization. Here, models which were not explicitly regularized also exhibited low generalization error.

### Learnings:
1) Stochastic gradient descent implicitly regularises the models.
2) Treat regularization as a model parameter which can be tuned.
3) L2 (Weight decay) regularization can sometimes help in optimization by making cost function more convex.
4) Even small NN’s (depth = 2) of large enough width for the input sample can have the expressing power to represent data. This makes more sense after getting to know that even Word2vec is a two-layered network and still possesses amazing representation power!

### Observations and Questions:
1) Exactly why do the “shuffled” and “random” pixels converge faster than random labels (a direction is suggested in the paper)?
2) Is similar stuff (as mentioned in insights) observed in kernel methods like SVM? If yes then why do the authors only attack the applicability of VC dimension, Rademacher complexity etc. on deep neural networks?
3) Does this paper suggest that all learning is memorization(brute force)? If yes; should these models be seen as a sophisticated expert system with near-infinite if and else statements?
