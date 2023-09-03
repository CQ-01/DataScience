# R
> 통계분석에 특화된 언어

## I. 기본 문법
### 1. 변수
```R
a <- 1
# a = 1도 같음
a
>>
1
```

### 2. 논리
```R
a == 1
>> TRUE

a != 1
>> FALSE
```

### 3. Vector
```R
a = c(1, 2, 3, 4, 5)
a
>> [1, 2, 3, 4, 5]


b = c(1, 2, 3, '4', '5')
b
>> ['1', '2', '3', '4', '5']


c = c(1:5)
c
>> [1, 2, 3, 4, 5]


d = seq(1, 10, 2)
d
>> [1, 3, 5, 7, 9]


e = rep(1, 5)
e
>> [1, 1, 1, 1, 1]
```

### 4. 조건문
```R
if (조건식) {
    조건식이 참일때 실행문
} else {
    조건문이 거짓일때 실행문
}
# 조건문에 &(and), |(or) 추가사용 가능
```

### 5. 반복문
```R
for (i in 1:5) {
    print('*')
}

while (i > 100) {
    sum = sum + i
    i = i + 1
}
```

### 6. 인덱싱
- vector에서
    ```R
    a = c(1, 2, 3, 4, 5)

    a[2]
    >> [2]
    # 인덱스 값이 1부터 시작!

    a[1:2]
    >> [1, 2]
    # [1:N]을 인덱싱할때 N-1번째 까지가 아닌 N번째까지 인덱싱!

    a[-3]
    >> [1, 2, 4, 5]
    # 음수가 붙으면 오른쪽부터 세는 것이 아닌 해당 숫자의 인덱스값 제외!

    a[c(1, 2, 4, 5)]
    >> [1, 2, 4, 5]
    # 여러개 인덱싱 가능
    ```
- 데이터프레임에서
    ```R
    DATA_FRAME[1,]
    # 1행 전부

    DATA_FRAME[,1]
    # 1열 전부

    DATA_FRAME[c(1, 2, 3), -2]
    # 1, 2, 3행 & 2열 제외
    # 여러 행/열 지정 가능, 특정 행/열 제외 가능
    ```
### 7. 기타 함수
- `as` : 
    ```R
    # 데이터타입 변경
    x1 = as.integer(x)
    x2 = as.numeric(x)
    x3 = as.factor(x)
    x4 = as.character(x)
    ```
- `summary(x)` : 요약값 제공, 데이터타입마다 다른 요약값
- `is`:
    ```R
    is.integer(x)
    is.numeric(x)
    is.factor(x)
    is.character(x)
    >> TRUE or FALSE
    ```
- sample
    ```R
    sample(1:45, 6, replace = FALSE)
    # 1 ~ 45 중 6개를, 비복원추출
    ```
- fumction
```R
Plus_One = function(x) {
    y = x + 1
    return(y)
}
Plus_One(3)
>> 4
```
## II. 데이터 전처리
### 1. 데이터 불러오기
- 작업경로 확인
    ```R
    getwd()
    # 현재 경로 확인

    setwd('이동하려는 경로')
    # 특정 경로로 이동하기
    ```

- 데이터 불러오기
    ```R
    HR = read.csv('HR_comma_sep.csv')
    # csv파일 불러오기

    read.delim
    # txt파일 불러오기
    ```
- 데이터 파악하기
    ```R
    head(HR)
    # 데이터 윗부분 확인

    str(HR)
    # 데이터 strings 파악

    summary(HR)
    # 요약된 데이터 확인
    ```
- 데이터 타입 변경
    ```R
    summary(HR$left)

    HR$Work_accident=as.factor(HR$Work_accident)
    HR$left=as.factor(HR$left)
    HR$promotion_last_5years=as.factor(HR$promotion_last_5years)
    
    summary(HR$left)
    ```