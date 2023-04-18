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