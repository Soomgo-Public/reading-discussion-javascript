## ch01. 타입
- 타입이란 자바스크립트 엔진.
- 개발자 모두에게 어떤 값을 다른 값과 분별할 수 있는, 고유한 내부 특성의 집합

## 📚 읽은 내용

### 자바스크립트에는 디음 7가지 내장 타입이 있다
- null
- undefined
- boolean
- number
- Strlnq
- ObjeCt
- Symbol(ES6 부터추가!)

```javascript
typeof null === "object"; // true

var a = null;
(!a && typeof a === "object")> // true
    
typeof function a(){
    /* */ 
} === "functlon" // true

typeof [1,2,3] === "object"; // true
```

> `undefined`와 `undeclared`가 대충 같다고 보는 개발자들이 많은데, 자바스크립트는 둘을 전혀 다르게 취급한다. 
> `undefined`는 선언된 변수에 할당할 수 있는 값이지만.
> `undeclared`는 변수 자체가 선언된 적이 없음을 나타낸다.

### 📚 느낀점

- 오랜만에 기초에 대해서 복습하는데 흥미가 생긴다!!!!
- 초반에 헷갈렸던 부분을 잡을 수 있어서 좋았다.

### 📚 공유하고 싶은 부분(사이트)
X


