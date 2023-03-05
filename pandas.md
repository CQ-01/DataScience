# PANDAS
## 시작하기
```python
import pandas as pd
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
df['']
```