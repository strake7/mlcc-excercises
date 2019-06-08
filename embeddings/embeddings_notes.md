# Embeddings

What is an embedding is and what is it for?
    They map items - texts, categories, to low-dimensional real vectors so that similar items are close to each other
    It can also be applied to dense data (audio) to create a meaningful similarity metric.
    Join diverse data types (text, images, audio) and define a similarity between them. 
    
    Examples: Words in a real estate ad to predict sales price

**Collaborative filtering** - making predictions about the interests of a user based on interests of many other users. 

**Input representation** - dictionary mapping each feature to an integers `0 through- len() -1`

To enact a collaborative filtering solution we need to determine what data is similar to each other. We can achieve this by embedding data into a low-dimensional space with similar data nearby.

Embeddings can have multiple dimensions to establish similarity. For example movies can be grouped by rating for a 1 dimensional embedding. Add Genre of movies for a 2nd dimension. 

**Categorical data** refers to input features that represent one or more discrete items from a finite set of choices. Such as Movie ratings or Genres. Catagorical data is most efficiently represented via sparse tensors which are tensors with very few non-zero elements.


How do you represent a word as a vector of numbers?
**One hot encoding** Create a vector for every word in your vocabulary and a node for every time the word appears in the data. 
The problem with these is that they become large and difficult for the model to train on. The better solution is to use embeddings which translate large sparse vectors into a lower-dimensional space that preserves semantic relationships


An **embedding** is a matrix in which each column is the vector that corresponds to an item in your vocabulary.

## Word2vec
Algorithm ivented at google for creating word embeddings. Maps semantically similar words to close embedding vectors using the distributional hypothesis. Distributional hypothesis states that words which often have the same neighboring words tend to be semantically similar. Both "dog" and "cat" frequently appear close to the word "vet", and this fact reflects their semantic similarity
