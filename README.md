# diabetes_CAD_prediction
Predicting the risk of coronary artery disease(CAD) onset in diabetes patients using the MIMIC-IV dataset and an undersampling-based model

1. MIMIC-IV 데이터 추출 및 정제
   ### extract_query_5
   ### extract_total_query

2. 데이터 전처리
   ### dataset_preprocessing.ipynb

3. 최종 데이터셋
   ### daiv_dataset_final_final_preprocessed

4. 5가지 모델에 훈련 후 성능 확인
   ### Model_5_train.ipynb

5. BalancedBagging 하이퍼파라미터 튜닝
```python

classifier = BalancedBaggingClassifier(
    random_state=0,
    n_estimators=400,
    max_features=0.75,
    sampling_strategy=0.7,
    base_estimator=DecisionTreeClassifier(
        max_depth=20,
        min_samples_split=10,
        min_samples_leaf=5,
        max_features=0.75,
        class_weight={0: 1.0, 1: 0.7}
    )
)
```

6. XGBoost와 BalancedBagging 비교
   ### XGBoost_train.ipynb

7. feature selection을 통한 최종 모델링 코드
   ### BalancedBagging_selected
