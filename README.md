# AI-generated-text-detection 

The objective of this project was to identify AI-generated text vs. human written text. The problem statement is as follows: Can you predict the 'ind' (0= human, 1 = AI) as a function of the 768 document embeddings, the word count and the punctuation?

All text data was converted into embeddings and the project further details the outcomes of this endeavor. Below are some comments that arose during this project. 

There are five critical observations from the study focusing on improving classification model performance:

1. Feature Selection Methods Impact on F-1 Score: Utilizing feature selection methods like Random Forest classifiers, PCA, Boruta shadow variables, and K-best led to lower F-1 scores, attributed to the model's inability to capture the full dataset trend and information loss. Conversely, using all parameters increased computational time, highlighting a balance challenge between interpretability and computational efficiency.

2. Decision Against SMOTE for Class Balancing: Opting out of using SMOTE, despite its potential for addressing class imbalance, was based on the observation that it introduced noise and reduced model performance metrics (F-1 score, accuracy, and precision), thereby impairing accurate target variable predictions.

3. Significance of Word Count as a Feature: Word count emerged as a crucial predictor for the target variable, supported by EDA and permutation importance analysis findings. This contrasts with the less significant role of punctuation number (punc_num), which correlated strongly with word count but did not emerge as a key feature.

4. Model Interpretability and Predictor Impact: The analysis of word_count through partial dependence plots revealed a direct correlation with the likelihood of the target variable indicating AI-origin. This was contrary to initial EDA findings. Conversely, higher values of specific features (feature_512 and feature_386) were associated with a higher likelihood of human-originated content.

5. Ensemble Modeling for Improved Accuracy: A singular model could not achieve an F-1 score above 0.68, limited by the complexity of the dataset. Success was achieved by employing a stacking ensemble approach, which significantly improved accuracy in predicting the target class, though at the expense of reduced interpretability due to the complex nature of ensemble models.

These observations underscore the complexities and trade-offs involved in model selection, feature importance, class balancing techniques, and the pursuit of higher accuracy versus interpretability in classification tasks.
