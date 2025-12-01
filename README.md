## Abstract
This project focuses on designing and implementing a web-based search pipeline, including document 
acquisition, indexing, and query retrieval. A Scrapy-powered crawler is used to download and store web documents in 
HTML format. An inverted index is then generated using TF-IDF weighting to support efficient similarity-based 
retrieval. Finally, a Flask-driven query processor enables users to submit free-text searches and receive ranked 
document results based on cosine similarity.

Future enhancements can focus on improving scalability and retrieval quality. Optional features such as concurrent 
and distributed crawling using AutoThrottle and Scrapyd would allow faster and broader document collection. Search 
accuracy could be increased by integrating semantic vector embeddings like Word2Vec or FAISS-based k-nearest neighbor 
similarity. Additionally, a front-end search interface and production deployment would make the system more 
user-accessible and robust.

## Overview
The project focus on web document retrieval and query processing. It consists
of three compononent: a web crawler, an indexer, and a query procesor. These
components works together to enable efficiant crawling, indexing, and 
querying of web docuemnts. 
### Soultion Outline
1. **Web Crawler**: Use Scrapy to roam the web and download web documents.
2. **Indexer**: Build an inverted index using the TF-IDF and Cosine similarities to search and retrieve 
3. **Query Processor**: Accepts user queries and returns ranked document results using TF-IDF and cosine similarity.
### Relevant Literature: 
- [Scrapy Documentation](https://docs.scrapy.org/en/latest/intro/tutorial.html):  
  This official tutorial provides a comprehensive introduction to Scrapy, a powerful Python framework for web crawling and scraping. It covers spider creation, data extraction, and best practices for scalable web data collection, which directly informs the design of the project's web crawler component.

- [Flask Documentation](https://flask.palletsprojects.com/en/stable):  
  The Flask documentation offers detailed guidance on building lightweight web applications and APIs in Python. It is the primary reference for implementing the query processor and REST API endpoints, enabling user interaction and search result delivery in this project.

For the search indexing section, I have already studied and applied established techniques, as demonstrated in this project.

### Proposed System
The system use the power of scrapy for web crawling, Skit-Learn for TF-IDF indexing and Cosine similarities, and Flask for query processing. The combination of these technologies, it delivers a solution for web docuement retrieval and query processing. 

## Design
The system's capabilities includes downloaading web documents, constucting an inverted index, and processing user queries. it involves the Scrapy crawler to collect web documents, th indexer building the TF-IDF matrix, and the Flask processor handeling user queries. Integration is achieved through data exchange between components and adherence to defined interfaces.

![Web Search Engine Diagram](/Web_Search_Engine_Diagram.png)

This activity diagram outlines the flow of activities within the system, including crawling, indexing, processing queries, and returning results. Each 
component interacts with the others to achieve the overall functionality of the system.

## Architecture

The architecture of the system involves three main components: the Scrapy crawler, the inverted indexer, and the Flask query processor. These components interact with each other to enable web document crawling, indexing, and query processing.

![Web Search Engine Diagram](/Architecture_Diagram.png)

This diagram illustrates the interaction between the components and how they utilize interfaces such as file I/O and HTTP endpoints for communication and data exchange. The implementation relies on external libraries such as Scikit-Learn, BeutifulSoup, Spider, and Flask to enable various functionality.

## 5. Operation

**Installation Instructions:**  
  - Ensure Python 3.8 or higher is installed.  
  - Create and activate a virtual environment:  
    - `python -m venv venv`  
    - `venv\Scripts\activate` (Windows) or `source venv/bin/activate` (Linux/Mac)  
  - Install all required dependencies using:  
    - `pip install -r requirements.txt`  

**Software Commands:**  
  - **Running the crawler:** Execute the relevant notebook cells or script to start the Scrapy crawler.  
  - **Building the index:** Run the indexing cells or script to generate the inverted index (`index.json`).  
  - **Running the Flask server and querying:** Start the Flask server by running the appropriate notebook cells or script. Submit queries via the web interface or batch CSV upload.

**Inputs:**  
  - **Seed URL:** The initial URL for the crawler.  
  - **CSV queries:** A CSV file containing `query_id` and `query_text` columns for batch search.  
  - **Configuration options:** Parameters such as maximum pages to crawl, crawl depth, and allowed domains.

**Outputs:**  
  - **Crawled HTML files:** Stored in the `pages/` directory.  
  - **Cleaned text files:** Stored in the `cleaned_text/` directory.  
  - **Inverted index:** Saved as `index.json`.  
  - **Search results:** Ranked results provided as a downloadable CSV file via the Flask API.
## 6. Conclusion
- **Success/Failure:**  
  The project successfully demonstrates the implementation of a modular web search pipeline, encompassing web crawling, document cleaning, inverted indexing, and query processing. The system is capable of acquiring web documents, extracting and cleaning their content, constructing a positional inverted index, and retrieving relevant documents in response to user queries using TF-IDF and cosine similarity. Error handling is incorporated to manage missing files or invalid queries, ensuring robust operation.

- **Outputs:**  
  The outputs of the system are as follows:  
  - Crawled HTML files are stored in the `pages/` directory.  
  - Cleaned text files are saved in the `cleaned_text/` directory.  
  - The positional inverted index is generated and saved as `index.json`.  
  - Search results for user queries are provided as ranked CSV files, which can be downloaded via the Flask API.  
  - Example outputs, including ranked document results and similarity scores for sample queries, are displayed below as evidence of successful retrieval and ranking.

## 7. Data Sources
- Web documents are sourced from [quotes.toscrape.com](https://quotes.toscrape.com)
- Additional data sources can be integrated as needed for testing and evaluation.

## 8. Test Cases
Test cases involve validating the functionality of the crawler, indexer, and query processor. Frameworks such as Scrapy's testing tools and unit testing libraries for Python can be utilized. Test coverage includes scenarios for crawling, indexing, and querying.
## 9. Source Code

The complete source code for this project, including the web crawler, indexer, and query processor, is provided in the accompanying Jupyter notebook (`Crawl_Search.ipynb`) and related Python scripts within the project directory. All implementation details, code cells, and configuration files are included to enable full reproducibility of the results.

Key files and directories:
- `Crawl_Search.ipynb`: Main notebook containing the code for crawling, indexing, and query processing.
- `pages/`: Directory where crawled HTML files are stored.
- `cleaned_text/`: Directory containing cleaned text files extracted from HTML pages.
- `index.json`: Generated inverted index used for search and retrieval.
- `requirements.txt`: List of required Python packages for the project.

To access or modify the source code, open the notebook or scripts in your preferred Python environment (e.g., Jupyter Notebook or Visual Studio Code).


## 10. Bibliography

- https://docs.scrapy.org/en/latest/intro/tutorial.html  
  *Official Scrapy tutorial providing step-by-step guidance on building web crawlers, extracting data, and managing large-scale scraping projects.*

- https://beautiful-soup-4.readthedocs.io/en/latest  
  *Comprehensive documentation for Beautiful Soup, a Python library used for parsing HTML and XML documents and extracting useful information.*

- https://www.w3schools.com/python/python_json.asp  
  *Introductory guide to working with JSON data in Python, including reading, writing, and parsing JSON files.*

- https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html  
  *Reference documentation for the cosine similarity function in scikit-learn, used to measure similarity between vectors, such as document and query vectors.*

- https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html  
  *Documentation for the TfidfVectorizer class in scikit-learn, which converts text documents to a matrix of TF-IDF features for information retrieval and text mining.*
