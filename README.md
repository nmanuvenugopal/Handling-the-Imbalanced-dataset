# Handling-the-Imbalanced-dataset

I am using an credit card fraud detection input file from kaggle dataset for this experiment. I am attaching the link for your reference.
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

We all know that credict card fraud is a serious issue of looting someone's money however it occur rarely. From below screenshot it is clear that dataset is not balanced one.

![image](https://github.com/nmanuvenugopal/Handling-the-Imbalanced-dataset/assets/99719105/2bf81862-a983-4223-a8d1-3734bb13b50c)

 ## What hapens if the dataset is imbalanced dataset ?
When dealing with an imbalanced dataset, where the classes are not equally represented, several issues can arise that can significantly affect the performance of machine learning models. Here's a detailed explanation of what happens, the criteria for balancing datasets, and various techniques including oversampling, undersampling, and weighted models.

1. **Model Bias**: Most machine learning algorithms assume or perform better when the number of examples in each class is roughly the same. An imbalanced dataset can lead to models that are biased towards the majority class, as they will tend to predict the majority class more often.
2. **Poor Generalization**: Since the minority class is underrepresented, the model might fail to capture the patterns in the minority class, leading to poor generalization when predicting new data.
3. **Performance Metrics Misinterpretation**: Traditional metrics like accuracy can be misleading in imbalanced datasets, as a model might achieve high accuracy by simply predicting the majority class all the time, ignoring the minority class.

### Techniques for Balancing

#### Oversampling
Oversampling involves increasing the number of instances in the minority class to balance the dataset. This can be done by:
- **Random Oversampling**: Replicating instances of the minority class randomly.
- **SMOTE (Synthetic Minority Over-sampling Technique)**: Generating synthetic examples of the minority class by interpolating between existing examples.

**Pros**:
- Improves model sensitivity to the minority class.
- Useful when the amount of data is small.

**Cons**:
- Can lead to overfitting due to the replication of minority class instances.
- Synthetic examples might not always be representative of real-world scenarios.

#### Undersampling
Undersampling reduces the number of instances in the majority class to balance the dataset. This can be achieved by:
- **Random Undersampling**: Randomly removing instances from the majority class.
- **Cluster-based Undersampling**: Grouping the majority class instances into clusters and then performing undersampling to maintain diversity.

**Pros**:
- Reduces the model training time by decreasing the dataset size.
- Can help in reducing overfitting by removing redundant instances.

**Cons**:
- Might lead to loss of important information if significant instances from the majority class are removed.
- Can decrease model performance if the dataset size becomes too small.

#### Weighted Models
Weighted models adjust the importance given to each class during the learning process, without physically altering the dataset. This is achieved by assigning a higher weight to the minority class and a lower weight to the majority class in the cost function used by the model.

**Pros**:
- No loss of information since no data is removed or replicated.
- Can be easily implemented in most machine learning algorithms.

**Cons**:
- Determining the optimal weights can be challenging and might require extensive experimentation.
- Might not be as effective if the class imbalance is severe.

It is easy to apply weights in the machine learning model. We just need to add a parameter and assign one of the different values available to that parameter. Let's take a look at how we can apply weights to Random forest classifier and Decision tree classifier models.

In the below examples I have added a parameter called "class_weights" to the Decision Tree Classifier model and assign it value "balanced".

![image](https://github.com/nmanuvenugopal/Handling-the-Imbalanced-dataset/assets/99719105/5d113ba6-5b72-48d9-894d-75bd87368267)

When it comes to the random forest classifier the parameter reamins the same ("class_weights") but the value I assigned to the Random Forest Classier model is "balanced_subsample".

![image](https://github.com/nmanuvenugopal/Handling-the-Imbalanced-dataset/assets/99719105/a395aeb8-8a7e-4515-a64e-3309b1ef21f9)




