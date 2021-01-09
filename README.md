
## Problem statement

This project is geared towards young researchers such as undergraduates motivated to pursue graduate school. 
Undergraduate research experience is a major factor in graduate admissions. 
However, as a beginner, it is extremely challenging for an undergrad to identify the broad research topics and 
the fastest growing areas in any field he/she is interested in. Moreover, simply going through publication databases 
isn't a viable solution: every year thousands of papers are published in every research area in physics!

This project attempts to answer some of these problems. I have identified and compared the buzzwords of two different years 
which gives us an indication of the rising trends in physics. Using topic modelling, I have identified broad research topics 
as well as sub-topics contained in them. An interested reader can not only get a clear view of the research landscape in any 
broad are in physics but also find out some of the specific questions that belong to any field. Some EDA results can be found on the `flask` web-application I created on `heroku`: [app](https://arxiv-topic-modeling.herokuapp.com/home)

## Data source and processing

I have used ~13,600 publications from year 2020 on [arxiv](https://export.arxiv.org/list/physics/20) website for data. I then applied lemmatization, removal of punctuations, math symbols, and stopwords, and vectorizer before feeding it to the machine learning algorithm.

## Machine Learning Algorithms

I have used two ML algorithms in this work. The first is _k_-means clustering, with `n_clusters` set to 5. There are several visualizations: size of the clusters, frequencies of some popular words in each cluster, most popular words in different clusters using wordclouds, and 2-D visualization of the vector space using PCA. I have used Silhoutte score as the evaluation metric. 

The second method I have applied is the Latent Dirichlet Allocation or LDA using the `gensim` library. A good introduction to LDA can be found [here](https://scikit-learn.org/stable/modules/decomposition.html#latentdirichletallocation). Again, the `num_topics` is set to 5. The evaluation metric used is the coherence score.
