# 🦟 서울시 모기예보제 분석 및 예측 모델

<!-- 프로젝트 대표 이미지를 여기에 추가하세요 -->
![모기예보 프로젝트 메인 이미지](이미지_URL_또는_경로)

> 서울 공공데이터와 기상청 데이터를 활용한 서울시 모기 발생량 분석 및 예측 시스템

---

## 📋 목차
1. [프로젝트 개요](#프로젝트-개요)
2. [개발자 소개](#개발자-소개)
3. [주요 기능](#주요-기능)
4. [개발 과정 및 일정](#개발-과정-및-일정)
5. [기술 스택](#기술-스택)
6. [프로젝트 구조](#프로젝트-구조)
7. [프로젝트 회고](#프로젝트-회고)
8. [프로젝트 후기](#프로젝트-후기)

---

## 🎯 프로젝트 개요

### 프로젝트 소개
- **프로젝트명**: 서울시 모기예보제 분석 및 예측 모델
- **개발 기간**: 2025.05 ~ 2025.06
- **개발자**: 전민서
- **프로젝트 유형**: 개인 데이터 분석 프로젝트

### 프로젝트 배경 및 목적
- **동기**: 다음날 혹은 그 이후의 모기지수를 미리 예측할 수 있다면, 시민들은 외출, 야외활동, 방충 대책 등을 사전에 준비할 수 있습니다.
- **문제 인식**: 현재 서울시 모기예보제는 당일 모기지수를 산출하여 시민들에게 제공하고 있습니다. 이는 당일의 모기 발생 상황에 대한 정보만을 제공하기 때문에, 시민이나 방역 당국이 미리 대비하거나 사전에 방역 계획을 수립하는 데에는 한계가 있습니다. 
- **학습 목표**: 
  - 공공데이터 활용 및 전처리 기술 향상
  - 머신러닝 회귀 모델(RandomForest) 실습
  - 다중 출력 회귀(MultiOutput Regression) 구현
  - 데이터 시각화 및 상관관계 분석 경험

### 프로젝트 목표
- **기술적 목표**: 
  - 서울시 공공데이터와 기상청 데이터 연동 및 전처리
  - RandomForest 기반 MultiOutput 회귀모델 구현
  - 모델 성능 평가 (MAE, RMSE 스코어)
- **기능적 목표**: 
  - 수변부, 주거지, 공원 3구역의 모기 발생량 동시 예측
  - 기상 요소와 모기 발생의 상관관계 분석
  - 직관적인 데이터 시각화 제공
- **개인적 목표**: 
  - 실무 수준의 데이터 분석 프로젝트 경험
  - 포트폴리오용 완성도 높은 프로젝트 구성

### 예상 사용자
- **1차 사용자**: 서울시민 (모기 발생 정보 확인)
- **2차 사용자**: 방역 담당자 (방역 계획 수립)
- **3차 사용자**: 데이터 분석 학습자 (분석 방법 참고)

---

## 👨‍💻 개발자 소개

### 개발자 정보
- **이름**: 전민서
- **전공**: 스마트소프트웨어공학과
- **GitHub**: (https://github.com/alseo0110)
- **이메일**: alseo0110@naver.com

### 관심 분야
- 데이터 분석 및 머신러닝
- 공공데이터 활용 프로젝트
- 백엔드 개발
- AI 기반 예측 모델링

### 보유 기술
**Programming Languages**
- 주력 언어: Python, SQL
- 사용 가능: C++, C#, JAVA

**Data Analysis & ML**
- pandas, numpy, scikit-learn
- matplotlib, seaborn, plotly
- Google Colab, Jupyter Notebook

**Tools & Platforms**
- Git, GitHub
- Google Colab
- Excel/Google Sheets

---

## ⭐ 주요 기능

### 🔧 핵심 기능
1. **데이터 수집 및 전처리**
   - 서울시 공공데이터포털에서 모기예보 데이터 수집
   - 기상청(KMA) 날씨 데이터 수집 및 연동
   - 날짜별 데이터 병합 및 결측치 처리
   - 특징: CSV 파일 날짜 컬럼 기준 병합, NaN 값 다양한 방법으로 처리
   
2. **상관관계 분석 및 시각화**
   - 기상 요소와 모기 발생량 간의 상관관계 히트맵 생성
   - 지역별, 시기별 모기 발생 패턴 시각화
   - 구현 이슈: Google Colab에서 한글 폰트 렌더링 문제 해결
   - 특징: 다양한 그래프를 통한 직관적 데이터 탐색

3. **다중 출력 예측 모델**
   - RandomForest 기반 MultiOutputRegressor 구현
   - 3개 지역의 모기 발생량 동시 예측
   - 모델 성능 평가: MAE, RMSE, R² 스코어 계산
   - 특징: 단일 모델로 여러 타겟 변수 동시 예측

### 📊 데이터 분석 결과
<!-- 주요 분석 결과 시각화들을 추가해주세요 -->
| 상관관계 히트맵 | 예측 성능 |
|----------------|-----------|
| ![히트맵](이미지경로) | ![성능차트](이미지경로) |

### 📈 모델 성능
- **MAE (Mean Absolute Error)**: [수치 입력]
- **RMSE (Root Mean Square Error)**: [수치 입력]  

---

## 📅 개발 과정 및 일정

### 🛠 개발 단계

#### 1단계: 데이터 수집 및 탐색 (Week 1)
- [x] 서울시 공공데이터포털 모기예보 데이터 수집
- [x] 기상청 날씨 데이터 수집
- [x] 데이터 구조 파악 및 탐색적 데이터 분석(EDA)
- [x] 데이터 품질 확인 및 문제점 파악

#### 2단계: 데이터 전처리 (Week 2)
- [x] CSV 파일 모기지수발생일 컬럼 기준 병합
- [x] 결측치 처리 전략 수립 및 적용
- [x] 이상치 탐지 및 처리
- [x] 피처 엔지니어링 및 변수 선택

#### 3단계: 모델 개발 (Week 3-4)
- [x] RandomForest 회귀 모델 구현
- [x] MultiOutputRegressor 적용
- [x] 성능 평가

#### 4단계: 시각화 및 분석 (Week 5-6)
- [x] 상관관계 히트맵 생성
- [x] Google Colab 한글 폰트 문제 해결
- [x] 다양한 시각화 차트 작성
- [x] 프레젠테이션 자료 작성

### 💡 개발하면서 새로 학습한 기술들
- **MultiOutputRegressor**: 단일 모델로 여러 타겟 변수를 동시에 예측하는 방법
- **pandas 고급 기능**: 날짜 기준 DataFrame 병합, 복잡한 결측치 처리
- **Google Colab 한글 처리**: 한글 폰트 설정 및 matplotlib 한글 출력 해결
- **상관관계 분석**: 히트맵을 통한 변수 간 관계 시각화

---

## 🛠 기술 스택

### 🐍 Data Analysis & ML
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)

### 📊 Visualization
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=python&logoColor=white)

### 🛠 Development Environment
![Google Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=google-colab&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white)

### 🗄 Data Sources
![서울 공공데이터](https://img.shields.io/badge/서울시_공공데이터-0066CC?style=for-the-badge)
![기상청 데이터](https://img.shields.io/badge/기상청_KMA-0066FF?style=for-the-badge)

### 📋 기술 선택 이유
- **Python**: 데이터 분석에 최적화된 라이브러리 생태계
- **RandomForest**: 비선형 관계 모델링에 강하고 오버피팅에 robust한 특성
- **Google Colab**: 무료 GPU 사용 가능, 협업 및 공유 용이
- **pandas**: 시계열 데이터 처리 및 병합에 강력한 기능 제공

---

## 📁 프로젝트 구조

```
seoul-mosquito-forecast/
├── data/
│   ├── raw/                    # 원본 데이터
│   │   ├── mosquito_data.csv   # 서울시 모기예보 데이터
│   │   └── weather_data.csv    # 기상청 날씨 데이터
│   ├── processed/              # 전처리된 데이터
│   │   └── merged_data.csv     # 병합된 최종 데이터
│   └── results/                # 분석 결과
│       ├── predictions.csv     # 예측 결과
│       └── model_scores.csv    # 모델 성능 지표
├── notebooks/
│   ├── 01_data_exploration.ipynb     # 탐색적 데이터 분석
│   ├── 02_data_preprocessing.ipynb   # 데이터 전처리
│   ├── 03_model_training.ipynb       # 모델 훈련 및 평가
│   └── 04_visualization.ipynb        # 시각화 및 분석
├── src/
│   ├── data_loader.py          # 데이터 로딩 함수
│   ├── preprocessor.py         # 전처리 함수들
│   ├── model.py               # 모델 정의 및 훈련
│   └── visualizer.py          # 시각화 함수들
├── images/                    # 프로젝트 이미지들
│   ├── correlation_heatmap.png
│   ├── prediction_results.png
│   └── data_distribution.png
├── docs/
│   ├── presentation.pdf       # 프레젠테이션 자료
│   └── analysis_report.md     # 분석 보고서
└── README.md
```

### 주요 파일 설명
- `notebooks/`: 단계별 분석 과정을 담은 Jupyter 노트북들
- `src/`: 재사용 가능한 함수들을 모듈화
- `data/`: 원본부터 최종 결과까지 모든 데이터 관리
- `images/`: 분석 결과 시각화 이미지들

---

## 🔍 프로젝트 회고

### 😊 잘한 점
- **체계적 접근**: 단계별로 체계적인 데이터 분석 프로세스를 적용
- **실무적 경험**: 실제 공공데이터를 활용한 현실적인 문제 해결 경험
- **기술적 성장**: MultiOutput 회귀, 복잡한 데이터 전처리 등 새로운 기술 습득
- **문제 해결**: Google Colab 한글 폰트 문제 등 실무에서 발생할 수 있는 이슈들을 직접 해결

### 😅 아쉬운 점
- **데이터 수집 범위**: 더 다양한 환경 요인 데이터와 서울시 모기예보제의 짧은 데이터로 인한 아쉬움
- **모델 다양성**: RandomForest 외에 다른 알고리즘(XGBoost, LSTM 등)과의 성능 비교 부족
- **실시간 예측**: 실시간 데이터 수집 및 예측 시스템 구축까지는 진행하지 못함
- **검증 데이터**: 모델 예측 결과의 실제 정확도 검증을 위한 추가 데이터 부족

### 🚧 개발 중 겪은 어려움과 해결과정
1. **CSV 파일 날짜 병합 문제**
   - **문제**: 두 데이터셋의 날짜 형식이 달라 병합 시 오류 발생
   - **해결**: pandas의 to_datetime() 함수를 활용해 날짜 형식 통일 후 merge() 적용
   
2. **Google Colab 한글 폰트 렌더링**
   - **문제**: matplotlib에서 한글이 깨져서 나타나는 문제
   - **해결**: 나눔글꼴 설치 및 matplotlib 폰트 설정 변경으로 해결

3. **결측치 처리 전략**
   - **문제**: 다양한 유형의 결측치에 대한 최적 처리 방법 선택의 어려움
   - **해결**: 변수별 특성을 고려해 보간법, 평균값 대체, 삭제 등 차별적 적용

### 📚 새로 배운 것들
- **MultiOutput 회귀**: 여러 타겟을 동시에 예측하는 모델 구현 방법
- **공공데이터 활용**: 실제 공공데이터의 특성과 전처리 노하우
- **상관관계 분석**: 히트맵을 통한 변수 간 관계 파악 및 해석
- **모델 평가**: 회귀 모델의 다양한 성능 지표 활용법

---

## 💭 프로젝트 후기

### 🎯 개인적인 소감
> "처음으로 공공데이터를 활용한 본격적인 데이터 분석 프로젝트를 진행했는데, 이론으로만 배웠던 머신러닝을 실제 문제에 적용하는 뜻깊은 경험이었습니다. 특히 데이터 전처리의 중요성과 실무에서 발생할 수 있는 다양한 이슈들을 직접 경험하며 많은 것을 배웠습니다. MultiOutput 회귀를 통해 효율적으로 여러 지역의 모기 발생량을 동시에 예측할 수 있다는 점이 가장 흥미로웠습니다."

### 🎓 성장한 부분
- **데이터 처리 역량**: 복잡한 실제 데이터의 전처리 및 병합 기술 향상
- **머신러닝 실무**: 이론을 실제 문제에 적용하는 실무 경험 축적
- **문제 해결 능력**: 예상치 못한 기술적 문제들을 스스로 해결하는 능력 향상
- **프로젝트 관리**: 단계별 체계적 접근과 문서화 습관 형성

### 🚀 향후 개선 계획
- [ ] **모델 고도화**: XGBoost, LSTM 등 다양한 알고리즘 적용 및 앙상블 기법 도입
- [ ] **추가 데이터 확보**: 미세먼지, 습도, 풍속 등 추가 환경 요인 데이터 수집
- [ ] **실시간 예측 시스템**: API를 통한 실시간 데이터 수집 및 예측 시스템 구축
- [ ] **웹 애플리케이션 개발**: 협업을 통해 일반 사용자가 쉽게 활용할 수 있는 웹 인터페이스 구현

### 🎯 다음 프로젝트 계획
이 프로젝트의 경험을 바탕으로 **"농수산물 가격 예측 모델"**을 다음 목표로 설정했습니다. 마찬가지로 공공데이터를 활용하되, 시계열 분석과 딥러닝 기법을 더 깊이 있게 적용해보고 싶습니다.

---

### 데이터 준비
1. [서울 열린데이터 광장](https://data.seoul.go.kr)에서 모기예보 데이터 다운로드
2. [기상청 기상자료개방포털](https://data.kma.go.kr)에서 날씨 데이터 다운로드
3. `data/raw/` 폴더에 데이터 파일 배치

---

## 📞 문의사항

프로젝트에 대한 문의사항이나 개선 제안이 있으시면 언제든지 연락주세요!

**GitHub**: [@your-username](https://github.com/your-username)  
**이메일**: alseo0110@naver.com  
**Issues**: [Issues 페이지](https://github.com/your-username/seoul-mosquito-forecast/issues)

---

## 🏆 관련 성과
- 개인 포트폴리오 프로젝트 완성
- 데이터 분석 역량 향상
- 공공데이터 활용 경험 축적

---

<div align="center">

**⭐ 이 프로젝트가 도움이 되셨다면 Star를 눌러주세요! ⭐**

</div>
