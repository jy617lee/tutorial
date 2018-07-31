## ROC 커브

#### 1. 민감도와 특이도

- 민감도(TPR : True Positive Rate) 
  - True인 케이스를 True로 예측한 비율
  - 예 : 암 환자를 진찰해서 암이라고 진단
- FPR (False Positive Rate)
  - False인 케이스를 True로 예측한 비율
  - 암환자가 아닌데 암이라고 진단.
- 특이도
  - False인 케이스를 False로 예측한 비율
  - 1 - FRR
  - 예 : 암환자가 아닌데 암이 아니라고 진단
- 특이도와 민감도는 반비례적인 관계가 있음. 성급한 의사의 경우, 약간의 징후만으로도 암으로 진단하기 때문에 특이도가 높다. 하지만 암이 아닌 경우에도 암이라고 하기 때문에 특이도는 낮다. 반대로 돌팔이 의사의 경우, 모든 환자를 암이 아니라고 하기 때문에 특이도가 높지만, 암 환자를 알아보지 못하기 때문에 민감도가 낮아진다. 
- 분석하려는 케이스에 따라 민감도와 특이도 중 어느 쪽에 강조를 둘지를 정할 수 있다. 
  - 확률은 낮지만 치사율이 극히 높은 병 : 민감도가 높아야 함. 
  - 감기처럼 확률은 낮지만 위험성이 별로 없는 병 : 민감도가 낮아도 됨. 

#### 2. ROC 커브

- 민감도와 특이도의 관계를 그래프로 표현하여 어느 지점을 기준으로 잡을 지 결정하기 쉽도록 시각화 한 것
- ![262E8E3F544837AD27](https://github.com/dataitgirls2/tutorial/262E8E3F544837AD27.png)
- X축 : 특이도
- Y축 : 민감도
- ROC 커브의 면적이 1에 가까울 수록(=왼쪽 위 꼭지점에 다가갈 수록) 좋은 성능이며, 면적은 0.5~1의 범위를 갖는다. 

참고 : http://newsight.tistory.com/53



## Lemmatizing

- 정의 : 앞/뒤 문맥을 보고 단어의 의미를 식별하는 것

- 예시 : 세 가지 배를 구분하는 것. 

  - `배`가 맛있다
  - `배`가 아프다
  - `배`를 타러가자

- 코드

  ```python
  from nltk.stem import WordNetLemmatizer
  wordnet_lemmatizer = WordNetLemmatizer()
  
  print(wordnet_lemmatizer.lemmatize('fly'))
  print(wordnet_lemmatizer.lemmatize('flies'))
  ```

  > fly
  >
  > fly