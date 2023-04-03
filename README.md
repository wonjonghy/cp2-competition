- augment_csv: 각 레이블 별 증강한 문장이 들어있음. non_aug(극성-미정)와 pred_aug(유형-예측)의 경우에 카테고리 수가 극히 적어 따로 역번역으로 증강했으며 역번역 문장이 포함되어 있음.
나머지는 rs,rd를 적용하여 증강했음. (aug_rs_rd.ipynb 참고)

- aug_rs_rd.ipynb: rs, rd 증강에 이용한 라이브러리와 함수가 있습니다.

- baseline_each: 증강 전후 비교용

- df_aug: pd.concat과 drop_duplicates()로 기존 문장과 증강문장을 포함시킨 데이터 프레임. 레이블마다 불균형 정도가 달라서 따로 증강해야겠다 싶어서 이렇게 했는데 이걸 통째로 모델에 넣지는 못해서 수정 예정. 

- requirements.txt: pip install -r requirements.txt