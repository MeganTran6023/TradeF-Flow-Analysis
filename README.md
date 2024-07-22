# Trade Flow Analysis

## 🌟 Highlights
- achieved an accuracy of 70% in the logistic regression model
- acquired coefficient values for each featue, allowing us to identify each of their influence on whether an option trade was a win/loss.

## ℹ️ Overview

Banks engage in options trading to mitigate the trisk asociated with their investments and make additional income. </br>

Using the dataset with stock trade information, I will attempt to apply machine learning to determine what feature(s) predict whether a contract from a trade was a win or loss. This could potentially allow me to aid financial/stock advisors in determining patterns for maximum monetary gain from options trading.

## 🚀 Usage

a) Requirements

python 3.X (I used Python 3.10.9)

b) Data preprocessing

* changed values to integer for columns Prems and OI
* One-hot encoding for column "C/P"
* got even split (2500:2500) of classes (win:loss)

c) Logistic Regression

* standardize all columns with continuous values
* Target variable = "ITM"

splitting conditions: </br>
```X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=0, shuffle=True)```

Results: </br>

1) Accuracy

```
              precision    recall  f1-score   support

           0       0.76      0.56      0.64       481
           1       0.67      0.84      0.75       519

    accuracy                           0.70      1000
   macro avg       0.72      0.70      0.70      1000
weighted avg       0.72      0.70      0.70      1000

Accuracy of logistic regression classifier on test set: 0.70

```

2) ROC AUC Curve

The dotted line is the ROC curve of a perfect classifier where the ratio between TPR and FPR is 1. We want a higher TPR relative to FPR. In other words, it's better when the blue curve is far away from the red line as possible.</br>
![image](https://github.com/user-attachments/assets/961c43bc-412f-4b97-8bde-e74d147cab8d)

3) Coefficients of features

Allows me to see the magnitude and direction of an effect a feature has on whether a trade was a win or loss.

```
The coefficient for Time is -4.2185484640257904e-06
The coefficient for Sym is -0.00015272399789444073
The coefficient for C/P is 0.2655289620896227
The coefficient for Exp is 0.12588852801760145
The coefficient for Strike is -0.045663673733153304
The coefficient for Spot is -0.0025129062576181383
The coefficient for BidAsk is -0.04750065005626259
The coefficient for Orders is 0.030872909781244177
The coefficient for Vol is -0.04833541530262957
The coefficient for Prems is -0.017785924726748812
The coefficient for OI is 0.0007222215120531627
The coefficient for Diff(%) is -1.9356040386569222

```

## ⬇️ Installation

type 
```
pip install {package}
```

**packages:**

* pandas
* numpy
* matplotlib
* scikit-learn
* matplotlib

## 💭 Future Improvements

* apply hyperparameter tuning to logistic regression model for accurate output 

