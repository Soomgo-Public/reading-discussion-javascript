## 📚 읽은 내용

### 3.3 언박싱
- 객체 레퍼의 원시 값은 valueOf() 메서드로 추출

```javascript
var a = new String("abc");

a.valueOf(); // "abc"

var b = a + ""; // b에는 언박싱되어 원시 값 "abc"가 대입된다.
```
- 이유에 대해서는 4장에서 언급예정!

### 네이티브, 나는 생성자다
- 배열, 객체, 함수, 정규식 값은 리터럴 형태로 생성하는것이 일반적
- 리터럴은 생성자 형식으로 만든것과 동일 종류의 객체
- 확실히 필요해서 쓰는게 아니라면 생성자는 가급적 피하는게 좋다. ......네?

### 3.4.1 Array
- Array 생성자에는 특이한 점이 있다..

```javascript
var a = new Array(1,2,3); // [1,2,3]
var b = new Array(5); // [empty × 5] <- 출력된 값 미리 배열의 크기를 정하는 Presize 기능
```
- 위와 같은 부분은 `구멍 난 배열` 이라고 한다.
- 브라우저 환경에 따라 콘솔에 찍히는 부분도 다르다. [ ,,, ]로 나오는 경우도 존재....
- 필요했던가에 대한 의문... undefined를 채우기 위해 `Array.apply(null, {length: 3})` 사용 가능

### 3.4.2 Object(), Function(), and RegExp()
- 리터럴 형태로 한번에 여러 프로퍼티를 다루거나 충분히 편하게 선언이 가능하기에, 리터럴 형식을 적극 권장

### 3.4.3 Date(), and Error()
- 해당 네이티브 생성자는 리터럴 형식이 없으므로 유용하다.
- date 객체는 유닉스 타임스탬프 값을 얻고, getTime() 호출 가능하다. `ES5부터는 Date.now()로 호출 가능`
- Error 객체 인스턴스에는 message 프로퍼티가 있어, 사용 가능하다.

### 3.4.4 Symbol()
- ES6부터 선보인 새로운 원시 값 타입이다.
```javascript
var mysym = Symbol( "my own symbol" );
mysym; // Symbol(my own symbol)
mysym.toString(); // "Symbol(my own symbol)"
typeof mysym; // Symbol

var a = { };
a[mysym] = "foobar";

Object.getOwnPropertySymbols(a); // [Symbol(my own symbol)]
// [ Symbol(my own symbol)
```
- 심볼은 객체가 아니고, 단순한 스칼라 원시 값이다.
### 3.4.5 네이티브 프로토타입
- 내장 네이티브 생성자는 .prototype 객체가 존재하며, 각 고유한 로직을 가지고 있다.
- 박싱으로 확장한 것 까지 포함하여, String을 가지고 있다면, String.prototype 객체에 정의된 메서드에 접근할 수 있다. (프로토타입 위임)

```javascript
// String#indexOf();
// String#charAt();
// String#substr();

a.indexOf("c"); // 3
a.toUpperCase(); // "ABC"
a.trim() // "abc"
```
- 네이티브 프로토타입을 변경할 수도 있는데, 바람직하지 않은 발상이다.

### 📚 느낀점
- 프로토타입에 대해서 깊게 알 수 있었다. 단번에 이해가 되지 않아, 몇번이고 반복해서 보아야 할 것 같다.

### 📚 공유하고 싶은 부분(사이트)
- https://developer.mozilla.org/ko/docs/Glossary/Primitive


