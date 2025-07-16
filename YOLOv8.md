# 📌 YOLOv8 전체 학습 목차

- [📘 YOLOv8 기본 개요](#-yolov8-기본-개요)
  - [1. YOLOv8이란?](#1-yolov8이란)
  - [2. YOLOv8의 핵심 특징](#2-yolov8의-핵심-특징)
  - [3. YOLOv8 설치 및 환경 구성](#3-yolov8-설치-및-환경-구성)
  - [4. YOLOv8 명령어 기초 사용법](#4-yolov8-명령어-기초-사용법)
  - [5. YOLOv8 모델 구조 및 종류](#5-yolov8-모델-구조-및-종류)

- [📘 YOLOv8 실습 활용](#-yolov8-실습-활용)
  - [✅ 사전 학습된 모델로 예측하기](#-사전-학습된-모델로-예측하기)
  - [✅ 커스텀 데이터로 학습하기](#-커스텀-데이터로-학습하기)
  - [✅ YOLOv8과 OpenCV 연동](#-yolov8과-opencv-연동)
  - [✅ YOLOv8의 자율주행 적용](#-yolov8의-자율주행-적용)

---

# 📘 YOLOv8 기본 개요

## 1. YOLOv8이란?

YOLOv8은 **Ultralytics**에서 개발한 객체 탐지 모델
YOLO 시리즈 중 가장 최신 버전으로, 기존 YOLOv5/YOLOv7과 비교해 **더 높은 정확도와 속도, 더 간단한 사용성**을 제공

- YOLO = You Only Look Once
- 이미지 전체를 한 번에 보고 객체 탐지를 수행하는 방식
- PyTorch 기반
- 클래스 분류, 객체 감지, 세그멘테이션, 포즈 추정까지 모두 지원

---

## 2. YOLOv8의 핵심 특징

| 항목 | 내용 |
|------|------|
| 프레임워크 | PyTorch 기반 |
| 지원 작업 | 분류(Classification), 탐지(Detection), 세분화(Segmentation), 포즈 추정(Pose Estimation) |
| 주요 기능 | ONNX/TFLite 등 다양한 내보내기(export) 지원, 학습/추론/검증 명령어 통합 |
| 향상된 성능 | 기존 모델 대비 mAP 증가, 경량화 및 속도 향상 |
| 활용 분야 | 자율주행, 보안, 의료, 스마트 팩토리, 로봇 등 |

---

## 3. YOLOv8 설치 및 환경 구성

✅ (1) pip 설치
```bash
pip install ultralytics
```

✅ (2) 설치 확인
```python
import ultralytics
ultralytics.checks()
```

✅ (3) CLI 버전 확인
```bash
yolo
```

---

## 4. YOLOv8 명령어 기초 사용법

YOLOv8은 CLI(Command Line Interface)로 매우 직관적인 명령어를 제공합니다.

```bash
# 사전 학습된 모델로 예측
yolo task=detect mode=predict model=yolov8n.pt source=이미지.jpg

# 학습
yolo task=detect mode=train model=yolov8n.yaml data=데이터셋.yaml epochs=50 imgsz=640

# 검증
yolo task=detect mode=val model=best.pt data=데이터셋.yaml

# 내보내기
yolo export model=best.pt format=onnx
```

---

## 5. YOLOv8 모델 구조 및 종류

| 모델 | 크기 | 속도 | 정확도 |
|------|------|------|--------|
| YOLOv8n | nano | 빠름 | 낮음 |
| YOLOv8s | small | 보통 | 보통 |
| YOLOv8m | medium | 중간 | 높음 |
| YOLOv8l | large | 느림 | 더 높음 |
| YOLOv8x | x-large | 느림 | 최고 정확도 |

모델 선택 시에는 **성능과 속도의 균형**을 고려

---

# 📘 YOLOv8 실습 활용

## ✅ 사전 학습된 모델로 예측하기

```python
from ultralytics import YOLO

model = YOLO('yolov8n.pt')
results = model('이미지.jpg')

results[0].show()
results[0].save(filename='output.jpg')
```

---

## ✅ 커스텀 데이터로 학습하기

1. 데이터셋 구성
   - `images/train`, `images/val`
   - `labels/train`, `labels/val`  
   - `data.yaml` 파일 필요

```yaml
# data.yaml 예시
path: ../mydataset
train: images/train
val: images/val

nc: 3
names: ['car', 'bus', 'person']
```

2. 학습 실행
```bash
yolo task=detect mode=train model=yolov8s.pt data=data.yaml epochs=100 imgsz=640
```

---

## ✅ YOLOv8과 OpenCV 연동

YOLOv8은 실시간 카메라 입력과 연동하여 영상 탐지 가능

```python
import cv2
from ultralytics import YOLO

cap = cv2.VideoCapture(0)
model = YOLO('yolov8n.pt')

while True:
    ret, frame = cap.read()
    results = model(frame)
    annotated_frame = results[0].plot()

    cv2.imshow("YOLOv8 Live", annotated_frame)
    if cv2.waitKey(1) == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

---

## ✅ YOLOv8의 자율주행 적용

YOLOv8은 자율주행에서 **다양한 객체(신호등, 보행자, 차량 등)** 를 실시간으로 탐지하는 데 매우 효과적

활용 사례:
- 신호등 인식 및 색상 분류
- 횡단보도 및 보행자 탐지
- 전방 차량 거리 측정 (Object + Depth Fusion)

```python
results = model('road_scene.jpg')
for box in results[0].boxes:
    print(box.cls, box.conf, box.xyxy)  # 클래스, 신뢰도, 위치
```

---

# 📌 학습 참고 링크

- [📘 Ultralytics 공식 문서](https://docs.ultralytics.com/)
- [🛠 YOLOv8 깃허브](https://github.com/ultralytics/ultralytics)
- [📺 실습 영상 예시](https://www.youtube.com/watch?v=6mT3Pe-D5rQ)
