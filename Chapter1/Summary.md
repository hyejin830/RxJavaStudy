
# 리액티브 프로그래밍

<br>

## 1.1 리액티브 프로그래밍란

### 리액티브 프로그래밍
- 데이터 흐름과 전달에 관한 프로그래밍 패러다임
- 데이터 흐름을 먼저 정의하고 데이터가 변경되었을 때 연관되는 함수나 수식이 업데이트되는 방식

예) 마이크로소프트 엑셀(스프레드 시트)
각 셀에 값을 넣거나 혹은 다른 셀을 조합해서 내가 원하는 값을 계산

구체적인 예)
회사에서 올해 1월부터 12월까지 매출액의 합을 구한다
리액티브 프로그래밍의 `데이터 소스` : 월 매출액

##### 과정
최종 매출액 결산 후, 매출이 변경되면 다시 가져와서 총합을 구하는 방식이 아닌 <br>
매월 매출액으로 지정해놓은 데이터 소스에서 변경된 값을 전달  <br>
미리 지정해둔 수식을 통해 계산되어 연말 매출액 갱신 <br>

<br>

### 방식의 종류

#### 명령형 프로그래밍 방식
변경이 발생했다는 통지를 받아서 연말 매출액을 새로 계산하는 당겨오는 방식 : Pull

#### 리액티브 프로그래밍 방식
데이터 소스가 변경된 데이터를 밀어주는 방식 : Push
일종의 옵서버 패턴

<br>

### 전통적인 개념

#### 컴퓨터 프로그래밍
모델의 값에 변화가 생겼을 때 뷰를 자동으로 업데이트 해주는 목적으로 사용
매월 매출액 : 모델

#### 하드웨어 분야
전자회로 일부 소자의 속성값이 변경되었을 때 전체 회로에 미치는 영향을 바로 알 수 있는 HDL
시스템에 어떤 이벤트가 발생했을 때 처리

#### 네트워크 프로그래밍
사용하는 콜백이나 UI프로그래밍할 때, 버튼 이벤트를 처리하는 클릭리스너도 개념상으로 리액티브 프로그래밍에 해당

<br>

### 결론

전통적인 개념 + 몇가지 요소 추가 = RxJava 기반의 리액티브 프로그래밍

---------------------------------------------------------------------------------------------------------------------

1.1.1 자바 언어와 리액티브 프로그래밍

두가지 관계

- 기존 pull 방식의 프로그래밍 개념을 push 방식의 프로그래밍 개념으로 바꾼다
- 함수형 프로그래밍의 지원을 받는다

! 함수형 프로그래밍은 정말 공부해야겠구나 !

자바 언어 : 객체지향
예) 2월 매출액 감소, 8월 매출액 중가 -> 데이터베이스에서 월간 매출액의 합계를 가져옴(Pull) 
계산 시점은 사용자가 새로 고침 버튼을 누를 때

전국 매장의 실시간 정보 집계 -----------> 분석 데이터를 전국 매장에 통지

자바 : 각 매장의 변화 상황을 데이터베이스에서 가져와야 함. 
       통지를 위해서는 전체 매장 리스트를 기반으로 순차적으로 상황 전달
       
리액티브 : 데이터 변화가 발생했을 때 변경이 발생한 곳에서 새로운 데이터를 보내줌(PUSH)

콜백이나 옵서버 패턴은 옵서버가 1개이거나 단일 스레드 환경에서는 문제 없지만,
멀티 스레드 환경에서는 사용할 때 많은 주의가 필요함
예) 데드락과 동기화 문제

! 스레드 공부도 필요하다 !

함수형 프로그래밍은 부수 효과가 없다

부수 효과 : 콜백이나 옵서버 패턴이 스레드에 안전하지 않은 이유는 같은 자원에 여러 스레드가 경쟁 조건에 빠지게 되었을 때 예측할 수 없는 잘못된 결과가 나오는 것

암튼 부수 효과가 없는 순수 함수를 지향하기 때문에
멀티 스레드 환경에서도 안전

자바언어로 리액티브 하려면 함수형 프로그래밍  지원이 필요~

1.1.2 리액티브 프로그래밍 개념 잡기

리액티브 프로그래밍은 데이터 흐름과 변화의 전달에 관한 프로그래밍 패러다임

컴퓨터 프로그램 3가지

변환 프로그램 : 주어진 입력값을 바탕으로 결과를 계산하는 프로그램
 예) 컴파일러와 수치 계산 프로그램

상호 작용 프로그램 : 프로그램이 주도하는 속도로 사용자 혹은 다른 프로그램과 상호작용
 예) 시분할 시스템
 
리액티브 프로그래밍 : 주변의 환경과 끊임없이 상호작용하는데 프로그래밍 주도하는 것이 아니라 환경이 변하면 이벤트를 받아 동작
외부 요구에 반응에 맞춰 일하고 대부분 정확한 인터럽트 처리를 담당

1.2 RxJava를 만들게 된 이유

- 동시성을 적극적으로 끌어안을 필요가 있다
- 자바 future를 조합하기 어렵다는 점을 해결해야 한다
- 콜백 방식의 문제점을 개선해야 한다



1.3 RxJava 처음 시작하기

1.3.1 io.reativex

1.3.2 Observable 클래스

1.3.3 just


