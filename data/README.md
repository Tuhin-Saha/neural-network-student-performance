\# Dataset Information



\## Dataset Used



The project uses the \*\*Student Performance Data Set\*\* from the UCI Machine Learning Repository.



The dataset file used is:



`student-por.csv`



\## Dataset Details



\- Number of records: 649

\- Number of attributes: 33

\- Data type: Structured tabular data

\- Problem type: Supervised binary classification



\## Target Variable



A new target variable called `result` was created from the original `G3` final grade:



\- `G3 >= 10` → Pass (`1`)

\- `G3 < 10` → Fail (`0`)



\## Input Features



The neural network uses the following 10 features:



\- studytime

\- failures

\- absences

\- Medu

\- Fedu

\- goout

\- freetime

\- health

\- higher

\- internet



The features `G1` and `G2` were excluded because they are earlier-period grades and could cause target leakage for an early prediction application.



\## Train-Test Split



The dataset was divided using an 80:20 stratified train-test split.



\- Training samples: 519

\- Testing samples: 130



The test set was kept separate from model training and was used to evaluate the final model.



\## Testing Results



The final model was evaluated on the 130 unseen test samples.



\- Test Accuracy: 88.46%

\- Precision: 90.98%

\- Recall: 96.52%

\- F1 Score: 93.67%



\## Dataset Sources



UCI Machine Learning Repository:



https://archive.ics.uci.edu/dataset/320/student+performance



Kaggle:



https://www.kaggle.com/datasets/larsen0966/student-performance-data-set



The raw dataset is not included in this repository. It can be downloaded from the above sources.

