---
title: Multi-stage ranking for relevance and user satisfaction for search
subtitle: Efficient and effective ways to improve ranking
date: 2021-05-12T09:45:23.538Z
summary: Ranking is a fundamental and critical component of modern search
  engines. The effectiveness of ranking is directly linked to the search
  relevancy and user satisfaction.
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
Ranking is a fundamental and critical component of modern search engines. The effectiveness of ranking is directly linked to the search relevancy and user satisfaction.

![](https://www.productsearch.ai/wp-content/uploads/2021/01/ranking.jpg)

Why ranking is so important? There’s a bit of history here.

The problem that a search engine, as well as other information retrieval (IR) system tries to solve, is to retrieve relevant documents from a document collection given a search query (for example, a search keyword).

#### Boolean Retrieval

Early search engines use Boolean retrieval models to achieve this efficiently. Heuristically, if a document contains one or all of the terms in the search query, the document can be relevant to the search query. For example, if the search query is ‘***Canon lens***‘, the documents contain both the term ‘***Canon***‘ and ‘l***ens***‘ could potentially be relevant.

![](https://www.productsearch.ai/wp-content/uploads/2021/01/boolean_retrieval-1024x695.png)

An example of Boolean retrieval

#### Inverted Index

The other benefit of using Boolean retrieval model is that it can be efficient with a technique called inverted index. Instead of looking up each document to check whether the document contains the terms, we can build an inverted index where the key is the terms in the vocabulary, and each key is attached to a posting list containing all the ids of documents containing the term. In such way, the retrieval can be very efficient.

![](https://www.productsearch.ai/wp-content/uploads/2021/01/inverted_index-1024x360.png)

There are different ways to implement inverted indexes to make the retrieval more efficient, we will not discuss the details here. If you are interested, you can find more details in [this book](https://nlp.stanford.edu/IR-book/html/htmledition/a-first-take-at-building-an-inverted-index-1.html).

Inverted index is fundamental to many search engines, for example Lucene, Elasticsearch, and Solr.

#### Ranking

Boolean retrieval solves the efficiency problem of search engines, however, the quality of the retrieved documents can be low, especially when the document collection is very large. You will potentially get a very noisy search result set containing many ‘***False Positives***‘. To improve the relevancy of the search results, you can develop advanced relevance models to estimate a relevance score for every document in the collection against a search query and then you can set a threshold of the relevance scores and only retrieve the documents with a score above the threshold. Furthermore, you can now **rank** documents according to the relevance score. In fact, due to the user behaviour in web search, ranking is critical to most search engines. Research has shown that users tend to only check the first page results when using web search engines, and similarly for product search engines. As a result, the ranking qualities determine users’ satisfaction of a search engines.

Furthermore, users’ attention and likelihood of engagement with the search results tend to decay with the ranking position, for example, the following figure is taken from a previous research of eye-movement within a search result page.

![](https://www.productsearch.ai/wp-content/uploads/2021/01/Google-SERP-Results-Heat-Map.png)

Similarly, the following figure shows how likely a search result is examined and selected when shown in different ranking position. From the figure, we can clearly see that when a search result is ranked higher, the likelihood of engagement is higher.

![](https://www.productsearch.ai/wp-content/uploads/2021/01/image.png)

For product search engines, if you rank certain products higher, the likelihood of a user will engage with or purchase the product is higher. In some cases, the distribution of the probability of engagements may not strictly following the above figure. For example, users sometimes can ignore the first item when search for products. In those cases, we need to understand these behaviours and design our ranking functions accordingly.

We will discuss more about the importance of rankings in a different article.

![](https://www.productsearch.ai/wp-content/uploads/2021/01/ranking_model-1024x474.png)

However, imagine if you have an advance ranking model trained with the state-of-art AI techniques, which will give you a perfect ranking of documents. Would that solve your search problem? Not really! Why? Because it will be super slow, as you will need to compute the relevance score for every documents in your collection.

As a result, modern search engines usually achieve good ranking/relevance quality in a multi-stage fashion.

1. Cheap retrieval operation to return a set of potentially relevant documents
2. Rank document with a light relevance scoring function
3. Re-rank the top-k documents with an advanced ranking model that requires more computational cost

![](https://www.productsearch.ai/wp-content/uploads/2021/01/multi-stage-ranking-1024x151.png)

multi-stage ranking

The initial retrieval usually determine the recall of the search results (whether you retrieved all relevant documents). Under different search applications, this could be Boolean retrieval, entity retrieval, or semantic-based retrieval.

The initial ranking can be achieved by some classical text-based ranking models like tf-idf, BM25, BM25 etc, or it could be similarity functions like cosine similarity. This will usually give a relative relevance order if the ranking algorithm is designed properly. In fact, at this layer, we usually can achieve ***‘topical relevance***‘ for product searches, which means users will find the returned products are mostly relevant to the product that they are looking for.

However, initial ranking will usually miss the importance of users’ preferences towards different products. Rankings for products should consider the products’ attributes, users’ personal preferences as well as business objectives. For example, the popularity, the price, the brand, etc. This is extremely important for product search engines as it will directly impact users’ satisfaction as well as your business outcome. Usually ranking functions at this layer can be very complex, for example, machine learning ranking models that takes lots of features.

As you can see now, with this method, we leave the heavily computation to the last step of ranking and only apply to a subset of documents with good quality. The benefit of this strategy is that we can achieve a good recall and ranking effectiveness at the same time.

#### Summary

Ranking is critical for search engines and especially for product search engines. Due to the consideration of efficiency requirement, modern search engines usually apply a multi-stage ranking strategy that can help achieve better recall and ranking effectiveness at the same time.