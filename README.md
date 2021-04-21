# Kaggle_training
해당 프로젝트는 kaggle 데이터를 사용했습니다.

https://www.kaggle.com/c/bosch-production-line-performance

train dataset은 train_date, train_category, train_numeric 세개로 이루어져 있습니다.
해당 contest의 목적은 불량여부(Response)를 예측하는 것이지만
dataset을 변형해서 어떤 station을 거치고 해당 station의 feature값이 어떠한지에 따라서 제품의 capacity를 예측하는 분석을 진행했습니다.


--------------------------
### train_date

해당 station에서 공정과정을 거쳐갔는지의 여부와 해당공정에서 찍힌 timestamp들을 데이터로 가지고 있다. 단위는 0.01 == 6분 이다.
0.01 == 6분을 추론하는 과정은 https://www.kaggle.com/gaborfodor/notebookd19d11e4f2 에 나와있습니다.


### train_category

명목형 변수로 되어있는 feature들이 모여있는 dataset입니다.


### train_numeric

연속형 변수로 되어있는 feature들이 모여있는 dataset입니다.


## main

각각의 Id별로 timestamp의 가장 큰값(max)와 가장 작은값(min)을 차이를 구해서 해당Id의 제품이 하나만들어 지는데 걸리는 시간이라고 가정했습니다. 그리고 0.01 == 6분이라는 뜻은 30일 == 72이기 때문에 72를 해당값으로 나누어서 capacity를 구한뒤 column으로 추가해줬습니다. 


해당 변수들을 모두포함해서 모델에 돌리기에는 결측값이 너무 많기 때문에 동일한 공정 path를 지닌 제품끼리 모델을 구성하였습니다. 해당코드에서는 10000개의 rows를 받았을 때, 가장 수가 많은 unique_path를 골라서 실험을 진행했습니다. 모델은 ols 선형회귀를 사용하였습니다.

