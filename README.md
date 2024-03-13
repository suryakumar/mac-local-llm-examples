# mac-local-llm-examples
A few examples of local LLM setup &amp; tasks on a macbook pro M1 Max

### langchain_RAG_pdfdoc.ipynb
This notebook provides a basic use-case for showcasing how you can use local LLMs for setting up a LLM based chat search to understand a PDF document and answer questions associated with the same.

To setup a langchain based RAG, you will need to go through 5 steps:


1. __Indexing - Loading__: Loading the raw data from  the data source (a *PDF* file, in our case).

2. __Indexing - Splitting__: Splitting the entire document into multiple smaller chunks. In practice, this is a very important step as the type of splitting & chunking will have a heavy downstream impact on the Retrieval. The hyperparameters like chunk-size, overlap & the logic associated with chunking have a very important role to play.

3. __Indexing - Store__: Every piece of data is embedded into a vector (768 dimensions).

4. __Retriever__: Create a retriever which can be used to find the top ranked embeddings from a store given a query. The retrieval is essentially a similarity search using techniques like 'cosine similarity'

5. __Generate__: Pass on the query (and the corresponding top retrieved documents) to the LLM alongwith a corresponding prompt for it to generate meaningful answers to the question posed to the document.