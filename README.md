# 📘 AI 학습 정리

## 1. About GitHub, Markdown, Colab
- [GitHub 사용법](#github-사용법)
- [Markdown 문법](#markdown-문법)  
- [Colab 기초](#colab-기초)

## GitHub 사용법

### ✅ GitHub 계정 만드는 순서 (2025년 기준)

1. **웹 브라우저 열기**
   크롬(Chrome), 엣지(Edge), 사파리(Safari) 중 편한 걸 사용하세요.

2. **GitHub 웹사이트 접속**
   주소창에 아래 주소를 입력하고 Enter 누르세요: https://github.com

3. **회원가입 시작하기**
   화면 오른쪽 위 또는 중간에 있는 Sign up 버튼 클릭

4. **이메일 주소 입력**
   평소 자주 사용하는 이메일을 입력

5. **비밀번호 만들기**
   영어 대문자, 소문자, 숫자, 특수문자를 섞어 안전하게!
   예시: Git1234!hub

6. **사용자 이름(Username) 정하기**
   나만의 고유한 이름을 지어요 (다른 사람이 쓰고 있으면 불가)
   - 예시: jetsunmom, sungsookjang66 등
   - 영어, 숫자, 하이픈(-) 가능 (띄어쓰기 ❌)

### ✅ Repository 만들기 순서

1. **GitHub에 로그인 후 New Repository 클릭**
2. ![new](https://github.com/user-attachments/assets/3481a680-f677-403b-be8c-1fe59d5aa7cb)

3. **Repository 이름 입력**
4. **Public/Private 선택**
5. **README.md 파일 생성 체크**
6. **Create repository 버튼 클릭**
   
![create_repository](https://github.com/user-attachments/assets/8c2eb16b-8dfc-465a-88cd-d35770d12df0)

## Markdown 문법

### 1. ✅ 제목(Heading) 작성하기
`#` 기호를 사용해 제목의 크기를 조절할 수 있어요.

- `#` 1개: 가장 큰 제목 (h1)
- `##` 2개: 중간 제목 (h2)
- `###` 3개: 소제목 (h3)
  
예시)
# 제목1
## 제목2
### 제목3

---

### 2. ✅ 텍스트 꾸미기 (굵게, 기울임)

- `**굵게**` → 텍스트 강조  
- `*기울임*` → 약한 강조  
- `***굵고 기울임***` → 이중 강조

예시)
**이것은 굵은 글씨입니다**  
*이것은 기울임입니다*  
***이것은 굵고 기울임입니다***

---

### 3. ✅ 목록 만들기

1. **순서 있는 목록**  
   숫자와 점(`1.`, `2.`)을 사용

2. **순서 없는 목록**  
   `-`, `*` 기호 사용

예시)
순서 있는 목록:
1. 첫 번째 항목
2. 두 번째 항목

순서 없는 목록:
- 사과
- 바나나
- 포도

---

### 4. ✅ 링크 삽입

`[링크이름](https://example.com)` 형태로 작성

예시) [Google](https://google.com)

---

### 5. ✅ 이미지 삽입

`![이미지설명](이미지주소)` 형태로 작성해요.

- **인터넷에 있는 이미지 주소(URL)** 를 복사해서 붙여넣기
- **GitHub에 직접 이미지 업로드 후 링크로 연결**
- **드래그 앤 드롭 또는 복사-붙여넣기**도 지원됨 (GitHub 에디터에서)

예시) 
이미지 주소 복사 붙여넣기 : ![고양이]([https://placekitten.com/200/200](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyNTAxMTBfODAg%2FMDAxNzM2NDk1Mjk5Mjcz.bDZ6N_18yXDMglefxe1JePFIscsy14JhF7uibXBJ4-0g.dTSTJqfluamoNkshNYo94CIuJXyF57U357a_Du0fa3kg.JPEG%2F4.jpg&type=sc960_832)

드래그 앤 드롭 또는 복사-붙여넣기
![image](https://github.com/user-attachments/assets/2e325e26-aa05-47ae-bf0b-a29ce40a2a42)

---

### 6. ✅ 코드 작성

- **한 줄 코드**: 백틱(`) 한 개로 감싸기 → `` `코드` ``
- **여러 줄 코드**: 백틱 3개 사용 → \`\`\`

예시)
- 한 줄 코드: `print("Hello, Markdown!")`

- 여러 줄 코드:
```python
for i in range(3):
    print("Hello, Colab!")
```
---

### 7. ✅ 인용문 만들기

`>` 기호를 사용해서 인용문 작성

예시:
> 이것은 인용문입니다.
줄을 바꿔도 인용이 유지됩니다.

---

### 8. ✅ 구분선 넣기

`---` 또는 `***`를 단독 줄에 작성하면 구분선이 생겨요.

예시:

## Colab 기초  
### 1. ✅ Colab 노트북 제목 설정하기
- 노트북 상단 왼쪽에 있는 제목을 클릭 -> 원하는 이름으로 변경 가능
- 작업 내용을 구분 가능
  
예시)
![image](https://github.com/user-attachments/assets/80bd7eb0-cf22-4cd1-b00e-a875407cbb80)

### 2. ✅ 런타임 환경 GPU(T4) 설정 방법

- 상단 메뉴에서 **런타임** → **런타임 유형 변경** 클릭  
(예: T4 GPU)
- ![image](https://github.com/user-attachments/assets/788b1054-cdf0-48d3-b858-db3cb8870274)
- ![image](https://github.com/user-attachments/assets/4b558878-188e-4cd3-9906-ad2de004bc27)
- ![image](https://github.com/user-attachments/assets/6ffa42bd-2a70-43c5-8782-195837d008d1)

### 3. ✅ GitHub와 연동하기

- 상단 메뉴에서 파일
- ![image](https://github.com/user-attachments/assets/a627a8d2-24b2-4e24-93de-f1c5aa8ca52a)
- GitHub에 사본 저장 클릭
- ![image](https://github.com/user-attachments/assets/bcf1070f-9e00-4e31-9f75-3b5ef1556d63)
- GitHub로 복사 → 확인
- ![image](https://github.com/user-attachments/assets/fd68cf1f-5b52-420b-b676-5dd9a9740540)

### 4. ✅ 코드 셀과 텍스트 셀 추가하기

- 상단 메뉴 아래에 있는 **`+ 코드`**, **`+ 텍스트`** 버튼을 클릭하여 셀을 추가할 수 있어요.  
- **코드 셀**: Python 코드를 입력하고 실행할 수 있는 공간  
- **텍스트 셀**: 마크다운 문법을 이용해 설명, 제목 등을 작성하는 공간  

예시)  
![image](https://github.com/user-attachments/assets/599c1017-e9be-4829-a8e2-715c77a3062a)

## 2. About Python3
- [Python basic](./docs/python3.md)

## 3.  data structure / data sciencs

- [데이터 구조 개요](./data_structures.md)
- [Pandas](./pandas.md)
- [Numpy](./numpy.md)
- [Matplotlib](./Matplotlib.md)

## 4. Machine Learning

- [Machine Learning Basic](./ml_basic.md)
- [모델 훈련 및 평가](./ml_test.md)

## 5. OpenCV

- [OpenCV Basic](./OpenCV_Basic.md)
- [이미지 처리](./image_test.md)

  
## 6. CNN(Convolution Neural Network
- [CNN_Basic](./CNN_basic.md)
- [CNN_자율주행 관련 코드](./cnn_test.md)

## 7. Ultralytics
- [Ultralytics_Basic](./Ultralytics_basic.md)
- [YOLOv8](./YOLOv8.md)
- [YOLOv11](./YOLOv11.md)
  
## 8. TensorRT vs PyTorch 
- [PyTorch_Basic](./PyTorch_basic.md)
- [TensorRT](./TensorRT_test.md)
- [YOLOv12](./YOLOv12_test.md)

## 9. TAO Toolkit on RunPod
- [TAO_사용법](.TAO_install.md)
- [TAO_Toolkit](.TAO_Toolkit.md)

## 10. 칼만필터, CARLA, 경로 알고리즘
- [kalman](.kalman.md)
- [CARLA_simulator](.CARLA.md)

## 11. ADAS & (ADAS TensorRT vs PyTorch)
- [adas_basic](.adas_basic.md)
- [TensorRT vs PyTorch 비교](.vs.md)
