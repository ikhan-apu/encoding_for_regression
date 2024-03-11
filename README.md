# encoding_for_regression
Comparing performances of 6 encoding schemes on 3 regression algorithms
Categorical data encoding is a crucial preprocessing step in machine learning, particularly when dealing with datasets containing categorical features. Categorical data refers to variables that take on a limited, fixed number of values or categories. However, many machine learning algorithms require numerical input, making it necessary to encode categorical variables into a numerical format. This process involves transforming categorical data into a numerical representation that algorithms can understand and process effectively. There are several encoding techniques commonly used for this purpose, including one-hot encoding, label encoding, ordinal encoding, target encoding, frequency encoding, and binary encoding. Choosing the appropriate encoding method depends on the nature of the data and the requirements of the machine learning model being used. Proper encoding ensures that categorical variables are represented in a way that preserves the relationships between categories while avoiding biases or misinterpretations by the model. Effective categorical data encoding is essential for achieving accurate and reliable predictions in machine learning tasks.
In this article, I will perform 6 different encoding techniques on 3 regression algorithms and compare their performances to find out which encoding technique did the best for each of the regression algorithm we have used.
We will first create a sample dataset with 3 numeric and 1 categorical attribute, and then encode the categorical features with 1. Mean encoding, 2. Frequency encoding, 3. Feature hashing, 4. Binary encoding, 5. One-hot encoding, and 6. Label encoding.
Below is a short theoretical detail on the mechanisms.
1. Mean or Target Encoding
Mean encoding involves replacing each category with the mean value of the target variable for that category. This method can be very effective, especially for supervised learning tasks, but it can lead to overfitting if not managed properly (e.g., by using regularization techniques).

2. Frequency or Count Encoding
Frequency encoding replaces each category with its frequency or count in the dataset. This method helps to maintain the information about the category's prevalence without expanding the feature space like one-hot encoding.

3. Feature Hashing or Hash Encoding
Feature hashing, also known as the hashing trick, involves using a hash function to transform categories into a fixed size of features. This can significantly reduce the dimensionality of the feature space but can introduce collisions where different values are mapped to the same feature space.

4. Binary Encoding
Binary encoding first converts categories into binary digits and then splits those digits into separate columns. It is more efficient than one-hot encoding as it requires fewer dimensions.
5. One-hot encoding
One-Hot Encoding transforms each categorical value into a new binary column and assigns a 1 or 0 (True/False) to indicate the presence of a feature. This method is particularly useful for linear models and scenarios where the categorical feature is not ordinal.
This method creates a separate column for each category, and then assigns 0 or 1 in each row/column. So, if we have many levels in the category features we plan to encode, this method will increase the dimensionality and thus be problematic for model fitting.
6. Label encoding
Label Encoding converts each category into an integer value. This method can be useful for non-linear models where you want to preserve memory and do not want to increase the dimensionality of your dataset.

Choosing the Right Encoding scheme
Mean or Target Encoding can be very powerful for machine learning models but requires careful treatment to avoid overfitting. It is particularly useful when the relationship between the categorical feature and the target is strong and clear.
Frequency Encoding is useful when the frequency of categories itself might be informative for the model.
Feature Hashing is a good choice when you have a very high cardinality and are willing to accept some information loss due to hash collisions.
Binary Encoding strikes a balance between the dimensionality increase of one-hot encoding and the information preservation of ordinal encoding.
One-Hot Encoding is preferable when the categorical variable does not have an intrinsic order (i.e., the categories are nominal). And, the model you're using does not inherently deal well with numerical representations of categories (e.g., linear regression models). 
Label Encoding is better suited when the categorical variable has an intrinsic order (ordinal data). And the model you're using can interpret the numerical values appropriately (e.g., decision trees, random forests).
Choosing the encoding scheme can significantly impact our model's performance and interpretation, so consider the context of the problem when deciding.
