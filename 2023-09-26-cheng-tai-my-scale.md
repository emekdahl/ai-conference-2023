#cheng_tai #my_scale

# SQL + Vector

## AI Summary

The notes discuss the integration of Language Models like LLMs with vector databases to build General AI applications. It highlights the existing dilemma between choosing for convenience, as offered by traditional databases like Postgres, and performance, as seen in vector databases like Pinecone.

#### Key Points:

- **SQL + Vector**: LLMs paired with vector databases form an essential stack for GenAI applications. The need for vector databases arises due to information limitations with GenAI models.
    
- **Dilemma**: The choice is often between convenience (Postgres) and performance (Pinecone).
    
- **Solution**: MyScale allows users to perform vector searches using SQL queries, thereby eliminating the need to learn new APIs for vector databases. It challenges the assumption that relational databases can't compete with vector databases in terms of performance.
    
- **Case Study**: A research assistant chatbot was built to interact with millions of papers, generating hundreds of millions of vectors. MyScale managed to reduce both the cost and latency of the operation.
    
- **Optimization Opportunities**: Hosting your own models and caching data can lead to significant improvements in performance, cost, and quality.
    
- **Conclusion**: MyScale not only allows SQL-based vector queries but also demonstrates that relational databases can match or even exceed the performance of vector databases.

## Notes


- LLM + vector DBs is essential stack to build Gen AI applications
- there's an information limitation with Gen AI, which is why we see more people using vector dbs

## Dilemma

- convenience vs. vector performance
- convenience
	- postgres - known quantity
- performance
	- pinecone

## Solution

- myscale allows users to run vector search with SQL, so users don't have to learn the APIs associated with vector DBs
- It was widely assumed that relational DBs couldn't compete or perform like a vector DB. However, myscale has demonstrated that this is not the case

### Case Study

- customer wants to build a research assistant chatbot that will chat with millions of papers
	- millions of papers turn into hundreds of millions of vectors
	- myscale reduced both cost and latency

## Huge Room to Optimize Performance, Cost, and Quality

- if you host your models
- if you cache your data

## Conclusion

- myscale allows users to query vectors with SQL
- demonstrates that the performance of relational databases can be on par or exceed vector dbs
