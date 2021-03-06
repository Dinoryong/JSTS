# CodeSpitz 77 - ES6+ Basics

-----

> [toc]

<br/>

## Chapter 01

> 프로그래밍이란 , 그 근간

### 1. Why did you do that ? (너 왜 코드를 그렇게 짰어?)

> 철학 => 가치 원칙 패턴 => 동기

- 철학 - 합리주의 , 상대주의

- 프로그래밍을 짤 때 3가지 원칙 : 가치, 원칙, 패턴 (켄트 백's 구현 패턴')

- 가치 - 의사소통, 단순함, 유연함 

- 원칙 

  -  ex(무더위에 교장선생님 훈화말씀), 원칙의 가치는 원칙의 예외를 금방 알아차릴 수 있다는 것, 

  - 지역화, 중복제거, 대칭성

- 패턴

  - 개발론 , 설계론 , 각종 적용 패턴
  - 경험, 디버깅 비용은 어지간해서 줄어드지 않았다, 절대적인 것이 아니라 상대적 및 경험, 경험이 반복되면 진리에 가까워진다,

- 동기

  - 돈 : 왜 이렇게 짰어 ? 이렇게 짜면 비용(시간)을 줄일 수 있어요 ! 소프트웨어는 원가율에서 인건비만 100% 다. 

<br/>

### 2. Program & Timing

> Timing - 급여 프로그램을 만들 때 lint error, compile error, run time error(잡기 어렵다, 프로그램 다시 갈아넣는 수 밖에 없다) , context error(런타임까지 통과한 후의 프로그래머의 논리 에러 - 팀의 의사소통으로 해결해야 한다, 개발자들끼리 모듈을 나눠서 개발하다가 기획안에 대한 해석 오류)

- Language Code : 사람이 읽을 수 있는 코드
  - Timing - Lint Time

- Machine Language : 컴파일링을 통해 기계가 읽을 수 있는 코드
  - 오히려 단순한 밥솥 작동처럼 머신 랭귀지를 바로 보는 것이 편할 떄도 있다.
  - Timing (시점) - Compile Time
- File :  java.file
- Load : 파일을 클릭하면 메모리에 로드가 된다. 로드 시점부터 프로그램이라고 부를 수 있다. 로드에 적재된 그 것만이 프로그램 파일이라고 한다. 로드까지의 영역은 프로그래머의 영역

- Run : 로드한 이후에 드디어 실행, 실행은 기계가 한다
  - Timing - Run Time

- Terminate : 종료

<br/>

### 3. Script Program

> JavaScript

- Language Code - Lint Time
- File - 파일로 바로 떨어뜨린다
- Load - 별도의 컴파일 과정 없이 브라우저에 로드한다
- Machine Language - 스크립트 언어를 구분하는 특성, 타 프로그램과 달리 순서가 바뀐다
- Run - Run Time - 즉, 스크립트 언어에서는 컴파일링 작업이 없기 떄문에 런 타임이 중요하다
- Terminate

<br/>

### 4. Run Time ( in Compile language )

> 공부를 한다는 것은 이 분야의 용어 설명을 정확하게 설명할 수 있다는 의미
>
> 폰 노이만의 프로그램 구조 - 끊임없이 순환하면서 명령어를 소진한다

- Loading

  - 파일을 로딩해서 메모리에 적재 될 때, 메모리에 명령 부분과 값(데이터) 부분으로 나눠서 적재된다

- Instructuon Fetch & Decoding

  > Instruction : CPU 가 해석할 수 있는 명령어 (프로그램을 만든 명령어랑은 다르다)
  >
  > Fetch : 메모리에서 가져온 명령어를 외부 버스에서 fetch 해서 디코더에서 디코딩
  >
  > Decoding : 디코더에서 디코딩
  >
  > Execution : 실행, 명령어를 끝까지 다 실행하면 종료(Terminate)
  >
  > 프로그램은 메모리에 적재된 명령어 부분과 데이터 부분

  - 다음으로 실행하면, CPU (대표적 4가지 장치) 에 보낸다 :
    - 외부 입출력 인터페이스 : 캐시 레이어 비롯해서 추상적인 명령이 메모리에서 들어올 때 거치는 관문 (why? 캐시를 통해서 이 명령어를 새로 해석하지 않고 바로 꺼낼 수도 있고, 자기 cpu에 맞게 번역작업을 하기도) 
    - 제어유닛 - 디코딩 : 추상적인 명령어를 디코딩해서  CPU가 알아들을 수 있게 해석
    - 연산유닛 - 제어정보 : 결국 cpu 가 하는 일, 제어유닛에서 명령어 받아오고 데이터유닛에서 데이터를 받아온다. 즉 실행한다
    - 데이터유닛 : 메모리에서 데이터 부분을 받아온다 (미리 많은 메모리블록을 로딩해두긴 한다), 데이터부분을 연산유닛으로 보낸다, 연산유닛의 결과 데이터를 다시 데이터 유닛으로 들어온다, 이 데이터를 그냥 지울건지 혹은 메모리 데이터부분으로 보낼건지를 결정하는 것은 또 다른 명령이다.

<br/>

- Compiler : 이 때에는 실제 메모리가 없다. 가상 메모리를 활용(매핑)해서 저 작업을 하는 것이다 (복습 체크)

<br/>

- Essential Definition Loading => V-Table Mapping (필수 과정) => Run => Runtime Definition Loading

