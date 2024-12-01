# Political Affiliation Classification with Keras

This project uses a neural network model to predict the political affiliation (Democrat or Republican) of U.S. House of Representatives members based on their voting records. The dataset is preprocessed, and a deep learning model is built and trained using Keras to achieve high prediction accuracy.

**Project Overview**

*Dataset*
The dataset house-votes-84.data.txt contains voting records for 16 key issues.
Features:
16 binary features representing votes: y (yes) and n (no).
A target label party:
Democrat (1).
Republican (0).
Missing values (?) are handled by dropping records with missing data.

**Workflow** 
1. **Data Loading and Preprocessing**
- Libraries: pandas, tensorflow, scikit-learn.
- Steps:
  1. Load the dataset using pandas.
  2. Replace missing values (?) with NaN and drop rows containing them.
  3. Encode categorical values:
     - party: Democrat = 1, Republican = 0.
     - Voting records: y = 1, n = 0.
  4. Separate features and labels:
     - Features: Voting records (16 issues).
     - Labels: Political affiliation.
2. **Model Design**
- Built using Keras Sequential API.
- Architecture:
  - Input layer: 16 neurons (one for each voting feature).
  - Hidden layers:
      - Dense layer with 64 neurons, ReLU activation.
      - Dense layer with 32 neurons, ReLU activation.
      - Dropout layer (30%).
      - Dense layer with 16 neurons, ReLU activation.
      - Dropout layer (50%).
  - Output layer:
      - Dense layer with 1 neuron, Sigmoid activation (binary classification).
 - Compilation:
  - Loss function: binary_crossentropy.
  - Optimizer: Adam.
  - Metric: accuracy.
3. **Model Training and Evaluation**
- Cross-validation:
  - 10-fold cross-validation using scikit-learn's cross_val_score.
  - Wrapper: KerasClassifier from scikeras.
- Average cross-validation accuracy achieved: 95.25%.
