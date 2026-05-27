# RDA_HRD_20260526
본 저장소는 아래 강의를 위해 강의 자료 및 관련 정보를 공유 및 아카이빙 하기 위한 저장소 입니다.
> 과정명: `AI와 파이썬 활용 데이터분석 기초`
> 교육 구분: `공무원 교육`
> 교육 기간: `2026.05.26`~`2026.05.27 오전`

> 진행: `전북 대학교 통계학과 조교수 황승용`,   
> 연락처: `063-270-3390`,    
> 이메일: `syhwang@jbnu.ac.kr`   
> github: `https://github.com/vic-dragon`    

## 이틀동안, 귀한 시간 참여해주셔서 너무 감사합니다. 도움이 될 수 있는 자료가 있다면, 하단에 계속 추가해두겠습니다.
> 마지막 갱신일시 `20260527 1235`

# 교육 자료 `다운 필수`

### 실습용 엑셀 파일

(다운 받으셔야 합니다.)

## 통합
**상단 메뉴에서 `파일` > `드라이브에 사본 저장`을 눌러 본인의 구글 드라이브에 복사본을 만든 후 작업** 하면, 추후에 혼자 복습하실 때 편하게 사용 가능합니다.

[https://drive.google.com/drive/folders/1lU_DtoIi1mNmivw4pm40m0-U1ig5fJF5?usp=sharing]


[농작물 종합 실습.xlsx](https://docs.google.com/spreadsheets/d/1-J6OCYz3zIHdeO4catAf2NPVbvePLf7X/edit?usp=drive_link&ouid=113037456119891269010&rtpof=true&sd=true)   

[종합실습 완료.xlsx](https://docs.google.com/spreadsheets/d/1puRIHFuICh2_vUoYeHMXl_SE9jry2R_8/edit?usp=drive_link&ouid=113037456119891269010&rtpof=true&sd=true)

[농작물 전처리 실습.xlsx](https://docs.google.com/spreadsheets/d/1mbDlxAecdJCg_HQ4nmDYG-Q9A1wqf77J/edit?usp=drive_link&ouid=113037456119891269010&rtpof=true&sd=true)

[농작물 정제 완료.xlsx](https://docs.google.com/spreadsheets/d/1oaGMNICnH0-KoIV28pYJsetX4BNZlgSI/edit?usp=drive_link&ouid=113037456119891269010&rtpof=true&sd=true)


## Day 1: 2026-05-26
### 실습용 ipynb 파일
**상단 메뉴에서 `파일` > `드라이브에 사본 저장`을 눌러 본인의 구글 드라이브에 복사본을 만든 후 작업** 하면, 추후에 혼자 복습하실 때 편하게 사용 가능합니다.

[Day1_데이터전처리_교재](https://drive.google.com/file/d/1Ax2KHSv-VlWnKmNb-bsIyzR0phA22YtZ/view?usp=drive_link)

[Day1_머신러닝기초_교재](https://drive.google.com/file/d/1nJtyvaBUe0wLTc0L2Njd4UxKNPMKHgEy/view?usp=drive_link)

### A/S
전처리 체크리스트(복사 하셔서 확인하면서 하시면 좋습니다.)

<details>
  
<summary>보기</summary>

``` markdown
데이터 전처리 표준 체크리스트 (실습용)
[ ] 1. 초기 데이터 탐색 (Data Inspection)

데이터 불러오기 (read_csv, read_excel)

데이터의 행과 열 크기 확인 (shape)

상/하위 데이터 및 전반적인 구조 확인 (head, tail, info)

수치형 데이터의 기초 통계량 확인 (describe)

[ ] 2. 열 이름 및 구조 정리 (Column Cleaning)

열 이름의 앞뒤 공백 및 불필요한 특수문자 제거 (str.strip, str.replace)

직관적이고 다루기 쉬운 이름으로 변경 (rename)

분석 목적과 무관하거나 값이 하나뿐인 불필요한 열 제거 (drop)

[ ] 3. 결측값 처리 (Missing Values)

각 열의 결측값 개수와 전체 대비 비율 파악 (isnull().sum())

결측값이 너무 많은 의미 없는 행/열 제거 (dropna)

데이터 특성에 맞춰 평균, 중앙값, 최빈값, 또는 앞/뒤 값으로 빈칸 대체 (fillna)

[ ] 4. 중복 데이터 제거 (Duplicates)

데이터 전체에서 완전히 동일한 중복 행 탐지 (duplicated().sum())

고유 식별자(ID 등)가 중복되는 행이 있는지 특정 열 기준으로 추가 확인

탐지된 중복 행 제거 및 원본 데이터 반영 (drop_duplicates)

[ ] 5. 데이터 타입 변환 (Type Conversion)

각 열의 실제 의미(숫자, 문자, 날짜 등)와 판다스에 인식된 자료형(dtype)이 일치하는지 확인

문자열로 잘못 인식된 숫자형 데이터를 올바르게 강제 변환 (to_numeric)

메모리 절약과 분석 효율을 위해 텍스트를 범주형으로 변환 (astype('category'))

[ ] 6. 문자열(텍스트) 데이터 정제 (String Cleaning)

문자열 값 내부의 불필요한 띄어쓰기 및 앞뒤 공백 제거 (str.strip)

데이터에 섞여 있는 기호(%, 원, $, , 등) 및 단위 텍스트 제거 (str.replace)

영문 데이터가 있다면 대소문자 중 하나로 통일 (str.lower, str.upper)

[ ] 7. 날짜/시간 데이터 처리 (Datetime Processing)

단순 문자열로 되어 있는 날짜 데이터를 시계열 분석이 가능한 형식으로 변환 (to_datetime)

분석에 필요한 경우 연, 월, 일, 요일, 시간 등의 파생 변수(파생 열) 생성 (dt.year, dt.month 등)

[ ] 8. 이상값 탐지 및 처리 (Outliers)

사분위수(IQR) 공식을 활용하여 데이터의 정상 범위(상한선/하한선) 계산

상자 수염 그림(Boxplot)이나 히스토그램을 그려 시각적으로 이상값 분포 확인

도출된 기준에 따라 이상값을 상하한값으로 대체(clip)하거나 분석에서 제외

[ ] 9. 최종 검증 및 파일 저장 (Verification & Export)

결측값 0개, 중복값 0개, 알맞은 자료형이 모두 적용되었는지 최종 코드 점검

정제가 완료된 깔끔한 데이터를 새로운 이름의 파일로 저장 (to_csv, to_excel)

저장 시 불필요한 인덱스 열이 추가되지 않도록 설정했는지 확인 (index=False)

```

</details>

## Day 2: 2026-05-27
### 실습용 ipynb 파일
**상단 메뉴에서 `파일` > `드라이브에 사본 저장`을 눌러 본인의 구글 드라이브에 복사본을 만든 후 작업** 하면, 추후에 혼자 복습하실 때 편하게 사용 가능합니다.

[Day2_데이터시각화_교재](https://drive.google.com/file/d/17y4pVQyReOrb5lFVZSwXjwZySxlH_JEe/view?usp=drive_link)

[Day2_GenAI활용_교재](https://drive.google.com/file/d/17J4r5c0Ps074UWAj9h8qAWFjRvHGCrYU/view?usp=drive_link)

### A/S

[시각화 cheatsheet](https://github.com/hanwo-ol/RDA_HRD_20260526/blob/main/visualizer.md)

[matplotlib 한국어 설명서](https://wikidocs.net/92071)

[인트라 넷 이용자는 어떻게 도움말을 보나요?](https://github.com/hanwo-ol/RDA_HRD_20260526/blob/main/intra_net_user.md)

각 데이터 시각화 모듈의 스타일 및 꾸미기 요소에 대한 공식 문서 위치를 정리해 드립니다. 

<details>
  
<summary>보기</summary>

1. Matplotlib

* [스타일 커스텀 가이드 (Customizing Matplotlib)](https://matplotlib.org/stable/users/customizing.html)
* [다양한 스타일 시트 미리보기 (Style sheets reference)](https://matplotlib.org/stable/gallery/style_sheets/style_sheets_reference.html)
* [Axes(그래프 영역) 세부 속성 (Axes API)](https://matplotlib.org/stable/api/axes_api.html)

2. Seaborn

* [테마 및 미적 요소 설정 (Aesthetics tutorial)](https://seaborn.pydata.org/tutorial/aesthetics.html)
* [색상 팔레트 가이드 (Color palettes)](https://seaborn.pydata.org/tutorial/color_palettes.html)
* [테마 관련 API 목록](https://www.google.com/search?q=https://seaborn.pydata.org/api.html%23themeing)

3. Plotly (Python)

* [레이아웃 및 스타일 전체 속성 (Figure Reference - Layout)](https://plotly.com/python/reference/layout/)
* [전체 API 참조 목록 (Single-Page Reference)](https://plotly.com/python/reference/)
* [스타일링 가이드 (Styling Plotly Express)](https://plotly.com/python/styling-plotly-express/)

해당 공식 문서들을 참고하시면 글꼴 크기, 배경색, 축 눈금 설정, 범례 위치 조정 등 시각화 자료의 완성도를 높이는 다양한 방법을 쉽게 찾으실 수 있습니다.

</details>

---

# QnA


<details>
  
<summary>보기</summary>

## 1. 코랩(Colab) 한글 폰트 깨짐 해결 코드

코랩 환경에서 `matplotlib`과 `seaborn`의 한글 깨짐을 해결하려면 리눅스 시스템에 나눔 폰트를 설치하고, 파이썬에서 해당 폰트를 기본 폰트로 설정해야 합니다. 아래 코드를 순서대로 실행 하시면 됩니다.

> **핵심 안내 사항:** 1번 셀(폰트 설치)을 실행한 직후에는 반드시 코랩 상단 메뉴에서 **[런타임] - [세션 다시 시작]**(또는 런타임 다시 시작)을 클릭해야 새로 설치된 폰트가 시스템에 인식됩니다. 그 후 2번 셀을 실행해야 합니다.

**[셀 1: 폰트 설치 및 캐시 삭제]**

```python
# 나눔 폰트 설치 (설치 완료 후 런타임 다시 시작 필수)
!sudo apt-get install -y fonts-nanum
!sudo fc-cache -fv
!rm ~/.cache/matplotlib -rf

```

**[셀 2: 폰트 적용 및 마이너스 기호 깨짐 방지]**

```python
import matplotlib.pyplot as plt
import seaborn as sns

# 나눔바른고딕으로 폰트 설정
plt.rc('font', family='NanumBarunGothic')

# 마이너스 기호(-)가 깨지는 현상 방지
plt.rcParams['axes.unicode_minus'] = False

# 테스트용 코드
plt.plot([1, 2, 3], [1, 2, 3])
plt.title('한글 폰트 테스트')
plt.show()

```

---

## 2. 상황별 제미나이 프롬프트 조합 예시

교재의 '좋은 프롬프트 원칙 '인 **역할 부여 + 구체적 요청 + 형식 지정**을 적용한 예시 템플릿입니다.

### 시각화 코드 수정 요청 시

주로 Day 2 세션 1에서 그린 그래프를 다듬고 싶을 때 활용할 수 있습니다. 코드를 먼저 붙여넣은 후 아래와 같이 질문 해 주세요.

| 상황 | 프롬프트 조합 예시 |
| --- | --- |
| **색상 및 라벨 추가** | 파이썬 데이터 시각화 전문가로서 도와주세요. 위 코드에서 막대 그래프의 색상을 작물별로 다르게 지정하고, 각 막대 위에 정확한 생산량 숫자를 표시하도록 코드를 수정해 주세요. |
| **정렬 및 크기 변경** | 데이터 분석가 관점에서 이 그래프를 보기 좋게 바꿔주세요. x축의 작물들을 단가가 높은 순서대로 내림차순 정렬하고, 그래프 전체 가로 크기를 12, 세로를 6으로 조정하는 코드로 다시 짜주세요. |
| **그래프 종류 변경** | 농업 데이터 분석가로서 제안해 주세요. 위 코드는 산점도(scatter)인데, 연도별 생산량 변화의 추이를 더 잘 볼 수 있도록 꺾은선 그래프(lineplot)로 바꾸고 엑셀 파일로 저장하는 코드까지 추가해 주세요. |

### 분석 결과 해석 요청 시

Day 1 세션 3의 머신러닝이나 통계 요약 결과를 보고 인사이트를 도출할 때 유용합니다. 데이터 프레임의 출력 결과나 R2, RMSE 수치 등을 붙여넣고 아래와 같이 질문하면 좋습니다.

| 상황 | 프롬프트 조합 예시 |
| --- | --- |
| **기초 통계 해석** | 농촌진흥청 소속 데이터 연구원이라고 생각하고 이 데이터 요약표를 분석해 주세요. 재배면적 대비 생산량이 가장 효율적인 시군구 Top 3를 뽑고, 그 이유를 3줄 이내의 개조식으로 요약해 주세요. |
| **모델 성능 평가** | 통계 전문가로서 대답해 주세요. 제가 돌린 랜덤 포레스트 모델의 R2 값이 0.85, RMSE가 120이 나왔습니다. 이 수치가 농작물 생산량 예측에서 어떤 의미를 가지는지 일반 농가에서도 이해할 수 있도록 쉽게 풀어서 300자 이내로 설명해 주세요. |
| **군집화(K-means) 해석** | 농업 경제 전문가로서 답변해 주세요. 1,000개 농가를 3개의 그룹으로 나눈 결과표입니다. 각 그룹의 가장 큰 특징을 비교해서 설명하고, 그룹 1(생산량 저조, 단가 낮음) 농가들에게 필요한 맞춤형 조언을 2가지 제안해 주세요. 형식은 번호를 매겨서 정리해 주세요. |

### 코드 오류(Error) 해결 요청 시

에러 메시지를 만났을 때 원인 파악과 수정된 코드를 동시에 얻어내는 프롬프트입니다.

| 상황 | 프롬프트 조합 예시 |
| --- | --- |
| **타입/값 오류 발생** | 파이썬 코딩 강사로서 도와주세요. 위 코드를 실행했더니 `TypeError: cannot convert the series to <class 'float'>`라는 오류가 났습니다. 어느 부분에서 발생한 문제인지 원인을 한 줄로 설명하고, 수정된 전체 코드를 코드 블록으로 제시해 주세요. |

</details>

---

# 금일 수업 자료 페이지 링크(현재 페이지 주소)

## https://zrr.kr/QQlDvi

**큐큐** 엘 **디** 브이 아이

---

# 수업 후 보안 check!

## 공용 PC 사용 하셨으면 -> 구글 로그아웃 확인 필수!
## 공용 PC 사용 하셨으면 -> `ctrl` + `h` -> 인터넷 사용기록 삭제 필수!
