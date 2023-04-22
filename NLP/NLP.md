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

### Tokenization
- 수집한 말뭉치(corpus)를 토큰 단위로 나누는 작업
  - 토큰 단위 : 의미를 가지는 크기
- 일반적으로 형태소 단위의 토큰화 수행
  - 형태소 : 의미를 가지는 가장 작은 말의 단위
- 단어 토큰화 : 단어를 기준으로 나눔
- 문장 토큰화 : 토큰의 단위가 문장
- 한국어의 경우 조사와 띄어쓰기 등으로 영어보다 토큰화가 어려움

### Encoding
- 정수 인코딩 : 단어를 고유한 정수로 매핑하는 방식(단어 각각에 고유한 정수를 인덱스로 부여)
- 원핫 인코딩 : 단어집합 크기의 벡터 차원으로 0, 1을 사용하여 표현하는 벡터

## 2. Language Model
- 언어(단어, 문장)에 존재하는 특징을 표현하기 위해 확률을 할당하는 것
- 문장이 적절한지, 말이 되는지 판단하기 위한 기준
  - P(승객이 버스에 탔다) vs P(승객이 버스에 태운다)
  - 나는 딥러닝을 ~P(배운다) vs P(어렵다) vs P(고친다) vs P(가르친다)
- Bag of Words
- n-gram
- TF_IDF

### Bag of Words
- 문장이 가지는 모든 단어를 문맥이나 순서를 무시하고 일괄적으로 빈도값을 부여해 특징을 추출
- 발생 빈도가 높을수록 중요한 단어로 인식
- 장점
  - 쉽고 빠른 구축
  - 예상보다 문장의 특징을 잘 반영함
- 단점
  - 언어의 특성상 자주 등장하는 단어에 높은 중요도를 부여
  - 단어의 순서를 고려하지 않아 문맥의미 반영 부족
  - 희소행렬(sparse metrix)을 생성하여 학습시간 및 성능에 부정적 영향
- BoW - Feature Vectorization
  - M * N 크기의 행렬(term-document matrix) 생성
  - M개의 문장이나 문서
  - N 종류의 단어

### n-gram
> N개의 단어를 활용하여 다음에 올 단어를 추출한다
- 1-gram(unigram), 2-gram(bigram), 3-gram(trigram)
- 단어 순서를 무시하는 BoW의 단점을 보완
- 문장 내 전체 단어를 고려하는 언어모델과 비교해 정확도가 낮음
- trade-off : N이 너무 작으면 문장 맥락 파악이 어렵고, 너무 크면 카운팅할 확률이 낮아 희소성 문제 대두

### TF-IDF(Term Frequency - Inverse Document Frequency)
> 단어마다 중요도를 고려하여 가중치를 준다
- TF(단어 출현빈도) * IDF(역 문서 빈도) = TF-IDF 가중치

## 3. Simularity

### Euclidean Distance Similarity

### Cosine Similarity

## 4. Embedding

## 5. Word2vec