- aug_rs_rd_tot.ipynb: 데이터 증강함수가 들어있는 코드.

- augment_csv: 각 레이블 별 증강한 문장이 들어있음. non_aug(극성-미정)와 pred_aug(유형-예측)의 경우에 카테고리 수가 극히 적어 따로 역번역으로 증강했으며 역번역 문장이 포함되어 있음.(trans_aug.csv)
나머지는 rs,rd를 적용하여 증강했음. (aug_rs_rd.ipynb 참고) df_train_aug와 df_val_aug는 각각 훈련 세트와 검증 세트를 3배 증강한 자료, df_train_aug, df_val_aug는 4배 증강한 자료.

- CP2_colab.ipynb: 코랩에서 프로젝트 진행 중 데이터 전처리와 은닉상태벡터를 만드는 과정이 있음.

- CP2_model_colab.ipynb: 코랩에서 프로젝트 진행 중 다양한 모델 변형을 시도한 과정이 있음.

- requirements.txt: pip install -r requirements.txt