# 📌 Matplotlib 전체 학습 목차

- [📘 Matplotlib 기초 정리](#matplotlib-기초-정리)
  - [1. Matplotlib이란](#1-matplotlib이란)
  - [2. Matplotlib은 언제 사용하나요](#2-matplotlib은-언제-사용하나요)
  - [3. Matplotlib 설치 및 준비물](#3-matplotlib-설치-및-준비물)
  - [4. 자율주행과 Matplotlib의 연관성](#4-자율주행과-matplotlib의-연관성)

- [📘 w3schools Matplotlib 튜토리얼](#w3schools-matplotlib-튜토리얼)
  - [✅ Matplotlib 학습 목차](#-matplotlib-학습-목차)
  - [1. Matplotlib 시작하기](#1-matplotlib-시작하기)
  - [2. Plot 만들기](#2-plot-만들기)
  - [3. 여러 개의 점](#3-여러-개의-점)
  - [4. 마커\(Markers\)](#4-마커markers)
  - [5. 선\(Line\)](#5-선line)
  - [6. 색상\(Color\)](#6-색상color)
  - [7. 선 너비\(Width\)](#7-선-너비width)
  - [8. 여러 선 그리기](#8-여러-선-그리기)
  - [9. 라벨과 제목\(Label-Title\)](#9-라벨과-제목label-title)
  - [10. 그리드\(Grid\)](#10-그리드grid)
  - [11. 서브플롯\(Subplots\)](#11-서브플롯subplots)
  - [12. 범례\(Legend\)](#12-범례legend)
  - [13. 축 설정\(Limits\)](#13-축-설정limits)
  - [14. 산점도\(Scatter\)](#14-산점도scatter)
  - [15. 막대그래프\(Bar\)](#15-막대그래프bar)
  - [16. 수평 막대그래프\(Barh\)](#16-수평-막대그래프barh)
  - [17. 히스토그램\(Histogram\)](#17-히스토그램histogram)
  - [18. 파이차트\(Pie\)](#18-파이차트pie)


# 📘 Matplotlib 기초 정리

## 1. Matplotlib이란

Matplotlib는 Python에서 데이터를 **시각화(Visualization)**하기 위한 대표적인 라이브러리입니다.  
차트, 그래프, 그림 등을 손쉽게 그릴 수 있으며, 특히 **과학적 분석 결과나 머신러닝 결과 시각화**에 자주 사용됩니다.

### ✔ 대표 기능
- 선 그래프, 막대 그래프, 산점도, 파이차트 등 다양한 형태의 시각화 가능
- 커스터마이징(색상, 스타일, 크기 등)이 유연함
- 다른 라이브러리(Pandas, NumPy)와 연동이 매우 뛰어남

---

## 2. Matplotlib은 언제 사용하나요

| 사용 상황 | 설명 |
|-----------|------|
| 데이터 분석 시각화 | 통계, 분석 데이터를 그래프로 표현할 때 |
| 머신러닝 모델 학습 결과 | 손실 함수(loss), 정확도(acc)를 그래프로 확인 |
| 이미지 처리 결과 표시 | 이미지 전처리, 필터링 결과 확인 |
| 실시간 센서 데이터 시각화 | 자율주행 차량의 거리, 속도 등 |

---

## 3. Matplotlib 설치 및 준비물

 (1) Python 설치  
이미 Python이 설치되어 있다면 OK!

 (2) Matplotlib 설치  
아래 명령어를 터미널에 입력하여 설치할 수 있어요.
```
pip install matplotlib
```
## 4. 자율주행과 Matplotlib의 연관성

- 예시: 라이다(LiDAR) 거리 시각화
```import matplotlib.pyplot as plt
import numpy as np

distances = np.random.randint(1, 20, size=100)
plt.plot(distances)
plt.title("LiDAR Distance Over Time")
plt.xlabel("Time")
plt.ylabel("Distance (m)")
plt.show()
```
- 예시: 이미지 처리 결과 시각화
```import matplotlib.pyplot as plt
import numpy as np

img = np.random.randint(0, 255, (64, 64), dtype=np.uint8)
plt.imshow(img, cmap='gray')
plt.title("Camera Image Output")
plt.axis('off')
plt.show()
```

---

# 📘 w3schools Matplotlib 튜토리얼
## ✅ Matplotlib 학습 목차

## 1. Matplotlib 시작하기

```
# 설치 및 가져오기
pip install matplotlib

import matplotlib
print(matplotlib.__version__)
```

## 2. Plot 만들기

Matplotlib에서 가장 기본이 되는 그래프는 선 그래프(Line Plot)입니다.

### ✅ 예제 코드
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array([0, 6])
y = np.array([0, 250])

plt.plot(x, y)  # 선 그래프
plt.show()
```

---

## 3. 여러 개의 점

선 없이 점만 표시하려면 `'o'` 마커를 사용합니다.

### ✅ 예제 코드
```python
x = np.array([1, 8])
y = np.array([3, 10])

plt.plot(x, y, 'o')  # 점만 표시
plt.show()
```

---

## 4. 마커(Markers)

각 점을 특정 모양으로 나타내는 것이 마커입니다. `'o'`, `'*'`, `'s'` 등 다양한 모양이 존재합니다.

### ✅ 예제 코드
```python
ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, marker='*')  # 별 모양 마커
plt.show()
```

---

## 5. 선(Line)

선 스타일은 선의 형태를 지정합니다. 축약 구문을 통해 간단히 표현할 수 있습니다.

### ✅ 1) 대표적인 선 스타일 종류

| 스타일 이름 | 축약 구문 | 의미           |
|-------------|------------|----------------|
| solid       | '-'        | 실선 (기본값)  |
| dashed      | '--'       | 파선           |
| dotted      | ':'        | 점선           |
| dashdot     | '-.'       | 점+선 반복     |

### ✅ 2) 예제 코드
```python
ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, linestyle='--')  # 파선
plt.plot(ypoints, ls=':')          # 점선 축약
plt.show()
```

---

## 6. 색상(Color)

선 색상은 `color` 또는 `c` 키워드로 지정할 수 있습니다. 문자열이나 HEX 코드를 사용합니다.

### ✅ 예제 코드
```python
ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, color='hotpink')  # 문자열
plt.plot(ypoints, c='#4CAF50')      # HEX 코드
plt.show()
```

---

## 7. 선 너비(Width)

`linewidth` 또는 `lw` 키워드를 사용하여 선의 두께를 설정할 수 있습니다.

### ✅ 예제 코드
```python
ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, linewidth=5)
plt.show()
```

---

## 8. 여러 선 그리기

하나의 플롯에 여러 선을 겹쳐서 그릴 수 있습니다.

### ✅ 예제 코드
```python
y1 = np.array([3, 8, 1, 10])
y2 = np.array([6, 2, 7, 11])

plt.plot(y1, label="Line 1")
plt.plot(y2, label="Line 2")
plt.legend()
plt.show()
```

---

## 9. 라벨과 제목(Label, Title)

`xlabel`, `ylabel`, `title`로 그래프에 텍스트를 추가할 수 있습니다.

### ✅ 예제 코드
```python
x = np.array([80, 85, 90])
y = np.array([240, 250, 260])

plt.plot(x, y)
plt.title("Sports Watch Data")
plt.xlabel("Pulse")
plt.ylabel("Calories")
plt.show()
```

---

## 10. 그리드(Grid)

`plt.grid()`를 사용하면 눈금선이 생겨 그래프 해석이 쉬워집니다.

### ✅ 예제 코드
```python
x = np.array([80, 85, 90])
y = np.array([240, 250, 260])

plt.plot(x, y)
plt.grid()
plt.show()
```

---

## 11. 서브플롯(Subplots)

여러 개의 그래프를 한 화면에 배치할 수 있습니다. `plt.subplot(행, 열, 번호)` 형식으로 사용합니다.

### ✅ 예제 코드
```python
x = np.array([1, 2, 3, 4])
y1 = np.array([3, 8, 1, 10])
y2 = np.array([6, 2, 7, 11])

plt.subplot(1, 2, 1)
plt.plot(x, y1)

plt.subplot(1, 2, 2)
plt.plot(x, y2)

plt.show()
```

---

## 12. 범례(Legend)

각 선의 의미를 명확히 표시할 수 있는 범례는 `plt.legend()`로 추가합니다.

### ✅ 예제 코드
```python
x = np.array([1, 2, 3, 4])
y = np.array([2, 6, 3, 8])

plt.plot(x, y, label='Speed')
plt.legend()
plt.show()
```

---

## 13. 축 설정(Limits)

`xlim`, `ylim`을 이용해 축의 범위를 조정할 수 있습니다.

### ✅ 예제 코드
```python
x = np.array([1, 2, 3, 4])
y = np.array([10, 20, 30, 40])

plt.plot(x, y)
plt.xlim(0, 6)
plt.ylim(0, 50)
plt.show()
```

---

## 14. 산점도(Scatter)

점들 간의 관계를 시각화할 때 사용합니다. `plt.scatter()` 함수로 그립니다.

### ✅ 예제 코드
```python
x = np.array([5, 7, 8, 7, 2, 17])
y = np.array([99, 86, 87, 88, 100, 86])

plt.scatter(x, y)
plt.show()
```

---

## 15. 막대그래프(Bar)

카테고리 데이터를 시각화하는 데 유용합니다. `plt.bar()` 사용.

### ✅ 예제 코드
```python
x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.bar(x, y)
plt.show()
```

---

## 16. 수평 막대그래프(Barh)

막대를 수평 방향으로 그릴 수 있습니다. `plt.barh()` 사용.

### ✅ 예제 코드
```python
x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.barh(x, y, color="hotpink")
plt.show()
```

---

## 17. 히스토그램(Histogram)

데이터의 분포를 시각화합니다. `plt.hist()` 사용.

### ✅ 예제 코드
```python
x = np.random.normal(170, 10, 250)  # 평균 170, 표준편차 10

plt.hist(x)
plt.show()
```

---

## 18. 파이차트(Pie)

비율을 표현할 때 사용하며, `plt.pie()` 함수로 작성합니다.

### ✅ 예제 코드
```python
y = np.array([35, 25, 25, 15])
labels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels=labels)
plt.show()
```
