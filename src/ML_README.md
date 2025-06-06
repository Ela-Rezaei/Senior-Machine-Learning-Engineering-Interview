## Chapter 3: ML System Design
Machine learning system design interviews are quite different from general system design questions, which is why I separated this from general system design. Honestly, I did quite a massive search, and there aren’t many resources available online. So, I drew from my own experience designing deep learning systems at work, along with the ML system design interviews I’ve conducted—both as an interviewee and interviewer—to create a comprehensive template that captures all the key aspects of ML system design.

In a machine learning system design interview, you typically have around 45 minutes—and it goes by fast. To make the most of this time, I created this template, inspired by [this amazing guide](https://github.com/alirezadir/Machine-Learning-Interviews/blob/main/src/MLSD/ml-system-design.md) , to outline steps that help structure your interview, bring order to your approach, and guide your thought process. When practicing for your interview, try using this framework until it becomes second nature.

### ML Sytem Design Template
#### 1- Clarifying Questions

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

#### 2-a Offline Metrics
* **Classification Metrics**
  * Precision, Recall, F1-score
  * ROC and AUC
  * Precision-Recall AUC
  * Mean Average Precision (mAP)
  * Log-loss
  * Strategies for imbalanced data
    
* **Retrieval and Ranking Metrics**
  * Position-aware
    * Mean Average Precision (mAP)
    * Mean Reciprocal Rank (MRR)
    * Normalized Discounted Cumulative Gain (nDCG)
  * Position-unaware
    * Precision@k
    * Recall@k
    
* **Regression Metrics**
  * Mean Squared Error (MSE)
  * Mean Absolute Error (MAE)
  * Root Mean Squared Error (RMSE)
    
* **Domain-Specific Metrics**
  * Natural Language Processing
    * BLEU, ROUGE, BLEURT
    * GLUE benchmark
  * Advertising
    * Cost Per Engagement (CPE)
    
* **System Performance Metrics**
  * Latency (inference time)
  * Computational cost
  * Memory usage (especially for on-device models)

#### 2-b Online Metrics
* **Engagement Metrics**
  * Click-Through Rate (CTR)
  * Task/session success rate
  * Task/session completion time
  * Interaction rates (likes, comments, shares)
    
* **Business Metrics**
  * Conversion rate
  * Revenue lift
  * Return on investment (ROI)
    
* **User Experience Metrics**
  * Reciprocal rank of first click
  * Time to first action
    
* **Negative Feedback Metrics**
  * Direct negative actions (hide, report, unsubscribe)
  * Bounce rate
  * Churn rate

#### 3- Architectural Components (MVP Logic)

At this stage, take a step back and examine your system holistically. Use the architecture diagram I created to guide your explanation of the high-level architecture and main components. Walk through the natural flow of data and processing in your system, highlighting the purpose and functionality of each key component.
This is your opportunity to discuss non-functional requirements such as latency, throughput, and scalability considerations. Address how your design accommodates these requirements and explain the reasoning behind critical trade-offs you've made.
Present the alternatives you considered for important design decisions and justify why you selected certain approaches over others. Connecting these technical choices back to business requirements is a plus.

![Image](https://github.com/user-attachments/assets/8be6dbb4-0675-4825-9840-80ae42989b5e)


#### 4- Data Collection and Preparation
* Data sources and collection methods
* ML Data types
   * Structured data
      * Numerical (discrete, continuous)
      * Categorical (ordinal, nominal)
   * Unstructured data (images, text, video, audio)
* Labeling for supervised learning
   * Labeling approaches and trade-offs
      * Negative sampling strategies
      * Explicit user feedback collection
      * Human annotation (costs, timeline, privacy concerns)
   * Handling limited labels
      * Semi-supervised learning techniques
      * Transfer learning approaches
         * Pre-training on large datasets
         * Zero-shot learning and fine-tuning options
      * Active learning implementation
* Data augmentation techniques
* Data Generation Pipeline components
   * Data collection/ingestion systems (offline, online)
   * Label generation mechanisms
 
#### 5- Feature Engineering
* Features
   * Post features
      * Text content
      * Image/video attributes
      * Engagement metrics (likes, shares, replies)
      * Post age
      * Hashtags and topics
   * User features
      * Identifiers (ID, username)
      * Demographics (age, gender, location)
      * Contextual information (device, time of day)
      * Historical interaction patterns (click rates, engagement)
   * User-Post interaction features
      * Entity IDs (user, post/ad)
      * Interaction type and metadata (time, location)
   * User-creator relationship features
      * Connection type
      * Historical engagement with creator
* Feature representation techniques
   * One-hot encoding for categorical variables
   * Embedding approaches
      * Pre-computation and storage strategies
   * Categorical encoding methods (one-hot, ordinal, count)
   * Numerical feature scaling and normalization
* Preprocessing requirements
   * Unstructured data processing
      * Text: Tokenization pipeline (normalization, tokenizer models, special tokens)
      * Images: Resizing, normalization
      * Video: Frame extraction, sampling, scaling
* Missing value handling strategies
* Feature importance analysis and selection methods
* Feature computation timing
   * Static features (from feature store)
   * Dynamic features (computed at serving time)

#### 6-Model Development and Tranining
* Model selection approach
   * Classical modeling options
      * Logistic Regression
      * Decision tree variants
         * Gradient Boosting (XGBoost)
         * Random Forests
      * Neural network architectures
         * Feedforward networks
         * Convolutional Neural Networks (CNN)
         * Recurrent Neural Networks (RNN)
         * Transformer models
   * Selection criteria
      * Task complexity considerations
      * Data characteristics (type, volume, complexity)
      * Training efficiency
      * Inference constraints (compute, latency, memory)
      * Continual learning requirements
      * Model interpretability needs
* Dataset management
   * Data partitioning strategy
      * Time-based splitting for temporal data
         * Accounting for seasonality and trends
      * Preventing data leakage
         * Restricting transformation statistics to training data
   * Addressing class imbalance
      * Resampling techniques
      * Loss function weighting
      * Class consolidation approaches
      * Stratified sampling
* Training process
   * Loss function selection
      * MSE, Cross-Entropy, MAE, Huber, Contrastive
   * Optimizer selection
      * SGD, AdaGrad, RMSProp, Adam
   * Training methodology
      * Full training vs. transfer learning
   * Comprehensive offline evaluation
   * Hyperparameter optimization
      * Grid search implementation
   * Iterative improvement cycle
      * Refining model selection
      * Enhancing data augmentation
      * Determining update frequency
    

#### 7- Online Testing and Model Deployment
* A/B testing methodology
* Shadow deployment techniques

#### 8-Serving, Monitoring, and Maintenance
* Deployment infrastructure
   * Hardware considerations (cloud, edge devices)
* Prediction delivery modes
   * Batch processing vs. real-time inference
* Comprehensive monitoring system
   * Logging framework
      * Feature values, model predictions, performance metrics, system events
   * Key monitoring indicators
      * System performance metrics
      * Model quality metrics
         * Integrated online and offline metric dashboards
   * Data distribution shift detection
* Failure handling
   * Infrastructure failures
   * Model performance degradation
* Model refresh strategy
   * Training approach
      * Full retraining vs. incremental updates
      * Optimal update frequency determination
   * Automated model deployment
   * Human oversight integration

### Sample Questions for ML System Design

- [Source 1](https://www.tryexponent.com/questions?company=facebook&role=ml-engineer)

- [Source 2](https://www.interviewquery.com/questions?searchQuery=&searchQuestionTag=&searchCompany=&tags=Behavioral&ordering=Recommended&orderingDirection=ASC&pageSize=100&page=0)

### Want to master the fundamentals?

[Source 1] (https://www.mlebook.com/wiki/doku.php)

