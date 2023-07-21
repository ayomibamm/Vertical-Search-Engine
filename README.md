# Vertical-Search-Engine

## Background
This project focussed on the development of a vertical search engine for Coventry University, Centre for Computational Science and Mathematical Modelling research department publications. A generalized search engine would not be the most efficient way to retrieve information related to the department as it would be time-consuming.
Link: https://pureportal.coventry.ac.uk/en/organisations/research-centre-for-computational-science-and-mathematical-modell/publications/

## Process
### Fully Functioning Crawler
The first step ensured that the robots.txt rules of the required page is preserved. The required data is obtained from the website HTML code and saved as a JSON file (a list of dictionaries, each representing information about a publication). Information extracted includes publication title, abstract, date, link, author information, and link.

### Inverted Index Construction
Application of preprocessing techniques on the publication titles: 
- The lower casing of all the words in the document
- Tokenisation- the splitting of documents into words/tokens
- Stop words removal- most common words in any language and do not add much information to the text, for example, the, a, so in the English language
- Normalisation- by applying the stemming technique, the process of transferring words to their word base.

The indexer is used for full-text search over a set of documents. It consists of the term as a key and frequency of the term [0] and document ID [1] as the value. An example of implementing an inverted indexer for only 1 to 2 termed queries is detailed in the Colab document. If the query is 2 termed, the processor was set to output an intersection of both document ID lists. Also, the processor prints the document ID of the term present in the indexer if the other term is not in the inverted index. 

### Robust Query Processor
The processor is a function that can be called whenever is query needs to be processed. Pre-processing tasks such as tokenization, stop word removal, and stemming were applied to the query. Then the query and document are further processed by using the Vector Space Model, where each document is represented by a vector of tf-idf scores in the space, as well as the query. Cosine similarity- cosine angle between 2 vectors of an inner product space is calculated. The scores were then ranked. The higher the score of a given document and the query, the more relevant it is to that query. Therefore, the output for the query is the order of ascending scores, i.e. the higher scores are at the top of the search results. 

# Thank you!
