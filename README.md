<h1 align='center'>Extract article based on query using BERT</h1>

Hear is the Demo App

[![Watch the video](https://i.ytimg.com/vi/b8w8rOAMOnY/hqdefault.jpg)](https://youtu.be/b8w8rOAMOnY)

We are building a system that can extract topics from an article and ranking of the documents according to relevance to the query.

1. Here,i used the distilbert-base-nli-stsb-mean-tokens model which performs great in Semantic Textual Similarity tasks and it’s quite faster than BERT as it is considerably smaller. 
2. The scalability of the model has decreased when there is the long sentence(50-60 words sentence).
3. Hear we dont need data to train the bert model because we use the pretrained bert model which is trained on Wikipedia and Book Corpus, a dataset containing +10,000 books of different genres.
4. this model is performed very well on the unseen data and give the best result.
5. we can deploy this model on cloud platform like AWS and Microsoft Azure because this model is light weight model unlike Bert model ,take very less time to resplond and performed very well on the noisy data.

 

## Tabel of contents
1. [ File Descriptions ](#File_Description)
2. [ Technologies Used ](#Technologies_Used)    
3. [ Executive Summary ](#Executive_Summary)

## File Descriptions
<details>
<a name="File_Description"></a>
<summary>Show/Hide</summary>
<br>
    
* <strong>[ Data ](https://github.com/HardikMochi/Assignment/tree/main/data)</strong>: folder containing csv file
* <strong>[ models ](https://github.com/HardikMochi/Assignment/tree/main/models)</strong>: folder containing faiss_index.pickle which used in Assignment_App.ipynb
* <strong>[ video ](https://github.com/HardikMochi/Assignment/tree/main/video)</strong>: folder contain the sample video of app 
* <strong>[ Assignment_App.ipynb ](https://github.com/HardikMochi/Assignment/blob/main/Assignment_App.ipynb)</strong>: This file is used to create app in streamlit
* <strong>[utils.py ](https://github.com/HardikMochi/Assignment/blob/main/utils.py)</strong>: this file contain some usefull function


</details>

## Tecnologies Used:
<details>
<a name="Technologies_Used"></a>
<summary>Show/Hide</summary>
<br>
    
* <strong>Python</strong>
* <strong>Pandas</strong>
* <strong>Numpy</strong>
* <strong>sentence_transformers</strong>
* <strong>Pytorch</strong>
* <strong>faiss</strong>
* <strong>streamlit</strong>
</details>


<a name="Executive_Summary"></a>
## Executive Summary:

### Apporach that we are follow for this project
1. first we embedded all the article using the BERT model
2. than we embedded the query using the BERT model
3. than we find the similarity between the query vector and every document vector in our database and return those with the highest score

#### Model
Next, let’s encode the paper abstracts. Sentence Transformers offers a number of pretrained models. Here, we used the distilbert-base-nli-stsb-mean-tokens model which performs great in Semantic Textual Similarity tasks and it’s quite faster than BERT as it is considerably smaller.

#### Vector similarity search with Faiss
Faiss is a library for efficient similarity search and clustering of dense vectors. It contains algorithms that search in sets of vectors of any size, even ones that do not fit in RAM.

Faiss is built around the Index object which contains, and sometimes preprocesses, the searchable vectors. Faiss has a large collection of indexes. You can even create composite indexes. Faiss handles collections of vectors of a fixed dimensionality d, typically a few 10s to 100s.

#### Searching the index
The index we built will perform a k-nearest-neighbour search. We have to provide the number of neighbours to be returned.

Let's query the index with an abstract from our dataset and retrieve the 5 most relevant documents. The first one must be our query!

#### Result 
Let’s try to find relevant academic articles for a new, unseen search query.
<p align="center">
  <img src="https://github.com/HardikMochi/Assignment/blob/main/images/3.PNG" height=200>
</p>
