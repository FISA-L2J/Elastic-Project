# 💳 우리카드 데이터 분석: 세대별 소비 패턴 및 우량 고객 유치 전략

**ELK Stack & DuckDB를 활용한 대용량 결제 데이터 기반 마케팅 인사이트 도출**


## 1. 👤 팀원 소개

| <img src="https://github.com/YongwanJoo.png" width="150"> | <img src="https://github.com/woojinni.png" width="150"> | <img src="https://github.com/chaeyuuu.png" width="150"> |
| :---: | :---: | :---: |
| **주용완** | **장우진** | **이채유** |
| [@YongwanJoo](https://avatars.githubusercontent.com/YongwanJoo) | [@woojinni](https://github.com/woojinni) | [@chaeyuuu](https://github.com/chaeyuuu) |

<br>


## 2. ⚙️ 기술 스택
* **Database:** `DuckDB`
* **Search & Analytics:** `Elasticsearch`
* **Visualization:** `Kibana`
* **Collaboration:** `GitHub`, `Slack`


<br>
<br>


## 3. 📉 카드사 동향 파악

* **수익성 하락:** 고금리로 인한 조달 비용 상승 및 가맹점 수수료 인하 압박
* **건전성 악화:** 우리카드 등 주요 카드사의 장기 연체율 급증(전년 대비 약 449% 증가 사례 등)으로 리스크 관리 비상

<br>

**전략적 벤치마킹: 현대카드 PLCC**
* **데이터 동맹:** 현대카드는 특정 브랜드와 결합한 PLCC(제휴 카드)를 통해 우량 고객을 선점하고 마케팅 비용을 효율화함
* -> 우리카드 또한 데이터 기반의 **'우량 고객(VIP) 선별 유치'** 와 **'타겟형 PLCC'** 도입이 필수적

<br>
<br>

## 4. 📊 데이터 분석 결과 및 인사이트 제시

### ⚙️ 데이터 전처리 
* **DuckDB**를 활용해 로컬에서 SQL로 데이터를 가공

<br>

### ✅ Case 1: 연령 별 소비 분야에 따른 PLCC 제안
전 세대 공통으로 '식당' 소비 비중이 높았으나, 세대별로 차이를 보이는 항목 존재

| 연령대 | 핵심 키워드 | 주요 소비 업종|
| :--- | :--- | :--- |
| **20대** | **경험/여행** | 여행 (TRVL_AM) |
| **40대** | **자녀/교육** | 학원 (ACDM_AM)  |
| **60대** | **건강/의료** | 병원 (HOS_AM)  |


-> 분석 결과 도출된 세대별 페르소나를 바탕으로 3가지 특화 모델 제안

<br>
<br>

1. **[20대] 아고다 X 우리카드:** 해외여행 및 숙박 특화 카드
<img width="720" height="483" alt="image" src="https://github.com/user-attachments/assets/badadf3b-bd6f-440e-8368-a76316f6b0c7" />

<br>
<br>

2. **[40대] 시대인재N X 우리카드:** 교육비 혜택 카드
<img width="719" height="215" alt="image" src="https://github.com/user-attachments/assets/e28cccf0-e239-4f28-85ad-ac3d6b2b19a7" />

<br>
<br>

3. **[60대] 의료 건강 카드:** 병원/약국 할인 및 건강보험료 지원 혜택 카드
<img width="720" height="483" alt="image" src="https://github.com/user-attachments/assets/e9449c82-5a74-4aaa-b27f-1743ce637465" />

<br>
<br>

### ✅ Case 2: VIP 등 우량 고객(VIP) 집중 분석
수익성이 높은 40대 VIP/VVIP 고객을 라이프 스테이지별로 세분화하여 분석

<img width="720" height="556" alt="image" src="https://github.com/user-attachments/assets/fcc0b3ba-c1c7-4c72-8620-e7e74d54e4ff" />

* **자녀 동반 그룹 (CHILD_TEEN):** **44.26%** (기존 40대 혜택인 '학원' 중심 소비)
* **자녀 미동반/독립 그룹:** **약 31~35%** (교육비 대신 여가 및 프리미엄 소비 집중)
* **핵심 인사이트:** * 자녀가 없는 40대 VIP 그룹 중 **`GOLLIFE`** 비중이 **32.23%** 로 상당한 비율을 차지함
    * 이들은 교육비 지출이 없는 대신 **총 이용 금액(`TOT_USE_AM`)** 이 타 그룹 대비 월등히 높은 **'핵심 우량 고객'**

<br>

-> 이들을 집중 공략하기 위해 **백화점/면세점 특화 바우처와 프리미엄 멤버십 혜택**을 대폭 강화하여 타사로부터 우량 고객을 유치하는 인사이트 도출

<br>
<br>
