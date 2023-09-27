#genai #langchain #harrison_chase #ai

https://github.com/langchain-ai/langsmith-sdk
https://github.com/langchain-ai/langsmith-cookbook/tree/main
https://docs.smith.langchain.com/
# Building Context-Aware Applications with Langchain
![[IMG_0099.jpeg]]
## AI Summary

The notes focus on building context-aware applications using Langchain, a toolkit designed to integrate with GenAI models and other tools. There are four primary types of context-aware techniques:

1. **Instruction Prompting**: Uses custom instructions and meta-prompts.
2. **Few Shot Examples**: Provides example inputs and outputs to dynamically guide the model.
3. **Retrieval Augmented Generation (RAG)**: Bases answers on specifically retrieved information.
4. **Fine-Tuning**: Updates model weights to incorporate context, especially when examples are hard to provide.

#### Reasoning Techniques:

- **LLM Call**: Fast, single call with no context.
- **Chaining**: Pre-determined sequences of calls.
- **Routing**: LLM decides next steps based on input.
- **Automatons / State Machines**: Agents manage a list of prompts or sub-tasks.
- **Autonomous Agents**: Shift between states implicitly.

#### Challenges:

- **Orchestration**: Langchain focuses on sequencing and routing tasks.
- **Data Engineering**: Time-consuming to find and transform the proper context.
- **Prompt Engineering**: Significant effort goes into crafting instruction sets.
- **Debugging**: Complexity increases as the application scales.

#### Evaluation and Metrics:

- Traditional ML metrics might not apply.
- Feedback mechanisms like RHLF, thumbs up/down and follow-up questions are used for evaluation.

#### Collaboration:

- Involves multiple teams and skill sets, including Subject Matter Experts (SMEs) for prompt engineering.

## Notes

- we saw people connecting GenAI models to other tools to power context-aware applications
- many applications around bringing the proper context to the language model so the model can give a correct and differentiated answer

## Context-Aware

### Four Different Types
![[IMG_0100.jpeg]]

#### Instruction Prompting

- a.k.a. custom instructions
- meta-prompting

#### Few Shot Examples

- provide a handful of example inputs and outputs, usually in the context of instructions
- next level: select the most relevant examples to give dynamic prompting with the most appropriate examples

#### Retrieval Augmented Generation (RAG)

![[IMG_0102.jpeg]]

- answer the question only based on the information that we've retrieved
- grounding the language model in this context

#### Fine-Tuning

- bringing context in the form of updated weights
- good when it is tough to give good examples or the amount of examples required is high

## Reasoning

- how do we get the LLM to take the context and respond appropriately

###  Levels of Reasoning

![[IMG_0103.jpeg]]

#### LLM Call
![[IMG_0104.jpeg]]

- no context, single call
- pros
	- fast

#### Chaining

![[IMG_0105.jpeg]]

- multiple calls or chains of calls
- example:
	- GPT researcher - check out this OSS project!
- in chaining, the sequences are pre-determined

#### Routing

![[IMG_0108.jpeg]]


- the LLM determines which step is next, depending on the input
	- may also determine whether to look things up in a private vector store vs. the internet
- for example, GPT researcher has a reporting agent that falls into this category of reasoning
![[IMG_0107.jpeg]]

#### Automatons / State Machines

![[IMG_0109.jpeg]]
- this is where you start to see things called "agents."
- ![[IMG_0110.jpeg]]
- plan-and-execute agent in langchain is similar to BabyAGI
	- the user passes an objective or task, which generates a list of prompts or sub-tasks that the agent manages
	- similar to the Reflexion paper
- ![[IMG_0111.jpeg]]
- another example is sweep.dev
	- inputs
	- Search
	- plan
	- execute
	- validate
	- pull request

#### Autonomous Agents

- ![[IMG_0113.jpeg]]
- input > LLMs > Action > output
- LLM is expected to shift between states implicitly vs. the automatons who run the plan execute validate loop explicitly


## Levels of Autonomy in State Machines

- ![[IMG_0114.jpeg]]
## Challenges

- ![[IMG_0115.jpeg]]

- orchestration
- data engineering
- prompt engineering
- debugging

### Orchestration

- the main thing that langchain is built around is this problem
	- sequencing, routing, etc.
	- two main value props
		- modules that integrate with LLMs and vector stores
		- agents that do end-to-end tasks

### Data Engineering

- we see people who use langchain spend the most time on data engineering
- we need to find the proper context, transform it, and provide the relevant context

### Prompt Engineering

- many people spend time on the instruction set

### Debugging

- this is difficult as applications scale because you've got a lot of stuff happening in the background to make all of this possible
- langsmith - check it out.


### Evaluation

- ![[IMG_0116.jpeg]]

- you don't necessarily start with a dataset, so you may not have actuals
- sometimes, people use human labeling
- sometimes, people use GPT to create synthetic data
- use prod logs
	- prod logs are a way that langchain gets data to evaluate

#### Metrics

- a lot of traditional ML metrics may not apply unless you're doing classic ML tasks like classification
- seeing many people doing human labeling
- using LLMs to evaluate the output
- add a thumbs up / down for explicit feedback
- implicit feedback - if they ask a follow-up question, I haven't provided a complete answer

### Collaboration

- there are multiple teams and individuals, not just technical people, the prompt engineering may be best done by an SME



