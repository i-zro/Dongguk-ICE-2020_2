![](2020-09-02-15-35-03.png)

## 모델 성능 평가 이유

: 현재 상태를 알고, 언제까지 발전시킬지 알기 위해

### convex

볼록 함수

# 수학적인거 각자 정리

# 20-09-07 (2)

### cmd 창에서 python 빠져나오기

`ctrl+z`

# numpy

다차원 배열 데이터를 효과적으로 처리해 줌

---

```python
a = np.array([1, 2, 3])
type(a)
```

```
numpy.ndarray
```

---

```python
a
```

```
array([1, 2, 3])
```

---

```python
a.shape
```

```
(3,)
```

- 숫자가 1개 = a가 3개의 column 가진 1차원 배열 이라는 뜻

---

```python
c = np.array([[1,2,3],[4,5,6]])
c
```

```
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])
```

---

```python
c.shape
```

```
(3, 3)
```

- `숫자가 2개` = c가 3개의 row와 3개의 column을 가진 2차원 배열이라는 뜻

### 다차원 배열에 숫자 채우기

```python
np.ones((3,4), dtype=np.int16)
```

```
array([[0., 0., 0., 0.],
       [0., 0., 0., 0.],
       [0., 0., 0., 0.]])
```

- np.ones : 1 다차원 배열 만들기

```python
np.zeros((3,4))
```

```
array([[0., 0., 0., 0.],
       [0., 0., 0., 0.],
       [0., 0., 0., 0.]])
```

- np.zeros : 0 다차원 배열 만들기

```python
np.full((3, 4), 0.11) # 0.11로 채우기
```

```
array([[0.11, 0.11, 0.11, 0.11],
       [0.11, 0.11, 0.11, 0.11],
       [0.11, 0.11, 0.11, 0.11]])
```

- np.full : 원하는 숫자로 다차원 배열 만들기

## 간격 정해서 배열 만들기

- arange(시작점, 종료점, 간격)
- 간격을 적지 않으면 기본적으로 1씩 증가

```python
np.arange(10, 30) # 종료점 = 종료점 - 1
```

```
array([10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26,
       27, 28, 29])
```

- linspace(시작점, 종료점, ...)
  - num = 개수 : 출력 원하는 개수 출력
  - endpoint = True : 종료점도 포함
  - retstep = True : 간격도 출력

```python
a = np.linspace(0, 10, num=5, endpoint=True, retstep=True)
b = np.linspace(1, 10, num=5, endpoint=True, retstep=False)
c = np.linspace(0, 10, num=5, endpoint=False, retstep=False)

print("a:", a)
print("b:", b)
print("c:", c)
```

```
a: (array([ 0. ,  2.5,  5. ,  7.5, 10. ]), 2.5)
b: [ 1.    3.25  5.5   7.75 10.  ]
c: [0. 2. 4. 6. 8.]
```

## 랜덤 배열 만들기

```python
np.random.rand(2, 3)
```

```
array([[0.10684162, 0.28064948, 0.55768774],
       [0.46908127, 0.19500359, 0.26814137]])
```

## empty

shape를 만들어주고 메모리 상 가까운 값을 가지고 오고, 메모리에 어떤 값이 없다면 0에 가까운 값을 가져온다
예를들어, np.empty((2,3))을 위의 랜덤 배열을 만든 후 바로 만들면

```
array([[0.10684162, 0.28064948, 0.55768774],
       [0.46908127, 0.19500359, 0.26814137]])
```

출력

#### dim

차원 수

#### size

배열 원소의 총 개수

#### itemsize

바이트 값 반환

### reshape(row, col)

배열의 차원의 크기 변경

### 배열 거꾸로 뒤집기

[::-1]

## array와 다르게 ndarray는 배열 요소 한꺼번에 변경 가능

```python
a = np.array([1, 2, 5, 7, 8])
a[1:3] = -1
a
```

```
array([ 1, -1, -1,  7,  8])
```

## 리스트 복사

```python
a = np.array([1, 2, 5, 7, 8])
a_slice = a[1:5].copy() #원래 값이 같이 안바뀌어지도록 copy 사용하기!
```

## boolean indexing

```python
a = np.arange(12).reshape(3, 4)
rows_on = np.array([True, False, True])
a[rows_on, 1]  #a[행, 열]
```

```
array([1, 9])
```

## 연립 방정식 풀기

```
2x + 6y = 6
5x + 3y = -9
```

```python
coeffs  = np.array([[2, 6], [5, 3]]) # 계수
depvars = np.array([6, -9]) # 상수항
solution = np.linalg.solve(coeffs, depvars)
solution
```

```
array([-3.,  2.])
```

# pandas

### 딕셔너리로 Data Frame 만들기

```python
people_dict = { "weight": pd.Series([68, 83, 112], index=["alice", "bob", "charles"]),  #Series : 값과 함께 index지정이 가능
#자동 매핑 느낌
               "birthyear": pd.Series([1984, 1985, 1992], index=["bob", "alice", "charles"], name="year"), #name 은 series의 이름을 말함
               "children": pd.Series([0, 3], index=["charles", "bob"]),
               "hobby": pd.Series(["Biking", "Dancing"], index=["alice", "bob"]),}


import pandas as pd

people = pd.DataFrame(people_dict) # 딕셔너리를 표로 만들어주기
people
```

```
       weight	birthyear	children	hobby
alice	   68	    1985	NaN	       Biking
bob	   83	    1984	3.0	       Dancing
charles	   112	    1992	0.0	       NaN
```

### 조건 추출

```python
people[people["birthyear"] < 1990]
```

```
	       weight	birthyear	children	hobby
alice	       68	1985	       NaN	    Biking
bob	       83	1984	       3.0	    Dancing
```

# matplotlib

```python
import matplotlib.pyplot as plt
```
