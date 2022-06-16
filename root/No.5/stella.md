## 📚 읽은 내용
### 값 변환
- `명시적 강제변환`은 코드만 뵈도 의도적으로 타입변환을 일으킨다는 사실이 명백한 반면.  
  `암시적 강제변환`은 다른 작업 도중 불분명한 부수 효과 로부터 발생히는 타입 변환이다.
```
var a = 42;
var b = a 十''"; // 암시적 강제변환
var C = 5tring( a ); // 명시적 강제변환
```

### 추상 연산
- JSON.stringify()는 인자가 undefined, 힘수, 심벌 값이면 자동으로 누락시키며 이런 값들이 만약 배열에 포함되어 있으면 (배열인덱스정보가뒤바뀌지않도록) null로 바꾼다. 객체 프로 퍼티에 있으면 간단히 지워버린다.
```
JSON.stringify( undefined ); // undefined 
JSON.Stringify( function(){} ); // undefined
J5ON.stringify( [1,undefined ,function (){},4] ); // "[1,null,null,4]"
J5ON.stringify( { a:2, b:function(){} } )' // "{"a":2}"
```
- JSON.stringify()에 환형 침조 객체를 넘기면 에러가난다.
- toJSON()의 역할은 '문자열화하기 적당한 JSON 안전 값으로 바꾸는 것'이지, 'JSON 문자열로 바꾸는 것'이 아니다
> 환형 참조: 프로퍼티 참조가 무한 순환되는 구조의 객체. 마지막 객체가 첫 번째 객체를 참조하는 등 순환 참조가 발생하여 결국 메모리 누수를 유발하는 객체.
- 자바스크립트에서는 숫자는 숫자고. 불리언은 불리언으로 서로 별개다.
- 불리언으로 강제변환하면 false인 값 (나머지는 다 'truthy'값)
    - undefined / null / false / +0 / -0 / NaN / ""
- 객체는 truthy 지만 document.all 은 레거시 문제로 falsy

### 📚 느낀점
- JSON.stringify() 의 기능들을 새로 알았다. (매개변수가 3개구나 + toJSON()이란게 있구나)
- undefined / null / false / +0 / -0 / NaN / "" 이 값들을 강제변환 할 생각은 안해봤지만, falsy 값들을 정리해줘서 좋았다. 외워질듯 ㅎ

### 📚 공유하고 싶은 부분(사이트)
