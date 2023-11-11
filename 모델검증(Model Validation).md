# Model Validation(모델 검증)

모델검증이란, 쉽게 말해서 이 모델이 다른 데이터를 넣었을 떄에도 실제 값(Actual Value)를 잘 예측하는지를 검증하는 것이다.

이때 우리는 새로운 데이터를 써서 위 모델을 평가해야 한다. 여기서 과적합의 개념이 조금 등장한다. 만약 모델이 특정 표본집단의 경우에만 예측을 잘한다면 그 모델이 좋은 모델이라고 할 수 있을까?

모집단에 해당 모델을 적용하면, 원하는 결과가 나오지 않을 수도 있다. 그래서 Python에서는 train_test_split()이라는 함수를 사용해서 훈련데이터와 검증데이터를 나눠준다.
~~~
from sklearn.model_selection import train_test_split

train_X, val_X, train_y, val_y = train_test_split(X,y,random_state=1)

step_1.check()
~~~


# MAE(Mean_Absolute_Error) 오차

오차를 판단하는 척도는 여러가지가 있다. 하지만 주로 평균을 사용하는 편이며,MSE,MAE...등등 여러가지가 있다. MAE는 실제데이터가 n개가 있을 떄, 실제 데이터와 예측 데이터를 뺀 값을 n번 더한후, n으로 나눠주는 것이다.

비교적 직관적으로 이해가능한 개념이며, 이를 사용하면 실제 오차가 얼마나 발생하는지 알수 있다.

다른 모델에서는 MSE를 사용하기도 하는데, 단순히 MAE에 루트를 씌운 것으로, 오차범위를 줄이기 위한 것이다.

~~~
from sklearn.metrics import mean_absolute_error
val_mae = mean_absolute_error(val_y,val_predictions)

#print(val_mae)

step_4.check()
~~~





