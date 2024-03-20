# 국유부동산 매각현황 분석

### 📁데이터셋
대상 파일: 한국자산관리공사_국유부동산 매각현황_20211231.csv
(https://www.data.go.kr/data/15004205/fileData.do)

공공데이터포털 (https://www.data.go.kr/) 이용

### 🖥️요약
본 분석 보고서에서는 한국자산관리공사의 국유부동산 매각현황 데이터를 통해 연도별, 지역별로 매각 특성을 확인하고 금리와 부동산 매각 건수 간의 관계를 분석하였다. 
처분 구분 별 비율 확인 결과 매각수의 매각이 약 88%의 높은 비율을 차지했고 매각 금액이 가장 많은 팀과 가장 적은 팀의 차이는  '국유재산3팀'과 '해안면무주지국유화지원추진단'의 매각금액 차이는 약 1조 6천 억 정도로 상당히 크게 나타났다. 연도별 매각금액은 2021년, 2022년이 가장 높았고, 지역별 매각 면적은 강원도, 경기도, 전라남도 등이 상위 5개 지역으로 나타났다. 또한, 금리가 낮은 년도에는 부동산 매각 건수가 증가할 것이라는 가설을 세우고 분석한 결과, 두 요소 간에 강한 음의 상관 관계를 도출하였다.
이 보고서 결과는 국유부동산 매각현황을 바탕으로 부동산 시장의 특성과 금리의 영향을 이해하는 데 도움을 주고 이후 부동산 정책 모델링과 평가에 영향을 줄 것으로 기대한다.
### ❓연구질문
필수분석
1)	매각 금액이 가장 많은 팀과 하위 팀의 차이 확인하기
2)	연도별 매각금액 추이 확인하기
3)	상위 5개 지역별 매각 면적 확인하기
4)	계약 일자 정보 기준으로, 매각이 많은 때의 특징 알아보기

선택분석
1)	처분 구분별 비율 확인하기
2)	필수-3 항목을 지역 규모에 따라 보정하기
3)	필수-2 항목을 증감액 그래프로 표현하기*

### 👩‍🔬연구가설
본 연구의 가설은 [필수-4]에 대해서만 작성하였다. 
1)	가설: 금리가 낮은 년도에는 부동산 매각 건수가 증가할 것이다.
가)	귀무가설 (H0): 금리와 부동산 매각 건수 간에는 유의미한 상관 관계가 없다.
나)	대립가설 (H1): 금리가 낮은 년도에는 부동산 매각 건수가 증가한다.

### ✏️연구방법
#### 1. 데이터 수집 방법
   본 연구는 공공데이터포털의 ‘한국자산관리공사_국유부동산 매각현황_20211231.csv’를 수집하여 활용하였다. 
   
#### 2. 조사 방법 및 사용된 통계적 방법
  ##### 가.	[선택-1] 처분 구분별 비율 확인하기
  1)	연구 절차
     
    가)	‘처분구분명’을 기준으로 빈도 계산 
    나)	전체 데이터 수 및 비율 계산
    다)	y축을 로그 스케일로 변경하여 시각화

  ##### 나.	[필수-1] 매각 금액이 가장 많은 팀과 하위 팀의 차이 확인하기
  1)	연구 절차
     
    가)	‘팀명’을 기준으로 그룹화하여 팀별 매각 금액의 총합 계산
    나)	매각 금액의 총합이 가장 많은 팀과 가장 적은 팀 식별
    다)	매각 금액의 총합이 가장 많은 팀과 가장 적은 팀 차이 계산
    라)	결과를 데이터프레임으로 변경하여 출력

  ##### 다.	[필수-2] 연도별 매각금액 추이 확인하기
  1)	연구 절차
     
    가)	‘연도구분’을 기준으로 연도별 매각금액 합계 계산
    나)	결과를 데이터프레임으로 변경하여 출력 

  ##### 라.	[선택-3] [필수-2] 항목을 증감액 그래프로 표현하기 
  1)	연구 절차
     
    가)	Seaborn 패키지를 활용하여 [필수-2]의 결과를 선 그래프로 출력
    나)	y축의 지수 표기법을 해제하고 y축의 눈금을 ‘천 만원’ 단위로 표시
    다)	선 그래프 출력 

  ##### 마.	[필수-3] 상위 5개 지역별 매각 면적 확인하기
  1)	연구 절차
     
    가)	‘지역구분’을 기준으로 그룹화하여 매각 면적의 합 계산 
    나)	매각 면적의 합이 많은 상위 5개 지역 식별
    다)	결과를 데이터프레임으로 변경하여 출력 

  ##### 바.	[선택-2] [필수-3] 항목을 지역 규모에 따라 보정하기
  1)	연구 절차
     
    가)	‘지역구분’을 기준으로 그룹화하여 대장면적의 합과 총 매각 건수 계산
    나)	보정된 지역 규모로 평균 대장면적 계산
    다)	평균 대장면적의 합이 많은 상위 5개 지역 식별
    라)	결과를 데이터프레임으로 변경하여 출력 

  ##### 사.	[필수-4] 계약 일자 정보 기준으로, 매각이 많은 때의 특징 알아보기
  1)	연구 절차
     
    가)	계약일자를 날짜 형식으로 변환
    나)	‘년도’ 열을 추가하여 계약일자의 년도 추출
    다)	년도별 총 매각 건수 계산
    라)	총 매각 건수가 많은 순으로 정렬
    마)	결과를 데이터프레임으로 변경하여 출력 
    
  2) 사용된 통계적 방법
    금리와 부동산 매각 건수의 상관관계를 파악하기 위해 상관분석을 실시하였다. 년도별 금리 값을 입력한 뒤 총 매각 건수와 금리 간의 상관 계수를 계산하여 이들 간 관계를 확인하고 p-value를 얻어 가설을 검정하였다.

### 📖결과
#### 결과 요약
#### 1.	결과 요약
이 보고서에서는 한국자산관리공사의 국유부동산 매각현황 데이터를 활용하여 분석을 진행하였다. 본 분석 결과는 다음과 같이 요약할 수 있다.
첫째, [선택-1]을 통해 처분 구분별 비율을 확인한 결과, 매각수의 처분이 압도적으로 큰 비율을 차지하였다. 둘째, [필수-1]을 통해 매각 금액이 가장 많은 팀인 ‘국유재산3팀’과 가장 적은 팀인 ‘해안면무주지국유화지원추진단’의 차이를 확인한 결과, 약 1조 6천억의 큰 차이를 보였다. 셋째, [필수-2]를 통해 연도별 매각금액 추이를 확인한 결과, 매각금액 합계가 큰 연도는 2021년, 2022년 등이었다. 넷째, [선택-3]을 통해 [필수-2] 항목을 증감액 그래프로 나타냄으로써 연도별 매각금액 추이를 시각화 하여 금액의 증감 패턴을 확인할 수 있었다. 다섯째, [필수-3]을 통해 상위 5개 지역별 매각 면적을 확인한 결과, 상위 5개 지역은 강원도, 경기도 등으로 나타났다. 여섯째, [선택-2]를 통해 [필수-3] 항목을 지역 규모에 따라 보정한 결과, 상위 지역은 강원도, 충청남도 등이었다. 일곱째, [필수-4]를 통해 계약 일자 정보를 기준으로 매각이 많은 때는 2017년, 2016년 등이었다. 이 결과를 바탕으로 금리와 부동산 매각 건수의 상관 분석을 진행하였고, 두 변수 간에 강한 음의 상관 관계가 있음을 확인함으로써 통계적으로 유의미한 결과를 얻었다.

#### 2.	한계점
본 분석의 한계는 다음과 같다. 
첫째, 상관 분석은 인과관계를 직접적으로 나타내지 않으며, 다양한 외부 요인들이 결과에 영향을 미칠 수 있으므로 통계적 한계를 갖는다. 둘째, 부동산 시장은 복잡하고 다양한 영향 요인들이 존재하므로, 이를 모두 고려하기 어렵다는 데이터 한계를 갖는다. 셋째, 본 분석은 특정 지역이나 시기에 대한 분석이므로 다른 지역이나 시기에서는 결과가 달라질 수 있기 때문에 분석의 일반성에서의 한계를 갖는다.

#### 3.	제언
이 보고서에서는 공공데이터, 그 중에서도 부동산 데이터를 수집하여 다각적으로 분석하였다. 추후 가능한 분석 방향은 다음과 같다.
먼저, 부동산 시장의 특수성을 고려한 모델링으로 추가적인 인자들을 고려한 심층 분석이 가능하다. 그리고 부동산 거래와 관련된 정책의 효과를 평가하여 향후 정책 제안에 활용할 수 있도록 정책적 시사점을 도출할 수 있다. 또한, 시계열 데이터를 이용하여 시간 경과에 따른 변동을 더욱 정확히 파악하는 것이 중요하다. 마지막으로 지역별 특성을 고려한 추가 분석을 통해 지역 간 부동산 시장의 특이성을 파악할 필요가 있다.
