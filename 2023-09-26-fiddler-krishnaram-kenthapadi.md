
#krishnaram_kenthapadi #fiddler #ai #genai 
# Deploying Trustworthy Generative AI

## AI Summary

The notes focus on trustworthiness challenges in Generative AI, as presented by Krishnaram Kenthapadi, the Chief AI Officer & Chief Scientist at Fiddler AI.

#### Key Challenges:

- **Robustness to Input**: Large Language Models (LLMs) are sensitive to slight changes in query content, which can result in untrustworthy outputs.
    
- **Privacy and Copyright**: There's a risk of violating individual rights or improperly using intellectual property, particularly in image generation tasks.
    
- **Bias**: Detecting and mitigating bias is particularly challenging, especially in high-stakes settings like HR and Finance.
    
- **Inconsistencies**: Generative AI models can sometimes provide inconsistent information.
    
- **Lack of Transparency**: Many models are proprietary, and their self-explanations are often unreliable.
    

#### Solutions and Observations:

- **Continuous Monitoring**: Enterprise solutions need real-time safety layers to evaluate the quality of responses for robustness, PII leaks, toxicity, or bias.
    
- **Fiddler's Approach**: Fiddler AI provides observability solutions for Generative AI through its Fiddler Auditor. It offers both validation and production-stage monitoring.
    
- **User Workflow**: Fiddler enables model validation, continuous monitoring, and score feedback, where human and model-based scoring are incorporated for comprehensive evaluation.
    

#### Conclusion:

Generative AI has many promising applications, but its enterprise adoption requires addressing multiple dimensions of trustworthiness, including robustness, security, privacy, and bias.


## Notes


- Krishnaram Kenthapadi, Chief AI Officer & Chief Scientist, Fiddler AI

### AI Has Come of Age!

- a new AI category is forming
- BUT trust issues remain

### Trustworthiness Challenges in Generative AI

- robustness to input perturbations
	- LLMs are NOT robust to input perturbations
	- for example: if you change the content of a query slightly, you can get the LLM to give you an answer that violates trustworthiness principles
- privacy and copyright concerns 
	- we do not want to improperly or illegally use intellectual property
	- for example, if the user prompts an image generation model to generate an image of a person in the training set, they will generate an almost identical image that would violate that individuals rights
- Bias in Generative AI
	- motivation
	- high stakes settings like HR, Finance
	- why is it hard to detect and mitigate bias 
- inconsistencies
- lack of transparency
	- many of these models have proprietary training which we may not have visibility into

### How Do We Achieve Transparency?

- make the model generate the reasoning
	- Chain of Thought
	- **bad news: self-explanations generated by LLMs are highly unreliable**
	- it doesn't reveal that it was influence by training data where the first answer was correct

### Hallucinations

- model generates factually incorrect or nonsensical response

### Continuous Monitoring of LLM Quality

#### Enterprise Concerns for Deploying Generative AI

- real-time safety or proxy layer between the model and the application
	- understand the quality of the response before it gets to the application
		- robustness to prompt injection
		- is the model leaking PII
		- how often is the response toxic or biased

### Fiddler's Response to these Challenges

#### Observability for Gen AI and LLMs

- both in validation and production
- Fiddler auditor https://github.com/fiddler-labs/fiddler-auditor

#### Generative AI User Workflow

- model validation
- continuous monitoring
	- publish production traffic to fiddler to track changes in aggregate user behavior
- score with feedback
	- publish human feedback into fiddler alongside query data
	- incorporate model-based scoring where human feedback is absent
### Conclusions

- emergence of generative AI - there are a lot of exciting applications
- enterprise adoption requires trustworthy development and deployment of generative AI
	- correctness robustness security privacy, bias, transparency, red teaming
- Check out the expanded version of the talk at a recent conference
