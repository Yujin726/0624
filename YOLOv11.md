# 📌 YOLOv11 전체 학습 목차

- [📘 YOLOv11 기본 개요](#-yolov11-기본-개요)
  - [1. YOLOv11이란?](#1-yolov11이란)
  - [2. YOLOv11의 핵심 특징](#2-yolov11의-핵심-특징)
  - [3. YOLOv11 설치 및 환경 구성](#3-yolov11-설치-및-환경-구성)
  - [4. YOLOv11 명령어 기초 사용법](#4-yolov11-명령어-기초-사용법)
  - [5. YOLOv11 모델 구조 및 종류](#5-yolov11-모델-구조-및-종류)

- [📘 YOLOv11 실습 활용](#-yolov11-실습-활용)
  - [✅ 사전 학습된 모델로 예측하기](#-사전-학습된-모델로-예측하기)
  - [✅ 커스텀 데이터로 학습하기](#-커스텀-데이터로-학습하기)
  - [✅ YOLOv11과 OpenCV 연동](#-yolov11과-opencv-연동)
  - [✅ YOLOv11의 자율주행 적용](#-yolov11의-자율주행-적용)
  - [📊 YOLOv8 vs YOLOv11 비교표](#-yolov8-vs-yolov11-비교표)

---

# 📘 YOLOv11 기본 개요

## 1. YOLOv11이란?

YOLOv11은 **Ultralytics** 또는 커뮤니티에서 발표한 차세대 YOLO 모델로,  
YOLOv8 대비 성능과 확장성 측면에서 큰 발전을 이루었으며,  
**자율주행, 산업 검사, 영상 분석 분야에 특화된 최적화 기능**을 포함합니다.

- YOLO = You Only Look Once  
- 전체 이미지에서 한 번에 객체 탐지  
- TensorRT, ONNX, OpenVINO 등 다양한 가속 프레임워크 지원
- Transformer 기반 백본 구조 실험적 적용

---

## 2. YOLOv11의 핵심 특징

| 항목 | 내용 |
|------|------|
| 프레임워크 | PyTorch + ONNX Runtime 지원 |
| 백본 구조 | 일부 모델에 Transformer 계열 적용 (YOLO-T variant) |
| 주요 기능 | 다중 입력 스트림, 3D 탐지, 자동 Augmentation, 모듈형 훈련 |
| 향상된 성능 | mAP 개선 (YOLOv8 대비 +3~5%), FPS 유지 또는 향상 |
| 활용 분야 | 자율주행, 공장 시각검사, UAV 탐지, 비디오 분석 등 |

---

## 3. YOLOv11 설치 및 환경 구성

✅ (1) GitHub에서 클론  
```bash
git clone https://github.com/ultralytics/yolov11
cd yolov11
pip install -r requirements.txt
```

✅ (2) 설치 확인  
```bash
python -m yolov11.check
```

✅ (3) 명령어 도움말 보기  
```bash
python detect.py --help
```

---

## 4. YOLOv11 명령어 기초 사용법

```bash
# 사전 학습된 모델로 예측
python detect.py --weights yolov11n.pt --source 이미지.jpg

# 학습 시작
python train.py --model yolov11s.yaml --data data.yaml --epochs 100 --img 640

# 검증
python val.py --weights best.pt --data data.yaml

# 내보내기
python export.py --weights best.pt --format onnx
```

---

## 5. YOLOv11 모델 구조 및 종류

| 모델 | 크기 | 속도 | 정확도 | 특징 |
|------|------|------|--------|------|
| YOLOv11n | nano | 빠름 | 보통 | 모바일 최적화 |
| YOLOv11s | small | 빠름 | ↑ | 전반적 밸런스 |
| YOLOv11m | medium | 중간 | 높음 | 대부분의 상황 적합 |
| YOLOv11l | large | 느림 | 매우 높음 | 정밀 작업용 |
| YOLOv11t | transformer | 실험적 | 최고 | 고정밀/고복잡도 용도 |

---

# 📘 YOLOv11 실습 활용

## ✅ 사전 학습된 모델로 예측하기

```python
from yolov11 import YOLO

model = YOLO('yolov11n.pt')
results = model('이미지.jpg')

results[0].show()
results[0].save('output.jpg')
```

---

## ✅ 커스텀 데이터로 학습하기

1. 데이터 구성  
   - `images/train`, `images/val`, `labels/train`, `labels/val`
   - `data.yaml` 파일 작성 필요

```yaml
# data.yaml
train: images/train
val: images/val
nc: 3
names: ['person', 'car', 'light']
```

2. 학습 실행  
```bash
python train.py --model yolov11s.yaml --data data.yaml --epochs 100 --img 640
```

---

## ✅ YOLOv11과 OpenCV 연동

```python
import cv2
from yolov11 import YOLO

model = YOLO('yolov11n.pt')
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    results = model(frame)
    cv2.imshow("YOLOv11 Live", results[0].plot())
    if cv2.waitKey(1) == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

---

## ✅ YOLOv11의 자율주행 적용

YOLOv11은 신호등, 보행자, 차량, 이륜차, 표지판 탐지에 최적화된 커스텀 학습을 지원

```python
results = model('road.jpg')
for box in results[0].boxes:
    print(f"Class: {box.cls}, Confidence: {box.conf:.2f}, BBox: {box.xyxy}")
```

---

## 📊 YOLOv8 vs YOLOv11 비교표

| 항목 | YOLOv8 | YOLOv11 |
|------|--------|--------|
| 발표 시기 | 2023 | 2024 |
| 백본 구조 | Conv + C2f | Conv + Transformer (옵션) |
| 학습 속도 | 빠름 | 비슷하거나 더 빠름 |
| 정확도 (mAP) | 높음 | 3~5% 더 향상 |
| 세그멘테이션 | 지원 | 개선된 세그멘테이션 |
| 포즈 추정 | 기본 지원 | 고급 포즈 지원 |
| 다양한 export | ONNX, TFLite, CoreML | ONNX, OpenVINO, TensorRT 최적화 |
| CLI 사용성 | 간단 | 개선된 help system |
| 적용 분야 | 자율주행, 보안 등 | 자율주행 + 산업 검사, 드론 등 확장 |

---

# 📌 학습 참고 링크

- [YOLOv11 GitHub](https://github.com/ultralytics/yolov11)
- [YOLO 논문 정리](https://arxiv.org/)
- [YOLOv8 공식 문서](https://docs.ultralytics.com/)
- [실습 영상 예시](https://www.youtube.com/watch?v=6mT3Pe-D5rQ)
