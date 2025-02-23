## Chapter 3: ML System Design
Machine learning system design interviews are quite different from general system design questions, which is why I separated this from general system design. Honestly, I did quite a massive search, and there aren’t many resources available online. So, I drew from my own experience designing deep learning systems at work, along with the ML system design interviews I’ve conducted—both as an interviewee and interviewer—to create a comprehensive template that captures all the key aspects of ML system design.

In a machine learning system design interview, you typically have around 45 minutes—and it goes by fast. To make the most of this time, I created this template, inspired by [this amazing guide](https://github.com/alirezadir/Machine-Learning-Interviews/blob/main/src/MLSD/ml-system-design.md) , to outline steps that help structure your interview, bring order to your approach, and guide your thought process. When practicing for your interview, try using this framework until it becomes second nature.

1- **Clarifying Questions**

- **Use Case(s) and Business Goal**  
  Identify the primary use cases and the overarching business objective.  

- **Requirements**  
  - Functional: Define the scope, including necessary features.  
  - Nonfunctional: Address performance metrics such as prediction latency, scalability, and system availability.(Optional here, we can discuss that later too.)
  - Constraints: Consider privacy regulations and compliance with data protection standards.  

- **Training Data and Labels**  
  - Sources: User interaction logs, ad content data, user profiles, contextual information, and user-user relationships (e.g., friendships in facebook).  
  - Historical click and impression data.  

- **Costs for Data**  
  - Data collection, annotation, and computational resources.  

- **Assumptions**  

- **Problem Translation to ML**  
  - Convert the abstract problem into a concrete ML problem.  
  - Define the *ML category* (e.g., binary classification, multi-class classification, unsupervised , reinforcement learning, etc.). 

