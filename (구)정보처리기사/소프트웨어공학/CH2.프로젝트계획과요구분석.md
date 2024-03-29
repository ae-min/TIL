# S1. 프로젝트 계획
## 1. 자원측정
- 개발 시 필요한 컴퓨터, 기타 장비들이나 프로그램들을 미리 확보하고 개발될 소프트웨어 규모나 특성에 따라 개발자들의 조직과 능력에 따라 역할을 결정해야함
- 하드웨어자원 / 소프트웨어자원 / 인적자원
## 2. CASE (Computer Aided Software Engineering) - 소프트웨어자원
- 소프트웨어를 개발하는 시점부터 요구분석, 설계, 개발, 유지보수에 이르기까지 소프트웨어의 생명주기 전반을 지원하는 프로그램 
- 소프트웨어 개발을 지원하는 자동화도구 혹은 방법론의 결합
- 소프트웨어를 효율적으로 정확하고 신속하게 개발할 수 있도록 도와줌
## 2.1 CASE의 분류
### 상위(Upper) CASE 
    - 소프트웨어 생명주기의 전반부 과정 지원
    - 요구분석과 설계 지원
    - 명세서와 문서를 작성
    - PSL/PSA, SREM, SYSREM, FOUNDATION 등이 있음
    
### 하위(Lower) CASE
    - 소프트웨어 생명주기의 하반부 과정 지원
    - 코드작성(구현), 검사(테스트) 지원
    - 문서화하는 과정에 도움을 주는 여러가지 도구들을 포함
    - 코드생성기, 링커, 로더, 디버그 등이 있음
    - 소프트웨어 생명주의 전체과정을 지원함

### 통합(Integrate) CASE
    - 공통의 정보저장소와 통일된 사용자인터페이스를 사용하여 도구들을 통합
    - POWERTOOLS, IEF, TAGS/IORL, TEAMWORK, PROMOD 등

## 2.2 CASE 특징
- 개발과정을 자동화함으로써 생산성을 증대시키고자 하는 목적으로 개발됨
- 소프트웨어 개발의 모든 단계에 걸쳐 일관된 방법론 지원
- CASE 툴의 가격은 비싸지만, 소프트웨어 개발 시 개발비용이 절감됨
- 수정이 용이하고 정확함
- 개발과정의 속도가 향상됨
- 모듈의 재사용성이 향상됨
- 생명주기의 모든 단계를 연결시켜주고 자동화시켜줌
- 분석가의 지원이 절대적으로 필요

## 3. 소프트웨어 개발 팀(조직) 구성 - 인적자원
## 3.1 책임프로그래머 팀(Chief, 중앙집중형 팀)
- 프로그래머 팀장(관리자)이 모든 개발 인적자원들의 지원을 받는 형태
- 팀 구성원이 관리자의 명령에 따라 일하고, 결과를 보고하는 방식 (한명이 모든 의사결정과 책임을 짐)
- 소규모, 단기적, 쉬운 프로젝트에 적합한 조직
- 구성원의 직업참여도와 만족도가 낮으므로 이직률이 높음
      
      [책임프로그래머 팀 구성원]
      - 책임프로그래머(Chief) : 요구분석, 설계, 기술적판단, 작업지시, 배분 담당
      - 보조프로그래머(Back-up) : 책임프로그래머를 보좌하여 여러가지 기술적인 자문을 함.
                                사용자 및 보증담당자 섭외, 책임프로그래머 감독하에 분석, 설계, 문서작성 등 담당
      - 프로그래머 : 책임프로그래머의 지시에 따라 원시코드 작성, 검사, 디버깅, 문서작성 등 담당
      - 프로그램사서(Program Librarian) : 프로그램리스트, 설계문서, 검사계획서 등의 문서 관리

## 3.2 민주주의식 팀(Democratic, 분산형 팀)
- 모든 프로그래머가 능력별로 개발하고자 하는 대상을 분리하여 각자 개발한 후, 통합하기 전에 전체 회의를 통하여 소프트웨어를 완성하는 형태의 조직
- 규모가 크고, 장기적인 프로젝트 개발 시 적합
- 팀 구성원의 사기와 작업 만족도를 높이며 이직률을 낮게 함

## 3.3 혼합형 팀(Hierarchical Structure Team)
- 중앙집중형과 혼합형 팀의 단점을 보완하고자, 두 방법을 혼합한 방식
- 중앙집중형처럼 경험자와 초보자를 구별함
- 경험자는 초보자에게 작업을 지시하며
- 초보자는 지시에 따라 작업하고 경험자에게 보고
- 모든 구성원은 상하좌우 구성원들과 유기적인 관계를 가짐

## 4. 비용측정방법론
- 하향식 : 프로젝트 총 비용을 측정 후, 단계별로 비용을 세분화
- 상향식 : 프로젝트 총 비용을 마지막에 측정한 후, 단계별로 측정한 결과들을 모아서 총 비용을 측정하는 방법

## 4.1 전문가측정방법(Expert Judgment)
- 경험이 많은 전문적인 비용측정가에게 의뢰하거나, 회사 내의 고급기술진의 의견대로 비용을 측정하는 방법
- 가장 편리하고 신속한 장점이 있으나
- 개인적이고 주관적인 의견 때문에 비용측정을 잘못할 수 있다는 단점도 있음

## 4.2 델파이
- 전문가측정방법의 단점인 한 두사람의 개인적이고 주관적인 편견으로 생길 수 있는 문제점을 보완한 방식
- 많은 전문가의 의견을 종합하여 측정하는 방법
- 전문가들의 의견을 중재하는 중재자(조정자, Coordinator)가 반드시 필요

## 4.3 원시코드라인 수 측정 (LOC : Line of code)
- 프로젝트의 각 기능별 라인 수를 측정(비관치, 기대치, 낙관치)하여 비용을 산정하는 기법

        예측치  = (비관치 + 기대치*4 + 낙관치) / 6

<img width="250" src="https://user-images.githubusercontent.com/29009929/154627564-80883511-6c87-4a32-a466-acf09d9e4e26.png">


## 4.4 COCOMO 모형
- 보헴이 제시한 원시프로그램 규모에 의한 비용예측모형
- 종류 : 기본(Basic), 중간(Intermediate), 세부(Detailed) 모델
        [COCOMO 개발유형]
        
        1) 유기형(Organic) : 중소규모 소프트웨어 / **5만라인 이하** / 업무용, 과학용, 사무처리용 소프트웨어에 적합
        2) 준 분리형(Semi-detached) : 중소규모 소프트웨어 / **30만라인 이하** / 개발지원도구인 컴파일러, 인터프리터 등에 적합
        3) 내재형(Embedded) : **최대형규모** 소프트웨어 / 대형시스템소프트웨어(DBMS, 운영체제, 통신용 등)에 적합

## 4.5 Putnam 모형
- 시간에 따른 함수로 표현되는 Rayleigh-Norden곡선의 노력 분포도 곡선으로 그려짐
- 개발기간이 길어질수록 프로젝트에 참여하는 인원의 노력이 감소하므로, 대형 프로젝트의 노력분포산정에 용이
- Putnam모형을 기초로하여 만든 자동화추정도구 : SLIM
- SLIM : 총인월, 개발기간 등의 비용측정값을 입력하면 소프트웨어 비용산출을 자동으로 출력해줌

---
# S2. 프로젝트관리
## 1. 프로젝트 관리 대상
사람(people) / 문제(Problem) / 프로세스(Process)

## 2. 일정계획방법론
## 2.1 PERT (Program Evaluation and Review Technique, 프로그램 평가 및 검토 기술)
- 각 활동시간을 세 가지로 추정하여 평균시간을 계산하는 일종의 확률적 모형
- 확률적인 추정치를 이용하여 단계중심의 확률적 모델을 전개
- 예측치  = (비관치 + 기대치*4 + 낙관치) / 6
- 최단기간에 목표를 달성하기 위함
- 프로젝트의 시작부터 종료까지의 모든 단계를 원, 직선, 화살표를 이용하여 표시하는 방법
- 모든 프로젝트들을 서로 연관된 소작업으로 분류하고,
- 이들의 시작부터 끝나는 시점까지의 관계를 화살표로 그려 개발기간(일정계획)을 예측

## 2.2 CPM (Critical Path Method, 중점경로기법)
- 과거 실적이나 경험 등의 확정적 결과값을 이용하여 활동중심의 확정적 모델을 전개
- 목표기일 단축과 비용 최소화를 달성하기 위함
- 개발기간의 최장경로(임계경로)를 파악 가능
- 노드에서 작업을 표시하고, 간선(화살표)은 작업 사이의 전후 의존 관계를 나타냄
- 한 이정표에서 다른 이정표에 도달하기 전에 이전 작업이 모두 완료되지 않으면 다음 작업으로 진행 불가
- 병행작업이 가능하도록 계획 가능하며, 이를 위한 자원할당도 가능
- 편차가 존재하므로 정확한 일정 예측은 불가능

### CPM을 이용한 일정계획순서

        1) 프로젝트 규모 추정
        2) 각 단계에 필요한 작업들을 분해
        3) 각 작업의 상호의존관계를 CPM네트워크로 표시
        4) 일정계획을 간트차트로 표시


### 간트차트

        - 각 단계별로 진행사항을 알 수 있도록 표시한 프로젝트 일정계획 및 이정표
        - 생명주기단계, 일정계획(작업일정), 이정표, 작업기간 등이 포함됨

## 2.3 WBS (work Breakdown Structure, 업무분류구조)
- 모든 개발단계를 서로 연관된 소작업으로 분류하고, 시작부터 끝나는 시점까지의 관계를 분석하여 개발기간(일정계획) 및 비용을 측정하는 방법
- 모든 작업을 트리구조로 분할한 후, 단 노드부터 일정을 측정하면서 전체 일정을 잡음

## 3. 소프트웨어 형상관리(SCM : Software Configration Management)
- 컴퓨터 소프트웨어 생명주기 전체의 변경을 관리하는 활동들의 집합 (소프트웨어 변경을 관리하기 위해 개발된 일련의 활동)
- 유지보수 단계에서 형상관리 진행됨
- 전체비용이 최소화되고, 소프트웨어 사용자에게 방해가 최소한으로 야기되도록 보증하는 것을 목적으로 함
- 버전관리와 버전제어기술이 가장 중요한 기술

## 3.1 형상관리 프로세스
        1) 식별(Identification) : 형상관리대상 프로세스들을 분리 후 정의
        2) 버전관리(Version Control) : 변경전과 변경후의 버전관리를 체계적으로 정리
        3) 변경관리(Change Control) : 변경으로 인한 성능이나 품질, 신뢰도 등을 파악
        4) 형상감사(Configration Auditing) : 변경을 평가하여 문제점 지적 및 보완
        5) 보고(Reporting) : 변경사항 문서화

## 3.2 형상관리 목표물(관리항목)
- 목표물 : 변경가능한 분석서, 설계서 코드 등
- 개발비용은 형상관리항목으로 정할 수 없음 (이미 측정된 개발비용은 소프트웨어 개발 진행 중 변경되어서는 안됨)
- 정의단계의 문서 : 시스템분석서, 프로젝트계획문서, 요구분석서 등
- 개발단계의 문서 : 설계분석서, 외부설계서, 내부설계서, 소스코드, 검사계획서 등
- 유지보수단계의 문서 : 유지보수계획서, 소스프로그램보고서, 유지보수활동서, 기술변경사항 등

## 4. 소프트웨어 위험관리(Risk Management)
- 프로젝트 진행 과정에서 예상되는 각종 돌발상황을 미리 예상하고, 이에 대한 적절한 대책을 수립하는 일련의 활동
## 4.1 위험관리 절차
        1) 위험식별 : 위험요소가 될 사항들을 파악
        2) 위험분석 및 평가 : 위험의 비중과 영향력 파악
        3) 위험관리계획 : 위험예방 및 위험발생 시 대안들을 준비하고 문서화
        4) 위험감시 및 조치 : 위험을 항상 관찰 및 발생 시 조치

---
# S3. 요구분석
## 1. 요구분석(Requirements Analysis)
- 개발요청자의 하드웨어나 소프트웨어에 대한 외부적 요구를 받아들여, 개발하고자 하는 소프트웨어의 특성을 기술하는 단계
- 요구분석의 성과는 앞으로의 개발 과정의 품질에 절대적인 영향을 주므로 어느 단계보다 중요
- 전체 생명주기 단계 중 가장 전문분석가를 필요로 하는 단계 (여러방면으로 능통, 사용자 요구를 정확히 반영할 수 있어야함)
## 1.1 요구분석 목적
- 사용자와 개발자간의 의사교환을 유지
- 소프트웨어 설계 및 개발에 필요한 기본적인 자료 제공
- 소프트웨어가 가져야할 외적인 기능을 기술하는 단계
- 사용자와의 하드웨어 및 소프트웨어 운영상의 계약 (요구분석서는 개발자와 사용자간의 계약서와 같은 역할)
## 1.2 요구분석 단계 특징
- 프로젝트를 이해할 수 있는 개발의 실질적인 첫 단계
- 현 상태를 파악하고 문제를 정의한 후, 문제해결과 목표를 정확히 도출하는 단계
- 사용자가 처음으로 참여하는 단계
- 전문인력을 가장 필요로 하는 단계
- 사용자도 알아볼 수 있는 자연언어(한국어, 영어 같은 일상언어)로 작성
- 판단 및 제어구조가 포함되어서는 안됨
## 1.3 요구분석 순서
        1) 니즈분석 : 사용자의 막연한 요구를 체계적으로 정리 
        2) 개발자준비분석 : 미리 준비된 분석자료를 사용자에게 질문하여 요구를 받아들이기
        3) 자료흐름도(DFD)작성 : 사용자의 요구에서 자료를 구분하여 자료들의 흐름을 그려내기
        4) 자료사전(DD)작성 : 구분된 자료를 체계적으로 정리하여 레코드나 파일설계시에 기본자료가 되도록 함
        5) 소단위명세서작성 : 규모가 큰 프로젝트에서 자료흐름도에 있는 처리를 간략하게 서술하는 것, 최하위 단계의 프로세스
        6) 요구명세화 : 요구분석에 대한 모든 내용 문서화
        
## 2. 구조적분석
## 1. 기본모형 3가지
- 자료흐름도(DFD) / 자료사전(DD) / 소단위명세서(Mini-spec)

## 3. 자료흐름도(DFD : Data Flow Diagram)
- 자료가 소프트웨어 내의 각 절차를 따라 흐르면서 변하는 과정을 도형화시키는 방법

## 3.1 자료흐름도 표기법
<img width="350" src="https://user-images.githubusercontent.com/29009929/155087355-b26fdc9c-0f5f-4159-a5df-061d46f24816.png">

## 4. 자료사전(DD : Date Dictionary)
- 자료흐름도의 대상이 되는 자료의 내용을 구체적으로 명시한 것
- 자료(데이터)를 설명하고 있는 데이터를 메타데이터라고 함

## 4.1 자료사전 표기법
<img width="350" src="https://user-images.githubusercontent.com/29009929/155087675-bc7c8b83-4633-43c2-8c63-4ba1cb596240.png">

## 5. 소단위명세서
- 세분화된 자료흐름도에서 최하위 단계의 프로세스 처리 절차를 설명하는 작업
- 설계단계의 모든 명세서를 요구분석단계에서 간단하게 작성하는 명세서
- 자료흐름도에서 각 프로세스가 수행할 기능을 자연언어로 간단하게 작성하는 작업
- 프로젝트 규모가 크고 복잡할 경우 주로 작성되며, 프로젝트가 작은 규모일 경우에는 대부분 생략함
- 실제 프로그램 코드와 비슷하게 작성되기도 하는 소단위명세서는 프로세스들의 설명을 1~2페이지의 소규모 분량으로 작성
- 프로그램 설계언어(PDL)를 사용한 논리적 절차 포함도 가능 (요구분석서에는 PDL이나 전문적인 표현 사용불가하고 자연언어로만 작성가능)

## 6. 요구분석용 자동화도구 (CASE)
## 1. SADT (Structure Analysis & Design Technique, 구조적분석 설계기법)
- SoftTech사에서 개발된 대규모 프로젝트용 요구분석 방법론
- 구조적인 도형표기와 그것을 효율적으로 수행하기 위한 설계방법으로 구성됨
- 요구분석과 설계분석, 설계명세서를 동시에 표현가능한 수동적 도구

## 2. PSL/PSA (Program Statement Language / Program Statement Analysis)
- 미시간 대학의 ISDOS 프로젝트에서 개발된 요구분석용 자동화 도구
- 요구분석에 필요한 내용을 PSL이란 기술언어를 사용하여 작성한 뒤,
- PSA에 입력하면 PSA는 분석 데이터 베이스에 저장하고 있는 자료를 분석하여 최적의 요구 명세서를 자동으로 출력해줌

## 3. SREM (Software Requirement Engineering Methodology) = RSL/REVS
- TRW사가 우주국방시스템그룹에 의해 실시간 처리 소프트웨어 시스템에서 요구사항을 명확히 기술하도록 할 목적으로 개발
- RSL과 REVS를 사용하는 자동화 도구
- RSL(Requirement Statement Language) : 요소, 속성, 관계, 구조들을 기술하는 요구사항 기술 언어
- REVS(Requirement Engineering and Validation System) : RSL로 기술된 요구사항들을 자동으로 분석하여 요구사항 분석 명세서를 출력하는 요구사항 분석기






