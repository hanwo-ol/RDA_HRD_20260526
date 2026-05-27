### 1. 시각화 목적별 그래프 선택 템플릿

데이터 분석의 목적에 맞춰 가장 효과적인 그래프 양식과 주요 라이브러리별 핵심 함수를 정리한 가이드입니다.

| 분석 목적 | 추천 그래프 | Matplotlib 코드 | Seaborn / Plotly 코드 | 주요 활용 예시 (농업 데이터) |
| --- | --- | --- | --- | --- |
| **시간에 따른 변화** | 선 그래프 | `ax.plot()` | `px.line()` | 연도별 주요 작물 생산량 추이 |
| **항목별 크기 비교** | 막대 그래프 | `ax.bar()`, `ax.barh()` | `sns.barplot()`, `px.bar()` | 작물별 평균 단가 비교 |
| **두 변수 간의 관계** | 산점도 | `ax.scatter()` | `sns.scatterplot()`, `px.scatter()` | 재배 면적과 생산량의 상관관계 |
| **비율 및 구성** | 파이/도넛 차트 | `ax.pie()` | `px.pie()` | 전체 농가 중 작물별 총생산량 비율 |
| **데이터 분포 및 이상값** | 히스토그램 | `ax.hist()` | `sns.histplot()` | 특정 작물의 단가 분포 확인 |
| **그룹별 데이터 분포** | 박스/바이올린 플롯 | `ax.boxplot()` | `sns.boxplot()`, `sns.violinplot()` | 작물별 생산량의 편차 및 이상값 탐지 |
| **다중 변수 상관관계** | 히트맵 | - | `sns.heatmap()` | 단가, 생산량, 면적 등 수치형 변수 간 관계 |

---

### 2. 라이브러리별 필수 코드 스니펫 (요약본)

강의에서 다루는 3가지 핵심 도구의 기본 뼈대와 자주 쓰이는 옵션을 모은 치트시트입니다.

#### A. Matplotlib (기본 구조 및 세밀한 제어)

가장 기본이 되는 도화지(Figure)와 그림 영역(Axes)을 분리하는 구조입니다. 논문이나 보고서용 정적 이미지 출력에 적합합니다.

```python
import matplotlib.pyplot as plt

# 1. 캔버스 및 그래프 영역 생성
fig, ax = plt.subplots(figsize=(10, 5))

# 2. 그래프 그리기 (예: 선 그래프, 막대 그래프 등)
ax.plot(x_data, y_data, color='#1565C0', marker='o', label='데이터명')

# 3. 그래프 꾸미기 (필수 옵션)
ax.set_title('그래프 제목', fontsize=14, fontweight='bold')
ax.set_xlabel('X축 이름')
ax.set_ylabel('Y축 이름')
ax.legend(loc='upper left')      # 범례 표시
ax.grid(True, alpha=0.3)         # 배경 격자선 추가

# 4. 출력 및 저장
plt.tight_layout()               # 여백 자동 조정
plt.savefig('파일명.png', dpi=150) # 고화질 이미지 저장
plt.show()

```

#### B. Seaborn (통계적 시각화 및 간결한 코드)

Matplotlib 기반이나, 복잡한 반복문 없이 변수(`hue`)를 지정하는 것만으로 색상 분리 및 통계 처리가 가능합니다.

```python
import seaborn as sns
import matplotlib.pyplot as plt

# 1. 산점도 (항목별 색상 자동 구분)
sns.scatterplot(data=df, x='재배면적(ha)', y='생산량(톤)', hue='작물')

# 2. 막대 그래프 (평균과 신뢰구간 동시 표시)
sns.barplot(data=df, x='연도', y='생산량(톤)', hue='작물')

# 3. 히트맵 (변수 간 상관관계)
# corr = df[['수치컬럼1', '수치컬럼2']].corr()
sns.heatmap(corr, annot=True, fmt='.2f', cmap='RdYlGn', center=0)

plt.show()

```

#### C. Plotly (인터랙티브 웹 그래프)

마우스 호버 시 값 표시, 확대/축소, 범례 클릭 온/오프 등 상호작용이 가능한 동적 그래프를 그립니다. 대시보드나 발표용으로 적합합니다.

```python
import plotly.express as px

# 1. 인터랙티브 선 그래프 생성
fig = px.line(
    df, 
    x='연도', 
    y='생산량(톤)', 
    color='작물', 
    markers=True,
    title='연도별 작물 생산량 추이'
)

# 2. 버블 산점도 (크기 변수 추가)
# fig = px.scatter(df, x='면적', y='생산량', color='작물', size='단가')

# 3. 출력 및 HTML 저장
fig.show()
fig.write_html('인터랙티브_그래프.html') # 브라우저에서 열 수 있는 파일로 저장

```

`gemini 3.1 pro`와 작업한 문서입니다.
