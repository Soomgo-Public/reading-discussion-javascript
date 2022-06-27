## 📚 읽은 내용

### 추상 동등 비교
##### 문자/숫자
```javascript
var a = 42; 
var b = "42";
a === b; // false 
a == b; // true
```
- Type(x)가 Number고 Type(y)가 String이면,x==ToNumber(y) 비교 결과를 반환한다.
- Type(x)가 String이고 Type(y)가 Number면,ToNumber(x)==y 비교 결과를 반환한다.

##### */불리언
```javascript
var a = "42";
var b = true;
a == b; // false
```
- Type(x)이 불리언이면 ToNumber(x)=y의 비교 결과를 반환한다.
- Type(y)이 불리언이면 x==ToNumber(y)의 비교 결과를 반환한다.

##### null/undefined
- null과 undefined는 느슨한 동등 비교 시 싱호 간의 암시적인 강제변환이 일어나므로 비교 관점에서 구분이 되지 않는 값으로 취급된다.

##### 객체/비객체
```javascript
var a = 42;
var b = [42];
a == b; // true
```
- Type(x)가 String 또는 Number고 Type(y)가 객체라면, x==ToPrimitive(y)의 비교 결과를 반환한다.
- Type(x)가 0bject이고 Type(y)가 String 또는 Number라면,ToPrimitive(x)==y의 비교 결과를 반환한다.
- null과 undefined는 객체 래퍼가 따로 없으므로 박싱할수없다. 그래서 Object(null)는 Object()로 해석되어 그냥 일반 객체가 만들어진다.

##### 희귀 사례
```javascript
Number.prototype.valueOf = function() { 
    return 3;
};
new Number(2) == 3; // true
```
- 내장 네이티브 프로토타입을 변경하면 이런식으로 가능 (감히 이런코드는 흉내도 내지 말지어다.)

## 📚 느낀점
- == 연산할때 숫자로 강제변환된다는걸 처음 알았다. (불리언도 숫자로 강제변환이되어 1이랑 비교를 하는구나..)
- 앞에서 읽었던 truthy 값과 == 연산에서 강제변환을 헷갈리지않게 예시를 잘 들어줘서 좋았다.
```javascript
var a = "42";

// 실패
if (a == true) 
// 실패
if (a === true)
// 암시적으로 작동
if (a)
// 명시적으로 작동한다 
if (!!a)
// 명시적으로 작동
if (Boolean(a))
```
- 희귀 사례는 이렇게 쓸 일도 그런 코드를 볼 일도 없겠지만, 이런식으로도 강제변환을 할 수 있다는게 신기했다.


다 못읽음...

## 📚 공유하고 싶은 부분(사이트)
