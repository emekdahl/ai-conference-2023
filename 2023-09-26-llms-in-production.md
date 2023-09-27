#ray #genai #ai_conf #ai #llm_ops #retrieval_augmented_generation
# LLMs in Production

## AI Summary

The notes discuss the challenges and solutions for deploying Large Language Models (LLMs) like GPT-4 and Llama2 in production, focusing on the use of Ray for optimization and Anyscale for endpoint management.

#### Key Points:

- **Why Ray**: ChatGPT was trained using Ray, which is faster and cheaper. Ray's managed version is also used for customer deployments.
    
- **LLMs in Products**: LLMs are provided as a service, used to enhance products, and help customers deploy their own LLMs.
    
- **Case Study**: Discusses a software for summarizing long email threads written in Langchain or Llama Index, utilizing GPT-4.
    

### Challenges:

- **Expense**: GPT models are costly. Open models and fine-tuned OSS models are suggested for cost optimization.
    
- **Instruction Following**: While ChatGPT is good at following instructions, Llama2 can be less reliable.
    
- **Data and Privacy**: Questions the wisdom of sending company emails to OpenAI and raises GDPR compliance issues.
    
- **Deployment Complexity**: LLMs require significant resources. For instance, deploying Llama2 70b needs 4x A100 80GB GPUs.
    

### Solutions:

- **Self-hosting**: Open-source options like ray-llm and vLLM are available for self-hosting.
    
- **Assisted Self-Hosting**: Anyscale offers private endpoints running in your cloud, handling auto-scaling, observability, and updates.
    
- **Using Others' Models** : like OpenAI or OSS and imported via CLI
### Future Outlook:

- **RAG in Enterprises**: Retrieval Augmented Generation (RAG) is predicted to become the default use-case for LLMs in enterprises.
    
- **Model Improvement**: Acknowledges that the model improvement over time is still an unsolved problem.
    

The notes emphasize the need for cost-effective, compliant, and scalable solutions when moving from LLM demos to production environments.
## Notes
## What we'll talk about

- easy to demo, hard to productionize
- lessons learned

## Why you should care

- chatGPT was trained using Ray
- Ray is faster and cheaper

## What's our experience with LLMs

- we provide LLMs as a service
- we use LLMs to make our products better
- we help our customers deploy LLMs on Ray and the managed version of Ray

## Anyscale Endpoints

## End to End LLM privacy, customization, and control

## Ray Docs also use LLMs

- you can combine your questions with their docs to get them to write the code implementing ray
- Anyscale doctor demo
	- it tells you what's wrong with your code and gives you a button to click to fix it

## Case Study

- you provide software for summarizing long email threads
- you've written in langchain and or llama index
- you use gpt-4

### Problems you will encounter

#### Expense

- GPT is EXPENSIVE - 30x Llama 70b for similar performance
	- how do we optimize cost without impacting quality
		many people will say llama2 is not as good as gpt4
	- example of comparable quality
		- factuality eval
		- factuality evals
			- GPT slightly edged out humans in performing these evals 
	- consider open models as you move to production because cost can be a huge issue
	- sometimes, a tiny, fine-tuned OSS model can outperform a vendor LLM
		- For example: fine-tuning for SQL syntax

#### There is still a price to be paid

- APIs are easy
	- Anyscale endpoints are OpenAI API compatible
- BUT
	- ChatGPT is good at following instructions
	- Llama2 doesn't always do what you tell it to do
	- Hypothesis
		- RHLF is the secret sauce of OpenAI
- we still use GPT-4 a lot
	- hard queries
	- evaluations - it is still the best grader

#### Instruction Following

#### Context Windows

- affect how much data you can feed into the LLMs
- anthropic is the leader because it allows 100k tokens

#### Vs. OpenAI strictly defined templates

- strictly defined templates

#### Data and Privacy

- are you comfortable sending your company's emails to openAI?
- are you worried about explaining to your users that you are sending data to OpenAI?
- Are there restrictions that you have that apply? (GDPR)
- when it comes to deploying LLMs, you may not go to OpenAI

## Deployment Complexity

- where and how do you run your LLMs if not OpenAI
- LLMs are not always small models
- Llama2 70b takes 4x A100 80GB GPUs to deploy

### Self-hosting is a viable option

- OSS options
	- ray-llm
	- vLLM
	- text-generation-inference used to be 

#### Self-hosted Llama 2 Models

- got to be running 70B tokens for it to make sense from a cost perspective

### Assisted Self-Hosted Endpoints

- anyscale private endpoints
- runs in your cloud
- handles auto-scaling, observability, updates

## What Does the Future Hold?

- one task requires many LLM calls and many LLMs
- RAG will be the default use of LLMs in enterprises
- we haven't fully solved the model improvement over time

