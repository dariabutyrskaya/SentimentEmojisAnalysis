# SentimentEmojisAnalysis

<b>Introduction</b>

The data given is s Sentiment140 dataset, a publicly available data set created by three graduate students at Stanford University: Alec Go, Richa Bhayani, and Lei Huang. The data comprises approximately 1,600,000 automatically annotated tweets.

The problem this mini project is solving is to predict sentiment (positive/negative) of the given tweets. 


<b>Data processing</b>

The first step of data processing was a loading .tsv file in correct way unto the data frame. After a thorough look at the data, it can be seen that the sentiments and text of tweets are separated by “\t”. The loaded example of data is shown in the fig. 1. 

 
 ![image](https://user-images.githubusercontent.com/90958123/156232519-b8b94baf-4dcb-4192-b72a-25f9183fa7bc.png)

 
Fig. 1. Dataset. 

Now, let’s see the sentiment distribution to see if data is balance or imbalanced. From the fig. 2 it is obvious that the data is pretty balance. But the positive sentiment is marked as “4”, which is not the most comprehensible way. Therefore, “4” was changed to “1” (see fig. 3.).


![image](https://user-images.githubusercontent.com/90958123/156232534-897b8f5d-8db4-47b9-8dde-c14e714a3ca5.png)

 
Fig. 2. Sentiment distribution.


![image](https://user-images.githubusercontent.com/90958123/156232705-8dc94c28-0e99-4d7a-9583-81eaa6b847d1.png)


 
Fig. 3. Updated sentiment distribution.

Furthermore, we check the data for null values. There are none of those, fortunately (see fig. 4). 

 
 ![image](https://user-images.githubusercontent.com/90958123/156232723-7f44b88a-fa53-43c2-ba32-fdd517981fb6.png)


Fig. 4. Checking for null values.

The next step in processing the data is to prepare it for the future models. We need to clean tweet text from:

•	Emojis (and convert them in words: “;)” -> “smiley”, for example).

•	Abbreviations (and convert them in full comprehensible words).

•	Links and usernames.

•	Punctuations.

•	Stop words (a, the, etc).

•	And, lastly, to process tweets in such manner: he’s -> he is; she’s -> she is.



After processing, the tweets look like this:


![image](https://user-images.githubusercontent.com/90958123/156232753-d953c326-93d6-4901-8df4-711aa2f36de9.png)

 
Fig. 5. Processed tweets. 
After tokenizing the tweets and dividing the into training set and test set we are ready to feed it to the model. 



<b>Modelling</b>

I used Naïve Bayes and CNN model to predict sentiment of the tweets. 

•	<b>Naïve Bayes</b>

The model preformed well, with accuracy 73%. Not surprising, remembering how popular Naïve Bayes in addressing NLP.

 ![image](https://user-images.githubusercontent.com/90958123/156232795-88882187-87cb-4cc0-a795-e7221dbb4ee0.png)

 
Fig. 6. Performance of Naïve Bayes model. 

•	<b>CNN</b>

CNN performed better than Naïve Bayes, achieving accuracy 0,75%, the highest accuracy.








![image](https://user-images.githubusercontent.com/90958123/156232828-8152979c-c7cf-4d3a-bcea-47be0de06974.png) ![image](https://user-images.githubusercontent.com/90958123/156232837-1e93441a-caa3-4f7a-a6e9-5ab069447e6b.png)













Fig. 7. CNN accuracy.

My hypothesis for CNN performing better than Naïve Bayes is that because CNN are applied to embedding vectors of a given sentence with the goal of extracting useful features (such as phrases and relationships between words that are closer together in the sentence) which can be used for text classification. The NLP CNN is usually made up of 3 or more 1D convolutional and pooling layers unlike traditional CNNs. This helps reduce the dimensionality of the text and acts as a summary of sorts which is then fed to a series of dense layers. This summary usually captures the relationships and meaning of the sentences and is good for classification.

Naive Bayes, on other hand, is more direct, it predicts the tag of a text. NB calculates the probability of each tag for a given text and then output the tag with the highest one. It does not detect relationships and understands text of tweets more in dependably. 


<b>Conclusion</b>

During the work on project, there were several bottlenecks, concerning the accuracy of the models. The accuracy of 75% is considered quite high during NLP processes, therefore for the project I was not able to achieve 80%, even after following all the advice from forum and using approximately more than 5 different models to predict the sentiment. 

However, in the conclusion, a CNN and Naïve Bayes model were built to predict sentiment of the tweet with accuracy 73% and 75% respectively. The data was thoroughly preprocessed and cleaned up before training and testing the model. 


