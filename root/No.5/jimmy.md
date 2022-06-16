## 📚 읽은 내용
- 명시적 강제변환
    - 의도적으로 일으키는 타입변환
    - ex) 42 + “”
- 암시적 강제변환
    - 다른 작업 도중 불분명한 부수 효과로부터 발생되는 타입변환
    - ex) String(42)
- 추상 연산 (Abstract Operation)
    - 엔진 내부 전용 연산
    - ToString
        - “문자열 아닌 값 → 문자열” 변환 작업
        - 내장 원시 값은 결과 값이 정해져 있다
            - ex)
                - null → “null”
                - undefined → “undefined”
        - 객체를 변환하는 경우 객체의 toString()을 호출
        - JSON 안전 값은 JSON.stringify() 를 통해 JSON 값으로 변환되는 방식은 ToString 추상 연산의 방식과 동일
    - ToNumber
        - “숫자 아닌 값 → 숫자” 변환 작업
        - true → 1, false → 0, undefined → NaN, null → 0
        - 문자열 값에 적용하면 숫자 리터럴처럼 작동한다
            - ex) “500” 에 ToNumber 연산 적용한 것과 숫자 리터럴 500은 동일
            - 예외: 0이 앞에 붙은 8진수 문자열 값은 10진수로 처리된다
        - 객체에 적용하면 우선 원시값으로 변환 후 그 결과값에 ToNumber를 적용한다
            - 객체 → 원시값 변환에는 ToPrimitive 추상 연산이 사용된다
    - ToPrimitive
        - “원시값이 아닌 값 → 원시값” 변환 작업
        - 객체의 valueOf()를 호출하고, 반환값이 원시값이 아니면 toString()을 호출, 이마저도 안되는 경우 TypeError 오류 던짐
    - ToBoolean
        - “Boolean이 아닌 값 → Boolean” 변환 작업
        - JS의 모든 값은 Boolean으로 강제변환하면 false가 되는 값과 그렇지 않은 값으로 나눌 수 있다
        - falsy 값
            - 강제변환시 false가 되는 값은 몇 없다
            - undefined, null, false, +0, -0, NaN, “”
        - truthy 값
            - falsy가 아닌 모든 값
            
## 📚 느낀점
- 머리 아프다
- 꼭 써먹을일이 오기를
- 추상 연산 이름 멋지네

## 📚 공유하고 싶은 부분(사이트)



