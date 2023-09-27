#genai #ai #vector #ram_sriharsha #pinecone
# Gen AI & Vector DBs

## AI Summary
  
The notes discuss the challenges and solutions associated with using Large Language Models (LLMs) and vector databases in the context of Generative AI (GenAI).

### LLM Challenges

- Quality depends on training data.
- Knowledge is static, based on when the model was trained.
- Finite context windows can limit performance.
- Hallucinations (incorrect or nonsensical outputs) are a concern.
- Attribution and privacy are challenging in current workflows.

### Solutions with RAG (Retrieval Augmented Generation)

- Solves problems like attribution, privacy, and updating the model's knowledge base.

### Vector Search and Databases

- Vector search involves transforming semantic search input to vector embeddings.
- Libraries like HNSW are used for building graph indexes.

### Challenges in Vector DBs

- Geometric filters are not always efficient.
- Handling metadata is complex.
- Index management can be inefficient and costly.
- Scalability is a concern, and existing solutions like scatter-gather don't scale well.

### Properties of a Good Vector Database

- Should be geometry-aware.
- Should have adaptive indexes.
- Should allow controlled trade-offs between recall and cost.

### Pinecone as a Solution

- It's a self-serve vector search solution.
- Allows creation, management, and scaling of indexes via API.
- Offers high freshness, scalability, and low-latency queries.
- Optimized for both performance and cost, with no need for manual tuning.

## Notes

### Agenda

- what is a vector db
- why is it relevant to GenAI


### GenAI Workflow

### LLM Challenges

- only as good as the training data
- knowledge is frozen as of the training period
- context windows are finite
- hallucinations
	- gets worse with large context windows
- attribution of content is hard with current workflows
- privacy

### Incorporating Knowledge Using RAG

- solves multiple problems in one shot
	- attribution
	- privacy
	- incorporation of knowledge

### GenAI Workflow with RAG

- retrieval
	- dense
	- sparse
	- hybrid

#### What is vector search?

- semantic search input > embedding model > vector embedding

### Challenges with geometric filters

### Why not just use a vector search library?

- the system understands geometry well, but it doesn't understand data management well
- not as good at handling metadata

### Graph Index

- preprocessing phase, build neighborhood graph
- HNSW is the leading graph index library

#### Challenges with Filters

- in the worst case scenario, it could be worse than brute force search
- not theoretical. It happens in practice

### Challenges with Index Management

- tradeoffs between efficiency and freshness
- concurrent workloads and contention
- expensive - even if you are querying a small set of data, you're paying to query the whole set
- hard to scale - you can bolt libraries onto databases but it is DIY
	- The only effective mechanism is scatter-gather, which doesn't scale well

### Properties of a Vector Database

- geometry aware
	- provide first-class support for efficient geometric
	- perform efficient metadata filtering
- adaptive indexes
	- indexes must be adaptive to updates and deletes
- controlled tradeoff between recall and cost
	- aim for high recall for the given cost budget
	- easy to say, hard to engineer
	- we need innovation in this area for vector DBs (other DBs have already made gains in this area)

### Pinecone

- self-serve for vector search
- create, manage, and scale indexes through API
- high freshness
- scalable, low latency queries
- performance and cost-optimized instances
- no tuning/parameter tweaking

