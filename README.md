## BERT 모델을 이용한 텍스트 분류
### 프로젝트 overview

- 프로젝트의 배경: DACON 문장 유형 분류 AI 경진대회 https://dacon.io/competitions/official/236037/overview/description
- 프로젝트의 목적
  - 허깅페이스 모델과 pytorch에 대한 이해도 향상
  - 실생활에서의 수많은 문장들을 효율적으로 분리하는 모델을  사용자 친화적인 서비스를 제작하는데 기여

### 프로젝트 구성
#### 프로젝트 진행 과정
- 프로젝트 기간: 2023.03.27 ~ 04.17 (24일)
- 프로젝트 도구: Pandas, Pytorch, Hugging Face, Transformers
- 프로젝트 진행 과정: 데이터 분석 -> EDA(증강 및 UnderSampling) -> 모델 선정 -> 모델 튜닝 -> 성능 측정 -> Feed Back
- 데이터셋
    - 16506 개의 뉴스 문장과 각 문장의 유형, 극성, 시제, 확실성이 레이블로 주어진 데이터
    - 평균 1.02 문장
    - 평균 64글자
    
- 방법(분석 기법, 모델 등)
    - 역번역
    - Random Swap
    - Random Deletion
    - snunlp/KR-BERT-char1642: CLS의 은닉상태 벡터와 완전연결층을 이용한 텍스트 분류
    - Focal Loss: 크로스 엔트로피 손실으로부터 심각한 불균형 데이터의 손실을 측정하기 위해 개선한 손실함수를 이용해야 했다.
    
- 프로젝트의 결과
    - 평균 0.7스코어, 150위권
    
- 프로젝트의 한계점 및 개선 방안
    - 프로젝트 한계
        - 데이터의 심각한 불균형을 해결하지 못했다. (8:1:0.6:0.4 -> 6:2:1:1)
        - 0.7스코어는 BERT 모델과 대회측에서 제공해준 BASELINE으로 제작한 모델로 나온 스코어이다. 직접 모델을 조작해서 스코어를 올리지 못했다.
    - 개선방안
        - 논문을 이해하고 구현하는 능력이 있었으면 성능을 더 올릴 수 있을 텐데 이해하고 구현하는 능력이 없다. 딥러닝에 대한 공부가 시급하다.

## 코드 정리
- aug_rs_rd_tot.ipynb: 데이터 증강함수가 들어있는 코드.

- augment_csv: 각 레이블 별 증강한 문장이 들어있음. non_aug(극성-미정)와 pred_aug(유형-예측)의 경우에 카테고리 수가 극히 적어 따로 역번역으로 증강했으며 역번역 문장이 포함되어 있음.(trans_aug.csv)
나머지는 rs,rd를 적용하여 증강했음. (aug_rs_rd.ipynb 참고) df_train_aug와 df_val_aug는 각각 훈련 세트와 검증 세트를 3배 증강한 자료, df_train_aug, df_val_aug는 4배 증강한 자료.

- CP2_colab.ipynb: 코랩에서 프로젝트 진행 중 데이터 전처리와 은닉상태벡터를 만드는 과정이 있음.

- CP2_model_colab.ipynb: 코랩에서 프로젝트 진행 중 다양한 모델 변형을 시도한 과정이 있음.

- requirements.txt: pip install -r requirements.txt
