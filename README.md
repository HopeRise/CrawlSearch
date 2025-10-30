# README Outline for Web Crawler + Indexer + Search Project
## 1. Abstract
- Brief summary
- Objectives:
  - Crawl web pages, extract content.
  - Build an index for search.
  - Enable ranked query results via Flask API.
- Next steps:
  - Improvements 

## 2. Overview
- Solution Outline: Explain the full workflow:
- Relevant Literature: Briefly cite research/articles on web crawling, TF-IDF, cosine similarity, or search systems.
- Proposed System: Highlight architecture and its intended functionality.

## 3. Design
- System Capabilities:
  - Max pages/depth crawling
  - TF-IDF index construction
  - Top-K query results
- Interactions: How crawler, indexer, and query processor communicate.
- Integration: File formats (JSON index, CSV queries), data flow.

## 4. Architecture
- Software Components:
  - Scrapy spider
  - Scikit-Learn indexer
  - Flask query processor
- Interfaces: APIs, endpoints, command-line interfaces.
- Implementation Notes: Python version, libraries (Scrapy, sklearn, Flask)

## 5. Operation
- Installation Instructions: Dependencies, environment setup, pip/venv usage.
- Software Commands:
  - Running crawler
  - Building the index
  - Running Flask server and querying
- Inputs: Seed URL, CSV queries, configuration options.

## 6. Conclusion
- Success/Failure:
- Outputs:

## 7. Data Sources
- Links to websites crawled (if allowed).

## 8. Test Cases
- Framework: Pytest, unittest, or custom scripts.
- Harness: How to test crawler, indexer, query processor.
- Coverage: Edge cases like empty pages, invalid URLs, long queries, or spelling errors.

## 9. Source Code

## 10. Bibliography


## To-Do List

### Step 1: Web Crawling
- [ ] Set up scrapy project
- [ ] Define crawling rule
- [ ] Extract content
- [ ] Save HTML files

### Step 2: Indexing
- [ ] Load and clean HTML
- [ ] Vectorize document
- [ ] Compute similarity

### Step 3: Query Processing
- [ ] Set up Flask
- [ ] Validate query
- [ ] Vectorize query
- [ ] Retrieve results

