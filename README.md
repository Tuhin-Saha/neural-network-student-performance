\# Neural Network for Student Performance Prediction



\## 1. Project Overview



This project uses a Neural Network to predict whether a student is likely to pass or fail based on selected academic, social, and demographic factors.



The project was developed as part of the ISA-1 Theory Presentation for the MSc Artificial Intelligence programme at Goa Business School, Goa University.



\## 2. Problem Statement



The objective is to classify students into two categories:



\- Pass

\- Fail



The prediction is based on student-related features such as study time, previous failures, absences, parental education, social activities, health, internet access, and intention to pursue higher education.



\## 3. Dataset



The project uses the Student Performance dataset from the UCI Machine Learning Repository.



Dataset used:



\- File: `student-por.csv`

\- Records: 649

\- Attributes: 33



The final grade (`G3`) was converted into a binary target:



\- `G3 >= 10` → Pass (1)

\- `G3 < 10` → Fail (0)



The features `G1` and `G2` were excluded to avoid target leakage and to make the model more suitable for early student-support applications.



\## 4. Features Used



The Neural Network uses 10 input features:



1\. `studytime`

2\. `failures`

3\. `absences`

4\. `Medu`

5\. `Fedu`

6\. `goout`

7\. `freetime`

8\. `health`

9\. `higher`

10\. `internet`



Categorical features were converted into numerical values and the numerical features were standardized using `StandardScaler`.



\## 5. Machine Learning Approach



\### Problem Type



\- Structured data

\- Supervised learning

\- Binary classification



\### Neural Network Architecture



```text

Input Layer: 10 features

&#x20;       ↓

Dense Layer: 16 neurons + ReLU

&#x20;       ↓

Dense Layer: 8 neurons + ReLU

&#x20;       ↓

Output Layer: 1 neuron + Sigmoid



Total trainable parameters: 321



Training Configuration

Optimizer: Adam

Loss function: Binary Cross-Entropy

Epochs: 50

Batch size: 16

Validation split: 20%

Test split: 20%

6\. Model Training



The Neural Network was trained using the training portion of the dataset.



Training and validation performance were monitored using:



Accuracy

Loss

Validation Accuracy

Validation Loss



The model achieved approximately 90.36% training accuracy at the end of training and 86.54% validation accuracy.



7\. Model Evaluation



The trained model was evaluated using 130 previously unseen test samples.



Performance Metrics

Metric	Result

Accuracy	88.46%

Precision	90.98%

Recall	96.52%

F1 Score	93.67%

Classification Report

Class	Precision	Recall	F1 Score

Fail	50%	27%	35%

Pass	91%	97%	94%

8\. Confusion Matrix



The confusion matrix obtained from the test data was:



&#x20;               Predicted

&#x20;             Fail    Pass

Actual Fail     4      11

Actual Pass     4     111



Interpretation:



4 Fail students were correctly classified as Fail.

11 Fail students were incorrectly classified as Pass.

4 Pass students were incorrectly classified as Fail.

111 Pass students were correctly classified as Pass.

9\. New Student Prediction



A hypothetical student's information was provided to the trained Neural Network.



The model predicted:



Probability of Passing: 98.41%

Prediction: PASS



This demonstrates how the trained model can be used to make a prediction for a new student.



10\. Limitations



The dataset is imbalanced:



Pass: 115 students

Fail: 15 students



Because there are significantly fewer Fail examples, the model performs much better at identifying Pass students than Fail students.



The Fail class achieved:



Precision: 50%

Recall: 27%

F1 Score: 35%



Therefore, although the overall accuracy is 88.46%, the model has difficulty identifying students who are actually at risk of failing.



The model should therefore not be used as the sole basis for important academic decisions.



11\. Possible Improvements



Future improvements could include:



Using a larger and more balanced dataset

Applying class-weighting techniques

Applying oversampling or undersampling

Hyperparameter tuning

Comparing the Neural Network with Decision Tree, Random Forest, and Logistic Regression

Using additional academic and behavioural features

Applying explainable AI techniques

Testing the model on data from a different institution

12\. Community Application



This application can potentially help educational institutions identify students who may need additional academic support.



For example, the model could be used as an early-warning system to help teachers:



Identify students who may require additional support

Provide targeted academic assistance

Monitor students with frequent absences or previous failures

Encourage students to seek help before final examinations



The model should support teachers rather than replace human judgement.



13\. Technologies Used

Python

Pandas

NumPy

Scikit-learn

TensorFlow

Keras

Matplotlib

Kaggle

Git

GitHub

14\. Project Structure

neural-network-student-performance/

│

├── notebook/

│   └── student\_performance\_neural\_network.ipynb

│

├── results/

│   ├── training\_accuracy.png

│   ├── training\_loss.png

│   └── confusion\_matrix.png

│

├── README.md

└── requirements.txt

15\. Conclusion



A Neural Network was successfully implemented to predict student Pass/Fail outcomes using structured student performance data.



The model achieved:



88.46% test accuracy

90.98% precision

96.52% recall

93.67% F1 score



The experiment demonstrates how Neural Networks can be applied to structured educational data for classification and potential early academic intervention.



However, the imbalance between Pass and Fail students limits the model's ability to correctly identify students who are at risk of failing.



16\. Dataset Source



Student Performance Dataset:



UCI Machine Learning Repository - Student Performance Dataset



The dataset was accessed through Kaggle for implementation and experimentation.

