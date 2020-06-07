# Critique-of-Taylor-s-Law-for-Human-Linguistic-Sequences
Summary and critique of the paper ['Taylor’s Law for Human Linguistic Sequences'](https://www.aclweb.org/anthology/P18-1105.pdf)

### Scope of the paper :
The paper discusses the statistical significance of the Taylor’s power law with respect to natural text. Taylor’s power law has been reported to hold in many natural and social domains along with derivations from Zipfs’ law and Heaps’ law. So, this paper attempts one such fluctuation analysis with Taylor’s law.

### Taylor’s law :
The law states that for any fixed species the fluctuations in the size of a population (characterized by the standard deviation) can be approximately written as a constant times the average population to a power α.

### Meaning of the Taylor’s law in the context of the paper :
In the context of natural language, the paper considers the frequency of occurrence of word in particular word segment.  Consider a set of words W and a segment of length N. We calculate the number of occurrences of the words in every segment of a particular document. Using this frequencies over the segments, we calculate mean and variance for each word in W. Now, the Taylor’s power law analysis is done for each word. As reported from previous works, the power takes value lies in the range 0.5 and 1.  

#### Significance of alpha = 0.5 :-
It is proven in the paper that for IID process, alpha comes out to be 0.5. That means, that words are independent, which is completely opposite of  the natural languages. That also means the exponent is greater than 0.5 for natural texts.####

#### Significance of alpha = 1.0 :-
For 1, the paper shows that, all segments always contain the same proportion of the words. Which would be partly be possible for some words, in programming languages, as some words always occur together.

##### This shows that natural languages reside in between this range. Also, it shows how the co-occurrence of the words as measure for natural languages is being justified by this method, in accordance with Taylor’s law. This also indicates that Taylor’s exponent is partly related to grammaticality.

### Estimation of Taylor’s exponent :
For a particular document, we have mean and variance for each word. To estimate the Taylor’s exponent, paper proposes to first transforms the equation with taking log and then using linear regression using least-squared error to estimate the exponent.
### Outcomes of the paper :

#### Analysis of the texts :
The paper considers texts from 14 languages, news articles, enwiki8 data, child utterances data, 4 program language sources, and musical data converted into text. The exponent was found to be around 0.58 for natural texts by using regression, using segment size 5620. The paper also considers the relation of segment size with exponent, which concludes that its better to use higher size.   
For enwiki8, child utterances, programming languages and music, exponent was found to be higher, showing higher number of fixed forms in the texts.

The standard deviation versus mean on log-log graph, showing low deviation from estimated Taylor’s exponent for almost all words in different text settings.

#### Evaluation of machine generated text :
When experimented on randomly sampled data from ‘Moby Dick’, the exponent was found to be 0.5, As expected from random sampling. The paper also tested text generated on character-based LSTM, which was trained on complete works of Shakespeare. The exponent was found to be 0.5, same as a I.I.D. process.  Which shows that model was unable to capture the word-level correlation. But for machine translation model, the paper found out the text generated had Taylor’s exponent equivalent to that of the original text.

### Merits of the paper :
* Proves that Taylor’s power law analysis is relevant in the context of human linguistics.
* Taylor’s exponent can be used as continuous quantification based upon lexical fluctuations. I.e., between natural texts and fixed-form texts as programming languages or music.
* The variation of Taylor’s exponent was lower than the analysis applied to other contexts, showing strong relevance of such fluctuation analysis for human linguistics.
* Can be used as a measure to compare model performance based on underlying language, aside from application performance. 
* Also showed the limitations of character-based LSTM, which could not capture the underlying natural text. 

### Limitations of the paper :
* The paper shows that exponent is only slightly dependent on document size, although it varies greatly with segment size. Hence, the document needs to have a large number of words, so we can have segments of large size,and also more number of these segments. So, such analysis can’t be performed for short-length texts like tweets or emails.
* The paper uses books and news articles for data source. But, there are many more forms of sources which should be considered.
* As stated in the paper, the Taylor’s exponent could not act as differentiator between languages.

### Possible extensions and applications of the paper :
* While calculating the frequencies, the paper does not do Lemmatization, i.e., the words are considered in their original forms and semantically equivalent words are not clubbed together while considering frequencies. As the analysis is done on multiple languages, this leads to uniformity while comparing the languages. But, fluctuation analysis with lemmatization might provide important insights.
* As covered in limitation section, the analysis could be applied to various forms of natural texts such as emails, scripts, legal documents, screen-plays, poems etc. where the limitation of text size can somewhat be mitigated. 
* It would also be interesting to see the analysis of the above mentioned formats of texts in different languages, across different scripts. Doing such analysis on variety of Indian languages would also be insightful as we have such diversity in languages.
* As stated in the paper, other fluctuation analysis can be done, like Zipfs’ law or Heaps’ law.
* As discussed in related works of the paper, Taylor’s power law is studied across multiple domains such as ecology, life science, physics, finance, and human dynamics (shown by Eisler, Bartos, and Kertész, 2007). The paper itself is one such analysis applied towards human linguistics. 
As stated in the definition, for complex systems of interacting elements, the activity (standard deviation) of element increase with average activity (mean). So, we may find Taylor’s power law behaviour underlined for these sort of systems.


