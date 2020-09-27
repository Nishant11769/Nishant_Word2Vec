# Word2Vec
## Word Embeddings
In order to use Word2Vec we must first understand what word embeddings are. Word embeddings are vectors assigned to each word in the vocabulary. These vectors lie in an n-dimensional space where n could range from 300 to 1000, and can be understood by  describing features for each word in the vocabulary.</b>
For example words like ‘man’ and ‘woman’ can be converted into vectors where they would have strongly contrasting values on the ‘gender’ axis  (say -1, 1 respectively) since they primarily describe a difference in gender; whereas they would score low on features like ‘food’ or ‘colour’ and would have equal if not similar values w.r.t each other. The following table considers a few more words to understand this better:</b>
Word|Man|Woman|King|Queen|Apple|Orange|Sky
-|-|-|-|-|--|--|-
**Gender**|-1|1|-0.95|0.97|0.00|0.00|0.005
**Colour**|0.01|0.009|0.01|0.009|0.98|0.94|-0.88
**Food**|0.03|0.04|0.04|0.02|0.95|0.956|0.002</b>

As can be seen words like apple and orange score high on the ‘food’ feature and are also very similar to each other on the ‘colour’ feature; whereas the sky which has an almost opposite colour (blue) has a high negative value.
Word embeddings help us find analogies among words by minimizing a distance metric between two vectors as follows:</b>

If;  man:woman ::king: ?</b>

E<sub>man</sub>-E<sub>woman</sub>=E<sub>king</sub>-E<sub>?</sub>+e </b>

![](https://github.com/Nishant11769/Nishant_Word2Vec/blob/master/analogy.png)

The value of E<sub>?</sub> that minimizes the magnitude of e turns out to be the embedding for the required word i.e 'queen':</b>

Hence: E<sub>queen</sub>=argmin(D(E<sub>king</sub>-E<sub>man</sub>+E<sub>woman</sub> , E<sub>?</sub>)); </b>

where the distance function D is usually cosine although root mean squared distance is also used in some cases</b>

Word embeddings can be thought of as a method by which a NLP model understands the meaning of a word and further applies it to other similar words. The embedding matrix can be treated as a parameter and it's values can be learned using the Word2Vec model which will now be discussed.</b>

## Word2Vec Model

