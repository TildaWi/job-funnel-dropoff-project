# 🧑‍💼 채용 플랫폼 '지원 비완료 탐색 유저' 이탈 개선 프로젝트

### 분석 카테고리: 프로덕트 데이터 분석
> **분석 기간** &nbsp;|&nbsp;  2025.04.04 - 2025.04.28 <br/>
> **분석 주체** &nbsp;|&nbsp;  팀 프로젝트 (팀원: 양태호, 최명빈, 유정원, 위이태인) <br/>
> **분석 기법** &nbsp;|&nbsp;  페르소나 기법, 퍼널 분석 방법, 유저 여정 분석, A/B Test 설계 <br/>
> **분석 기술** &nbsp;|&nbsp;  <img src="https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white"/> <img src="https://img.shields.io/badge/Numpy-013243?style=flat&logo=numpy&logoColor=white"/> <img src="https://img.shields.io/badge/Matplotlib-004D7A?style=flat&logo=matplotlib&logoColor=white"/> <img src="https://img.shields.io/badge/Seaborn-5A5AA5?style=flat&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/Plotly-3F4F75?style=flat&logo=plotly&logoColor=white"/> <img src="https://img.shields.io/badge/Scipy-8CAAE6?style=flat&logo=scipy&logoColor=white"/> <img src="https://img.shields.io/badge/Koreanize_Matplotlib-FF9900?style=flat&logo=python&logoColor=white"/>

---

## 0. 프로젝트 구성 안내

### 📂 디렉토리 구조

```plaintext
📁 job_funnel_analysis_project/
 ┣ 📁 notebooks/         분석 코드 (Colab)
 ┣ 📁 images/            시각화 결과 (유저 여정, 체류시간 등)
 ┣ 📁 reports/           요약 보고서 및 발표자료 (PDF)
 ┣ 📄 README.md          프로젝트 설명 문서
 ┗ 📄 requirements.txt   사용한 Python 패키지 목록
```

---

## 1. 프로젝트 개요

### 📌 세 줄 요약
- 채용 플랫폼에서 유저 539명의 전환 흐름을 분석해 이탈 원인을 파악했습니다.  
- 로그 데이터를 기반으로 탐색 > 클릭 > 지원 흐름의 병목 구간을 진단했습니다.  
- 전환율 개선을 위한 UX 제안과 A/B 테스트 설계를 통해 실행 가능성까지 검토했습니다.  

---

## 2. 문제 정의 및 접근 방식

### 🔍 Situation
- 구직 서비스에서 공고 조회 수는 많지만 클릭률이 낮고, 지원까지의 전환율도 저조한 문제가 발생  

### 💡 Task  
- 탐색 → 공고 클릭 → 지원으로 이어지는 유저 전환 퍼널을 정의하고, 이탈이 심한 구간의 원인을 분석  

### 🏃 Action
- 로그 기반 유저 행동 흐름 분석, 클릭률 저하 요인별 가설 수립 및 통계적 검정, 개선 제안 및 A/B 테스트 설계  

### 🚀 Result
- 공고 매체 및 구성요소, 체류시간 기반의 정량적 이탈 원인 도출 및 UX 기반 개선 전략 도출

---

## 3. 프로젝트 진행

### 3-1) 📊 데이터 전처리

- 유저 로그 데이터 URL 분류

  ![데이터 전처리](images/user_log.png)

---

### 3-2) 🧪 가설 검정

단계별 현황 파악을 위해 설정한 주요 가설
- 개인 이력서에 대한 확인 및 수정이 잦은 유저의 경우 이탈률이 낮다(V)
- 단계별 체류시간이 짧을수록 다음 단계로의 전환이 낮다(V)
- 지원 공고에 대한 클릭이 적은 유저는 다음 단계로의 전환이 낮다(V)
- 관련 공고 불러오기 클릭이 잦을수록 다음 단계로의 전환이 높다(V)
- 북마크 빈도가 높을수록 다음 단계 전환이높다(X)
- 채용 기업의 규모에 따른 전환 차이가 있다 (X)

  ![가설 검정](images/hypothesis_test_results.png)

---

### 3-3) 🎞️ 분석 프레임워크 

#### 페르소나 기법
- 페르소나 설정

  ![페르소나](images/persona.png)

#### 퍼널 분석 방법
- URL, 시간, 공고 수 등의 특성을 기반으로 탐색 행동을 세분화

  ![퍼널 분석 단게](images/funnel_step.png)

- 각 단계별 전환율 분석 결과, **3단계 (탐색 → 공고 클릭)** 구간에서 이탈률이 가장 높음

  ![퍼널 단계별 전환율/이탈률](images/funnel_conversion_rate.png)

#### A/B Test 설계
- A/B Test 설계표

  ![A/B 테스트 설계](images/ab_test_plan.png)

---

## 4. 프로젝트 회고
### ✏️ Learned Lessons
- 유저 퍼널 분석은 단순한 페이지뷰가 아닌 **행동 흐름과 의도**에 기반해야 함을 깨달음  
- 체류 시간과 클릭률 간의 관계에서 **UX 피드백과 데이터 지표 해석이 함께 필요**함을 실감  
- 데이터를 기반으로 **A/B 테스트 안까지 연결된 인사이트 도출**을 연습해본 의미 있는 경험이었음  
