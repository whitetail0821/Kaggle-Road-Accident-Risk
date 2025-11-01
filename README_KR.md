
# 🏆 [Kaggle] 도로 사고 위험도 예측 경진대회 분석 (Regression)

**"복잡한 환경 데이터로부터 미세한 사고 위험도를 예측하고, 강력한 부스팅 모델을 튜닝하는 과정"**

---

## 1. 💡 프로젝트 개요 (Overview)

| 항목 | 내용 |
| :--- | :--- |
| **목표** | 도로의 지리적, 환경적 요인을 기반으로 **사고 위험도(Accident Risk)**를 예측하는 회귀(Regression) 모델 개발. |
| **성능 지표** | $\text{RMSE}$ (Root Mean Squared Error) 최소화 |
| **최고 성능** | **Public Score: 0.05566** (개인 최고 기록) |
| **최종 순위** | 2112위 (총 참가자 4083명) |
| **사용 기술** | $\text{Python}$, $\text{Pandas}$, $\text{Scikit-learn}$, $\mathbf{LightGBM}$ |

---

## 2. 🛠️ 문제 해결 과정 및 성과 (Process & Achievement)

이 프로젝트는 단순히 높은 성능을 얻는 것을 넘어, **최고 수준의 부스팅 모델을 튜닝하고 기술적 난관을 극복**하는 데 중점을 두었습니다.

### A. 데이터 전처리 및 EDA

* **변수 처리:** $\text{road\_type}$, $\text{lighting}$, $\text{time\_of\_day}$ 등 범주형 특징에 대해 $\text{One-Hot Encoding}$을 적용하여 모델 학습 준비.
* **이상치 처리:** 사고 건수($\text{num\_reported\_accidents}$)의 왜곡(Skewness)을 완화하기 위해 **로그 변환**을 시도했으나, $\text{Public Score}$에 유의미한 개선이 없어 최종 모델에서는 제외하고, 대신 하이퍼파라미터 튜닝에 집중했습니다.

### B. 베이스라인 모델 구축 및 분석

* **모델 선택:** 회귀 문제에서 뛰어난 성능을 보이는 **LightGBM**을 베이스라인 모델로 선정.
* **초기 성과:** 초기 튜닝 ($\text{learning\_rate}=0.05, \text{n\_estimators}=1000$) 후 $\text{Validation RMSE}\ \mathbf{0.0559}$ 최종 달성.
* **특징 중요도 분석:** $\mathbf{curvature}$와 $\mathbf{speed\_limit}$이 사고 위험도 예측에 가장 중요한 특징임을 확인하고, 이 특징들을 중심으로 튜닝 및 개선 방향을 설정함.


---

## 3. 🎯 핵심 교훈 및 향후 개선 방향 (Key Learnings)

이 프로젝트를 통해 복잡한 머신러닝 워크플로우를 완주하는 것 외에도 중요한 교훈을 얻었습니다.

* **튜닝의 한계 인지:** 파라미터 튜닝만으로는 $\text{0.05566}$의 성능 벽을 깨기 어렵다는 것을 확인.
* **미래 전략:** 다음 프로젝트에서는 성능을 극한으로 끌어올리기 위해 **$\mathbf{LGBM}$과 $\mathbf{XGBoost}$ 예측값을 섞는 앙상블 기법** 및 **심층적인 특징 공학**에 집중하여 $\text{RMSE}$를 더욱 낮출 계획임.

---

### 파일 구성

* `final_submission.ipynb`: 최종 모델링 및 분석 과정이 담긴 주피터 노트북 파일.
* `test.csv`, `train.csv`: (데이터셋 파일명)
