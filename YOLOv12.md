# 📘 YOLOv12 정리 (2025 정식 출시)

---

## ✅ 목차

- [📘 YOLOv12 기본 개요](#-yolov12-기본-개요)  
- [✅ YOLOv12 주요 특징](#-yolov12-주요-특징)  
- [🛠 지원 작업 및 모델 종류](#-지원-작업-및-모델-종류)  
- [⚙️ 설치 및 사용 예제](#-설치-및-사용-예제)  
- [📚 참고 링크](#-참고-링크)

---

## 📘 YOLOv12 기본 개요

YOLOv12는 **Ultralytics**에서 2025년 2월 공식 발표한 **어텐션 중심(AIttention-Centric)** 기반 최신 모델로,  
기존 YOLO 시리즈보다 **정확도와 속도의 혁신적인 균형**을 달성한 것으로 평가받고 있습니다:contentReference[oaicite:1]{index=1}.

---

## ✅ YOLOv12 주요 특징

- **어텐션 기반 백본 + R-ELAN + 7×7 separable convolution** 구조 적용:contentReference[oaicite:2]{index=2}  
- **COCO val2017 기준 mAP 향상**  
  - YOLOv12‑n: +2.1% mAP vs YOLOv10‑n, +1.2% vs YOLOv11‑n, 추론 연산 속도 1.64ms (T4 GPU):contentReference[oaicite:3]{index=3}  
  - YOLOv12‑s: RT‑DETR 대비 +1.5% mAP 및 +42% 속도 향상:contentReference[oaicite:4]{index=4}  
- **FlashAttention 지원**, 메모리 최적화 및 실시간 추론 효과:contentReference[oaicite:5]{index=5}  
- **다중 CV 작업 지원**: 탐지, 세그멘테이션, 분류, 포즈, OBB 등 다양 작업 모드 지원:contentReference[oaicite:6]{index=6}

---

## 🛠 지원 작업 및 모델 종류

| 모델 리포지토리 | 작업 유형 |
|----------------|-------------|
| `yolo12n/s/m/l/x` | 일반 객체 탐지 (Detect) |
| `yolo12*-seg` | 인스턴스 세그멘테이션 (Segmentation) |
| `yolo12*-pose` | 포즈 추정 (Pose Estimation) |
| `yolo12*-obb` | 회전 바운딩 박스 탐지 (Oriented Detection) |
| `yolo12*-cls` | 이미지 분류 (Classification) |

⊕ Ultralytics 자체와 추가 커뮤니티 구현에서 모두 지원하며, 학습·검증·추론·내보내기 모드 가능

---

## ⚙️ 설치 및 사용 예제

### 🔧 설치 방법 (Ultralytics 기준)
```bash
pip install ultralytics
```
또는 커뮤니티 구현:
```bash
pip install git+https://github.com/sunsmarterjie/yolov12
```
:contentReference[oaicite:8]{index=8}

### 🔍 추론 예시 (CLI)
```bash
yolo task=detect mode=predict model=yolo12s.pt source=이미지.jpg
```
### 🧪 Python 추론 예시
```python
from ultralytics import YOLO
model = YOLO("yolo12s.pt")
results = model("image.jpg")
results.save("output/")
```
### 🧠 학습 예시
```bash
yolo task=detect mode=train model=yolo12m.pt data=coco.yaml epochs=100 imgsz=640
```

---

## 📚 참고 링크

- **Ultralytics 공식 모델 문서**: YOLOv12 개요, 지원 작업 및 주요 특징:contentReference[oaicite:9]{index=9}  
- **arXiv 논문 (YOLOv12: Attention-Centric...)**: 모델 설계와 성능 상세:contentReference[oaicite:10]{index=10}  
- **커뮤니티 구현 GitHub**: `sunsmarterjie/yolov12` (seg, cls, obb 등 확장 기능 포함):contentReference[oaicite:11]{index=11}  
- **학습 적용 사례 연구**: LLM 기반 합성 데이터로 벼룩사과 탐지 실험:contentReference[oaicite:12]{index=12}

---

