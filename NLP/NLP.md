# I. Natural Language Processing
## 1. Preprocessing
- 자연어 학습을 위해 수집된 데이터에 대한 전처리 작업이 중요
- 토큰화(Tokenization)
  - sentence, word, chracter
  - stop words (내용전달에 의미없는 단어)
  - stemming, lemmatization
- Encoding(vectorization)
  - 정수 인코딩(Integer Encoding)
  - 원핫 인코딩(One-Hot Encoding)

## 2. Tokenization
- 수집한 말뭉치(corpus)를 토큰 단위로 나누는 작업
  - 토큰 단위 : 의미를 가지는 크기
- 일반적으로 형태소 단위의 토큰화 수행
  - 형태소 : 의미를 가지는 가장 작은 말의 단위
- 단어 토큰화 : 단어를 기준으로 나눔
- 문장 토큰화 : 토큰의 단위가 문장
- 한국어의 경우 조사와 띄어쓰기 등으로 영어보다 토큰화가 어려움

## 3. Encoding
- 정수 인코딩 : 단어를 고유한 정수로 매핑하는 방식(단어 각각에 고유한 정수를 인덱스로 부여)
- 원핫 인코딩 : 단어집합 크기의 벡터 차원으로 0, 1을 사용하여 표현하는 벡터

## 4. Language Model
- 언어(단어, 문장)에 존재하는 특징을 표현하기 위해 확률을 할당하는 것
- 문장이 적절한지, 말이 되는지 판단하기 위한 기준