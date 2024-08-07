# 📈 정형-비정형 데이터를 활용한 연방준비제도 기준 금리 예측 🙂

본 프로젝트는 MLP 금융&마케팅 데이터분석 17기 세미 프로젝트로 진행되었습니다.

---

## 📑 목차 (Table of Contents)
- [**프로젝트 개요**](#프로젝트-개요)
  - [기획 배경](#기획-배경)
  - [프로젝트 목표](#프로젝트-목표)
  - [구성원 및 역할](#구성원-및-역할)
  - [프로젝트 기간](#프로젝트-기간)
- [**프로젝트 수행 절차 및 방법**](#프로젝트-수행-절차-및-방법)
- [**기대 효과**](#기대-효과)
  - [인사이트 도출](#인사이트-도출)
  - [향후 개선 사항 및 기대효과](#향후-개선-사항-및-기대효과)
- [**사용된 기술 스택**](#사용된-기술-스택)

---

## 프로젝트 개요

### 기획 배경
연방준비제도(Federal Reserve, Fed)의 **기준 금리**는 세계 경제에 중대한 영향을 미치는 핵심 요소입니다. 금리 변동은 글로벌 경제 안정성과 금융 시장에 직접적인 영향을 끼치기 때문에, 이를 예측하는 것은 경제정책 수립과 투자 전략에 있어 매우 중요합니다.

### 프로젝트 목표
이 프로젝트의 주요 목표는 다음과 같습니다:
1. **연방준비제도 기준 금리의 변동을 예측**할 수 있는 모델을 개발
2. **기준 금리에 영향을 미치는 주요 경제 요인**을 분석하고 탐색

이를 통해 우리는 **경제 안정화 정책**과 **금융 시장 예측**에 기여할 수 있는 인사이트를 제공하고자 합니다.

### 구성원 및 역할
- [**김동현**](https://github.com/superdupermulti17): 회귀분석을 사용하여 기준 금리에 영향을 미치는 요인의 인과관계 탐색
- [**김주성**](https://github.com/kimjuseong-99): 비정형 데이터(Beige Book) 크롤링, EDA, 모델링, 평가 및 예측
- [**백동열**](https://github.com/dybaek9): 정형 데이터 크롤링 및 전처리, 정형/비정형 데이터 통합, EDA, 모델링, 평가 및 예측
- [**서웅진**](https://github.com/UngJinSeo): 비정형 데이터(Beige Book) 크롤링, EDA, 모델링, 평가 및 예측

### 프로젝트 기간
- **2024년 7월 25일 ~ 2024년 8월 9일**

---

## 프로젝트 수행 절차 및 방법

1. **데이터 수집 및 전처리**
   - **정형 데이터 수집**: 연준 기준 금리, 실질 GDP 성장률, 실업률, 개인 소비 지출(PCEPI), 명목이자율(미국 국채 10년물), 한은 USD환율, 한은 기준 금리, ECB 기준 금리 등 다양한 경제 지표 데이터를 수집하였습니다.
   - **비정형 데이터 수집**: Beige Book의 텍스트 데이터를 수집하여 감정 분석을 수행하였습니다.
   - **데이터 전처리**: 정형 데이터는 일자 기준으로 1차 가공한 후, 매월 말 데이터를 매월 초일 기준으로 2차 가공하였으며, 비정형 데이터는 감정 점수를 컬럼화하여 정형 데이터와 결합하였습니다.

2. **데이터 분석**
   - **텍스트 데이터 전처리 및 분석**: 소문자 변환, 불필요한 문자 제거, 불용어 제거 및 감정 분석을 통해 긍정, 중립, 부정 점수를 추출하였습니다.
   - **EDA (탐색적 데이터 분석)**:
     - 정형 데이터: 각 요인의 추세 시각화, 상관관계 분석, 회귀 분석을 통해 데이터 간의 관계를 분석했습니다.
     - 비정형 데이터: 단어 바이그램 빈도, 문서 길이 분포, WordCloud를 통해 텍스트 데이터를 분석했습니다.

3. **모델링 및 평가**
   - **모델링 기법**: SimpleRNN, CNN, LSTM, MLP, 선형 회귀 모델을 사용하여 데이터의 패턴을 학습하고 예측을 수행했습니다.
   - **모델링 결과**: LSTM 모델은 시계열 데이터에서 높은 예측 성능을 보였으며, MLP 모델은 복잡한 비선형 관계를 잘 처리하여 분류 문제를 효과적으로 해결했습니다.

---

## 기대 효과

### 인사이트 도출
- **연방준비제도 기준 금리와 관련된 주요 요인**: 소비자 지출 지수(PCEPI)와 유럽 중앙은행 기준 금리(ECB_IR)는 연방준비제도 기준 금리에 밀접한 관련이 있는 주요 요인으로 확인되었습니다.
- **시간에 따른 금리 변동 예측**: LSTM 모델을 활용하여 금리 변동을 예측하고, 주요 경제 지표의 영향을 분석했습니다.
- **경제 지표 간의 관계 파악**: 주요 경제 지표(예: 실업률, GDP 성장률 등)와 금리 간의 상관관계를 분석하여, 실업률이 증가할 때 금리가 하락하고, GDP 성장률이 높을 때 금리가 상승하는 패턴을 파악했습니다.

### 향후 개선 사항 및 기대효과
- **데이터의 추가 확보**: 더 많은 경제 지표와 최신 데이터를 확보하여 모델의 예측 성능을 향상시킬 수 있습니다. 특히 전 세계 경제 데이터나 더 많은 기간의 데이터를 포함하면 더 정확한 예측이 가능합니다.
- **모델의 복잡도 조정**: LSTM 및 MLP 모델의 하이퍼파라미터를 조정하거나 더 깊은 신경망을 사용하여 모델의 복잡도를 높임으로써 예측 정확도를 개선할 수 있습니다.
- **모델 앙상블**: 여러 모델을 앙상블(결합)하여 각 모델의 강점을 활용하는 예측 방법을 도입할 수 있습니다. 이를 통해 예측의 안정성을 높이고 다양한 시나리오에서의 성능을 개선할 수 있을 것입니다.
- **해석 가능성 향상**: 복잡한 모델의 해석 가능성을 높이기 위해 SHAP(Shapley Additive Explanations)이나 LIME(Local Interpretable Model-agnostic Explanations) 같은 해석 도구를 사용할 수 있습니다.

---

## 사용된 기술 스택

- **프로그래밍 언어**: ![Python](https://img.shields.io/badge/python-v3.8-blue)
- **데이터 처리 및 분석**:
  - Pandas
  - NumPy
  - Scikit-learn
- **텍스트 분석**:
  - NLTK (Natural Language Toolkit)
  - TextBlob
- **모델링 및 딥러닝**:
  - TensorFlow (with Keras)
    - 사용된 모델: LSTM, CNN, SimpleRNN, MLP 등
- **시각화**:
  - Matplotlib
  - Seaborn
- **데이터 크롤링**:
  - BeautifulSoup
  - Selenium
