# Topic-Modelling-using-LSA-and-LDA
In this project, I will do a modeling topic by utilizing _Dimensionality Reduction_ in text data which is news data. By compressing text data, it will get important components. So, the result of these important components is the topic of the news. So he will group certain topics from the news.

# Import Package
import package:
- import pandas as pd
- from nltk.tokenize import word_tokenize
- from nltk.corpus import stopwords
- from string import punctuation
- from sklearn.feature_extraction.text import CountVectorizer
- from sklearn.decomposition import TruncatedSVD
- from sklearn.decomposition import LatentDirichletAllocation

# Import Dataset
The data I use is data from the Kompas news agency in Indonesia. The data contains online news from year to year that has been collected. The data consists of 2008 rows (news), and 1 column

# Extract Bag of Words (BoW)
In topic modeling, you can use PCA or NMF, but in this case I use LSA & LDA which are special techniques designed for text data. And usually on LSA & LDA use Bag of Words (BoW) as encoder.

All that has to be done is extract the features into BoW. Bag of Words is an encoder by counting vectors.
The parameter I put in BoW is:
- ngram = 1,2 
- tokenizer = word_tokenizer
- stop_words = sw_indo (Bahasa Indonesia)
- min_df = 5, the minimum token that appears is 5 documents

# Topic Modeling
### Latent Semantic Analysis (LSA)
This Latent Semantic Analysis utilizes the Bag of Words, then it is reduced. Because Bag of Words generates a lot of vocabs, which in our data are as many as 25132, it will be reduced to get more important meaning and will later become a Topic.

I'm going to convert the thousands of vocabs in the Bag of Words into just 10 documents that matter.

![Screenshot 2022-06-05 152556](https://user-images.githubusercontent.com/86812576/172042123-8063b4a3-5440-4a04-b881-369304717ef1.png)

These are the news topics in the dataset. We can see the result is 10 components, this is generated by taking the largest value and then returning it as text.

### Latent Dirichlet Allocation (LDA)
LDA makes use of probabilistic techniques. Wsing different techniques but the use is the same for the modeling topic.
Later he will try to do probability estimates, distribution of topics to sentences in the document, and what sentences are in the document. That's what LDA uses to generate topics, and the way behind the scenes is decomposition.

![Screenshot 2022-06-05 153735](https://user-images.githubusercontent.com/86812576/172042499-09db2a32-2f6b-4de8-a1fa-427ed1bc797a.png)

The results look different with LSA, maybe because the way it works is also different between LDA and LSA. Such is the unsupervised, the machine that works according to the pattern, the human's job is to deduce the meaning.
