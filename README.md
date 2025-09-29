📂 Project Overview

This project explores Decision Tree Classifiers and Random Forests on the Heart Disease dataset. We train, evaluate, and interpret the models while addressing overfitting and model generalization using cross-validation.

⚙️ Steps Performed
1. Load and Preprocess Data

Dataset: heart.csv (commonly used heart disease dataset).
Split into features (X) and target (y).
Standardization or scaling applied to features when necessary.
Train-test split (80/20).

2. Decision Tree Classifier

Trained using sklearn.tree.DecisionTreeClassifier.
Initial model fitted with limited depth (max_depth=4) for readability.
Problem: Decision Trees can overfit by growing too deep and memorizing training data.

3. Visualizing the Tree

Used Graphviz and export_graphviz to visualize the structure.
Alternative: plot_tree() from scikit-learn (works inline in Jupyter).

4. Overfitting & Controlling Tree Depth

Overfitting occurs when tree depth is too high (training accuracy = 100%, test accuracy drops).
Controlled using hyperparameters:
max_depth: maximum levels of the tree.
min_samples_split: minimum samples required to split a node.
min_samples_leaf: minimum samples required at a leaf node.
ccp_alpha: cost-complexity pruning to remove unnecessary branches.
Plotted train vs test accuracy against tree depth → helps find the “sweet spot.”

5. Random Forest Classifier

Trained using sklearn.ensemble.RandomForestClassifier.
Combines multiple decision trees (bagging + randomness).
Advantages over single tree:
Reduces overfitting.
Improves accuracy and stability.

6. Feature Importances

Random Forest provides feature importance scores.
Helps interpret which health factors (e.g., age, cholesterol, thalach) influence predictions the most.
Visualized via bar plot of feature importances.

7. Evaluation Metrics

Accuracy: Correct predictions / total predictions.
Classification Report: Precision, Recall, F1-score.
Cross-validation:
Used cross_val_score with cv=5.
Provides more reliable performance estimates.
Compared Decision Tree vs Random Forest.

📊 Results & Insights

Decision Tree → simple, interpretable, but prone to overfitting.
Random Forest → more robust, generalizes better, and usually achieves higher accuracy.
Feature Importances → highlighted key predictors of heart disease.
Cross-validation → reduced variance in evaluation and confirmed Random Forest’s consistency.
