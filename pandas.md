# PANDAS
## 시작하기
```python
import pandas as pd
pd.__version__
```
## 파일 불러오기
```python
df = pd.read_csv('file.csv')
# 파일에 저장된 데이터 읽어오기
# txt파일의 경우 특정 구분자로 구분된 데이터는 sep인자에 명시하여 불러올 수 있음
# tap으로 구분시 : sep = '\t'
df = pd.read_csv('file.csv', encoding='cp949')
# 한글파일 인코딩 에러 시
df = pd.read_csv('file.csv', dtype = ({'column' : 'str'}))
# 불러오면서 특정 칼럼의 type 변경 가능
```
```python
df = pd.read_excel('file.xlsx')
# 엑셀파일 불러오기
df = pd.read_excel('file.xlsx', sheet_name = 0)
# 시트순번을 입력해 특정 시트만 불러올 수 있음
df = pd.read_excel('file.xlsx', sheet_name = 'first_sheet')
# 시트명을 입력해 특정 시트만 불러올 수 있음
```
```python
df.head(n)
# 첫 n개 row를 출력한다. n 미입력시 5개 출력
df.tail(n)
# 마지막 n개 row를 출력한다. n 미입력시 5개 출력
df.len()
# 데이터프레임에 사용하면 row개수를 반환
```
## 데이터프레임 생성
```python
df = pd.DataFrame({'carat' : [1, 11]. 'depth' : [60, 61]}, index = ['a','b'])
# 컬럼명 : 'carat', 'depth'
# row 인덱스 : 'a', 'b'
# row 인덱스명 생략 가능
df = df[0:1]
# 0행만 슬라이싱해서 df생성
dic = df.to_dict()
# 데이터프레임 딕셔너리로 만들기
# 값 입력 쉽게하기 위해
df = pd.DataFrame(dic)
# 딕셔너리를 다시 데이터프레임으로 만들기
```
## 기초
### 함수 및 메서드
```python
df['cut'].min()  # 최소값
df['cut'].max()  # 최대값
df['cut'].mean()  # 평균값
df['cut'].var()  # 분산
df['cut'].std()  # 표준편차
df['cut'].skew()  # 왜도(분포의 비대칭도)
df['cut'].kurt()  # 첨도(정규분포 기준 뾰족한 정도)
df['cut'].idxmin()  # 최소값의 위치
df['cut'].idxmax()  # 최대값의 위치
df['cut'].count()  # 개체 수
df['cut'].quantile(q = 0.25)  # 1사분위수
```
### 속성(attribute)
```python
df.ndim  # 객체의 차원
df.shape  # 각 차원의 길이(N * N)
df.dtypes  # 전 컬럼의 dtype
df.columns  # 컬럼명
pd.Series(df.columns)  # 컬럼명에 인덱스 붙이기(0, 1, 2)
df.info()  # 데이터타입, 결측치 등의 정보
df.describe()  # 각종통계량 정보(브라이틱스 stastics summary)
```
### astype
```python
df.astype(str)
# df내 타입을 전부 str로 변경
df.astype({'col1' : 'int32', 'col2' : 'int64'})
# 특정 컬럼만 변경
df = pd.read_csv('3.csv', dtype = ({'jumin7' : 'str'}))
# 파일 데이터를 불러올 때 데이터타입 변경 가능
```
### value_counts
```python
df['col1'].value_counts()
# 데이터들의 빈도 출력
df['col1'].value.counts(dropna = False)
# NaN값의 개수도 같이 출력, True가 default
```
### nunique
```python
df = df['col1'].nunique().reset_index()
# 컬럼 내 몇개의 고유값이 있는지 파악
```
## 데이터 변환
### 결측치
```python
df.isna(), df.isnull()
# 결측값 확인
df.notna(), df.notnull()
# 결측 아닌 값 확인
df.isna().sum()
# 결측치 갯수(column)
df.isna().sum(axis=1)
# 결측치 개수(row) 
```
```python
df.dropna()
# 결측치 제거
df.dropna(how = 'any')
# 한 값이라도 결측치가 있는 레이블을 삭제, default
df.dropna(how = 'all')
# 모든 값이 결측치인 레이블만 삭제
df.dropna(subset = ['col1','col2','col3'])
# 3개 변수에 대해 결측치삭제
```
```python
df.filna({'행정구역':'서울','국가':'대한민국'})
# 결측치를 해당값으로 채움
df.filna({'확진자' : df['확진자'].mean()})
# 결측치를 평균값으로 채움
```
```python
# 결측치 채운 값을 원본에 적용하기
df.filna({'행정구역' : '서울', '국가' : '대한민국', '확진자' : df['확진자'].mean()}, inplace=True)
df['Cabin'] = df['Cabin'].filna('C000')
df['Age'] = df['Age'].filna(df['Age'].mean())
```
```python
df = df.drop(columns = ['A', 'C'])
# 컬럼 별로 drop
df = df.drop(['A', 'C'], axis = 1)
# axis = 1을 이용해 컬럼별로 drop가능
df = df.drop(index = [1, 4, 5])
```




```python
```
```python
```
```python
```
```python
```
```python
```
```python
```
```python
```
```python
```
```python
```
```python
```