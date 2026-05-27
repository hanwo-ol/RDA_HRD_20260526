언제, 어떤 검정을, 또 어떤 시각화를 실질적으로 할 지 생각해보았습니다.

### 1. 비료 종류에 따른 작물 수확량 비교 (일원 분산분석, One-way ANOVA)

단일 농가나 연구소에서 새로운 비료를 도입할 때 가장 기본적으로 수행하는 검정입니다.

* **가설 설정**
* $H_0$: 처리한 비료 종류(A, B, C, 대조군)에 따라 작물의 평균 수확량 차이가 없다. ($\mu_A = \mu_B = \mu_C = \mu_{control}$)
* $H_1$: 적어도 하나의 비료 처리군에서 평균 수확량 차이가 존재한다.


* **검정 통계량:** $F$-통계량 (집단 간 분산과 집단 내 분산의 비율)
* **p-value 해석:** $p < 0.05$일 경우 $H_0$ 기각. 이후 Tukey 등의 사후검정을 통해 어떤 비료가 가장 우수한지 확정합니다.
* **실질적 시각화:** 박스플롯(Boxplot). 수확량의 극단값(Outlier)과 데이터의 퍼짐(분산)을 동시에 확인해야 기후 변화에도 안정적인 수확을 보장하는 비료를 선택할 수 있습니다.

### 2. 스마트팜(ICT)과 일반 노지 재배의 생산성 검증 (독립표본 t-검정)

막대한 비용이 드는 스마트팜 설비 투자의 타당성을 검증하기 위한 분석입니다.

* **가설 설정**
* $H_0$: 스마트팜 재배와 노지 재배 간의 단위 면적당 평균 생산량에 차이가 없다. ($\mu_{smart} = \mu_{open}$)
* $H_1$: 스마트팜 재배의 평균 생산량이 노지 재배보다 유의미하게 높다. ($\mu_{smart} > \mu_{open}$)


* **검정 통계량:** $t$-통계량
* **p-value 해석:** $p < 0.05$일 경우 $H_0$ 기각. 스마트팜의 경제적 효용성을 통계적으로 뒷받침합니다.
* **실질적 시각화:** 오차막대가 포함된 막대그래프(Bar chart with error bars) 또는 바이올린 플롯(Violin plot). 평균 생산량뿐만 아니라, 시설 투자로 인해 수확량의 편차(리스크)가 얼마나 줄어들었는지 직관적으로 설득해야 합니다.

### 3. 기온 변화가 작물 수확량에 미치는 영향 (단순 선형 회귀 분석)

기후 변화에 따른 식량 안보 리스크를 평가할 때 주로 사용합니다.

* **가설 설정**
* $H_0$: 생육기 평균 기온 변화는 수확량에 영향을 주지 않는다. ($\beta_1 = 0$)
* $H_1$: 평균 기온 변화는 수확량에 유의미한 영향을 준다. ($\beta_1 \neq 0$)


* **검정 통계량:** $t$-통계량 (독립변수인 기온의 회귀계수에 대한 검정)
* **p-value 해석:** $p < 0.05$일 경우 $H_0$ 기각. 온도가 1도 변할 때 수확량이 얼마나 증감하는지 정량화할 수 있습니다.
* **실질적 시각화:** 산점도와 추세선(Scatter plot with regression line). 특정 온도 구간을 넘어서면 생산량이 급감하는 임계점(Tipping point)을 보여주는 데 유용합니다.

### 4. 관수 방식 변경에 따른 토양 수분 유지력 비교 (대응표본 t-검정)

동일한 밭에 새로운 자동 관수 센서를 도입하기 전과 후를 비교합니다.

* **가설 설정**
* $H_0$: 새로운 관수 시스템 도입 전과 후의 일평균 토양 수분량 편차에 차이가 없다. ($\mu_d = 0$)
* $H_1$: 새로운 센서 도입 후 토양 수분량 편차가 줄어들어 더 일정하게 유지된다.


* **검정 통계량:** $t$-통계량
* **p-value 해석:** $p < 0.05$일 경우 $H_0$ 기각. 센서 도입 효과가 유의미함을 뜻합니다.
* **실질적 시각화:** 시계열 라인 플롯(Time-series line plot). 관수 시점 전후로 토양 수분이 얼마나 빠르게 회복되고 안정적으로 유지되는지 시간 흐름에 따라 증명해야 합니다.

### 5. 물 절약 관개 방식(AWD)과 토양 개량제 효과 (이원 분산분석, Two-way ANOVA)

가뭄 대비용 물 절약 농법이 수확량에 악영향을 주는지, 이를 개량제가 보완할 수 있는지 검증합니다.

* **가설 설정**
* $H_0$: 관개 방식(절수 vs 상시 담수)과 토양 개량제 투입 여부는 벼 수확량에 주효과 및 교호작용이 없다.
* $H_1$: 두 요인 중 하나라도 주효과가 있거나, 요인 간 상호작용(Interaction)이 존재한다.


* **검정 통계량:** $F$-통계량 (주효과 2개, 상호작용 1개)
* **p-value 해석:** $p < 0.05$일 경우 상호작용 또는 주효과가 유의미하게 존재합니다.
* **실질적 시각화:** 교호작용 플롯(Interaction plot). 물을 덜 대는 방식을 쓸 때 토양 개량제가 수확량 감소 폭을 얼마나 효과적으로 방어해주는지 선의 기울기 차이로 보여줍니다.

### 6. 유무기 비료 혼합 비율에 따른 장기 수확량 안정성 (반복측정 분산분석, Repeated Measures ANOVA)

단기적인 수확량이 아닌, 장기적인 토양 지력 회복과 수확량 유지력을 평가합니다.

* **가설 설정**
* $H_0$: 비료 처리 방식에 따라 다년간(예: 10년)의 수확량 추이 변화에 차이가 없다.
* $H_1$: 비료 처리 방식에 따라 시간이 지남에 따라 수확량 추이에 차이가 나타난다.


* **검정 통계량:** $F$-통계량
* **p-value 해석:** $p < 0.05$일 경우 $H_0$ 기각. 시간이 지날수록 유기질 비료 혼합군의 효과가 나타남을 의미합니다.
* **실질적 시각화:** 신뢰구간(음영)이 포함된 연도별 라인 차트. 초기 연도에는 큰 차이가 없더라도, 장기적으로 토양 환경이 개선되며 수확량 격차가 벌어지는 양상을 시각화합니다.

### 7. 기후 인자(기온, 강수량, CO2)와 생산성의 다중 회귀 분석

다양한 기후 변화 요인 중 어떤 인자가 농업 생산에 가장 치명적인지 파악하기 위한 분석입니다.

* **가설 설정**
* $H_0$: 기온, 강수량, 이산화탄소 농도는 작물 생산성과 선형적인 관계가 없다. (모든 회귀계수 $\beta = 0$)
* $H_1$: 적어도 하나의 기후 인자는 생산성과 유의미한 관계를 가진다.


* **검정 통계량:** $F$-통계량 (전체 모형 적합도) 및 $t$-통계량 (개별 변수의 유의성)
* **p-value 해석:** $p < 0.05$일 경우 모형 및 특정 기후 변수가 수확량에 미치는 영향이 유의미합니다.
* **실질적 시각화:** 상관관계 히트맵(Heatmap) 및 변수 중요도 막대그래프. 농민이나 정책 입안자에게 어떤 기후 변수를 가장 우선적으로 대비해야 하는지 직관적인 지표를 제공합니다.

---

### 참고 문헌 및 출처

1. Hochmuth, G., et al. "Fertilizer Experimentation, Data Analyses, and Interpretation for Developing Fertilization Recommendations". University of Florida, EDIS. (시나리오 1 참고)
2. Lee, Y. et al. "An Effect of ICT Technology Adoption on Small-Sized Horticulture Farms in Korea". IJAIR. (시나리오 2 참고)
3. Cao, J., et al. "Predicting spatial and temporal variability in crop yields: an inter-comparison of machine learning, regression and process-based models". Environmental Research Letters. (시나리오 3 참고)
4. Souza, C. F., et al. "Precision Agriculture: Semiautomatic Irrigation Management in Tomato". (시나리오 4 참고)
5. MDPI. "Impact of Soil Amendments and Alternate Wetting and Drying Irrigation on Growth, Physiology, and Yield of Deeper-Rooted Rice Cultivar". (시나리오 5 참고)
6. Li, X., et al. "Long term effects of crop rotation and fertilization on crop yield stability in southeast China". Scientific Reports. (시나리오 6 참고)
7. Preprints. "Modeling Climate Change Impacts on Agricultural Productivity Using Integrated Regression and Transformer-Based Deep Learning". (시나리오 7 참고)
