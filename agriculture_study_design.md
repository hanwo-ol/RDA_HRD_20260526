언제, 어떤 검정을, 또 어떤 시각화를 실질적으로 할 지 생각해보았습니다.

# 농학 연구를 위한 가설검정 및 데이터 시각화 시나리오

## 1. 비료 종류에 따른 작물 수확량 비교 (One-way ANOVA)

단일 농가나 연구소에서 새로운 비료를 도입할 때 가장 기본적으로 수행하는 검정입니다.

- **가설 (①):** $H_0: \mu_A = \mu_B = \mu_C = \mu_{control}$ / $H_1$: 적어도 하나의 비료 처리군에서 평균 수확량 차이 존재
- **검정 통계량 (②):** $F$-통계량 (집단 간 분산 / 집단 내 분산)
- **p-value 해석 (③):** $p < 0.05$일 경우 $H_0$ 기각, Tukey HSD 등 사후검정으로 우수 비료 확정
- **실질적 시각화:** 박스플롯 — 극단값(Outlier)과 분산을 동시에 확인하여 기후 변동에도 안정적인 비료 선택 가능

## 2. 스마트팜(ICT)과 일반 노지 재배의 생산성 검증 (독립표본 t-검정)

스마트팜 설비 투자 타당성을 검증하기 위한 분석입니다.

- **가설 (①):** $H_0: \mu_{smart} = \mu_{open}$ / $H_1: \mu_{smart} > \mu_{open}$
- **검정 통계량 (②):** $t$-통계량 (단측검정)
- **p-value 해석 (③):** $p < 0.05$일 경우 $H_0$ 기각, 스마트팜의 경제적 효용성 통계적 뒷받침
- **실질적 시각화:** 오차막대 포함 막대그래프 또는 바이올린 플롯 — 평균뿐 아니라 시설 투자로 인한 수확량 편차(리스크) 감소를 직관적으로 설득

## 3. 기온 변화가 작물 수확량에 미치는 영향 (단순 선형 회귀 분석)

독립변인 1개가 종속변인에 미치는 선형적 영향을 정량화할 때 사용합니다(예: 생육기 평균기온 → 작물 수확량).

- **가설 (①):** $H_0: \beta_1 = 0$ / $H_1: \beta_1 \neq 0$
- **검정 통계량 (②):** $t$-통계량 (회귀계수 유의성), $R^2$ (설명력)
- **p-value 해석 (③):** $p < 0.05$일 경우 $H_0$ 기각, 독립변인 1단위 변화에 따른 종속변인 변화량을 정량화
- **전제 가정:** 선형성, 오차항의 정규성·독립성·등분산성
- **실질적 시각화:** 산점도 + 회귀직선, 잔차도(Residual plot)

## 4. 관수 방식 변경 전후 토양 수분 유지력 비교 (대응표본 t-검정)

동일한 포장(plot)에 자동 관수 센서를 도입하기 전후의 일평균 토양 수분량을 비교하는 사전-사후 설계입니다.

- **가설 (①):** $H_0: \mu_d = 0$ / $H_1: \mu_d \neq 0$ (또는 단측 $\mu_d > 0$)
- **검정 통계량 (②):** $t = \dfrac{\bar{d}}{s_d / \sqrt{n}}$, 자유도 $df = n-1$
- **p-value 해석 (③):** $p < 0.05$일 경우 $H_0$ 기각, 센서 도입에 따른 토양 수분 유지력 변화가 통계적으로 유의함을 의미
- **전제 가정:** 차이값($d_i$)의 정규성, 짝(pair)의 독립성
- **실질적 시각화:** 시계열 라인 플롯(관수 시점 전후 수분량 회복 곡선) + 사전-사후 페어드 도트플롯(개체별 변화 방향)

## 5. 물 절약 관개 방식(AWD)과 토양 개량제 효과 (이원 분산분석, Two-way ANOVA)

가뭄 대비용 물 절약 농법의 수확량 영향과 개량제의 보완 효과를 검증합니다.

- **가설 (①):** $H_0$: 관개 방식과 토양 개량제 투입 여부는 주효과 및 교호작용 없음 / $H_1$: 적어도 하나의 주효과 또는 상호작용 존재
- **검정 통계량 (②):** $F$-통계량 (주효과 2개, 상호작용 1개)
- **p-value 해석 (③):** $p < 0.05$일 경우 해당 효과 유의
- **실질적 시각화:** 교호작용 플롯 — 절수 관개 시 토양 개량제의 수확량 감소 방어 효과를 선의 기울기 차이로 제시

## 6. 유무기 비료 혼합 비율에 따른 장기 수확량 안정성 (반복측정 분산분석)

동일한 시험구를 다년간 추적하며 비료 처리군별 수확량 추이의 차이를 검정하는 종단 설계입니다.

- **가설 (①):** $H_0$: 처리군 간 시간에 따른 수확량 추이 차이 없음 (처리×시간 상호작용 = 0) / $H_1$: 처리군과 시간의 상호작용 존재
- **검정 통계량 (②):** $F$-통계량 (개체 내 시간 주효과, 개체 간 처리 주효과, 처리×시간 상호작용 3개)
- **p-value 해석 (③):** 상호작용 $p < 0.05$일 경우 처리 효과가 시간에 따라 다르게 나타남을 의미, 구형성 가정 위배 시 Greenhouse-Geisser 보정 적용
- **전제 가정:** 잔차 정규성, 구형성(sphericity), 동일 개체 내 반복측정
- **실질적 시각화:** 처리군별 연도-수확량 라인 플롯(95% 신뢰구간 음영 포함), 처리×시간 상호작용 플롯

## 7. 기후 인자(기온, 강수량, CO₂)와 생산성의 다중 회귀 분석

복수의 독립변인 중 어떤 변인이 종속변인에 더 큰 영향을 미치는지 파악할 때 사용합니다.

- **가설 (①):** $H_0$: 모든 회귀계수 $\beta_i = 0$ / $H_1$: 적어도 하나의 $\beta_i \neq 0$
- **검정 통계량 (②):** $F$-통계량 (모형 적합도), 개별 $t$-통계량 (변수별 유의성), 조정 $R^2$
- **p-value 해석 (③):** 모형 전체 $F$ 검정과 개별 변수 $t$ 검정을 분리하여 해석
- **추가 진단:** 다중공선성(VIF), 단계적 회귀(stepwise regression) 활용 가능
- **실질적 시각화:** 상관관계 히트맵, 표준화 회귀계수 막대그래프, 변수 중요도 플롯

---

## 참고 문헌 및 출처

| # | 시나리오 | 인용 (APA 7판) | 출처 유형 | 검증 상태 |
|---|---|---|---|---|
| 1 | One-way ANOVA (비료×수확량) | Lock, R. H., Lock, P. F., Lock Morgan, K., Lock, E. F., & Lock, D. F. (2018). One-way ANOVA. In *Mathematical Statistics with Resampling and R* (Ch. 12). Wiley. https://doi.org/10.1002/9781119505969.ch12 | 교재 챕터 | Crossref 확인 |
| 1 | One-way ANOVA (방법론 보조) | Field, A. (2013). One-way independent ANOVA. In *Explaining Psychological Statistics* (Ch. 12). Wiley. https://doi.org/10.1002/9781394260638.ch12 | 교재 챕터 | Crossref 확인 |
| 2 | 스마트팜 vs 노지 (독립표본 t) | 한국농촌경제연구원. (2013). *KREI 농정포커스 제60호*. 한국농촌경제연구원. (DBpia 수록) | 정책보고서 | DBpia 확인 |
| 3 | 단순 선형 회귀 (방법론) | Linear regression analysis. (2005). In *Dictionary of statistics & methodology*. SAGE. https://doi.org/10.4135/9781412983907.n1069 | 사전 항목 | Crossref 확인 |
| 3 | 회귀분석 일반 (방법론) | Regression analysis. (2005). In *Dictionary of statistics & methodology*. SAGE. https://doi.org/10.4135/9781412983907.n1638 | 사전 항목 | Crossref 확인 |
| 3·7 | 회귀분석 가설검정 (방법론) | Hypothesis testing. (1986). In *Understanding regression analysis* (Ch. 3). SAGE. https://doi.org/10.4135/9781412986410.n3 | 교재 챕터 | Crossref 확인 |
| 4 | 대응표본 t-검정 (방법론) | Currell, G. (2015). Hypothesis testing. In *Scientific data analysis* (Ch. 4). Oxford University Press. https://doi.org/10.1093/hesc/9780198712541.003.0004 | 교재 챕터 | Crossref 확인 |
| 4·6 | 가설검정 추론통계 (방법론) | Köhler, T. (2022). Quantitative data analysis: Hypothesis testing and inferential statistics. In *Business research methods* (Ch. 27). Oxford University Press. https://doi.org/10.1093/hebz/9780198869443.003.0027 | 교재 챕터 | Crossref 확인 |
| 5 | AWD × 토양개량제 (이원 ANOVA) | Amin, M. W., Sediqui, N., Azizi, A. H., Joya, K., Amin, M. S., Mahmoodzada, A. B., Aryan, S., Suzuki, S., Irie, K., & Mihara, M. (2025). Impact of soil amendments and alternate wetting and drying irrigation on growth, physiology, and yield of deeper-rooted rice cultivar under IoT-based soil moisture monitoring. *AgriEngineering, 7*(3), 69. https://doi.org/10.3390/agriengineering7030069 | 동료심사 논문 | Crossref 확인 |
| 6 | 반복측정·시각화 (방법론) | Oyana, T. J. (2020). Engaging in exploratory data analysis, visualization, and hypothesis testing. In *Spatial analysis with R* (Ch. 4). CRC Press. https://doi.org/10.1201/9781003021643-4 | 교재 챕터 | Crossref 확인 |
| 7 | 다중 회귀 (상관·회귀 통합) | Dubey, U. K. B., & Kothari, D. P. (2022). Correlation and regression analysis. In *Research methodology* (Ch. 15). CRC Press. https://doi.org/10.1201/9781315167138-15 | 교재 챕터 | Crossref 확인 |
| 7 | 위계적 회귀 (다변량 확장) | Hierarchical regression analysis. (2005). In *Dictionary of statistics & methodology*. SAGE. https://doi.org/10.4135/9781412983907.n889 | 사전 항목 | Crossref 확인 |
| 7 | 다항 회귀 (비선형 확장) | Polynomial regression analysis. (2005). In *Dictionary of statistics & methodology*. SAGE. https://doi.org/10.4135/9781412983907.n1459 | 사전 항목 | Crossref 확인 |
| 공통 | ANOVA 방법론 사례 | One-Way ANOVA: Part II. (2014). SAGE Research Methods. https://doi.org/10.4135/9781473997509 | 방법론 교재 | Crossref 확인 |
| 공통 | ANOVA 방법론 사례 | One-Way ANOVA: Part III. (2014). SAGE Research Methods. https://doi.org/10.4135/9781473997516 | 방법론 교재 | Crossref 확인 |
| 공통 | ANOVA 적용 사례 (표) | Table 3: One-way ANOVA. *PeerJ Computer Science*. https://doi.org/10.7717/peerj-cs.3377/table-3 | 논문 구성요소 | Crossref 확인 |

---

## 한계 명시

본 문서의 참고문헌은 가설검정·회귀분석 방법론 표준 교재 중심으로 구성되어 있으며, 농학 도메인의 1차 실증 응용 사례는 시나리오 5(Amin et al., 2025, *AgriEngineering*) 1건이 해당됩니다. 나머지 시나리오(1·2·3·4·6·7)는 방법론적 근거 + 농학 적용 가능성 설명 구조로 작성되어 있으므로, 연구용으로 활용 시 각 시나리오별 도메인 1차 출처(예: 장기 시비 시험, 자동 관수 센서 실증, 기후-수확량 회귀 응용)를 Crossref/Scopus/DBpia에서 별도로 보강하실 것을 권고드립니다.
