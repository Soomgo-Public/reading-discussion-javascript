## 📚 읽은 내용

### 문자열
```javascript
var a = 'foo'
var b = ['f','o' ,'o' ];

// 문자열은 불변 값, 배열은 가변 값이다.
// IE 버전에 따라 b[0]이 undefined가 되거나, 정상 할당된다.
// hack을 이용하여 문자열의 reverse 등을 조작한다.
// string > array > use array method > string
```

### 숫자
- JS에서는 number 타입이 유일하다.
- 여러가지 표현 방식을 수용한다.

```javascript
var a = 42.300 // (0)
var b = 42.0 // (0)
var c = 42. // (0)

0.1 + 0.2 === 0.3 // false

// Number.EPSILON을 사용하여 동등함 (오차 이내)를 비교할 수 있다.

var a = 42;
console.log( void a, a ); // undefined 42
// void 연산자

var b = "foo"
window.isNaN(b) // true 함수의 결함 존재 foo가 숫자는 아니지만, Nan은 아니다.
Number.isNaN(b) // false ES6에서 등장, 폴리필 사용하여 체크
```

### 📚 느낀점

- 수학적인 부분이 많이 나와서 혼란스러웠다.
- 여기서 언급했는데, 어플리케이션 단에서 정수를 주로 사용하고, 큰 값들을 사용하기 때문에, 소수에 관한 부분은 깊게 고려 하지 않아도 된다는거에 공감이 됐다.
  - (그래도 알면 좋을 것 같은....)

### 📚 공유하고 싶은 부분(사이트)
X


