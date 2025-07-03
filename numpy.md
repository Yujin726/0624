# 📌 NumPy 전체 학습 목차

- [📘 NumPy 기초 정리](#-numpy-기초-정리)
  - [1. NumPy란?](#1-numpynd)
  - [2. NumPy는 언제 사용하나요?](#2-numpy는-언제-사용하나요)
  - [3. NumPy를 쓰기 위해 필요한 준비물](#3-numpy를-쓰기-위해-필요한-준비물)
  - [4. NumPy에서 꼭 알아야 하는 기본 요소들](#4-numpy에서-꼭-알아야-하는-기본-요소들)
  - [5. NumPy 공부 전에 알면 좋은 기초 지식](#5-numpy-공부-전에-알면-좋은-기초-지식)
  - [6. 자율주행과 NumPy는 어떤 관련이 있나요?](#6-자율주행과-numpy는-어떤-관련이-있나요)

- [📘 w3schools NumPy 튜토리얼](#-w3schools-numpy-튜토리얼)
  - [✅ NumPy 학습 목차](#-numpy-학습-목차)

# 📘 NumPy 기초 정리

## 1. NumPy란?

NumPy는 Numerical Python의 줄임말입니다.  
**수치 계산을 빠르게 처리할 수 있도록 도와주는 파이썬 라이브러리**입니다.

### ✔ NumPy의 특징
- 대규모 숫자 데이터를 빠르게 처리
- 리스트보다 빠르고 효율적인 연산
- 수학, 통계, 과학, 인공지능에서 자주 사용

---

## 2. NumPy는 언제 사용하나요?

| 사용 상황 | 설명 |
|-----------|------|
| 수학 연산 | 벡터, 행렬 계산, 제곱, 평균 등 |
| 통계 분석 | 평균, 분산, 표준편차 계산 |
| 데이터 분석 | 대규모 데이터 처리 |
| 머신러닝 | 데이터 전처리, 수치 기반 연산 |
| 이미지 처리 | 이미지 = 숫자 배열로 구성됨 |

---

## 3. NumPy를 쓰기 위해 필요한 준비물  
✅ (1) Python 설치  
파이썬이 먼저 설치되어 있어야 해요.  
👉 이미 있다면 OK!

✅ (2) NumPy 설치  
터미널이나 명령 프롬프트(cmd)에 아래 명령어를 입력해서 설치해요:
👉 Google Colab을 쓰면 numpy가 이미 설치되어 있어서 따로 안 해도 돼요!

---

## 4. NumPy에서 꼭 알아야 하는 기본 요소들  
✅ (1) NumPy 불러오기  
NumPy를 사용하려면 항상 import 먼저 해요:
import numpy as np
```python 
import numpy as np
```
 👉 np는 별칭이에요. NumPy 함수들을 쉽게 쓰기 위해 보통 이렇게 불러와요.
 
✅ (2) 배열(Array)
NumPy의 핵심은 배열(넘파이 배열, numpy array) 이에요.
```
import numpy as np

a = np.array([1, 2, 3])
print(a)  # 출력: [1 2 3]
```

| 용어    | 설명                       |
| ----- | ------------------------ |
| 1D 배열 | \[1, 2, 3] — 리스트처럼 생김    |
| 2D 배열 | \[\[1, 2], \[3, 4]] — 행렬 |
| 3D 배열 | 이미지, 영상 등 고차원 데이터        |

---

## 5. NumPy 공부 전에 알면 좋은 기초 지식
| 개념         | 설명                                  |
| ---------- | ----------------------------------- |
| 리스트(List)  | 파이썬의 기본 자료구조. NumPy는 리스트를 확장한 개념이에요 |
| for문 / 반복문 | 배열을 다루는 데 자주 써요                     |
| 인덱싱 / 슬라이싱 | 배열의 특정 위치 데이터를 가져올 때 사용             |
| 수학 기초      | 덧셈, 곱셈, 제곱, 평균 등 기본 수학 개념           |
| 라이브러리 사용법  | import해서 외부 기능을 가져오는 법              |
  
---

## 6. 자율주행과 NumPy는 어떤 관련이 있나요?

자율주행 시스템은 다양한 센서와 알고리즘을 통해 주변 환경을 인식하고 판단하며 주행을 수행함. 이 과정에서 **수치 데이터를 빠르게 처리하는 능력**이 중요하며, NumPy는 이 역할에 최적화된 도구임.

---

### ✅ (1) 센서 데이터 처리

자율주행차에 사용되는 대표 센서:
- 라이다(LiDAR)
- 카메라
- 레이더
- GPS
- IMU(관성 측정 장치)

이 센서들은 모두 **숫자 배열 형태의 데이터**를 생성함. NumPy는 이러한 데이터를 빠르게 계산하고 분석하는 데 사용됨.
```import numpy as np
lidar_data = np.array([12.3, 8.7, 5.1, 20.0])
obstacles = lidar_data[lidar_data < 10]  # 10m 이내 장애물 필터링
print(obstacles)
```

### ✅ (2) 이미지 및 영상 처리
카메라 센서로부터 입력되는 이미지는 모두 픽셀 값으로 구성된 다차원 배열
NumPy를 활용하면 이미지 전처리, 색상 분석, 차선 탐지 등의 연산 가능
```import numpy as np
image = np.random.randint(0, 256, (720, 1280, 3))  # RGB 이미지
gray = np.mean(image, axis=2)  # 흑백 이미지 변환
```

### ✅ (3) 수학적 연산 (벡터, 행렬)
자율주행 알고리즘에서 자주 사용되는 수학 연산:
- 좌표 변환
- 경로 예측
- 제어 시스템 설계 (PID, 칼만 필터 등)
NumPy는 선형대수 기반의 계산을 빠르게 처리하는 데 최적화된 라이브러리임
```A = np.array([[1, 2], [3, 4]])
B = np.array([[2, 0], [1, 3]])
result = np.dot(A, B)  # 행렬 곱
```
### ✅ (4) 머신러닝, 딥러닝 연동
딥러닝 기반 자율주행 인공지능 학습 시 NumPy는 필수
- 데이터 전처리
- 정규화
- 배치 처리
TensorFlow, PyTorch에서도 내부적으로 NumPy와 유사한 연산 환경 사용

### ✅ (5) 실시간 판단 로직
차선 이탈, 전방 차량 거리 비교 등 실시간 조건 판단에 배열 연산 필수
NumPy는 빠른 조건 비교, 필터링, 브로드캐스팅 연산 제공
```distances = np.array([15, 9, 30])  # 앞차와 거리
warnings = distances < 10  # 위험 거리만 True
```

# 📘 w3schools NumPy 튜토리얼
## ✅ NumPy 학습 목차
  * [1. NumPy 시작하기](#1-numpy-시작하기)
  * [2. NumPy 배열 만들기](#2-numpy-배열-만들기)
  * [3. NumPy 배열 인덱싱](#3-numpy-배열-인덱싱)
  * [4. NumPy 배열 슬라이싱](#4-numpy-배열-슬라이싱)
  * [5. NumPy 데이터 유형](#5-numpy-데이터-유형)
  * [6. NumPy 복사 대 보기](#6-numpy-복사-대-보기)
  * [7. NumPy 배열 모양](#7-numpy-배열-모양)
  * [8. NumPy 배열 모양 변경](#8-numpy-배열-모양-변경)
  * [9. NumPy 배열 반복](#9-numpy-배열-반복)
  * [10. NumPy 배열 조인](#10-numpy-배열-조인)
  * [11. NumPy 배열 분할](#11-numpy-배열-분할)
  * [12. NumPy 배열 검색](#12-numpy-배열-검색)
  * [13. NumPy 배열 정렬](#13-numpy-배열-정렬)
  * [14. NumPy 배열 필터](#14-numpy-배열-필터)

---

## 1. NumPy 시작하기
(1) NumPy 가져오기
NumPy가 설치되면 키워드를 추가하여 응용 프로그램에 가져옵니다.
```import numpy
```
이제 NumPy를 가져와서 사용할 준비가 되었습니다.
(2) NumPy를 np로
NumPy는 일반적으로 별칭으로 가져옵니다.np
```import numpy as np
```
(3) NumPy 버전 확인
```import numpy as np
print(np.__version__)
```
---

## 2. NumPy 배열 만들기
(1) NumPy ndarray 객체 만들기
NumPy의 배열 객체는 .ndarray
```import numpy as np
arr = np.array([1, 2, 3, 4, 5])
print(arr)
print(type(arr))
```
(2) 배열의 차원
배열의 차원은 배열 깊이(중첩된 배열)의 한 수준
-> 중첩 배열: 배열을 요소로 포함하는 배열

1) 0차원 배열
```import numpy as np
arr = np.array(42)
print(arr)
```
2) 1차원 배열
```import numpy as np
arr = np.array([1, 2, 3, 4, 5])
print(arr)
```
3) 2차원 배열
```import numpy as np
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr)
```
4) 3차원 배열
```import numpy as np
arr = np.array([[[1, 2, 3], [4, 5, 6]], [[1, 2, 3], [4, 5, 6]]])
print(arr)
```
(3) 차원 수확인
```import numpy as np

a = np.array(42)
b = np.array([1, 2, 3, 4, 5])
c = np.array([[1, 2, 3], [4, 5, 6]])
d = np.array([[[1, 2, 3], [4, 5, 6]], [[1, 2, 3], [4, 5, 6]]])

print(a.ndim)
print(b.ndim)
print(c.ndim)
print(d.ndim)
```
(4) 5차원 배열 및 배열 수 확인
```import numpy as np
arr = np.array([1, 2, 3, 4], ndmin=5)
print(arr)
print('number of dimensions :', arr.ndim)
```

---

## 3. NumPy 배열 인덱싱
(1) Access 배열 요소
-> 배열 요소에 액세스하는 것과 동일
--> NumPy 배열의 인덱스는 0으로 시작, 이는 첫 번째 요소가 인덱스는 0, 두 번째는 인덱스 1
1) 배열에서 요소 가져오기
```import numpy as np
arr = np.array([1, 2, 3, 4])
print(arr[0])
```
2) 배열에서 요소 가져오기 및 추가
```import numpy as np
arr = np.array([1, 2, 3, 4])
print(arr[2] + arr[3])
```
(2) 배열에 액세스하기
import numpy as np
arr = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])
print(arr[0, 1, 2])

---

## 4. NumPy 배열 슬라이싱
-> 파이썬에서 슬라이싱은 주어진 한 인덱스에서 다른 주어진 인덱스로 요소를 가져 오는 것을 의미
(1) 배열 슬라이싱
```import numpy as np
arr = np.array([1, 2, 3, 4, 5, 6, 7])
print(arr[1:5])
```
(2) 네거티브 슬라이싱
```import numpy as np
arr = np.array([1, 2, 3, 4, 5, 6, 7])
print(arr[-3:-1])
```
(3) 슬라이싱 단계 결정 step
1) 다른 모든 요소를 반환
```import numpy as np
arr = np.array([1, 2, 3, 4, 5, 6, 7])
print(arr[1:5:2])
```
2) 2차원 배열 슬라이싱
```import numpy as np
arr = np.array([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]])
print(arr[1, 1:4])
```

---

## 5. NumPy 데이터 유형
(1) Python의 데이터 유형
- strings - 텍스트 데이터를 나타내는 데 사용되며 텍스트는 따옴표 아래에 표시됩니다. 예) "ABCD"
- integer - 정수를 나타내는 데 사용됩니다. 예) -1, -2, -3
- float - 실수를 나타내는 데 사용됩니다. 예) 1.2, 42.42
- boolean - 참 또는 거짓을 나타내는 데 사용됩니다.
- complex - 복잡함을 나타내는 데 사용됩니다. 숫자. 예) 1.0 + 2.0j, 1.5 + 2.5j
(2) NumPy의 데이터 유형
-> 몇 가지 추가 데이터 유형이 있으며 하나로 데이터 유형을 참조
- i -정수
- b -부울
- u - 부호 없는 정수
- f -뜨다
- c - 복합 부동 소수점
- m - 타임델타
- M - 날짜/시간
- O -객체
- S -문자열
- U - 유니코드 문자열
- V - 다른 타입에 대한 메모리 청크 수정 ( void )
---

## 6. NumPy 복사 대 보기
(1) 복사와 보기의 차이점
복사본은 새 배열이고 보기는 원래 배열의 보기
(2) 복사
```
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
x = arr.copy()
arr[0] = 42

print(arr)
print(x)
```
(3) 보기
```import numpy as np

arr = np.array([1, 2, 3, 4, 5])
x = arr.view()
arr[0] = 42

print(arr)
print(x)
```
(4) 뷰를 만들고, 뷰를 변경하고, 두 배열을 모두 표시
```import numpy as np

arr = np.array([1, 2, 3, 4, 5])
x = arr.view()
x[0] = 31

print(arr)
print(x)
```

---

## 7. NumPy 배열 모양
(1) 배열의 모양
---

## 8. NumPy 배열 모양 변경

---

## 9. NumPy 배열 반복

---

## 10. NumPy 배열 조인

---

## 11. NumPy 배열 분할

---

## 12. NumPy 배열 검색

---

## 13. NumPy 배열 정렬

---

## 14. NumPy 배열 필터

#0703 선생님 링크
https://docs.google.com/document/d/17Avhfbh0q_K7FgLGbhBY_yvD3xCIdlAfVIRJUAP-lFU/edit?tab=t.0
필터 코드 코랩에서 해보기
## 초보자 학습 순서
1. Creating Arrays → Indexing → Slicing (기본기)
애니메이션  https://claude.ai/public/artifacts/6accf154-ceb5-470a-b2e2-543df2d49b4a
2. shape와 reshape 애니메이션
https://claude.ai/public/artifacts/e9e50b3f-cd6a-4a15-8858-3a84f0b4bb36

## numpy 완전 기초 설명 1/12
https://claude.ai/public/artifacts/0594c0ae-662a-4c1b-b29f-16dc69aff934
 
## 애니메이션  : array indexing, slicing, 브로드캐스팅, reshape, flatten, 전치행렬
https://claude.ai/public/artifacts/fdea1f0a-439f-47d8-b954-956f34693a2e
