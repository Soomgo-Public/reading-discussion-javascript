## 📚 읽은 내용
- 코드 블록 {} 은 혼자 독립적으로 존재할 수 있다
- 레이블 문 (Labeled Statement)
    - goto와 비슷하지만 조금 다른
    - 루프문에서 continue, break 를 Labeled 로 사용 가능
        - 사용 시 지정한 루프문의 다음 순회를 바로 이어서 실행
    - 비 루프(Nonloop) 블록에서 break를 Labled로 사용 가능
        - 사용 시 지정한 블록을 탈출
    - 권장되지 않음
- js에 else if 절은 없다
    - if의 경우 실행문이 하나인 경우 블록을 감싸는 {} 를 생략해도 되는 것처럼, else 도 마찬가지로 생략할 수 있다
    - 그래서 else if 가 동작했던 것..
- 연산자 우선순위
    - 표([https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#표](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#%ED%91%9C))
    - 예시
        1. &&
        2. ||
        3. ?:
        4. =
        5. ,
    - 단락 평가: 일부 평가 결과만으로 전체 결과가 이미 결정될 경우 나머지의 평가를 건너뛰는 것
    - 결합성
        - 연산자는 좌측부터 그룹핑이 일어나는지, 우측부터 그룹핑이 일어나는지에 따라 좌측 결합성(Left-Associative) 또는 우측 결합성(Right-Associative)를 가진다
        - 처리방향과는 무관한 이야기

## 📚 느낀점
- 레이블 문 신기
- else if 충격
- 연산자 우선순위 새롭게 배워갑니다
- 결합성 이해하느라 애먹었어요. 설명이 개떡이 아닌가하는 작은 반항심을 가져봅니다.

## 📚 공유하고 싶은 부분(사이트)
- 연산자 우선순위 표([https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#표](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#%ED%91%9C))
