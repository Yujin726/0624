# 📘 OpenCV 기초 정리

## ✅ 목차

1. [OpenCV란?](#1-opencv란)  
   - [1-1) OpenCV의 정의](#1-1-opencv의-정의)  
   - [1-2) OpenCV의 특징](#1-2-opencv의-특징)  
   - [1-3) 주요 활용 분야](#1-3-주요-활용-분야)  
   - [1-4) 구조 및 모듈 구성](#1-4-구조-및-모듈-구성)

2. [OpenCV에 필요한 라이브러리들](#2-opencv에-필요한-라이브러리들)  
   - [2-1) opencv-python vs opencv-contrib-python](#2-1-opencv-python-vs-opencv-contrib-python)  
   - [2-2) NumPy와 OpenCV의 관계](#2-2-numpy와-opencv의-관계)  
   - [2-3) Matplotlib과 함께 사용하는 이유](#2-3-matplotlib과-함께-사용하는-이유)  
   - [2-4) Pillow의 역할](#2-4-pillow의-역할)

3. [OpenCV 자주 나오는 용어 정리](#3-opencv-자주-나오는-용어-정리)

---

## 1. OpenCV란?

### 🔹 1-1) OpenCV의 정의
OpenCV(Open Source Computer Vision Library)는 실시간 컴퓨터 비전 및 이미지 처리 기능을 제공하는 오픈소스 라이브러리입니다.  
C++, Python, Java 등 다양한 언어를 지원하며, 크로스 플랫폼으로 사용 가능합니다.

### 🔹 1-2) OpenCV의 특징
- 오픈소스이자 무료
- 실시간 영상 처리 성능 우수
- 다양한 이미지/영상 처리 함수 제공
- 머신러닝, 딥러닝과 연동 가능
- 다양한 플랫폼(CPU, GPU, 모바일) 지원

### 🔹 1-3) 주요 활용 분야
- 객체 인식 및 추적
- 얼굴 인식, OCR(문자 인식)
- 자율주행 차량 비전 시스템
- 로봇 비전
- 증강현실(AR) 기술

### 🔹 1-4) 구조 및 모듈 구성
- core: 기본 데이터 구조와 연산 기능
- imgproc: 이미지 처리 기능 (블러, 필터 등)
- highgui: GUI 및 이미지 입출력
- video: 동영상 처리 기능
- objdetect: 객체 탐지 (ex. 얼굴 인식)
- ml: 머신러닝 기능
- contrib: 추가 기능 (SIFT, SURF 등)

---

## 2. OpenCV에 필요한 라이브러리들

| 라이브러리 | 설명 | 설치 명령어 |
|------------|------|--------------|
| `opencv-python` | OpenCV의 Python 버전 | `pip install opencv-python` |
| `numpy` | 이미지를 NumPy 배열로 처리 | `pip install numpy` |
| `matplotlib` | 이미지 출력 및 디버깅용 시각화 | `pip install matplotlib` |
| `opencv-contrib-python` | SIFT, SURF 등 고급 모듈 포함 | `pip install opencv-contrib-python` |
| `Pillow` | 이미지 저장 및 변환 | `pip install pillow` |

### 🔹 2-1) opencv-python vs opencv-contrib-python
- `opencv-python`: 기본적인 이미지/영상 처리 기능
- `opencv-contrib-python`: SIFT, SURF, DNN 등 고급 알고리즘 포함

### 🔹 2-2) NumPy와 OpenCV의 관계
OpenCV는 이미지를 기본적으로 NumPy 배열로 표현하며, 모든 처리 결과도 배열로 반환됩니다.

### 🔹 2-3) Matplotlib과 함께 사용하는 이유
디버깅 중 이미지 결과를 시각화하거나 비교할 때 유용하며, Colab이나 Jupyter 환경에서 출력이 간편합니다.

### 🔹 2-4) Pillow의 역할
이미지를 다양한 포맷으로 저장하거나, 파일 변환 및 필터링 작업을 수행할 수 있습니다.

---

## 3. OpenCV 자주 나오는 용어 정리

| 용어        | 의미 |
|-------------|------|
| **BGR**     | OpenCV의 기본 색상 순서 (Blue, Green, Red) |
| **ROI**     | Region of Interest: 관심 영역 |
| **Threshold** | 이미지 이진화 시 임계값 기준 설정 |
| **Morphology** | 팽창, 침식 등 형태학적 연산 |
| **Kernel**  | 이미지 처리 시 사용하는 작은 행렬(마스크) |
| **Contour** | 윤곽선: 이미지에서 객체 경계 검출 |
| **Cascade** | 사전 학습된 객체 탐지기 (ex. 얼굴 인식용) |
| **Grayscale** | 흑백 이미지 (1채널) |
| **FPS**     | Frame Per Second: 초당 프레임 수 |
| **HSV**     | 색상(H), 채도(S), 명도(V) 색상공간 |

이 용어들은 실습 중 코드와 문서에서 자주 등장하며, 정확한 의미 파악이 중요합니다.

---
