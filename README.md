# **Decoding Biases in the GPT-3 Language Model**
![image](https://user-images.githubusercontent.com/74886618/205187167-515d8b2d-ee4b-4d4c-87a3-7b703ebf5174.png)

👨‍💻 Final project in "Decoding Biases in Artificial Intelligence" course - Sciences Po Paris, Master in Digital & New Technology <br>
🙋‍♀️ Aissatou Keita, Anna Soulier, Luisa Veronica Arroyo Revatta and Marine Dupuis   <br>
⚡ Theme : Open AI GPT-3 and its biases  <br>

Our final work can be consulted here : https://marine-dupuis.github.io/Decoding-Biases-in-AI---GPT3/

### **Summary**
<br>

* [Introduction](#introduction)
* [Theory](#theory)
* [Methodology](#methodology)
* [Results](#results)
* [Conclusion](#conclusion)
* [References](#references)

### **Introduction**
<br>

*To what extend GPT-3 trained models reflect biased patterns?*

<br>
GPT-3 (Generative Pre-trained Transformer 3) is a language model, created by OpenAI company in 2020. To understand what a language model is, one must first know the scientific field to which this concept belongs to: natural language processing (NLP). At the confluence of artificial intelligence and linguistics, it aims to process linguistic elements using computer tools (Powers & Turk, 1989).

More precisely, the GPT-3 language model is based on pre-trained deep learning algorithms, and is able to generate entire texts, which tone and writing style are meant to be very natural and realistic. GPT-3 can also predict the end of a text that has already been started, with an advanced understanding of its writing context. Its algorithms are trained unsupervised on massive databases of human-written content like the Wikipedia website. As a result, we assume that GPT-3 algorithms incorporate into their learning process several biases present on the Internet. For instance, in this study we will focus on several adjectives, their connotation, and the semantic meaning they have in GPT-3 language model.

Applying a sentiment analysis to the database, we will rank adjectives according to their type (neutral, positive or negative) via the NLP tool Vader. Using the GPT-3 language model API (Open AI) and focusing on similarity of word embeddings, this study is aiming try to see if words designating certains categories of people ("women" and "men") are more associated than others to positive adjectives. The results could further highlight the existence of several sexist biases in the GPT-3 language model.

### **Theory**
<br>

According to IBM (2020), Natural Language processing, or NLP, is a “branch of artificial intelligence or AI—concerned with giving computers the ability to understand text and spoken words in much the same way human beings can.” In other words, NLP breaks down spoken and written language inputs to help algorithms categorize them. Languages are complex, and even within one language, the meaning of a word can vary depending on the context and the tone of the speaker. NLP attempts to clarify these complexities by breaking down inputs and categorizing them. 

The Generative Pre-trained Transformer 3, or GPT-3, is the third iteration of GPT. The previous version, GPT-2, was able to use the context of a sentence to predict the following word. OpenAI did not release it due to concerns about it being used to publish “malicious content” like fake-news.  On the other hand, GPT-3 “uses deep learning to produce human-like text”  and “can write parody and poems: can generate texts of up to 50,000 characters, with no supervision" (Panchiota, 2021). Despite its ability to produce text, GPT-3 still has limitations. Indeed, The Guardian (2020) released an article titled “A robot wrote this entire article. Are you scared yet, human?” Later on, they admitted that GPT-3 produced several texts and they selected parts that they wanted to show. Dale (2021) explains that the longer the output, the less coherent the content becomes. This becomes an issue when you ask the tool to produce a news story founded in truth.

Furthermore, GPT-3 still has not passed a Turing test, a test used to determine “whether machines can think.” In other words it attempts to determine whether machines are simply imitating the models they were trained on or whether they follow a logic similar to the way humans  use language to produce content. According to Elkins and Chun (2020), while a human’s writing skills tend to remain consistent, GPT-3’s output can strongly vary. As a result, the tool might be able to produce a short story, however it will not be able to keep a narrative throughout a long period of time. 

Another limitation GPT-3 has, according to Dale (2021), is the reproduction of biases. In our case, GPT-3 was trained on the "Common Crawl" dataset. Sumrak (2020) states that “the model’s output is dependent on its input: garbage in, garbage out.” The statement illustrates the fact that the algorithm can replicate the biases found in the data it was trained on. For example, Lucy & Bamman (2021) tested GPT-3 gender bias and found that short stories generated by GPT-3 tended to describe feminine characters through their beauty and masculine characters through their strength. And indeed, an article by Elkins and Chun (2020) indicates that the tool “mindlessly” reproduces the biases found in the model it was trained on.  

One attempt at correcting this is the use of sentiment analysis which would allow the machine to determine the emotional tone of a message. Currently, this tool is usually trained using product reviews. It can then try to identify the sentiment behind a document, sentence or word before classifying it. The advantages of sentiment analysis are that they can allow businesses to have a better idea of consumer sentiment towards their brand. Many also see an opportunity in healthcare where sentiment analysis can be used to monitor social media and identify the effects of a medication that were not shown during the research and development process. However, since a lot of sentiment analysis models are trained in English they are still lacking in other languages. In addition, sentiment analysis is still not fully able to detect subtleties like sarcasm. 

### **Methodology**

 a)  Timsit (2017) emphasizes that English is an example of gender-neutral language, compared to other languages like French. This applies to verbs, adjectives, and adverbs. Therefore, any adjective in English should be equally used when refering to a "man" or "woman" independently if they have a positive, negative or neutral tone. To know if that happens in GPT-3, we first need to work on the adjectives and then do a similarity text analysis. For the adjectives work, we will classify them to know whether they are positive, negative and neutral. Later, we will check if GPT-3 prefers to associate them with "woman" or "man". If GPT-3 deploys gender-neutral language the preference in both cases should be equal.
 
  **Sentimental Analysis:**
   
b) As part of the NLP field, sentiment analysis is used to determine if a word is positive, negative or neutral. Using VADER (Valence Aware Dictionary and Sentiment Reasoner), an English-language sentiment analysis tool, we will be studying a database of adjectives determined randomly (n=1133) via the website: www.randomlists.com.   
c) A loop running on all the lines of the adjectives database will print, in digital form, a polarity score corresponding to the classification of the adjective studied (positive, neutral or negative). Polarity refers to the overall feeling conveyed by a written element. As explained by Beri (2020), "VADER sentimental analysis relies on a dictionary that maps lexical features to emotion intensities known as sentiment scores". In more detail, the scoring of the words studied is calculated as follows :  "a compound score is computed by summing the valence scores (namely, the "pos", "neu", and "neg" scores, which are ratios for proportions of text that fall in each category) of each word in the lexicon, and then normalized to be between -1 (most extreme negative) and +1 (most extreme positive)" (Hutto & Gilbert, 2014). Afterwards, to determine the type (postive, negative or neutral) of the word, the following rule has been used :
- compound score > 0, word = positive 
- compound score = 0, word = neutral
- compound score < 0, word = negative 
  
  **Text similarity Analysis:**
   
d) Open AI's GPT-3 offers word embeddings model, allowing to compare the similarity of two words or sentences. Word embeddings correspond to representation of vectors of a certain distance between different words. The more two words are semantically close, the more their distance will be reduced in the vector space (Harris, 1954). We chose to use the Davinci engine for its performances and rapidity of calculation of similarity scores between different words. The similarity score corresponds to the product of the two vectors representing each word, also called the "dot product" (Open AI, 2022). The higher the similarity score between two entries (on a scale ranging from -1 to 1), the higher their semantic proximity. In other words, the closer they are, the higher the possibility that GPT-3 will use them together in their generation language model. 
  
e) We will therefore run several semantic comparisons between adjectives of the database and external inputs corresponding to specific categories of people. It will reveal the existence or not of biases in the GTP-3 model.
One of the hypotheses tested will be the following:<br>
•	**Hypothesis 0** : Men are more associated with positive adjectives.<br>
•	**Hypothesis 1** : The gender has no influence on the association with positive or negative connation adjectives.

If we do not manage to reject the null hypothesis, we can deduce that Open AI models are biased towards women: the training data of these algorithms associate more positive adjectives with men than with women.

f) Then a qualitative analysis will be realised: we will rank the results obtained for given adjectives. We want to check if we can find the same general results in a more detailed analysis. In other words, we will see if the hypothesis is still valid when realising an in-depth analysis of adjectives.  

g) Finally, the last part will consist in a data visualisation of our results, to visually indicate the difference in terms of similarity scores between men and for women, for given adjectives.

### **Results**

*First step : the sentiment analysis*

The studied adjectives are classified by a sentiment analysis tool, their polarity scores are then integrated into a new column of the database. We then create sub-databases, bringing together all the adjectives classified as negative, positive, and neutral together.
We observe an overrepresentation of neutral adjectives, while the number of negative and positive adjectives is quite similar.

![image](https://user-images.githubusercontent.com/74886618/204872887-83663855-3e6a-4129-aca7-a9f65fe8b6dc.png)

![image](https://user-images.githubusercontent.com/74886618/204873186-4b74a0b8-e765-47b4-9973-15b8035d3b22.png)

![image](https://user-images.githubusercontent.com/74886618/204872982-64044051-d3ae-42c9-945f-1c07b3135ea2.png)

*Second step : GPT-3 embeddings and calculation of semantic proximity*

Providing embeddings for the word "dizzy", "man", "woman", we will see which word is closer to the other in vector space, and is therefore considered semantically closer by GPT-3.

The first adjective of our dataset is "dizzy". It refers to the state of someone feeling unsteady or confused (Oxford, 2022). It has been classified as a negative word by the sentiment analysis tool VADER. We will now test the similarity between this adjective and these external imputs : "man" and "woman".

![image](https://user-images.githubusercontent.com/74886618/204873414-46ee86f3-88a5-41b7-9b23-74c91de25e1b.png)

The similarity score associated with the word "dizzy" is higher for "woman" compared to "man". Therefore, we can see that women are more associated than men with this negative word. We explained in the introduction that the GPT-3 language model is trained on several sources, with data scraped from sources like the BBC, NYT, Wikipedia, Reddit... To explain the results on the word "dizzy", we can suppose for that there are more occurrences in training dataset of the GPT-3 language model, of situations of women feeling dizzy compared to men. This seems quite consistent with the stigmate and common prejudice that women are fragile and weak compared to men (UN, 2014): this word must be more often, in a biased way, associated with women than with men on the Internet. Mimicking its training data, the GPT-3 model therefore indicates a higher similarity between a woman and being "dizzy", compared to a man.

But it this also the case in the rest of the database? Are all positive adjectives more associated with men than women? To answer this question, we will test the semantic proximity between the entire dataframe of positivly-ranked adjectives created earlier (called "count"), and two external inputs : "man" and "woman". The question is therefore the following: which word between "man" and "woman" is the closest semantically to all the positively classified adjectives in our database ?

![image](https://user-images.githubusercontent.com/74886618/204873682-d188b989-2565-41d3-825a-24f1426ea7f3.png)

Men are more associated to positive adjectives than women, the similarity score is higher for men.

It therefore seems that the GPT-3 language model is reflecting certain gender biases.

*Third step : qualitative analysis*

In the last part, we obtained the general score of the similarity test between all the positive adjectives embeddings and the words "woman" and "man". Next, we want to take a deep look into five positive adjectives and see if men are also more associated with positive adjectives than women. For this step, we choose five adjectives and create a specific data frame called "nd".

![image](https://user-images.githubusercontent.com/74886618/205116762-9757b793-faf1-42d3-b1fa-5d1faa0c57f8.png)

Then, we run a for loop for each positive adjective, and we save the result in a variable called "score_woman". Later, we place the score values inside the dataframe we created before. 

![image](https://user-images.githubusercontent.com/74886618/204969939-39d5d391-994c-4f19-9141-10c22d2b3f66.png) 

We repeat the same process with the word "man" and store the results of the text similarity analysis inside the dataframe. 

![image](https://user-images.githubusercontent.com/74886618/204969998-79ba6336-0b69-4d72-940a-e5ecdbed7ae2.png)

As we want to analyze each word starting with the one that is more associated with the words "woman" and "man", we have to arrange the dataframe in descending order.

![image](https://user-images.githubusercontent.com/74886618/204970125-6347ab9f-42d5-4fec-a20f-74f857e0be7b.png)

As we can see here "solid" is a word that is highly associated with "woman" and "man". However, as predicted before, the closeness is higher with "man" than with "woman". The adjective "solid"  may define how reliable is a person (Oxford, 2022). Therefore, we can imagine that using GPT-3, there is a better chance to get results that describe a man as more reliable than a woman. This clearly projects an old tradition of thinking about a woman as a being that should not be trusted because they cannot be understood or can manipulate. There is a lot of online material that still reflects this belief. (Quora, 2020)

The second word is "romantic" and we see that the score is higher in the comparison with "woman", compared to "man". Even if this case does not follow the general results, it is no surprise in our current context that being romantic is still more linked to "woman" than "man". This reflects a bias since "being romantic" is not about gender but about showing feelings of love (Oxford, 2022). 

The following word is "important", this word used as an adjective shows that the person has great influence or authority (Oxford, 2022). To our surprise, this adjective is more close to "woman" than to "man". We find here a case that doesn't follow the general results (reminder : an higher score of similarity between positive adjectives and men). The reason behind this could be the recent work to recognize the path and work of women around the world. A simple clue to understanding this result could be found in Google. If we type in the search engine the words "important woman" and "important man", we will get about 9,850,000,000 results for the first search and about 7,090,000,000 results for the second. This might tell us that there is more information that uses the word "important" and "woman". Nevertheless, the results are reversed if we search for the two words in quotes.

The next two adjectives are "clever" and "intelligent", both are synonyms. In both cases, the adjective is more related to "woman" than to "man". Again, we see a different result from the general one. The only difference between the two is that closeness between "woman" and "intelligent" is bigger than for the word "clever". The explanation of these results might also rely upon a current trend to vindicate women's cognitive abilities. As examples, we can take "Girls in ICT day" as a way to promote the inclusion of women in careers traditionally meant for "intelligent" men, or the activism towards breaking the "glass ceiling" in the workplace that does not enable a woman to achieve high hierarchy positions (Adsoftheworld, 2018).
 
As a conclusion in this third step, we found that in a detailed analysis that our null hypothesis is valid on only one of the adjectives studied. However, this is not enough to reject it, as there are still differences between the results in the "woman" and "man" columns. In the next step, we will get a closer look into those differences in a visual way. 

*Fourth step : data visualisation*

To conclude our work, we used matplotlib to create some graphs in order to better visualise our data. 
We first created a scatter plot, representing by each point the similarity score with the words “woman” and “man” for each adjective. By adding the two scatter plots in one graph, we can see the gap between the similarity scores.
The similarity score for women is in red, and in blue for men.

<img width="531" alt="Capture d'écran_20221201_235811" src="https://user-images.githubusercontent.com/118388867/205177287-87e1e7c4-726a-4b8a-9272-2cef58bf4c76.png">

The two following graphs are used to better visualise the score for each adjective, with the label close to the point. The dots in red represent the similarity score for women, while the dots in blue represent the similarity score for men.

<img width="316" alt="Capture d'écran_20221201_164849" src="https://user-images.githubusercontent.com/118388867/205104632-897e6dfb-d202-484c-8e8d-9ed05862817f.png">
<img width="296" alt="Capture d'écran_20221201_164902" src="https://user-images.githubusercontent.com/118388867/205103960-af7004b5-529b-42cd-82e9-fd7cf233fa8c.png">

We wanted to get plots with a curve to see the augmentation of the similarity score for adjectives. 
We created a variable called “nd_val”, that stored the “nd” dataframe in ascending order for the Score for women. This allowed us to visualise the data with a curve. 

<img width="414" alt="Capture d'écran_20221202_000319" src="https://user-images.githubusercontent.com/118388867/205177590-8579a8a5-f959-4f3b-b7d9-6b331c5de6d9.png">
<img width="296" alt="Capture d'écran_20221201_164946" src="https://user-images.githubusercontent.com/118388867/205104165-98cdd1aa-0da2-4f1b-b336-9455f66a2927.png">

We then repeated the process for the Score for men, by creating a second variable called “nd_val2".

<img width="352" alt="Capture d'écran_20221202_000334" src="https://user-images.githubusercontent.com/118388867/205177607-77caae0e-c805-4f2e-9887-cd0fa55b3dcf.png">
<img width="277" alt="Capture d'écran_20221202_002103" src="https://user-images.githubusercontent.com/118388867/205179946-5484119c-a4c1-4982-a330-083afe06eeb2.png">

Finally, we put the two plots next to each other, in order to better visualise the differences between the evolution of the score for the word “woman”, and for the word “man”. 

<img width="403" alt="Capture d'écran_20221201_235452" src="https://user-images.githubusercontent.com/118388867/205177697-db95d63d-9e20-424d-832a-fe60ccdf69e0.png">

It has to be noted that the scale is not the same for both graphs : the y axis is between 0.8 and (almost) 0.82 for the score for women, while it is between 0.78 and 0.82 for the score for men. It means that the five adjectives are almost equally associated with the word “woman”, while some adjectives are more closely associated with the word “man” than others.


### **Conclusion**

Through this analysis, we wanted to see if GPT-3 was a biased language model. After studying the similarity score for several adjectives with the words “woman” and “man”, we found that in general, positive adjectives are more associated with the word “man” than with the word “woman” : for all the positive adjectives in our list, the similarity score was higher for men than women (0.81 vs 0.77). 
But upon a more detailed analysis, we found that the similarity score varies depending on the adjective. And for the five adjectives that we studied more in depth, only the adjective “solid” was more associated with men than with women. 

We cannot conclude that our null hypothesis , “men are more associated with positive adjectives”, is always true : in general, men are more associated with positive adjectives, but when we study this hypothesis further, we found that we cannot assume that each adjective has a similarity score higher for men than for women. 
Still, some biases could be detected in the adjectives that are more closely associated with the word “woman”. The adjective “romantic” is usually associated with women, and GPT-3 reproduced this bias, by giving it a higher similarity score with the word woman than with the word man.

The scope of our results could be limited by the fact that we had to restrict our in-depth analysis of the similarity score for men and women to five adjectives, due to several technicalities. In order to confirm our results, we should do this analysis on all of the positive adjectives in our database, to see if other adjectives that could be considered more “feminime”, such as “romantic”, are more associated with women than men, and vice versa for adjectives that could be considered more associated with men. 
Still, for the moment, we can conclude that the influence of gender on the association with positive or negative adjectives is limited, and it seems that GPT-3 is not as biased as one could think.

### **References**
<br> 

*Academic articles and books*

- Al Amin, A. & Kabir, K. (2022). A Disability Lens towards Biases in GPT-3 Generated Open-Ended Languages, *IJCAI 2022 Workshop on Diversity in Artificial Intelligence.* https://arxiv.org/pdf/2206.11993 
- Chiu, K. L., & Alexander, R. (2021). Detecting hate speech with gpt-3, *University of Toronto*. https://doi.org/10.48550/arXiv.2103.12407 
- Dale, R (2021). GPT-3: What’s it good for? *Natural Language Engineering*, 27, 113–118, https://doi.org/10.1017/S1351324920000601 
- Elkins, K. & Chun, J. (2020). Can GPT-3 Pass a Writer’s Turing Test?. *Journal of Cultural Analytics*, 5. 10.22148/001c.17212. 
- Floridi, L., Chiriatti, M. (2020). GPT-3: Its Nature, Scope, Limits, and Consequences. *Minds & Machines*, 30, 681–694 . https://doi.org/10.1007/s11023-020-09548-1 
- Hutto, C., & Gilbert, E. (2014). VADER: A Parsimonious Rule-Based Model for Sentiment Analysis of Social Media Text. *Proceedings of the International AAAI Conference on Web and Social Media*, 8(1), 216-225. https://doi.org/10.1609/icwsm.v8i1.14550
- Lucy, L & Bamman, D. (2021). Gender and Representation Bias in GPT-3 Generated Stories, *Proceedings of the 3rd Workshop on Narrative Understanding*, 48–55. https://aclanthology.org/2021.nuse-1.5.pdf 
- McGuffie, K., & Newhouse, A. (2020). The radicalization risks of GPT-3 and advanced neural language models, *Cornell University*.https://doi.org/10.48550/arXiv.2009.06807 
- Min, Z. & Juntao, L. (2021), A commentary of GPT-3 in MIT Technology Review 2021, *Fundamental Research*, 1(6),831-833, https://doi.org/10.1016/j.fmre.2021.11.011.
- Open AI. (2022). Embeddings. https://beta.openai.com/docs/guides/embeddings/embeddings
- Powers,D. & Turk, C. (1989). Machine Learning of Natural Language. *Springer-Verlag*.
- Troske, A. et al (2022). Brilliance Bias in GPT-3, *Santa Clara University*. https://scholarcommons.scu.edu/cgi/viewcontent.cgi?article=1220&context=cseng_senior 

*Press articles and websites*

- Adsoftheworld (2018). Women vs. The Glass Ceiling. https://www.adsoftheworld.com/campaigns/women-vs-the-glass-ceiling
- Beri, A. (2020). SENTIMENTAL ANALYSIS USING VADER. https://towardsdatascience.com/sentimental-analysis-using-vader-a3415fef7664
- IBM. (2020). Natural Language Processing (NLP). https://www.ibm.com/cloud/learn/natural-language-processing 
- Oxford Dictionaries. (2022). https://www.oxfordlearnersdictionaries.com/us
- Panchotia, R. (2021). What Is GPT-3 And Why It is Revolutionizing Artificial Intelligence? Medium. https://medium.com/analytics-vidhya/what-is-gpt-3-and-why-it-is-revolutionizing-artificial-intelligence-44d8e17c7edf
- Quora (2020). Why there's a saying "No One can understand women? https://www.quora.com/Why-theres-a-saying-No-One-can-understand-women
- Sumrak, J. (2020). What Is GPT-3: How It Works and Why You Should Care. *Twilio*. https://www.twilio.com/blog/what-is-gpt-3
- The Guardian. (2020). A robot wrote this entire article. Are you scared yet, human?. https://www.theguardian.com/commentisfree/2020/sep/08/robot-wrote-this-article-gpt-3 
