#genai #llama #effective_data_science_infra #jerry_liu 

## AI Summary

The notes focus on the challenges and solutions for augmenting Language Models like LLMs with private data, particularly through the use of Retrieval Augmented Generation (RAG) and LlamaIndex.

#### Key Points:

- **Context**: Discusses paradigms for inserting knowledge into LLMs, including fine-tuning and RAG.
    
- **LlamaIndex**: A data management and query engine tailored for LLM applications. It handles data ingestion, data structures, and queries, enabling quick development of chat interfaces over documents.
    
- **New ETL in RAG Stack**: Highlights the ease of using LlamaIndex to process and store text chunks into a vector database, which are later used for querying.
    
- **Challenges in RAG**: Identifies issues such as quality-related failure modes (hallucination, accuracy) and non-quality-related issues (latency, cost).
    
- **Handling Challenges**: Suggests storing additional information beyond raw text, using custom embeddings, improving retrieval methods, and leveraging LLMs for more than just response generation.
    
- **Evaluation**: Discusses the need for benchmarks and metrics to evaluate RAG systems, either end-to-end (E2E) or by isolating each component. Suggests using GPT-4 for human-like grading.
    
- **Techniques for Better RAG**: Recommends decoupling embeddings from text, using smaller chunks for retrieval but larger ones for synthesis, and fine-tuning embeddings.
    

The notes underscore the importance of a well-thought-out approach to data management, query mechanisms, and evaluation metrics when deploying LLMs with RAG.

## Notes

- ![[IMG_0117.jpeg]]

## Context

 ![[IMG_0118.jpeg]]
- how do we best augment LLMs with our own private data?
![[IMG_0119.jpeg]]
### Paradigms for inserting knowledge

 ![[IMG_0120.jpeg]]

- fine-tuning - baking knowledge and reasoning into the weights of the network
- RAG - retrieval augmentation
	- fix the model, put context into the prompt
	- fancy prompt engineering

## LlamaIndex

 ![[IMG_0121.jpeg]]

- data management and Query Engine for your LLM application
- offers components across the data lifecycle
	- data ingestion (LlamaHub)
	- data structures
		- store and index your data for different use cases 
		- integrate with different DBs
	- queries
		- retrieve and query over data
		- includes QA, summarization, agents, and more
- advantages
	- build chat over any documents using llama_index in 3 lines of code

 ![[IMG_0122.jpeg]]
## RAG stack

### The New ETL

- 5 lines of code in llama index!
- split up documents into even chunks
- each chunk is a piece of raw text
- generate embedding for each chunk
	- e.g., openai embeddings or sentence transformer
- store each chunk into a vector db

### Current RAG stack (querying)

 ![[IMG_0124.jpeg]]
 ![[IMG_0123.jpeg]]

- find top-k most similar chunks from the vector database collection
- plug into the LLM response synthesis module


## Challenges with Naive RAG

 ![[IMG_0126.jpeg]]

- failure modes
	- quality-related: hallucination, accuracy
	- non-quality-related (latency, cost)
- bad retrieval
	- lower precision - not all chunks in a retrieved set are relevant
	- low recall - lacks enough context for LLM to synthesize an answer
	- outdated information 
- bad response generation
	- hallucination - model makes up an answer that isn't in the context
	- irrelevance - model makes up an answer that doesn't answer the question
	- toxicity/bias 

## How do we handle these challenges?

 ![[IMG_0127.jpeg]]

- data: can we store additional information beyond the raw text chunks
- embeddings - can we do better than using a pre-trained embedding model
- retrieval - can we do anything better than top-k
- synthesis: can we use the LLMs for more than generation

## Evaluation: Measuring Performance

 ![[IMG_0128.jpeg]]

- defining benchmarks
- how do we properly evaluate a RAG system?
	- E2E
	- evaluate each component in isolation
- open question: what to do first?

### Evaluation in Isolation

 ![[IMG_0129.jpeg]]

- details: evaluate the quality of retrieved chunks given user query
- collect dataset
	- input: query
	- output: the "ground truth" documents relevant to the query
- run retriever over the dataset
- Measure ranking metrics
	- success
	- MRR
- Synthetic Dataset Generation for Retrieval Evals
	- parse / chunk up text corpus
	- Prompt GPT_4 to generate questions from each chunk
	- each question/chunk is now your eval pair

 ![[IMG_0130.jpeg]]
### Evaluation E2E

![[IMG_0131.jpeg]]

- Details: evaluation of final generated response given input
- collect dataset
	- input query
	- Output: the "ground-truth" answer
- Run through the entire RAG pipeline
- Collect evaluation metrics
	- if no labels: label-free evals
	- if labels: with-label evals

#### Synthetic Dataset Generation for E2E Evals
![[IMG_0132.jpeg]]
### LLM-based Evaluation Modules

![[IMG_0133.jpeg]]

- GPT-4 is an excellent human grader
- label-free modules
	- faithfulness - does the response match the received context?
	- relevancy: whether the response matches the query?
	- guidelines: whether the response matches guidelines or custom instructions?

## Techniques for Better Performing RAG

![[IMG_0134.jpeg]]
- decouple embeddings from raw text chunks
	- beware of overfitting on the test set. Use validation and test set
![[IMG_0135.jpeg]]
![[IMG_0136.jpeg]]
- small to big retrieval
	- generally, relevance is higher when you chunk it smaller
	- But then you may need the surrounding context 
	- one challenge may be that you have the "lost in the middle" LLM problem, which is what happens when you widen the top k

![[IMG_0137.jpeg]]
- embedding references to text chunks
	- embed references to text chunks instead of the text chunks directly
		- but then do retrieval on the smaller chunks
		- use the bigger chunk for synthesis
![[IMG_0138.jpeg]]
- organize your data for more structured retrieval
	- summarize
![[IMG_0139.jpeg]]
- fine-tuning embeddings
![[IMG_0140.jpeg]]


![[IMG_0141.jpeg]]

![[IMG_0142.jpeg]]