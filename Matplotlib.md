# 📌 Matplotlib 전체 학습 목차

- [📘 Matplotlib 기초 정리](#-matplotlib-기초-정리)
  - [1. Matplotlib이란?](#1-matplotlib이란)
  - [2. Matplotlib은 언제 사용하나요?](#2-matplotlib은-언제-사용하나요)
  - [3. Matplotlib 설치 및 준비물](#3-matplotlib-설치-및-준비물)
  - [4. 자율주행과 Matplotlib의 연관성](#4-자율주행과-matplotlib의-연관성)

- [📘 w3schools Matplotlib 튜토리얼](#-w3schools-matplotlib-튜토리얼)
  - [✅ Matplotlib 학습 목차](#✅-matplotlib-학습-목차)
    - [1. Matplotlib 시작하기](#1-matplotlib-시작하기)
    - [2. Plot 만들기](#2-plot-만들기)
    - [3. 여러 개의 점](#3-여러-개의-점)
    - [4. 마커(Markers)](#4-마커markers)
    - [5. 선(Line)](#5-선line)
    - [6. 라벨(Label)](#6-라벨label)
    - [7. 색상(Colors)](#7-색상colors)
    - [8. 라인 스타일](#8-라인-스타일)
    - [9. 너비(Width)](#9-너비width)
    - [10. 다중 Plot](#10-다중-plot)
    - [11. 서브플롯(Subplot)](#11-서브플롯subplot)
    - [12. 범례(Legend)](#12-범례legend)
    - [13. 그리드(Grid)](#13-그리드grid)
    - [14. 축(X, Y축) 설정](#14-축x-y축-설정)
    - [15. 산점도(Scatter Plot)](#15-산점도scatter-plot)
    - [16. 막대그래프(Bar Chart)](#16-막대그래프bar-chart)
    - [17. 히스토그램(Histogram)](#17-히스토그램histogram)
    - [18. 파이차트(Pie Chart)](#18-파이차트pie-chart)

# 📘 Matplotlib 기초 정리

## 1. Matplotlib이란?

Matplotlib는 Python에서 데이터를 **시각화(Visualization)**하기 위한 대표적인 라이브러리입니다.  
차트, 그래프, 그림 등을 손쉽게 그릴 수 있으며, 특히 **과학적 분석 결과나 머신러닝 결과 시각화**에 자주 사용됩니다.

### ✔ 대표 기능
- 선 그래프, 막대 그래프, 산점도, 파이차트 등 다양한 형태의 시각화 가능
- 커스터마이징(색상, 스타일, 크기 등)이 유연함
- 다른 라이브러리(Pandas, NumPy)와 연동이 매우 뛰어남

---

## 2. Matplotlib은 언제 사용하나요?

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
