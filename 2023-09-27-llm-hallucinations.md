
#vectara #genai #ai #ofer_mendelevitch

Ofer Mendelevitch, Vectara
# Why Do LLMs Hallucinate?

## AI Summary

Ofer Mendelevitch from Vectara discusses why Large Language Models (LLMs) tend to "hallucinate," or generate incorrect or nonsensical information, and how to address this issue.

#### Conceptual Framework:

- LLMs can be conceptualized as having a "knowledge graph" embedded in their weights.

#### Reasons for Hallucination:

1. **Incomplete Knowledge**: LLMs attempt to complete sentences even when the required information is not in their knowledge graph.
2. **Fictional or Subjective Content**: The existing information in the LLM's knowledge graph may be inaccurate or subjective.

#### Solutions:

- Research is ongoing to improve training data and incorporate human feedback.
- Strategies include improved prompting methods like "chain of thought" or "tree of thought," and techniques like Retrieval Augmented Generation (RAG).

#### Retrieval Augmented Generation (RAG):

- Allows for "grounded generation" by augmenting LLMs with specific data, thus reducing hallucinations.
- Benefits include better privacy and cost-effectiveness as it doesn't require retraining or human feedback.
- Vectara offers RAG as a service.

#### Best Practices for RAG:

- **Retrieval**: Use state-of-the-art (SOTA) retrieval methods to bring proper context.
- **Chunking**: Utilize NLP-based chunking instead of fixed chunking, as it works well.
- **Embedding**: Choose effective embedding models as they are not all created equal.

Vectara emphasizes that as LLMs continue to improve, the efficacy of solutions like RAG will also improve.
## Notes

### What is hallucination?

LLM provides incorrect or unfaithful information when responding to a query

### LLM Knowledge Graph: Conceptual paradigm

- not literal, but a conceptual framework for understanding
- it is helpful to imagine that the LLM has some knowledge graph embedded in its weights
- when we ask the LLM to respond, it relies on its knowledge graph

### Reason #1: You ask a question to which the answer is not in the knowledge graph

- LLMs are trained to complete the sentence, even if the information isn't present
- they aren't good at saying "I don't know" and generally aren't trained to do that

### Reason #2: There is information in the graph, but...

- it might include fictional content
- it might include subjective content

### What to do about it?

- there's a ton of research going on
	- improve the training data
	- incorporate human feedback using RLHF or similar techniques
	- improved prompting 
		- chain of thought
		- tree of thought
		- react
	- retrieval augmented generation 

#### Addressing Hallucinations with RAG

- LLM with "your data"
- aka grounded generation
- reduces hallucination
- use cases
	- chatbot/co-pilot
	- Q&A

#### RAG Reference Architecture

- vectara is RAG as a service

### Why RAG?

- augment your LLM with your own data
- privacy
- inexpensive to implement and use since there's no retraining or human feedback collection required
- complementary to model improvements like LRJF or better data curation: as LLMs continue to improve and evolve, RAG/GG becomes better as well

### Doing RAG Right

#### Retrieval

- SOTA retrieval and bringing the proper context to the LLM matters

#### Chunking

- fixed chunking (not so great to break sentences in the middle)
- use the SOTA embeddings model
- recursive chunking
- vectara has found that NLP chunking works well

#### Embedding

- not all embedding models are created equal


### Demos

https://asknews.demo.vectara.com 