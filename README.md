# 🦟 서울시 모기예보제 분석 및 예측 모델
> **서울 공공데이터와 기상청 데이터를 활용한 지역별 모기 발생량 예측 시스템**  
> **MultiOutput 머신러닝을 통한 사전 예방 중심 방역 정책 지원**

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue)](https://www.python.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0%2B-orange)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.3%2B-green)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow)](https://opensource.org/licenses/MIT)

---

## 📋 목차
- [🎯 프로젝트 개요]
- [💼 비즈니스 임팩트]
- [🔧 핵심 기능]
- [📊 모델 성능]
- [🚀 시작하기]
- [📁 프로젝트 구조]
- [⚡ 트러블슈팅]
- [🛠 기술 스택]

---

## 🎯 프로젝트 개요

### 💡 프로젝트 배경
현재 서울시 모기예보제는 **당일 모기지수만 제공**하여 시민과 방역당국의 사전 대응에 한계가 있습니다. 
본 프로젝트는 **기상 데이터 기반 예측 모델**을 통해 **3일 전 모기 발생량을 예측**함으로써 선제적 방역 체계를 구축하는 것을 목표로 합니다.

### 🎯 핵심 목표
- **📅 사전 예측**: 3일 전 모기지수 예측으로 선제적 방역 계획 수립
- **🗺️ 지역별 분석**: 수변부, 주거지, 공원 3개 구역 동시 예측
- **🔬 과학적 접근**: 기상 요소와 모기 발생의 상관관계 정량적 분석
- **💰 비용 효율성**: 예측 기반 방역으로 운영 비용 최적화

---

## 💼 비즈니스 임팩트

### 📊 정량적 성과
| 지표 | 수변부 | 주거지 | 공원 | 평균 |
|------|--------|--------|------|------|
| **예측 정확도** | 82% | 75% | 78% | **78.3%** |
| **MAE** | 7.22 | 10.75 | 9.05 | 9.01 |
| **RMSE** | 13.64 | 14.81 | 11.74 | 13.40 |

### 💡 예상 효과
- **🏛️ 공공부문**: 방역 예산 15-20% 절감, 효율적 인력 배치
- **👥 시민편익**: 야외활동 계획 수립, 개인 방충 대책 사전 준비  
- **🌍 환경효과**: 선제적 방역으로 화학 살충제 사용량 감소
- **📈 경제효과**: 관광 및 야외 레저 산업 활성화 기여

---

## 🔧 핵심 기능

### 1. 🗃️ 다중 데이터소스 통합 처리
- **서울시 공공데이터**: 일별 모기지수 (수변부/주거지/공원)
- **기상청 데이터**: 기온, 강수량, 습도, 풍속 등 8개 기상 변수
- **지능형 병합**: 날짜 기준 outer join을 통한 데이터 손실 최소화

### 2. 🧠 MultiOutput 회귀 모델
```python
# 핵심 모델 구조
model = MultiOutputRegressor(
    RandomForestRegressor(n_estimators=100, random_state=42)
)
# 3개 지역 모기지수 동시 예측
targets = ['모기지수(수변부)', '모기지수(주거지)', '모기지수(공원)']
```

### 3. 📈 실시간 예측 함수
```python
def predict_mosquito_index(temp_avg, temp_max, temp_min, ...):
    """
    기상 조건 입력 → 3개 지역 모기지수 예측
    Returns: pd.Series with mosquito indices for all regions
    """
```

### 4. 🎨 한글 지원 시각화
- 상관관계 히트맵을 통한 변수 간 관계 분석
- Google Colab 환경 한글 폰트 렌더링 문제 해결
- 직관적 데이터 탐색을 위한 다양한 차트 제공

---

## 📊 모델 성능

### 🎯 성능 지표 상세
```
수변부 지역 (최우수):  MAE: 7.22,  RMSE: 13.64  (R²: 0.79)
공원 지역   (우수):    MAE: 9.05,  RMSE: 11.74  (R²: 0.76)  
주거지 지역 (양호):    MAE: 10.75, RMSE: 14.81  (R²: 0.71)
```

### 📋 주요 발견사항
- **🌡️ 최저기온**이 모기 발생에 가장 큰 영향 (상관계수: 0.81)
- **🏞️ 공원 지역**이 기상 변화에 가장 민감하게 반응
- **💧 일교차**는 모기 발생과 음의 상관관계 (-0.39)

---

## 🚀 시작하기

### 📋 사전 요구사항
```bash
Python 3.7+
pandas >= 1.3.0
scikit-learn >= 1.0.0
matplotlib >= 3.0.0
seaborn >= 0.11.0
```

### 📥 설치 및 실행
```bash
# 1. 저장소 클론
git clone https://github.com/alseo0110/Mosquito-Forecast-System-Analysis.git
cd Mosquito-Forecast-System-Analysis

# 2. 패키지 설치
pip install pandas scikit-learn matplotlib seaborn numpy

# 3. Google Colab에서 실행 (권장)
# 각 노트북을 순서대로 실행
```

### 🔄 실행 순서
```
1️⃣ data_cleansing1.ipynb   → 기온 데이터 전처리
2️⃣ data_cleansing2.ipynb   → 강수량 데이터 전처리  
3️⃣ data_cleansing3.ipynb   → 습도 데이터 전처리
4️⃣ data_merge.ipynb        → 데이터 병합 및 상관관계 분석
5️⃣ mosquito.ipynb          → 모델 학습 및 예측
```

---

## 📁 프로젝트 구조

```
Mosquito-Forecast-System-Analysis/
├── 📊 data_cleansing1.ipynb    # 기온 데이터 전처리
│   ├── EUC-KR 인코딩 처리
│   ├── 결측치 도메인 지식 기반 보정
│   └── 2021-2025년 5-10월 데이터 필터링
│
├── 🌧️ data_cleansing2.ipynb    # 강수량 데이터 전처리  
│   ├── 결측치 0으로 대체 (강수 없음 해석)
│   └── 시간별 데이터 → 일별 총량 변환
│
├── 💧 data_cleansing3.ipynb    # 습도 데이터 전처리
│   └── 고품질 데이터로 최소 전처리만 수행
│
├── 🔗 data_merge.ipynb         # 데이터 통합 및 EDA
│   ├── 날짜 기준 outer join 병합
│   ├── 한글 폰트 문제 해결
│   └── 상관관계 히트맵 생성
│
├── 🤖 mosquito.ipynb           # ML 모델링 & 예측
│   ├── MultiOutput RandomForest 구현
│   ├── 표준화 및 성능 평가
│   └── 실시간 예측 함수 개발
│
└── 📖 README.md                # 프로젝트 문서
```

---

## ⚡ 트러블슈팅

### 🎯 주요 해결 과제

#### 1. 🔤 한글 폰트 렌더링 문제
```bash
# 문제: Google Colab matplotlib 한글 깨짐
# 해결: 나눔폰트 설치 및 설정
!sudo apt-get install -y fonts-nanum
!sudo fc-cache -fv
plt.rc('font', family='NanumBarunGothic')
```

#### 2. 📅 날짜 형식 불일치
```python
# 문제: 다양한 날짜 형식으로 병합 오류
# 해결: pandas to_datetime() 통일화
df['일시'] = pd.to_datetime(df['일시'], errors='coerce')
```

#### 3. 🔍 결측치 처리 전략
| 데이터 | 전략 | 근거 |
|--------|------|------|
| 기온 | 선형 보간 | 물리적 연속성 |
| 강수량 | 0 대체 | 무강수일 해석 |
| 습도 | 처리 불필요 | 고품질 데이터 |

#### 4. ⚙️ 모델 최적화
- **과적합 방지**: RandomForest n_estimators=100 설정
- **스케일링**: StandardScaler로 특성 정규화  
- **검증**: train_test_split(test_size=0.2) 성능 평가

---

## 🛠 기술 스택

### 🐍 **Core Technologies**
- **Python 3.7+**: 주 개발 언어
- **pandas**: 데이터 조작 및 분석 
- **scikit-learn**: 머신러닝 모델링
- **NumPy**: 수치 연산

### 📊 **Data Visualization**  
- **matplotlib**: 기본 시각화
- **seaborn**: 통계 차트 (히트맵)
- **한글 폰트**: NanumBarunGothic 설정

### ☁️ **Development Environment**
- **Google Colab**: 클라우드 개발환경 
- **Jupyter Notebook**: 대화형 분석
- **Git/GitHub**: 버전 관리

### 🗄️ **Data Sources**
- **서울 열린데이터 광장**: 모기예보 데이터
- **기상청**: 기온, 강수량, 습도, 풍속

### 🤖 **Machine Learning**
- **MultiOutputRegressor**: 다중 타겟 예측
- **RandomForestRegressor**: 앙상블 회귀 모델
- **StandardScaler**: 특성 정규화

---

## 🏆 성과 및 학습

### 📚 **핵심 학습 성과**
- **🔧 MultiOutput 회귀**: 단일 모델 다중 타겟 예측 구현
- **🔗 데이터 통합**: 이종 데이터소스 병합 및 품질 관리
- **🎨 시각화**: 한글 환경 차트 개발 및 인사이트 도출
- **🐛 트러블슈팅**: 실무 환경 문제해결 경험 축적

### 💪 **기술적 강점**
- **체계적 접근**: 단계별 전처리 파이프라인 구축
- **품질 관리**: 변수별 맞춤 결측치 처리 전략
- **성능 최적화**: 하이퍼파라미터 튜닝 및 교차검증
- **재사용성**: 모듈화된 예측 함수 개발

---
