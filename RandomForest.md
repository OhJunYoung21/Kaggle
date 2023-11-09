# RandomForest란 무엇인가?

RandomForest란, 특정 데이터가 주어졌을 떄, 해당 데이터가 우리가 원하는 범주에 포함되는지를 예측하는 분류기 모델이다.

코드는 아래와 같다.(Kaggle의 Titanic Survival Competition에서 발췌)

~~~
from sklearn.ensemble import RandomForestClassifier

y = train_data["Survived"]

features = ["Pclass", "Sex", "SibSp", "Parch"]
X = pd.get_dummies(train_data[features])
X_test = pd.get_dummies(test_data[features])

//model을 선언해준다.

model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
model.fit(X, y)
predictions = model.predict(X_test)

output = pd.DataFrame({'PassengerId': test_data.PassengerId, 'Survived': predictions})
output.to_csv('submission.csv', index=False)

print("Your submission was successfully saved!")
~~~

RandomForest의 매개변수들
n_estimators,max_depth,random_state들을 알아보자.
~~~
model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
~~~

n_estimator는 결정트리의 개수를, max_depth는 각 트리의 깊이를 나타낸다. max_depth가 너무 깊게 설정되면 overfitting의 위험이 있으니 주의해야 한다.

### Overfitting이란?

모델이 특정 데이터만 지나치게 수행을 잘 해내는 경우를 말한다. 비유하자면 한 학생이 수능공부를 한다. 목표는 11.16일에 수능을 잘 치는 것이다. 그러나, 사설 모의고사만 많이 푼 탓에 사설모의고사에 익숙해져버려서 수능을 망하고 말았다. 위 학생을 모델이라고 하면, 위 모델은 사설모의고사에 과적합(Over Fitting)된 것이다.

### 모델을 훈련시켜보자.

~~~
features = ["Pclass", "Sex", "SibSp", "Parch"]
X = pd.get_dummies(train_data[features])
X_test = pd.get_dummies(test_data[features])

model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
model.fit(X, y)
~~~

model.fit(X,y)를 통해서 모델을 훈련시킨다. 100개의 트리를 사용해서 모델을 학습시킨다. 한명의 데이터를 100개의 트리가 학습하며, 해당 데이터가 survived면 해당 데이터의 특징을 모델은 기억한다.

이렇게 학습된 모델의 성능은 test_Data를 써서 확인한다.

~~~
prediction = model.predict(X_test)
~~~



