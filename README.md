# Big-data-Assignment-2    
Taha hasan 21i-1767
Hassaan hameed

Search Engine Development Using MapReduce: Project Report
Introduction
This project aimed to develop a basic search engine utilizing Apache Hadoop's MapReduce framework. The search engine was designed to index and query a subset of the English Wikipedia dump provided by Wikimedia, comprising around 5 million Wikipedia articles. The primary focus was on implementing document indexing and query processing techniques using MapReduce, with the goal of efficiently retrieving relevant documents based on user queries.

Dataset Description
The dataset provided in CSV format contained the following columns:

ARTICLE_ID: Integer serving as the identifier for each unique article title.
TITLE: String denoting the titles of articles.
SECTION_TITLE: String representing subsection titles from each article.
SECTION_TEXT: String containing text from each subsection.
Preprocessing Steps
Before proceeding with indexing and query processing, several preprocessing steps were performed:

Data Cleaning: Removed any irrelevant characters, punctuation, and special symbols from the text data.
Tokenization: Split the text into individual tokens (words) for further processing.
Stopword Removal: Eliminated common stopwords such as "the", "is", "and", etc., which do not contribute significantly to document relevance.
Normalization: Converted all text to lowercase to ensure case-insensitive matching during querying.
Stemming: Reduced inflected or derived words to their base or root form to improve indexing and retrieval accuracy.
Indexing Implementation
The indexing process involved the following steps:

Word Enumeration: Scanned the corpus to generate a set of unique words and assigned a unique ID to each word.
Document Count: Calculated the Inverse Document Frequency (IDF) for each term, representing the number of documents in which each term appears.
TF-IDF Computation: For each document, computed the Term Frequency-Inverse Document Frequency (TF-IDF) weights for each term to create a vector representation.
Index Storage: Stored the index efficiently, typically as key-value pairs, where the key represents the term ID, and the value contains relevant document IDs and their corresponding TF-IDF weights.
Query Processing
Query processing involved the following steps:

Query Vectorization: Generated a vectorized representation of the query using the same TF-IDF weighting scheme as used for documents.
Relevance Analysis: Calculated the relevance score between the query vector and each document vector using the inner product (scalar product) of the two vectors.
Ranking: Ranked the documents based on their relevance scores and returned the top-n most relevant documents as query results.
Testing and Optimization
The search engine was extensively tested using local datasets to validate its functionality and performance. Various optimization techniques were employed to improve efficiency and scalability, including:

Combiner optimization to reduce the volume of intermediate data.
Partitioning techniques to evenly distribute workload among reducers.
Caching frequently accessed data to minimize disk I/O operations.
Conclusion
In conclusion, the development of the basic search engine using MapReduce provided valuable insights into information retrieval techniques and distributed computing principles. The project demonstrated the feasibility of implementing document indexing and query processing tasks at scale using Apache Hadoop's MapReduce framework. Further enhancements could include implementing more advanced indexing techniques, such as distributed inverted indexing, and optimizing query processing algorithms for even faster retrieval speeds.
