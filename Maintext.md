# **Decoding Biases in the GPT-3 Language Model**
<br>
To what extend GPT-3 trained models reflect biased patterns ?
<br>

### **Introduction**
<br>
GPT-3 (Generative Pre-trained Transformer 3) is a language model, created by the OpenAI company in 2020. To understand what a language model is, one must first know the scientific field to which this concept belongs : natural language processing (NLP). At the confluence of artificial intelligence and linguistics, it aims to process linguistic elements using computer tools (Powers & Turk, 1989).

More precisely, the GPT-3 language model is based on pre-trained deep learning algorithms, and is able to generate entire texts, which tone and writing style are very natural and realistic. GPT-3 can also predict the end of a text that has already been started, with an advanced understanding of its writing context. Its algorithms are trained unsupervised on massive databases of human-written content like the Wikipedia website. As a result, we assume that GPT-3 algorithms incorporate into their learning process several biases present on the Internet.

Applying a sentiment analysis to the database, we will rank adjectives according to their type (neutral, positive or negative) via the NLP tool Vader. Using the GPT-3 language model API (Open AI) and focusing on word embeddings, this study is aiming try to see if words designating certains categories of people  are more associated than others to negative or positive adjectives. The results could further highlight the existence of several sexist, racist and abeist biases in the GPT-3 language model.

### **Litterature review**
<br>

### **Methodology**

 a)  Timsit (2017) emphasizes that English is an example of gender-neutral language, compared to other languages like French. If this assumption is not entirely true, given that English expresses gender with pronouns (he/she), there is however no gender forms linked to verbs, adjectives, and adverbs. Realising a sentiment analysis on *adjectives* is therefore interesting : any adjective used in English can be adapted to a man or a woman.
  
b) As part of the NLP field, sentiment analysis is used to determine if a word is positive, negative or neutral. Using VADER (Valence Aware Dictionary and Sentiment Reasoner), an English-language sentiment analysis tool, we will be studying a database of adjectives determined randomly (n=1133) via the website : www.randomlists.com.   
  
c) Polarity refers to the overall feeling conveyed by a written element. As explained by Beri (2020), "VADER sentimental analysis relies on a dictionary that maps lexical features to emotion intensities known as sentiment scores". A loop running on all the lines of the database will print, in digital form, a polarity score corresponding to the classification of the adjective studied (positive, neutral or negative).
  
d) Word embeddings correspond to the representation of vectors of a certain distance between different words. The more two words are semantically close, the more their distance will be reduced in the vector space (Harris, 1954). Open AI's GPT-3 offers word embeddings model, allowing to compare the similarity of two words or sentences. We chose to use the Davinci engine, for its performances and rapidity of calculation of similarity scores between different words. The similarity score corresponds to the product of the two vectors representing each word, also called the "dot product" (Open AI, 2022). The higher the similarity score between two entries (on a scale ranging from -1 to 1), the higher their semantic proximity.
  
e) We will therefore run several semantic comparisons between adjectives of the database and external inputs corresponding to specific categories of people. It will reveal the existence or not of biases in the database.
One of the hypotheses tested will be the following:
•	H0: Women are more associated with negative adjectives than men, men are more associated with positive adjectives.<br>
•	H1: The gender has no influence on the association with positive or negative connation adjectives.

If we do not manage to reject the null hypothesis, we can deduce that Open AI models are biased towards women: the training data of these algorithms associate more negative adjectives with women than with men. Other categories of people will be compared to specific adjectives of the database.

### **Results**

*First step : the sentiment analysis*

The studied adjectives are classified by a sentiment analysis tool, their polarity scores are then integrated into a new column of the databse. We then create sub-databases, bringing together all the adjectives classified as negative, positive, and neutral together.
We observe an overrepresentation of neutral adjectives, while the number of negative and postive adjectives is quite similar.

![image](https://user-images.githubusercontent.com/74886618/202903862-506e27dd-afaa-4673-9724-5b16b9c8eeb9.png)

![image](https://user-images.githubusercontent.com/74886618/202904774-e20fb335-32f1-4fb3-ba70-218e01c2a51a.png)

*GPT-3 embeddings and calculation of semantic proximity*

Providing embeddings for the word "dizzy", "man", "woman", we will see which word is closer to the other in vector space, and is therefore considered semantically closer by GPT-3.

The first adjective of our dataset is "dizzy". It refers to the state of someone feeling unsteady or confused (Oxford, 2022). It has been classified as a negative word by the sentiment analysis tool VADER. We will now test the similarity between this adjective and these words : "man" and "woman".
 Text similarity models are used to "provide embeddings that capture the semantic similarity of pieces of text" (Open AI, 2022). For that, we will use one of the GPT-3 text similarity models called *Davinci*, for its performances and rapidity of calculation. 

![image](https://user-images.githubusercontent.com/74886618/202904176-589ee054-18c6-424f-a481-bc28d1d4c5e6.png)

The similarity score associated with the word "dizzy" is higher for "woman" compared to "man". Therefore, we can see that women are more associated than men with this negative word. We explained in the introduction that the GPT-3 language model is trained on several sources, with data scraped from sources like the BBC, NYT, Wikipedia, Reddit... To explain the results on the word "dizzy", we can suppose for that there are more occurrences in training dataset of the GPT-3 language model, of situations of women feeling dizzy compared to men. This seems quite consistent with the sigmate and common prejudice that women are fragile and weak compared to men (UN, 2014): this word must be more often, in a biased way, associated with women than with men on the Internet. Mimicking its training data, the GPT-3 model therefore indiciates a higher similarity between a woman and being "dizzy", compared to a man.

But it this also the case in the rest of the database? Are all positive adjectives more associated with men than women? To answer this question, we will test the semantic proximity between the entire database of positive-ranked adjectives created earlier (called "count"), and two external inputs : "man" and "woman". The question is therefore the following: which word between "man" and "woman" is the closest semantically to all the positive classified adjectives in our database ?

![image](https://user-images.githubusercontent.com/74886618/202904324-0a475b3d-d58e-42da-a27a-b82ca4fbad06.png)

Men are more associated to positive adjectives than women, the similarity score is higher for men.

It therefore seems that the GPT-3 language model is reflecting certain gender biases. We will now test other categories, using word embeddings, to see if we can highlight other remaining biases in the algorithm.

### **Concluding remarks**
<br>

### **References**
<br> 

#####

- Al Amin, A. & Kabir, K. (2022). A Disability Lens towards Biases in GPT-3 Generated Open-Ended Languages, IJCAI 2022 Workshop on Diversity in Artificial Intelligence. https://arxiv.org/pdf/2206.11993 
- Chiu, K. L., & Alexander, R. (2021). Detecting hate speech with gpt-3, University of Toronto. https://doi.org/10.48550/arXiv.2103.12407 
- Dale, R (2021). GPT-3: What’s it good for? Natural Language Engineering, 27, 113–118, https://doi.org/10.1017/S1351324920000601 
- Floridi, L., Chiriatti, M. (2020). GPT-3: Its Nature, Scope, Limits, and Consequences. Minds & Machines, 30, 681–694 . https://doi.org/10.1007/s11023-020-09548-1 
- Lucy, L & Bamman, D. (2021). Gender and Representation Bias in GPT-3 Generated Stories, Proceedings of the 3rd Workshop on Narrative Understanding, 48–55. https://aclanthology.org/2021.nuse-1.5.pdf 
- McGuffie, K., & Newhouse, A. (2020). The radicalization risks of GPT-3 and advanced neural language models, Cornell University.https://doi.org/10.48550/arXiv.2009.06807 
- Min, Z. & Juntao, L. (2021), A commentary of GPT-3 in MIT Technology Review 2021, Fundamental Research, 1, 6,831-833, https://doi.org/10.1016/j.fmre.2021.11.011. 
- Troske, A. et al (2022). Brilliance Bias in GPT-3, Santa Clara University. https://scholarcommons.scu.edu/cgi/viewcontent.cgi?article=1220&context=cseng_senior 


