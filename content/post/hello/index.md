---
title: Why search is so hard
subtitle: Understanding the challenges for developing a search engine
date: 2020-06-15T10:05:48.585Z
summary: Search is one of the key areas where big companies have spent lots of
  investment on. Working as an applied search scientist, I was always questioned
  why we still spend so much time on a problem that has been solved by many
  platforms like Elasticsearch, Luence and many others? The truth is, unless you
  are familar with the area, you probably won't realise how challenging the
  problem is.
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
Search is one of the key areas where big companies have spent lots of investment on. Working as an applied search scientist, I was always questioned why we still spend so much time on a problem that has been solved by many platforms like Elasticsearch, Luence and many others? The truth is, unless you are familar with the area, you probably won't realise how challenging the problem is.

![Search](photo-1502240868472-18259bc0f863.jpeg)

Search belongs to a wider discipline called information retrieval. Information retrieval is about finding information to satisfying individuals’ needs and search is an application of information retrieval.

**So, what is a perfect search system?**

A perfect search system should understand what's happening in your mind given a few keywords you typed in the search box, and being able to return all the information you wanted as a really fast speed!

One of the key challenging in information retrieval/search engines is to understand the information needs given the user input. For example, for a typical search engine, the user inputs are keywords. Users come to a search engine with a specific or blur information need, and then formalise a search query to give to the search engine. In most cases, users hope that the search engine can understand what is looked for, rather than expecting the search engine to return documents with certain keywords.

For example, if you search for “*machine learning books*”, your information need is not looking for some web documents which contains the three keywords: **machine**, **learning**, **books**. Probably you will get a book called “The Art of Fixing Things, Principles of Machines, and How to Repair Them”.

![](screen-shot-2020-06-15-at-3.17.40-pm.png)

Now you might think, well, why not restrict the keywords matching so that you’ll match exactly the phrase. It might make sense if you are searching for a book called “machine learning books”. However, if you are searching for some books on machine learning technology, you probably won’t get what you want. For example, you won’t find the famous book: “The elements of statistical learning”!

![](screen-shot-2020-06-15-at-3.24.29-pm.png)

**Beyond finding the relevant documents**

Imagine you now have a solution to understand the semantics of the keywords, now you have solved the search problems? No! Imagine how many search for “best restaurant in Melbourne”. You figure out the person is looking for a restaurant, but you definitely don’t want to return a random list of restaurants to the person. Don’t expect people to look at your search results over **the second page**! Established research has found that people tend to look at the **first 10 search results** only. As a result, the ranking quality of a search engine is really important, and the ranking will be based on a lot of factors: relevance, document quality, authority, popularity, personalisation, etc.

If you are building a search engine for an ecommerce store, the properly ranking is definitely the key to improve your profit. Imagine you have a search engine that can understand what your customer is looking for, and always return relevant and personalised products to the user!

**Efficiency in search**

The other challenging part of search is the requirement of efficiency. Even if you come up with a genius solution, it needs to be under 200ms! That has been a serious constraint for many machine learning algorithms.

Search is a quite challenging problem and no one has a good answer for it yet. However, both industries and academics have been trying to come up with various solutions.

**Understand your search performance**

 As the 19 century mathematical phyisicitist William Thomas said:

> If you can't measure it you can't improve it!

Measuring the performance of a search engine is challenging too. Business usually monitors their sales performance, which is not directly attributed to the search performance.

In the academic community, it has been year-by-year research on how to properly evaluate the search performance. A good search system should return search results that are most relevant and rank them on top of the search results. However, it is not straightforward to know whether results are relevant, and whether there are missing relevant results from current system.

 In the later post, I'll explain how practically search evaluation works.