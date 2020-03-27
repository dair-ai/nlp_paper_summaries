## Rapid Adaptation of BERT for Information Extraction on Domain-Specific Business Documents

On the information extraction side of things, [Zhang et al. (2020)](https://arxiv.org/abs/2002.01861) adopt BERT for extracting important content elements from domain-specific business documents such as regulatory filings and property lease agreements. The model is used in the context of a cloud environment that allows annotation and inferencing on uploaded documents. Not only can this type of work help to optimize business operations but it also shows the applicability and effectiveness of BERT-based models on low-annotated data regimes and documents that are not the typical type of text that most NLP techniques process. For instance, it can certainly help to automatically extract certain types of information from contracts so that they can better be queried.

This process of extracting content elements is possible because transformer-based models already support sequence labeling. The model is applied to domain-specific data, so the authors aim to find out how good BERT — trained on general natural language corpora — can perform in such scenarios. Keep in mind that BERT models are typically applied to natural language corpora which rarely contains the linguistic structures and vocabularies that would arise in business documents. This makes the task challenging. However, the authors discover that it only takes ~100 documents to fine-tune BERT to do well on the content extraction task. BERT also appears to adapt to the linguistic properties of the domain-specific data and generalizes to the unseen expressions of the content elements (e.g. leaseholder and tenant) which is desirable when dealing with domain-specific data.

![img txt](https://github.com/dair-ai/nlp_paper_summaries/blob/master/images/bert-information-retrieval.png)

_F1 score on regulatory filings (left) and lease agreements (right) using different entities and with a varying number of documents used to fine-tune the model — (Zhang et al., 2020)._


It is very exciting to see how BERT was applied to sequence labeling on these types of domain-specific business documents. Going forward, we should expect more applications of transfer learning for NLP in different domains such as health and finance.
