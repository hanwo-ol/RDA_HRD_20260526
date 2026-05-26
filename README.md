# RDA_HRD_20260526
본 저장소는 아래 강의를 위해 강의 자료 및 관련 정보를 공유 및 아카이빙 하기 위한 저장소 입니다.
> 과정명: `AI와 파이썬 활용 데이터분석 기초`
> 교육 구분: `공무원 교육`
> 교육 기간: `2026.05.26`

> 진행: `전북 대학교 통계학과 조교수 황승용`,   
> 연락처: `063-270-3390`,    
> 이메일: `syhwang@jbnu.ac.kr`   
> github: `https://github.com/vic-dragon`    

# 교육 자료 

### 실습용 엑셀 파일(다운 받으셔야 합니다.)
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

빈칸이 모두 채워저 있는 교안 파일은 편히 복습하실 수 있게 Day 1이 끝난 이후 일괄 공유 드리겠습니다.

## Day 2: 2026-05-27
### 실습용 ipynb 파일
**상단 메뉴에서 `파일` > `드라이브에 사본 저장`을 눌러 본인의 구글 드라이브에 복사본을 만든 후 작업** 하면, 추후에 혼자 복습하실 때 편하게 사용 가능합니다.

[Day2_데이터시각화_교재](https://drive.google.com/file/d/17y4pVQyReOrb5lFVZSwXjwZySxlH_JEe/view?usp=drive_link)

[Day2_GenAI활용_교재](https://drive.google.com/file/d/17J4r5c0Ps074UWAj9h8qAWFjRvHGCrYU/view?usp=drive_link)

### A/S

빈칸이 모두 채워저 있는 교안 파일은 편히 복습하실 수 있게 Day 2가 끝난 이후 일괄 공유 드리겠습니다.




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
