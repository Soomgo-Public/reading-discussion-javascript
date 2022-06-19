## 📚 읽은 내용

## 4.3 명시적 강제변환
- 분명하고 확실한 타입 변환
- 추론 필요가 없다.

### 4.3.1 명시적 강제변환: 문자열 <-> 숫자
```javascript
var a = 42;
var b = String(a);

var c = "3.14";
var d = Number(c);
```

- 박싱을 통해서 .toString()으로 명시적으로 String으로 변환 가능
- 앞에 + 단항 연산자를 이용하여 명시적 변환 가능

### 날짜 -> 숫자

```javascript
var d = new Date( 'Mon, 18 Aug 2014 08:53:06 1T");
console.log(+d); // 1408369986000

var timestamp = new Date().getTime();
// 해당 방법이 더 권장되는 방법

// ES5에 추가된 Date.now() 도 좋은 방법!
```

### 틸드(~)
- `~` 연산자는 32비트 숫자로 변환 후 NOT 연산을 한다.

```javascript
var a = 'Hello World'
~a.indexOf( "lo" ); // -4 <-- truthy!

if (~a.indexOf( "lo" )) { // true
    
}
//찾았다!

~a.indexOf( "ol" ); // 0 <-- falsy!
!~a.indexOf( "ol" ); // true

if (!~a.indexOf( "ol" )) { // true
    
};
//
```

### 비트 잘라내기
- ~~와 !!를 사용할 때 의도된 값을 정확히 출력하기 위해서 신중히 활용해야한다.

### 4.3.2 명시적 강제변환: 숫자 형태의 문자열 파싱
- parseInt, parseFloat은 문자열에서 부동 소수점 숫자를 추출한다.
- 하지만 예외상황이 많음으로, 2번째 인자로 진수 형태를 넣을 수 있는데, 넣는게 안전하다.

### 4.3.3 명시적 강제변환: -> 불리언
- 
### 📚 느낀점
- 박싱에 대해 효율적인 면을 또 느낄 수 있었다. (.toString() 등등)
- 앞에 + 를 붙였을 때, 명시적으로 숫자로 변환할 수 있는걸 알게 되었다.
- string의 값을 찾을 때, 틸드를 이용하는 방법도 있다는 것을 알게 되었다
- Number()와 parseInt 차이점과 두번째 인자의 소중함을 알게 되었다.
- Boolean이나 !!를 쓰는 방법에 대해서는 이해를 위해서는 Boolean이 조금 더 이점이 있지 않을까 싶었습니다!

### 📚 공유하고 싶은 부분(사이트)
- https://gist.github.com/arthurvi/66cb1e2bcfc92f99f465e0db04264367