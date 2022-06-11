## 📚 읽은 내용

### 0(영)
```javascript
var a = 0 / -3;
// (일부 브라우저에 한하여) 제대로 묘사한다.
a; // -0

a.toString(); // "0"
String( a ); // "0"
JSON.stringify( a ); // "0"

// 신기하게도 반대로 하면(문자열에서 숫자로 비꾸면) 있는 그대로 보여준다

+ "-0" / // -0
Number( "-0" ); // -0
JSON.parse( "-0" ); // -0

// ES6부터 지원하는 Object.is 함수 (예외 처리도 되어 있음)

var a = 2 / "foo";
var b = -3 * 0;

Object.is(a, NaN); // true
Object.is(b, -0); // true
Object.is(b, 0); // false
```
- 0에 대한 부분에 대한 필요성을 느껴서 존재하다고는 하지만 경험적으로도 없고 예시가 뚜렷하지 않아서 애매한 것 같다.

### 값 vs 레퍼런스

- 자바스크립트는 포인터라는 개념 자체가 없다.
- JS에서는 변수가 다른 변수를 참조할 수 없다. 오호..
- 자바스크립트에서는 값의 타입을 기준으로 값-복사, 레퍼런스-복사가 결정된다
  - 원시 값은 값을 전달
  - 객체나 함수 등 합성 값은 레퍼런스 사본 전달
- [].slice를 통해 레퍼런스 원본을 가르키지 않도록 사본 생성 가능
- 같은 스칼라 원시 값을 레퍼런스 형태로 넘기려면 Number 객체 래퍼로 원시 값을 박싱하면 된다

```javascript
function foo(x) {
  x = x + 1;
  x; // 3
}

var a = 2
var b = new Number( a ); // Object(a)
foo( b );
console.log(b); // 3이 아닌 2가 출력
```

## 3장. 네이티브
- 가장 많이 쓰이는 네이티브 (내장함수)

<img src=daniel/img.png alt="img" width="250"/>

```javascript
// 네이티브 함수 String()
var a = new String('abc') // 원시값이 아닌 "abc" 값을 감싼 레퍼이다.
console.log(a); // String {0: "a", 1 : "b", 2: "c", length: 3, [PrimitiveValue] : "abc"}
```

### 내부[[Class]]

```javascript
Object.prototype.toString.call([1,2,3]);
// "[object Array]"
Object.prototype.toString.call(/regex-literal/i);
// "[object RegExp]"

// typeof가 object일 경우에는 [[Class]] 라는 내부 프로퍼티가 붙는다.
Object.prototype.toString.call(true);
// "[object Boolean]"
```
- 다른 원시값들도 박싱의 과정을 거쳐 해당 객체 레퍼로 감싸진다. 
- 필요시 엔진이 알아서 암시적으로 박싱하는 과정을 거쳐, length 같은 부분을 사용할 수 있다.
- 수동으로 원시값을 박싱하려면 Object() 함수를 사용하자!

### 📚 느낀점
- 이론적인 부분을 다뤄서 새로운 부분이 많았던 것 같다! 항상 코딩을 하고 있지만, 의미론적으로 맞게 사용하는것인지에 대한 의문이 생기는 장이였던 것 같습니다!

### 📚 공유하고 싶은 부분(사이트)
X


