## Chapter 3: ML System Design
Machine learning system design interviews are quite different from general system design questions, which is why I separated this from general system design. Honestly, I did quite a massive search, and there aren’t many resources available online. So, I drew from my own experience designing deep learning systems at work, along with the ML system design interviews I’ve conducted—both as an interviewee and interviewer—to create a comprehensive template that captures all the key aspects of ML system design.

In a machine learning system design interview, you typically have around 45 minutes—and it goes by fast. To make the most of this time, I created this template, inspired by [this amazing guide](https://github.com/alirezadir/Machine-Learning-Interviews/blob/main/src/MLSD/ml-system-design.md) , to outline steps that help structure your interview, bring order to your approach, and guide your thought process. When practicing for your interview, try using this framework until it becomes second nature.

### 1. **Problem Formulation**

- **Clarifying Questions**  
  Define the problem clearly by asking targeted questions to ensure full understanding.  

- **Use Case(s) and Business Goal**  
  Identify the primary use cases and the overarching business objective.  

- **Requirements**  
  - *Functional*: Define the scope, including necessary features and personalization needs.  
  - *Nonfunctional*: Address performance metrics such as prediction latency, scalability, and system availability.  
  - *Constraints*: Consider privacy regulations and compliance with data protection standards.  

- **Training Data and Labels**  
  - Sources: User interaction logs, ad content data, user profiles, contextual information, and user-user relationships (e.g., friendships).  
  - Historical click and impression data for model training and evaluation.  
  - Ensure the availability of labeled data for supervised learning.  

- **Costs**  
  - Data collection, annotation, and computational resources.  

- **Assumptions**  
  - Clarify assumptions that simplify the problem without compromising the solution’s integrity.  

- **Problem Translation**  
  - Convert the abstract problem into a concrete ML problem.  
  - Define the *ML category* (e.g., binary classification, multi-class classification, unsupervised learning, etc.).  
