### EX6 Information Retrieval Using Vector Space Model in Python
### DATE: 
### AIM: To implement Information Retrieval Using Vector Space Model in Python.
### Description: 
<div align = "justify">
Implementing Information Retrieval using the Vector Space Model in Python involves several steps, including preprocessing text data, constructing a term-document matrix, 
calculating TF-IDF scores, and performing similarity calculations between queries and documents. Below is a basic example using Python and libraries like nltk and 
sklearn to demonstrate Information Retrieval using the Vector Space Model.

### Procedure:
1. Define sample documents.
2. Preprocess text data by tokenizing, removing stopwords, and punctuation.
3. Construct a TF-IDF matrix using TfidfVectorizer from sklearn.
4. Define a search function that calculates cosine similarity between a query and documents based on the TF-IDF matrix.
5. Execute a sample query and display the search results along with similarity scores.

### Program:

```python
import requests
from bs4 import BeautifulSoup
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.metrics.pairwise import cosine_similarity
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords
import string
import nltk

nltk.download('punkt')
nltk.download('stopwords')
```
Sample documents stored in a dictionary

```python
documents = {
    "doc1": "This is the first document.",
    "doc2": "This document is the second document.",
    "doc3": "And this is the third one.",
    "doc4": "Is this the first document?",
}
```

Preprocessing function to tokenize and remove stopwords/punctuation
```python
def preprocess_text(text):
    tokens = word_tokenize(text.lower())
    tokens = [token for token in tokens if token not in stopwords.words("english") and token not in               string.punctuation]
    return " ".join(tokens)
```

Preprocess documents and store them in a dictionary
```python
preprocessed_docs = {doc_id: preprocess_text(doc) for doc_id, doc in documents.items()}
```

Construct TF-IDF matrix
```python
tfidf_vectorizer = TfidfVectorizer()
tfidf_matrix = tfidf_vectorizer.fit_transform(preprocessed_docs.values())
```

### Output:
![image](https://github.com/user-attachments/assets/ec36251f-487b-4779-8f4a-0238d19c9f67)

### Result:
Thus, the implementation of Information Retrieval Using Vector Space Model in Python is executed successfully.
