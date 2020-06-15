---
title: Why search is so hard
subtitle: Understanding the challenges for developing a search engine
date: 2020-06-14T23:51:34.718Z
summary: Search is one of the key areas where big companies have spent lots of
  investment on. Working as an applied search scientist, I was always questioned
  why we still spend so much time on a problem that has been solved by many
  platforms like Elasticsearch, Luence and many others? The truth is, unless you
  are familar with the area, you probably won't realise how challenging the
  problem is.
draft: true
view: 2
header:
  caption: ""
  image: ""
featured: true
image:
  filename: featured.jpg
  preview_only: true
---
Search is one of the key areas where big companies have spent lots of investment on. Working as an applied search scientist, I was always questioned why we still spend so much time on a problem that has been solved by many platforms like Elasticsearch, Luence and many others? The truth is, unless you are familar with the area, you probably won't realise how challenging the problem is.

![Search](photo-1502240868472-18259bc0f863.jpeg)



Search belongs to a wider discipline called information retrieval. Information retrieval is about finding information to satisfying individuals’ needs and search is an application of information retrieval.

**So, what is a perfect search system?** 

A perfect search system should understand what's happening in your mind given a few keywords you typed in the search box, and being able to return all the information you wanted as a really fast speed!

![robot](lenin-estrada-oi1toozskbw-unsplash.jpg)

So, let’s go back to the search problems. If search for “machine learning books”, your information need is not looking for some web documents which contains the three keywords: machine, learning, books. Probably you will get a book called “learning machine mechanics”. Now you might think, well, why not restrict the keywords matching so that you’ll match exactly the phrase. It might make sense if you are searching for a book called “machine learning books”. However, if you are searching for some books on machine learning technology, you probably won’t get what you want. For example, you won’t find the famous book: “The elements of statistical learning”!

Imagine you now have a solution to understand the semantics of the keywords, now you have solved the search problems? No! Imagine how many search for “best restaurant in Melbourne”. You figure out the person is looking for a restaurant, but you definitely don’t want to return a random list of restaurants to the person. Don’t expect people to look at your search results over the second page! Established research has found that people tend to look at the first 10 search results only. As a result, the ranking quality of a search engine is really important, and the ranking will be based on a lot of factors: relevance, document quality, authority, popularity, personalisation, etc.

Now you might say, let’s use machine learning algorithms to solve the ranking problems. Yes, you can use machine learning to rank documents. However, it may be more complicated than you might thought. Ranking is not as straightforward as classification algorithms. You training instance is not a single document, instead, it is one query and a document, and you’ll need to know how to represent this relationship.

Once you got the representation of query-document pairs, you’ll need to design an objective function to optimise a function that predicts the relevance labels. There are a few questions though: what is your objective function? what is your relevance label? how this learned function can be applied?

At this stage, many of you might think, you can train a classification algorithm to predict whether a pair is relevant or not. There are couple of reasons why this doesn’t work: the binary relevance labels don’t fully represent the reality: some documents are more preferable than others; the definition of relevance varies across different queries: term matching may be important for some queries but not others, for example, the machine learning books examples; you simply cannot get labels for the full set as it does not scale. In the future posts, I’ll show you how those problems have been tackled with so-called learning-to-rank algorithms.

Imagine if you have a good machine learning solution to solve the ranking problems, now you think, let’s get some labels! Obtaining labels for search tasks are not easy. You may need to get a large amount of search queries and ask some annotators to rate the relevance of queries and documents in your corpus, this is only doable if you got a few hundreds of documents. Instead, you’ll need get a subset of documents for each query for annotations, and maintaining the quality of annotations is hard! Okay, how about user behaviour, like clicks? Yes, clicks and other types of implicit user feedbacks have been studied for inferring relevance labels. However, again, it’s a bit tricky. Research has shown that users are less likely to engage with the document as the ranking positions goes down, which means that if someone didn’t click on the last results on the second page, it doesn’t mean that the document is irrelevant, likewise, if they click on the first document returned, it doesn’t mean that the first document is always relevant. Apart from this click bias, there are other factors attributed to the behaviours, attractiveness, freshness, etc. The challenge of getting relevance labels online also makes it challenging to evaluate search performance online.

The other challenging part of search is the requirement of efficiency. Even if you come up with a genius solution, it needs to be under 200ms! That has been a serious constraint for many machine learning algorithms.

Search is a quite challenging problem and no one has a good answer for it yet. However, both industries and academics have been trying to come up with various solutions.

In the next posts, I’ll try to cover this topic from different angles.

*