# S1. 논리회로의 기본
## 1. 불대수의 기본정리
<img width="400" src="https://user-images.githubusercontent.com/29009929/152480395-36509e9f-352b-4607-b3d0-77075ce0794c.png">

- 드모르간의 법칙 (A+B)' = A'B'

## 2. 논리게이트
<img width="400" src="https://user-images.githubusercontent.com/29009929/152480681-ce34ffc5-bbcb-4f9c-92e1-caf25cd96466.png">

## 3. 카르노맵
<img width="250" src="https://user-images.githubusercontent.com/29009929/152481594-5bf7a2f3-5238-4225-a0d6-923c163c932d.png">

---
# S2. 조합논리회로 (Combination Logic Circuit)
- 논리게이트의 조합으로 만들어진 회로이며, 현재의 입력 변화에 의해서만 출력이 결정되는 회로
- 플립플롭과 같은 기억회로를 가지지 않음
- 불대수, 진리표 사용
- 가산기, 감산기, 디코더, 인코더, 멀티플렉서, 디멀티플렉서, 연산기(ALU)

## 1. 조합논리회로의 종류
## 1.1 반가산기 (Half Adder)
- A와 B를 더한 합 S와 자리올림수 C를 얻는 회로
     
      AND 1개, XOR 1개
      합(S) = A⊕B
      캐리(C) = A·B
      
<img width="250" src="https://user-images.githubusercontent.com/29009929/159107719-66c568bf-6a39-43ec-a1be-1b537497243d.png">
<img width="200" src="https://user-images.githubusercontent.com/29009929/159107731-6270a542-dd65-4bf7-892e-c3d4e8130b15.png">


## 1.2 반감산기 (Half Subtracter)
- A에서 B를 뺀 차 D와 빌려온 수(자리내림수) B를 얻는 회로

      NOT 1개, AND 1개, XOR 1개
      -> 반가산기와 달리 NOT게이트 1개가 추가됨
      차(D) = X⊕Y
      빌려온수(B) = X'·Y

<img width="300" src="https://user-images.githubusercontent.com/29009929/159108294-c68ac126-1095-4b6a-8c97-c6289e2bb737.png">


## 1.3 전가산기 (Full Adder)
- 자리올림수도 고려하여 3개의 2진수를 더할 수 있게 만든 회로

      반가산기 2개, OR 1개  (반가산기 : AND 1개, XOR 1개)
      -> AND 2개, XOR 2개, OR 1개
      합(S) = A⊕B⊕C
      캐리(C) = (A⊕B)·C + A·B 또는 A·B + B·C + A·C

<img width="300" src="https://user-images.githubusercontent.com/29009929/159107913-6fded893-37c5-4e95-b2a5-6e9b4f8e9231.png">
<img width="300" src="https://user-images.githubusercontent.com/29009929/159107948-7c8764ed-383f-4304-8dfa-4e433a761dbc.png">
<img width="300" src="https://user-images.githubusercontent.com/29009929/159107973-8b50383f-90d5-4083-9960-e607ebab6fe1.png">
<img width="350" src="https://user-images.githubusercontent.com/29009929/159108006-7a425a90-dd5c-4a9b-8664-22a9060a5dcb.png">


## 1.4 전감산기 (Full Subtracter)
- 자리내림수도 고려하여 3개의 2진수를 감산할 수 있게 만든 회로
      
      반감산기 2개, OR게이트 1개  (반감산기 : NOT 1개, AND 1개, XOR 1개)
      -> AND 2개, XOR 2개, NOT 2개, OR 1개
      차(D) = X⊕Y⊕B
      빌려온수(B) = (X⊕Y)'·B + X'·Y

<img width="400" src="https://user-images.githubusercontent.com/29009929/159108424-6d9a5f18-874f-4361-b8d4-b5a34ee4793d.png">

### 가산기 및 감산기 정리

     반가산기 : AND 1개, XOR 1개
     전가산기 : AND 2개, XOR 2개, OR 1개
     반감산기 : AND 1개, XOR 1개, NOT 1개
     전감산기 : AND 2개, XOR 2개, NOT 2개, OR 1     

## 1.5 병렬가산기 (Parallel Adder)
- 여러 비트를 가산하기 위한 회로
- 반가산기 또는 전가산기 여러개를 합쳐서 만들어짐
- 반가산기를 이용해서 만들 경우 : (2n-1)개의 반가산기, (n-1)개의 or게이트 필요
- 전가산기를 이용해서 만들 경우 : 전가산기 n개 
## 1.5.1 병렬가감산기
- 덧셈과 뺄셈을 동시에 할 수 있는 4비트 병렬 가감산기
- 전가산기 4개, XOR 4개
## 1.6 디코더
- 컴퓨터 내부에서 2진수로 코드화된 데이터를 해독하여, 대응되는 한개의 신호로 바꾸어주기 때문에 해독기라고 함
- n개의 입력으로, 최대 2<sup>n</sup> 개의 출력을 얻을 수 있음
- AND 게이트로 만들어짐

<img width="250" src="https://user-images.githubusercontent.com/29009929/159109119-6ee3cca0-a7a2-4d76-a5d5-2bcb6caad799.png">

## 1.7 인코더
- 입력 정보를 여러 자리의 2진수로 코드화하여 전달하는 회로
- 해독기(디코더)와 정반대의 동작을 수행
- 2<sup>n</sup> 개의 입력을 받아 n개를 출력
## 1.8 멀티플렉서 (Multiplexer, MUX)
- 2<sup>n</sup> 개의 입력선에서 n개의 선택선을 가지고, 하나의 출력을 얻도록 구성
- 여러개의 입력회선이 들어가서 하나의 특정회선을 선택하도록 하므로, 선택기라고도 함
- 공통적인 버스라인을 구성하는데 많이 사용됨
## 1.9 디멀티플렉서
- 하나의 입력정보를 n개의 선택선을 가지고 2<sup>n</sup> 개의 출력을 얻도록 구성
- 중앙처리장치에서 어떤 내용을 특정 장치로 출력시킬 때 많이 사용
## 1.10 3-상태버퍼 (Tri-state Buffer)
- 세가지 상태 중 1의 상태는 전기적으로 하이레벨(H)이고, 0의 상태는 로우레벨(L)이며, 또 하나의 상태는 고 임피던스(회로가 끊어진 상태)상태를 말함
- 3상태버퍼 회로는 인에이블(1) 또는 디스에이블(0) 단자에 의하여 데이터의 전송방향을 하드웨어적으로 제어하는데 사용하게 됨
 
---
# S3. 순서논리회로 (Sequential Logic Circuit)
- 외부로부터의 입력과 현재상태에 의해 출력이 결정되는 회로
- 플립플롭이나 레지스터 장치로 구성되는 회로
- 기억 능력을 갖추고 있는 회로
- 플립플롭, 카운터, 레지스터, ROM
- (조합논리회로 : 현재의 입력 변화에 의해서만 출력이 결정)

## 1. 플립플롭 (Flip-Flop)
- 전원이 공급되고 있는 한, 상태의 변화를 위한 외부신호가 발생할 때까지 현재의 상태를 그대로 유지하는 논리회로
- 순서논리회로를 구성하는 기본기억소자
- 플립플롭 1개가 1비트를 기억할 수 있는 2진cell을 의미
- 반도체 기억장치에서 2진수 1자리 값을 기억하는 메모리소자

## 1.1 RS플립플롭
- 보통 NAND 게이트를 이용해 구성
- S와 R선의 입력을 조절하여 임의의 비트값을 그대로 유지시키거나, 무조건 0 또는 1의 값을 기억시키기 위해서 사용됨
- SET(S)단자와 RESET(R)단자를 가짐
- SET(S)단자와 RESET(R)단자가 모두 1인 경우는 모순이 발생하므로 허용되지 않음
- SET(S)단자에만 신호를 보내면 1값을 기억
- RESET(R)단자에만 신호를 보내면 0값을 기억
- Q(t) : time, Q(t+1) : 다음 time 
 
 <img width="300" src="https://user-images.githubusercontent.com/29009929/152485572-11e08663-43f0-4438-af5a-a2a46d03d83c.png"> <img width="245" src="https://user-images.githubusercontent.com/29009929/159109664-f632ff4b-10cf-49dd-8582-63700149ac32.png">

## 1.2 JK플립플롭
- RS플립플롭에서 S와 R이 각각 1일 때 허용되지 않는 것을 보완한 플립플롭
- RS플립플롭의 내부상태와 입력상태를 AND게이트로 처리하여 입력하는 플립플롭

 <img width="340" src="https://user-images.githubusercontent.com/29009929/152630640-3347f249-e05b-4d09-bf37-59b746a3ed69.png"> <img width="250" src="https://user-images.githubusercontent.com/29009929/159109677-a74ba20f-fcf9-49a6-a106-ef91befea4b5.png">

## 1.3 D플립플롭
- 입력값과 출력값이 같은 플립플롭
- 클록펄스(CP)의 시간 간격만큼 지연시켜 출력함 (1비트 지연소자로 사용됨)
- RS플립플롭에 NOT게이트(인버터)를 연결한 형태
- RS, JK플립플롭에서 서로 배타적인 경우만 이용되도록 고안된 플립플롭
 <img width="310" src="https://user-images.githubusercontent.com/29009929/152630702-ac211f5a-1438-45ab-b1bd-3aeb130c43c3.png"> <img width="250" src="https://user-images.githubusercontent.com/29009929/159109700-0764b2c5-743a-4b90-b31a-9e270b4c03a1.png">

## 1.4 T플립플롭
- JK플립플롭에서 J,K가 같은 값이 입력될 때만 이용할 수 있도록 고안된 플립플롭
- 토글기능(반전,보수)을 이용하고자 할 때 사용됨
- J와 K를 하나로 묶어 T(Toglle, 토글)로 표현
- 주로 카운터회로로 많이 사용되며, 누를 때마다 ON, OFF가 교차되는 스위치에 이용됨

 <img width="300" src="https://user-images.githubusercontent.com/29009929/152630810-1f73c405-204b-4357-a54e-d24fb28cccc0.png"> <img width="250" src="https://user-images.githubusercontent.com/29009929/159109718-e8e4f145-79fa-45af-ade6-ad32e8593163.png">

## 1.5 마스터슬레이브 플립플롭
- race현상을 해결하기 위해서 고안된 플립플롭
- 하나의 플립플롭이 주인역할을 하고, 다른 플립플롭이 종속되어 동작하도록 두 개 이상의 플립플롭 회로를 결합한 것
- 주 플립플롭은 시간펄스가 상승할 때(1일때) 동작하고, 종 플립플롭은 시간펄스가 하락할 때(0일때) 동작

          [race현상 (경쟁현상)]

          - 출력값을 입력값으로 사용하는 피드백과정에서의 불안정한 상태
          - JK플립플롭의 문제점 중, 출력이 보수가 된 다음에도 클록펄스가 계속 남아있게 되면 다시 보수를 취하는 연속적인 변화가 일어나는 것

<img width="250" src="https://user-images.githubusercontent.com/29009929/159109985-c6450cef-0097-4c31-bf8c-ce8a69ee6dc7.png">

## 2. 카운터 (Counter)
시간펄스의 수를 카운트하거나, 제어 장치에서 각종 회로의 동작을 제어하는데 사용됨
### 1. 리플카운터(비동기카운터)
- 가장 기본이 되는 비동기형 카운터
- 플립플롭 수를 n이라 한다면, 2<sup>n</sup> 개까지의 독립된 수를 전부 표현
- 첫번째 플립플롭의 클럭입력에만 클럭신호를 사용하고, 다른 플립플롭은 각 플립플롭의 출력을 다음 플립플롭의 클럭입력으로 사용함
- 즉, 플립플롭의 출력이 다른 플립플롭을 동작시키는 원인으로 작용하게됨
### 2. 동기카운터
- 모든 플립플롭에 공통으로 들어오는 클럭신호가 있음
- 하나의 펄스입력이 주어지면 모든 플립플롭이 동시에 동작한다는 장점이 있음
### 3. 모드카운터 
- 리플카운터는 전부 표현하는 반면, 모드(MOD)카운터는 임의의 수로 나눈 나머지만 표현할 수 있도록 개선한 카운터

## 3. 레지스터
- 여러개의 플립플롭을 합쳐서 만든 회로로, 연산에 사용될 데이터가 대기하거나, 연산된 결과 데이터가 임시적으로 대기함
- 일정 개수를 모아서 연산이나 누계에 사용하는 플립플롭의 특수한 모임
- 주로 CPU내부에서 연산결과를 중간저장하거나, 데이터를 불러오거나 저장할 때 사용함
1) 시프트레지스터 : 현재 레지스터에 있는 내용을 왼쪽이나 오른쪽의 연결된 플립플롭으로 1비트씩 이동시켜 밀어내기와 같은 동작을 수행하는 레지스터
2) 병렬시프트레지스터 : n개의 비트로 구성된 레지스터의 내용을, 연결된 다른 레지스터로 한 번에 이동시킬 수 있는 레지스터


