# DA-ML-project-predictHSCode
데이터분석-기계학습_HSCode 예측 모델

## 💻 프로젝트 소개
기계학습을 통한 HS Code 예측 모델 개발

## 🐎 개발 기간
* 23.12.01 - 24.01.10

### 🐤 멤버구성
* 팀장 이XX : 데이터 수집, 데이터 전처리, 코사인 유사도 모델 개발
* 팀원 전XX : 데이터 수집, 데이터 전처리, LSTM 모델 개발
* 팀원 오XX : 데이터 수집, 형상 및 일정관리, PPT 제작
* 팀원 강XX : 데이터 수집, 형상 및 일정관리, 발표
* 팀원 심세현 : 데이터 수집, 데이터 전처리, LSVC 모델 개발

### ⚒ 개발환경
* Python 3.11
* Anaconda
* IDE : Jupyter Notebook

## ✅ 프로젝트 기획
일반 중소기업들은 수출입 상품의 HS 코드를 선정하는 데 어려움을 겪는 경우가 많습니다.
이러한 어려움을 해결하고 기업들에게 도움을 주기 위해 해당 프로젝트를 기획하게 되었습니다.


이전 연구들이 주로 상품명과 같은 간단한 단어로만 HS 코드를 추측했다면, 본 프로젝트는 상품명과 문장으로 된 상품 설명을 입력하면 HS 코드를 예측하는 데 초점을 맞추고 있습니다.
이를 위해 머신러닝, 딥러닝 및 코사인 유사도 등을 함께 활용하여 입력값에 대한 HS 코드를 정확히 예측하는 모델을 구현하고자 하였습니다.

## ✅ 프로젝트 과정
데이터 수집 - 데이터 전처리 - 모델링

1. 데이터 수집
   - 관세청법령정보포털의 품목불류사례 中 가장 사례가 많았던 84, 85류의 2012-2023 데이터 수집
   - selenium을 이용해 크롤링 코드 작성
   - 총 127,332개의 데이터 수집
  
2. 데이터 전처리
   - 중복행 제거, 소문자 변환 등 전처리 준비
   - stopwords를 이용해 불용어 제거
   - pos tagging을 이용해 각 단어 품사 할당
   - WordNetLammatizer를 이용해 단어의 원형 복원
   - TF-IDF를 이용해 단어의 벡터화

3. 모델링
   - 머신러닝
     - Logistic Regression : 정확도 0.813
     - RandomForest : 정확도 0.733
     - **LinearSVC : 정확도 0.914**

      ---
      
      **딥러닝과 코사인 유사도 사용 이유**
      - 딥러닝 : 사용자가 입력한 문장은 자연어이기 때문에 자연어 처리 모델 사용
      - 코사인 유사도 : 데이터의 불균형이 심했기 때문에, 데이터의 양이 적은 독립변수도 단어 사전과의 유사도 분석을 통해 예측할 수 있게 하였음
      - LSVC 모델만 단독 사용시 과적합 현상 발생
      
      ---
       
   - 딥러닝
  
   - 코사인 유사도
     - HS Code의 해설서에서 각 코드의 핵심단어를 추출해 단어 사전 완성
     - TF-IDF 학습을 통해 입력딘 문장과 단어 사전의 코사인 유사도 확인

## ✅ 프로젝트 결과
최종 LSVC / LSTM / 코사인 유사도를 조합한 ENSEMBLE MODEL : 정확도 0.847
   


