#marie_chatfield_rivas #ai #genai #llms 

# Learn Less, Parse More

## AI Summary

## Notes

### Agenda

- parse standard grammars
- post-process for reliabilty
- craft domain-specific grammars
- optimize grammars for LLM cooperation

### Case Study: Recipes

- example application: paprika
- data.world custom collector - import paprika recipes to maximize metadata
	- e.g. difficulty levels
	- feedback
		- ingredients attached to recipes would make this truly useful

### Parsing Standard Grammars

- for example: dump the recipe in chat GPT and ask for ingredients
- iterate: ask for json, not a bullet list

#### What is a Grammar?

- explaining a concept in a super-detailed concrete way that allows a computer to understand what a thing is

#### What is an Abstract Syntax Tree (AST)?

- astexplorer.net
	- paste in your json example and get the full AST
	- meaning, not just description
- once you have an AST, you can use it in whatever programming language you want to use
- you could also just return other text
	- prettier JSON
	- YAML

### Process

- generate ingredients list with LLM
- parse into JSON
- create structured data


### When Should I Parse?

- anytime you expect your model to generate structured data


### What Should We Do Now?

- make it more reliable
- for example: we don't need 5 different synonyms for refined sugar, in fact, we definitely don't want that
- instead: 
	- use the LLM to determine whether or not things are actually the same thing
	- OR do a rules-based code method that combines things on a synonym list
		- that code is unit-testable and can be shown to other people
		- THIS is the power of post-processing


### The Model just needs to be "good enough" and post-processing can take you the rest of the way!

- prompt for main use case
- post-process for edge cases and known issues


### Craft Domain-Specific Grammars

- we *could* prompt for json but it gets wordy and can spend a lot of tokens doing that
- alternatively you can just create your own grammar
	- they used special characters to route around the wordiness of json

#### How do you get the model to listen to your grammars?

- you can give them the rules but it is hard to overcome all of the training of the LLM
- OR you can create a custom parser

#### Parser Generator

- define your own grammar
- the parser generator will generate the code for you
- a lot better and more consistent than regex

### When to Write Your Own Grammars

- if your domain is difficult to model with standard formats or requires precise and complex syntax

### Optimize grammars for LLM Cooperation

- 
