# RandomForest란 무엇인가?

RandomForest란, 특정 데이터가 주어졌을 떄, 해당 데이터가 우리가 원하는 범주에 포함되는지를 예측하는 분류기 모델이다.

코드는 아래와 같다.(Kaggle의 Titanic Survival Competition에서 발췌)

~~~
from sklearn.ensemble import RandomForestClassifier

y = train_data["Survived"]

features = ["Pclass", "Sex", "SibSp", "Parch"]
X = pd.get_dummies(train_data[features])
X_test = pd.get_dummies(test_data[features])

model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
model.fit(X, y)
predictions = model.predict(X_test)

output = pd.DataFrame({'PassengerId': test_data.PassengerId, 'Survived': predictions})
output.to_csv('submission.csv', index=False)

print("Your submission was successfully saved!")
~~~


