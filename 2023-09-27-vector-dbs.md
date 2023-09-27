# Vector DBs, the Unsung Hero of AI

#vector #zilliz #ai #genai 

## AI Summary

## Notes

### Unstructured Data is Everywhere

### Extracting Value from Unstructured Data

- example: a company has 100k pages of proprietary docs to enable their staff to service ustomers
- problem: searching can be slow, inefficient, or lack context
- solution: create internal chatbot iwth chatGPT and a vector db

### How do Vector DBs Work?

- semantic similarity: how close are two words in meaning?
- vectors quantify the distance in meaning in numeric terms
- TLDR: vectors allow you to do math on things that are not numbers

### Where Do Vectors Come From?

- any type of unstructured data AS LONG AS you have the embeddings model

### How Does Similarity Search Work?

- nearest neighbor

### How To Evaluate a Vector DB

- query on the embedding rather than a hash key or primary key

### Why Not Use Relational DBs?

- TLDR: vector operations are too computationally intensive for relational database infrastructures

### Why Not Use Vector Search Libraries?

- there's no supporting infra to help you scale

### Why is Milvus Different?

- makes use of cloud architecture
- seperation of concerns: indexing, storage, & querying
- scalable index creation with 512MB segments


### Check out OSS Project!!! 
https://github.com/zilliztech/awesome-milvus


### Check out this advanced demo! 
https://mlops.community/combine-and-query-multiple-documents-with-llm/
