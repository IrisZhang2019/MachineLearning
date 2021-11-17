##### Regression
* logistic regression: sigmoid
* l1 vs l2 regulation:  

l1: min((y - yhat)**2) + lambda * sum(|w_i|)  
l2: min((y - yhat)**2) + lambda * sum(w_i**2)

l1: 会将没用的特征weight逐渐减少到0，筛选变量，sparse solution. 可能有不是唯一解. 对异常值不是很敏感
l2: 减少但是不致于到0，导数计算方便，对outlier不够鲁棒

##### DT
* ID3, C4.5, CART?
* adaboost? gbdt? xgb?

##### Confusion Matrix
TBA

##### T-test, Z-test
1. 是否总体方差已知？ Y: Z-test  N: 2
2. 是否是大样本？ Y: Z-test  N: T-test

