
Observable

데이터 흐름에 맞게 알림을 보내 구독자가 데이터를 처리할 수 있도록 한다

RxJava 1.x의 데이터 소스 
 - Observable
 - Single

RxJava 2.x
 - Observable
    - Observable
    - Maybe
    - Flowable
 - Single


Maybe : reduce()함수나 firstElement() 함수와 같이 데이터가 발행될 수 있거나 혹은 발행되지 않고도 완료되는 경우를 의미
Flowable : Observable에서 데이터가 발행되는 속도가 구독자가 처리하는 속도보다 현저하게 빠른 경우 발새하는 배압 이슈에 대응하는 기능을 추가로 제공한다
