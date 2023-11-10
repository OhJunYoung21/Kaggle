# DecisionTreeRegressor(회귀모델)

위 모델은 Sklearn.tree에서 제공하는 회귀모델이다. 인공지능의 모델은 학습초기에는 두 분류로 나눌 수가 있다. 분류와 예측이다.

분류에는 SVM,k-clustering등을 활용하는 모델등이 있다. 분류는 내가 선택한 데이터가 어떤 범주에 속하는지를 알아내는 모델이다.

가령, 내가 고른 상품 할인 상품에 속할지, 아닐지 등을 구별하는 것또한 분류에 속한다. Kaggle에서 유명한 Titanic 예제 또한 분류에 속한다고 볼 수 있다. 

회귀 모델이란, y = ax + b와 같이 a,b상수를 조절해서 알맞은 답을 내놓는 것을 말한다. 즉, x = input data가 되는것이고, a와 b를 조절해서 output_data,즉, y를 예측하는 것이다.

코드로 살펴보자.

먼저, Sklearn.tree에서 DecisionTreeRegessor를 가져온다.

~~~
from sklearn.tree import DecisionTreeRegressor

melbourne_model = DecisionTreeRegressor(random_state=1)

melbourne_model.fit(X, y)
~~~

# Random State란 무엇인가?

DecistionTreeRegressor를 보면 매개변수로 random_State를 갖는다. 이는 모델이 데이터를 학습 할때, 매번 무작위로 데이터를 골라서 학습하는 것을 방지하는 것이다. 머신러닝의 모델학습과정에는 데이터를 섞는 Shuffling과정이 포함되기도 한다.

만일 random_state가 none이라면 매번 실행때마다 서로 다른 결과값이 도출되어 해당 모델은 신빙성을 잃게 된다.

random_state는 쉽게 말하자면, 규칙이다. 위 모델이 어떤 방식으로 데이터를 학습할 것인지에 대한 규칙인 것이다. random_state안에 들어가는 숫자는 크게 의미가 없다. 사람이 보기에는 random_state가 1 인 경우와 100인 경우가 차이가 커보이지만

컴퓨터 입장에서는 1과100은 하나의 규칙을 상징할 뿐, 숫자의 크기에는 영향을 크게 받지 않는다.

다시 말하자면, random_state는 모델이 규칙성을 가지고 데이터를 선택하여 학습하게 하기 위한 장치이다. None으로 설정된다면 매번 결과가 달라지기 때문에 바람직하지 않다.(사실상 쓰레기 모델이나 마찬가지이다.)

