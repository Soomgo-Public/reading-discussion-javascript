## 📚 읽은 내용

## Chapter 4. 강제변환
- 강제변환에 대한 좋은 점도 있다..!?

## 4.1 값 변환

```javascript
var a = 42;
var b = a + ""; // 암시적 강제변환
var c = String(a); // 명시적 강제변환
```

## 4.2 추상 연산

### 4.2.1 ToString
- 너무 큰 숫자 값은 지수 형태로 변환한다.
```javascript
var a = 1.07 * 10000000000000
a.toString(); // 1.07e21;
```
- 배열은 콤마 형태로 분리된다.
- JSON.stringify("42"); //  ""42""로 문자열화 된다.
- toJSON() 역할은 `문자열화하기 적당한 JSON 안전 값으로 바꾸는 것`

### 4.2.2 ToNumber
- 변환이 실패하면 NaN 발생
- 객체인 경우에 valueOf()를 쓸 수 있고, 반환값이 원시 값이면 그대로 강제변환, 그렇지 않을 경우 toString()을 이용해 강제변환

```javascript
var a = {
    valueOf: function() {
        return "42";
    }
};

var b = {
    toString: function() {
        return "42";
    }
}

var c = [4,2];
c.toString = function (){
    return this.join( "" ); // "42"
}

Number(a); // 42
Number(b); // 42
Number(c); // 42

```

### 4.2.3 ToBoolean
- 불리언으로 강제 변환 시, 경우의 수

- undefined
- null
- false
- +0, -0, Nan
- ""

```javascript
var a = new Boolean(false);
var b = new Number(0);
var c = new String("");

var d = Boolean( a && b && c )
d; // true
```

- JavaScript 시멘틱 뿐 아니라, 브라우저만의 특이한 작동 방식을 가진 값은 falsy 객체의 정의

### 📚 느낀점
- 추상 연산에 대해서 생각할 수 있었고, 새로운 결과 값들도 많이 봐서 신기했다.
- 특히 falsy 객체의 정의가 흥미로웠고, falsy의 목록을 기준으로 값을 구분하는 것도 처음 알게 되었다. 

### 📚 공유하고 싶은 부분(사이트)
- nil