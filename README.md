# assignment4
This code contains a PoS-tagger called tagger.py, a twitter crawler called twitter_query.py, a wiki crawler called wiki_query.py ,  and term plotter for US presidential 
speeches called term_plotter.py

---PoS Tagger---

The tagger uses four different arguments

--mode
1. train, which trains a Support Vector Machine using a training file specified in config.yaml, and stores the model in a location specified by config.yaml
2. SGD, which works identically but uses Stochastic Gradient Descent
3. tag, which uses the trained model to tag either a sentence or a file specified in --text, and deposists the file in the same directory
4. eval, which evaluates the trained model with a gold standard .txt or .conllu file specified in --gold

--text
specifies the text or .txt file to be used by tag

--gold
specifies the gold standard file to be used by eval

--config
specifies the training data file, whether the training data is cross-validated and with how many folds, as well the location for the trained model.

The features supplied to the developer were kept, and supplemented by the prefix feature, which takes the first two letters of the word, 
a suffix feature that takes the final two letters of the word that comes before in the sentence, and both a pre- and suffix feature for the word 
that comes afterwards in the sentence. 


---Twitter Crawler---

twitter_query.py contains a function retrieve_tweets, which takes two arguments, a twitter username and a number, and prints the number of most recent tweets 
by this user.
 
The number is an optional argument, and, if left blank retrieves the most recent tweet.

No distinction is made between tweets, replies, or retweets, and no special encoding is used for non-ASCII characters.


---Wiki Crawler---

wiki_query.py has a function wiki_query, which takes one argument and retrieves the wikipedia page of what is written in this argument. 

It uses utf8 encoding in order to handle non ASCII characters.


---Term Plotter---

term_plotter.py is a python script that takes a raw text us_presidential_speeches as corpus and gives output of an image. 

1. Install os ,  json , argparse, spacy, numpy, panda, seaborn and matplotlib
2. Takes us_presidential_speeches as corpus and keep speeches in one list and dates in another lists.
3. It can takes upto four arguments: 
	first, it can take a list up to five terms in quotation, seperated by white space with English stopwords assumed to be filtered out.
	Secondly, an optional path is given as default if not provided.
	Thirdly, an optional title, if not given the program output without title.
	Fourthly, output will be saved in an image file named according to the term provided seperated by an underscore token. 

4. After the terms given the program then calculate Tf idf score of the whole texts and get the ngams.
5. Then extract the frequency of terms and concatenate them into an vector.
6. Prepare date, score and term for pandas 
7. Draw plot, set title & save the figure in the same directory as the program.




