# APS_alpha
해당 프로젝트는 kaggle 데이터를 사용했습니다.

https://www.kaggle.com/c/bosch-production-line-performance

train dataset은 train_date, train_category, train_numeric 세개로 이루어져 있습니다.
해당 contest의 목적은 불량여부(Response)를 예측하는 것이지만
dataset을 변형해서 어떤 station을 거치고 해당 station의 feature값이 어떠한지에 따라서 제품의 capacity를 예측하는 분석을 진행했습니다.


--------------------------
### train_date
```
해당 station에서 공정과정을 거쳐갔는지의 여부와 해당공정에서 찍힌 timestamp들을 데이터로 가지고 있다. 단위는 0.01 == 6분 이다.
0.01 == 6분을 추론하는 과정은 https://www.kaggle.com/gaborfodor/notebookd19d11e4f2 에 나와있습니다.
```

### train_category
```
명목형 변수로 되어있는 feature들이 모여있는 dataset입니다.
```

### train_numeric
```
연속형 변수로 되어있는 feature들이 모여있는 dataset입니다.
```
