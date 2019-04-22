---
layout: post
title:  "Data Science Capstone Project"
date:   2019-04-07 11:24:29 +0400
categories: DS-C10
permalink: "/ds-journey/data-caps"
---

**Course 10/10 of the Specialization**

The capstone project was like a mystery box. It was only unlocked after all the previous 9 courses were completed. I was excited to see SwiftKey collaborating with the specialization to bring this project. The fact that the capstone project was based on Natural Language Processing (NLP) and this topic wasn't covered in the previous courses, was exciting and frightening at the same time. 

The first 2 weeks introduced the topic and they pointed us to various online resources to guide us with the project. There was also a milestone report at the end of week 2 to perform exploratory analysis on the dataset. 


![SwiftKey, Bloomberg & Coursera Logo]({{site.url}}{{site.baseurl}}/images/logos.png)

******

#### Project Results

This is what the web app looks like. It was built with shiny using R Studio and is hosted on shiny apps. The user can enter the sequence of words, and the app is able to predict the next word based on the given corpus.
![App Interface]({{site.url}}{{site.baseurl}}/images/nlp.png)

In addition, the app can be accessed through this link:
[Word Predictor](https://sakibshahriar95.shinyapps.io/cdsc/)

******

******

#### Project Description

The functionality of the application is to predict the next word after a user types a word. 
The application is programmed in R Language and using various libraries from the R Packages. 

The Capstone Project itself was subdivided into various modules, including exploratory analysis and Research sections regarding Natural Language Processing.

There was a Project Milestone Report to present Exploratory analysis and also a methodology to build the model.

In addition, multiple Quizzes tested the students regarding the corpus summary.

******

#### Project Procedure

First, the text corpus was cleaned by removing things like punctuation and numbers. [Tokenization](http://en.wikipedia.org/wiki/Tokenization_%28lexical_analysis%29) was 
performed, followed by so-called n-gram modeling [*n*-grams](https://web.stanford.edu/~jurafsky/slp3/3.pdf). 
> An n-gram is a contiguous sequence of n items from a given sequence of text. Given a sentence, s, we can construct a list of n-grams from s by finding pairs of words that occur next to each other. For example, given the sentence “I am Sam” you can construct bigrams (n-grams of length 2) by finding consecutive pairs of words. ([Kevin Sookocheff
](https://sookocheff.com/post/nlp/n-gram-modeling/))

The next word is predicted using the n-gram table.

N-gram utilizes the concept of Probabilistic Language Model. This allows us to get an accurate prediction of the next word and is suitable for predicting the next word from a sequence
of words. This is because the next word is dependent on the previous. So from probability (chain rule) we get that : P(A n B) = p (A|B) * P(B). But this chain rule can be extended
to more general and fit more terms:

![formula]({{site.url}}{{site.baseurl}}/images/formula.png) 

Source : [Wikipedia](https://en.wikipedia.org/wiki/Chain_rule_(probability))


So, for example. The probability of the sentence "I like fluffy cats" is P(I) * P(like/I) * P(fluffy/ I like) * P(cats/ I like fluffy)

Note: P(fluffy/ I like) is the Probability of fluffy given the probability of I like

But, as you may realize from the example that it can be too complex for a long sentence. 
Well, the solution to this is using Markov Model developed by Russian mathematician Andrey Markov.

![ngram]({{site.url}}{{site.baseurl}}/images/ngram.png)

 [Image source- Kevin Sookocheff](https://sookocheff.com/post/nlp/ngram-modeling-with-markov-chains/)

 It simply says that instead of using all the previous probabilities, just use the last 
few. So, for instance, to calculate P(cats| I like fluffy) just find P(cats| fluffy) or for better results use P(cats| like fluffy) and so on. But this way we can reduce the complexity 
and this is what essentially is an N-gram model. 

Unigram (or 1 gram) will use the probability of the word itself, so its the least accurate. To improve on it, we can use bigram (2 gram) where the probability of the previous word is 
considered. So for our example, P(cats| fluffy). But for this project, a trigram model was used and it achieves a decent result as you might have realized. 

******

Overall, the capstone was fun, although lots of self-study was required, considering NLP is not something covered in any of the previous courses. 

My Rating: 9.1/10

![Course 10 certificate]({{site.url}}{{site.baseurl}}/images/10.png)
