## 📚 읽은 내용

### 3.3 스코프 역할을 하는 함수
- 함수선언 > foo라는 확인자 이름으로 둘러싸인 스코프는 '오염시킨다'는 의미
```javascript

(function foo() {
    var a = 3;
})();

```
- 함수 선언문이 아닌 함수 표현식으로 취급됌
- 함수 표현식에서도 이름을 항상 쓰는 것이, 좋다. (디버깅 어려움, 폐기 예정 arguments.callee 참조 필요 등)

### 3.3.2 함수 표현식 즉시 호출하기
- 즉시 호출 함수

```javascript
var a = 2;
(function IIFE() {
    var a = 3;
    console.log(a); // 3
})();

console.log(a); // 2

var a = 2;

(functlon IIFE( global ){
    var a = 3;
    console.log( a ); // 3
    console.log(global.a); // 2
})( window );

console.log(a); // 2

```

### 3.4.3 let
- let을 이용해 변수를 현재 블록에 붙이는 것은 약간 비명시적이다. 명시적 블록 스코프 스타일은 자연스럽기 때문에 중요
- let을 사용한 선언문은 속하는 스코프에서 호이스팅 효과를 받지 않는다.

```javascript

{
    console.log(bar); // ReferenceError!
    let bar = 2;
}

```

- 명시적으로 블록을 선언하여 변수의 영역을 한정하는 것은, 가비지 컬렉션에서도 효과적이다.
```javascript

function process(data) {
    // do something
}

{
    let someReallyBigData = {};
    process(someReallyBigData);
}
```

## 📚 느낀점
- 명시적으로 블록 선언한 부분에서 가비지 컬렉션에 효과적이라는 것을 처음 알게됌
- let const ES6에 나왔던 부분, 복습하게 됐다.
- 즉시 호출 함수에 대한 부분에 window 객체를 넘기는 예제가 와닿았고, 저렇게 사용할 수 있는것도 처음알게된... 어디에 필요한지는 아직 의문..

## 📚 공유하고 싶은 부분(사이트)
