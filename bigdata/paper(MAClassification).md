# 형태소 분석을 통한 비정형 데이터 분류 연구

## 비정형 데이터 분류를 위한 분석 모델 설계 및 검증

### 데이터 셋 생성 과정
크롤링을 통한 데이터 수집(dbpia 논문 요약, 주제어 및 부주제어)

-> 데이터베이스 생성 with KoNLP 데이터 사전

-> 형태소 분석 with 토큰화

-> 명사 추출 with KAIST 9품사 분류 체계

-> TF-IDF 값 생성

-> Y 값에 결합하여 분석 데이터 셋 생성(+ 상관관계 분석)

### 분류의 적정성 측정
분석 데이터 셋에 알고리즘 적용
1. 랜덤 포레스트
2. 서포트 벡터머신
3. 의사결정트리


### The Proposed Scheme

1. Data Collection
2. Tokenization
3. Characteristic Analysis
4. Analytical Model

## Implementation and Testing

1. Collecting thesis data and creating a database
2. Word tokenization and data Preconfiguration
3. Analyze attributes by classification and organize analysis data sets
4. Classification model validation
5. Analysis Result
6. 

