#meta #genai #automl #ml #mia_gerrard #meta_ai
# Self-Serve ML Platforms

## AI Summary

The notes discuss the increasing importance and utility of self-serve Machine Learning (ML) platforms in today's business landscape.

#### Key Points:

- **Why Self-Serve ML**: These platforms enable broader adoption of ML technologies across both Small and Medium-sized Enterprises (SMEs) and novices, driving business value by making ML more accessible.
    
- **Expanding Impact**: The value proposition includes shared engineering effort and AutoML, which helps in scaling configuration and optimization.
    
- **Industry Usage**: There is a pervasive use of AI & ML across industries, but there are concerns regarding scalability and speed.
    
- **From Kaggle to ML Ops**: The focus is shifting from hyper-tuning models for marginal performance gains to considering implementation and runtime trade-offs like model size and latency.
    

### Platforms:

- **Looper**: A general-purpose, end-to-end ML platform that supports everyday tasks throughout the ML lifecycle.
    
- **PEX**: A specialized platform for optimizing user experience at the individual level, focusing on product metrics over traditional ML metrics.
    

### Requirements:

- Self-serve ML platforms should offer features such as automated data collection, product-impact evaluation, and full custody of data. They should also be resilient, scalable, and provide customer support.

### Additional Capabilities:

- Open architecture, customizations, reproducibility, meta-learning, interpretability, and fairness in ML are some of the other features that could add value.

### Metric Improvement:

- Empirical validation shows that automated updates can save engineering time and increase client trust.

### Discussion:

- The focus should shift from just ML performance to overall product metric performance. These platforms democratize ML, leading to a wider adoption and greater impact.

The notes emphasize that self-serve ML platforms are not just a trend but a necessity for businesses aiming to harness the full power of ML efficiently.

## Notes


## Why Self-Serve ML Platforms?

- enable dramatic scaling of adoption of ML platforms by both SMEs and novices
- directly drive business value by expanding the use of ML to previously untapped applications via the reuse of ML capabilities and infrastructure with high client productivity


## Expanding Impact of ML 

- the value proposition of "self-serve" end-to-end ML platforms
	- shared engineering effort( new tech, platform maintenance, system upgrades)
	- supported by AutoML by scaling configuration and optimization

## Background and Current Landscape

### AI & ML usage across the industry is pervasive

- common concerns on how to scale up and speed up the use of AI

### Shifting the focus from the Kaggle Paradigm -> ML Ops

- hyper tuning models to eke out relatively small performance improvements
- overlooks implementation and runtime tradeoffs
	- model size, latency

## ML Platform Development

- tradeoffs 
- data collection
- integration with A/B testing
- automate data collection and model retraining

### AutoML & E2E ML

- critical

## Looper & PEX

- > 100 product teams leverage for metric improvement
- 3-4 million AI outputs per second
- Hundreds of use cases

### Looper

- general purpose E2E ML platform
- supports everyday ML tasks
- via API, they get access to all of the everyday tasks you need to do in the ML lifecycle

### PEX Personalized Experiment Platform

- specialized platform enabling product teams to leverage heterogeneous treatment effects to optimize end-user experience at the individual level
- optimizes directly for product metrics rather than ML metrics
- supports HTE meta-learning and RL models
- check out the paper!

### Commonalities

- both have full custody of the data
- no experience requirement for customers


## Requirements to Achieve Self-Serve ML Platform

- data handling
	- The platform should maintain full custody of data to reduce human error and manual pipelining
- product impact evaluation and optimization 
	- platforms should be able to conduct 

1. low cognitive barrier
2. automated data collection
3. autoConf
	1. automated selection of ML problem foculation, ML tasks, model type, and default parameters
	2. followed by workflow traditional AutoML
4. product-impact metrics 
	1. tracking and automatic optimization
	2. counter-factual policy evaluation
5. sufficient ML quality
6. complete management of hosting
7. adaptation to data drift
8. resilience and robustness to disruptions in data and system environment
9. customer-facing monitoring and root-causing of customer errors
10. scalable internal platform maintenance and white-glove customer support


## 6 additional capabilities

- open arch 
- customizations to everyday ML tasks
- reproducibility of models
- meta-learning, including transfer learning
- interpretable ML
- fairness in ML

## Metric Improvement via automated updates to ML models and decision policies

- saves > two weeks use case of eng time to run validation experiments
- enables automatic online experiments for retuning of decision policies
- increases client trust via accurate tracking and optimization of their goals

### Empirical validation: Client-driven PEX Improvement

- product team eval of PEX vs. hand-tuning vs. ML tool-box and selection of PEX
	- the time savings made PEX a compelling alternative to hand-tuning

### Tradeoffs

- if the tiniest of performance increases turn into meaningful dollar value or customer experience, autoML may not be for you
- seasoned ML engineers may not be comfortable ceding control


## Discussion

- shift focus from ML performance to product metric performance
- democratizes the use of ML techniques beyond ML experts
- impact grows with economy of scale usage of these platforms
- wide adoption of platforms enables usage of integrated ML techniques
- 