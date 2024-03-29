# S1. 인터럽트의 기본
## 1. 인터럽트의 개념
중앙처리장치와 주변장치 차이에 따른 효율적인 시스템 자원의 활용과 기계적 장애로 인하여 실행하던 프로그램을 완료하지 못하였을 때, 
처음부터 다시하지 않고 중단된 위치로 복귀되어 이상없이 계속해서 프로긂이 진행되도록 하는데 있음
## 1.1 인터럽트의 원인
    - 정전, 데이터전달과정의 오류, 기계장치의 장애
    - 타이머, 외부프로세스 등의 요청
    - 컴퓨터 조작원의 의도적인 동작
    - 보호된 기억공간 접근, 불법적인 명령어 수행 (프로그램오류로 발생, 인터럽트 발생 시 보존 필요 없음)
    - 0으로 나누기, 오버플로우/언더플로우 발생 (프로그램오류로 발생, 인터럽트 발생 시 보존 필요 없음)
    - 페이지폴트, 캐시미스 발생 (프로그램오류와 상관없이 발생, 인터럽트 발생 시 보존 필요)
    - 입출력장치에서 CPU에게 기능 요청 시
    - SVC(SUPER VISOR CALL) 인터럽트
## 2. 인터럽트의 종류
## 2.1 발생위치에 따른 구분

    1) 외부인터럽트(external) : 예상할 수 없는 시기에 프로세스 외부인 주변장치에서 처리를 요청하는 인터럽트
                               타이머인터럽트, I/O인터럽트, 머신체크인터럽트, 정전인터럽트

    2) 내부인터럽트(internal) : 예상된 시기에 어떤 기능을 발휘하도록 하기 위해 프로세스 내부에서 발생하는 인터럽트로, 트랩이라고도 함
                               0으로나누기, 오버플로우/언더플로우 인터럽트, 불법적인 명령어사용 인터럽트, 보호공간접근 인터럽트
 
 ## 2.2 발생주체에 따른 구분
 
     1) 하드웨어인터럽트 : 타이머, I/O, 머신체크, 정전 인터럽트
     2) 소프트웨어인터럽트 : SVC인터럽트, 프로그램 
 
---
# S2. 인터럽트 체제
## 1. 인터럽트 동작순서
- **인터럽트요청 - 현상태보존 - 인터럽트판별(원인판별,처리루틴시작) - 인터럽트취급(조치) - 인터럽트복귀(원래프로그램다시실행)**
- 
## 1.1 인터럽트 발생 시 CPU 처리사항
- PC(프로그램카운터)내용, 프로그램에서 사용한 모든 레지스터 내용, 플래그 상태조건 내용, 스택의 내용 또는 메모리 0번지 내용
 
## 2. 인터럽트 요청신호
## 2.1 단일 인터럽트 신호요청회선 (폴드인터럽트 방식, Polled)
- 인터럽트 요청이 가능한 장치를 CPU와 단일회선으로 연결한 방식
- 인터럽트를 요청한 장치 판별 과정이 필요
- 폴드인터럽트 방식이라고도 하며, 복귀주소인 PC(프로그램카운터)의 값을 메모리 0번지나 스택에 저장
- 인터럽트 요구가 있는 장치를 찾기위해 하나하나 찾아가는 방식으로 속도가 느림

## 2.2 고유 인터럽트 신호요청회선 (벡터인터럽트)
- CPU에 있는 인터럽트 레지스터의 각 비트에 고유의 회선을 연결하는 방식
- 벡터인터럽트 방식이라고도 하며, 하드웨어 신호가 발생하면 인터럽트 서비스 루틴으로 분기하는 명령들로 구성된 인터럽트 벡터를 이용하여 바로 인터럽트 서비스 루틴 실행
- 장치마다 고유한 인터럽트 요청신호회선을 가지므로 인터럽트를 요청한 장치판별과정이 필요없음

## 3. 인터럽트 원인 판별 방법
## 3.1 소프트웨어에 의한 판별 (폴링 Polling) : 인터럽트 우선순위 대로 정렬, 각각의 장치플래그 검사
- 인터럽트 요청을 받았을 때, 프로그램에 의해 **각각의 장치 플래그를 검사하여 어느장치에서 발생하였는가를 판별**하는 방식
- 프로그램으로 처리를 하기 때문에 인터럽트 반응 속도가 느림
- 소프트웨어 형식이기 때문에 변경이 쉽고 융통성이 있음
- 하드웨어적인 장비가 없기 때문에 경제적(비용저렴)
- 비교적 큰 정보를 교환하는 시스템에 적합
- 우선순위 변경이 비교적 쉬움
-
## 3.2 하드웨어에 의한 판별 (데이지체인 Daisy Chain) : 우선순위직렬연결, 장치번호찾아가기
- 인터럽트 요청장치를 **인터럽트 우선순위에 따라 직렬로 연결하고**,
- **CPU의 신호를 인지하여 자신의 장치번호를 CPU에 보냄으로써 요청한 장치를 판별하는 방식**
- 인터럽트 반응속도가 폴링방식에 비해 빠름
- 융통성이 없고 하드웨어 비용이 많이 들음
 
---
# S3. 인터럽트 우선순위 체제
## 1. 인터럽트 우선순위 순서
- **전원이상 > 기계고장 > 외부신호 > 프로그램(내부) > SVC (SuperVisor Call)**
 
## 2. 소프트웨어에 의한 우선순위 부여방식 (폴링 Polling)
- **인터럽트 순위가 가장 높은 장치부터 가장 낮은 장치 순으로 비교순서를 정해놓고, 우선순위를 부여하는 방식**
- 프로그램으로 처리하기 때문에 인터럽트 반응속도 느림
- 소프트웨어적이므로 프로그램의 변경이나 수정이 쉽기 때문에 융통성이 높음
- 하드웨어 장비가 없으므로 경제적

## 3. 하드웨어에 의한 우선순위 부여방식 (데이지체인 / 병렬)
- **하드웨어 회로에 의해 우선순위를 부여하는 것**으로,
- **CPU와 인터럽트를 요청할 수 있는 장치 사이에, 장치번호에 해당하는 버스를 연결하여 요청장치의 번호를 CPU에게 알려주는 방식**
- 인터럽트 반응속도가 폴링 방식보다 빠름
- 회로 복잡, 융통성 없음, 추가 하드웨어 필요로 인해 비경제적, 변경이나 수정 어려움

## 3.1 데이지체인에 의한 우선순위 부여방식
- 인터럽트 우선순위가 높은 순서부터 가장 낮은 순으로 하드웨어 회로를 직렬로 연결(데이지체인)하여 우선순위 부여
### 1) 인터럽트 요청 체인방식 (request)

    직접연결회로에서 CPU의 인터럽트 인지신호를 최초로 받은 장치가 가장 우선순위가 높도록 회로를 설계하여 우선순위 부여

### 2) 인터럽트 우선순위 체인방식 (Priority)

    인터럽트 요청을 하는 장치 중에서 가장 우선순위가 높은 장치만이 장치번호 버스를 이용하여 
    장치번호를 보낼 수 있도록 회로를 설계하여 우선순위 부여
    
## 3.2 병렬 우선순위 부여방식 (Parallel Priority)
- 인터럽트 요청 회선이 여러개로 이루어진 경우 우선순위를 병렬로 처리 가능
- 현재 취급 중인 인터럽트와 요청된 인터럽트를 비교하여 
- 요청된 인터럽트의 우선순위가 높은 경우에는 우선순위가 높은 인터럽트를 처리하고,
- 그렇지 않은 경우에는 취급 중인 인터럽트를 처리하는 것
- 처리중인 인터럽트보다 우선순위가 낮은 것을 비활성화 시키는 마스크레지스터를 가지고 있음

## 4. 가변-우선순위 방식
    1) 회전 우선순위 (Rotating Priority) : 중재동작이 끝날 때마다 모든 마스터들의 우선순위가 한 단계씩 낮아지고,
                                          가장 우선순위가 낮았던 마스터가 최상위 우선순위를 가지도록 하는 방법               
    2) 임의 우선순위 (Random Priority) : 각 중재동작이 끝날 때마다 우선순위를 임의로 결정하는 방법
    3) 동등 우선순위 (Equal Priority) : 모든 마스터들이 동등한 우선순위를 가지며 FIFO알고리즘을 사용하여 우선순위 결정
    4) 최소-최근사용 (LRU : Least-Recently Used) : 최근 가장 오래동안 버스를 사용하지 않은 버스 마스터에게 최상위 우선순위 할당

---
# S4. 병렬컴퓨터구조
## 1. 병렬처리기 (Parallel Processor)
## 1.1 파이프라인 처리기 (중첩)
- 하나의 처리기를 서로 다른 기능을 가진 여러개의 처리기로 나눈 후, 각각의 처리기가 동시에 서로 다른 데이터를 취급하는 방법
- 시간적 병렬성을 활용하기 위해 프로그램 수행에 필요한 작업을 시간적으로 중첩시키는 처리기

## 1.2 배열처리기
- 한 컴퓨터 내에서 여러개의 처리기를 배열 형태로 가지고 있는 것
- 배열처리기들을 동기화시켜 동일한 종류의 계산이 병렬적으로 실행되도록 함
- 벡터계산이나 행렬(매트릭스) 계산에 적합
- 제어처리기가 명령어를 인출

## 1.3 다중처리기
- 자율적 실행이 가능한 두개 이상의 처리기로 구성되며, 처리기들은 여러 자원을 공유할 수 있음
- 전체 하드웨어 시스템은 단일 운영체제에 의해 운영되도록 함
- 한 작업을 여러개로 나누어서 서로 다른 처리기에 할당하여 동시 수행되도록 함으로써, 실행시간을 줄이고 전체 처리효율이 향상됨
<img width="300" src="https://user-images.githubusercontent.com/29009929/153235084-c4191d31-d05c-4daa-bb63-cb8bbd7286d0.png">
   
    <다중처리기> (위 이미지 참고)
    - CPU들이 하나의 메모리를 공유하므로, 종속적
    - 강결합 (각 처리기가 공유기억장치를 통하여 정보를 교환하는 방식으로, 한가지 일을 처리하는 고속처리방식)
    - CPU가 똑같은 일을 수행 가능하므로 대칭구조

    <다중컴퓨터>
    - CPU가 각각의 메모리를 이용하는 방식으로, 독립적
    - 약결합 (각 처리기가 독립적인 기억장소를 가지고 통신으로 연결되어 상호 정보를 교환하는 방식으로, 많은 양을 처리하는 분산처리시스템)
    - CPU와 메모리가 떨어져있으므로 분리구조
    - OS 여러개

## 1.4 벡터처리기
- 파이프라인 기법을 이용한 다중처리기법 사용
- 시슬로틱배열구조로 나타낸 벡터처리기는 신호 및 화상처리와 같은 특별한 응용에 사용됨
- 비용과 성능 면에서 우수하나 응용의 한계성, 프로그램 등의 단점이 있다

      * 시슬로틱배열구조 : 파이프라인배열구조의 새로운 범주로서, 지역적으로 연결된 프로세서들이 규칙적으로 데이터를 계산하고, 
                          시스템을 통해 데이터를 전달하는 프로세서 네트워크
 
## 2. 병렬컴퓨터 구조의 분류
## 2.1 플린(Flynn)의 분류
프로그램 수행 중 처리기가 동시에 수행하는 명령과 데이터 수에 따라 구분하는 방법

    1) SISD (single instruction stream, single data stream) : 하나의 명령에 하나의 데이터를 처리하는 단일 프로세서 시스템.
                                                              파이프라인 처리기가 SISD에 속함.
                                                              명령이 하나씩 순서대로 실행되지만, 실행과정은 여러개의 단계로 나누어 
                                                              파이프라인으로 연결하여 처리하는 방식.

    2) SIMD (single instruction stream, multiple data stream) : 하나의 명령에 여러개의 데이터를 처리하는 배열처리 형태.
                                                                배열처리기가 SIMD에 속함.
                                                                여러개의 프로세서가 하나의 제어장치에 의해 제어되는 구조.

    3) MISD (multiple instruction stream, single data stream) : 하나의 데이터에 대해 여러개의 명령을 수행하는 구조
                                                                벡터처리기인 시슬로틱배열 구조가 MISD에 속함.
                                                                일반용도의 컴퓨터로는 거의 사용하지 않음.

    4) MIMD (multiple instruction stream, multiple data stream) : 여러개의 명령이 여러개의 데이터를 처리하는 방식.
                                                                  다중프로세서가 MIMD에 속함.
                                                                  진정한 의미의 병렬처리방법




 
