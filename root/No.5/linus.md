## 📚 읽은 내용

### 강제변환
- 강제변환의 나쁜점은 알고 있으니, 강제변환의 좋은 점을 알고싶다.
- toString
  - 너무 크거나 작은 값은 지수 형태로 바뀜
  - JSON.stringify : JSON 안전값은 모두 문자열화 가 (JSON 안전 값이 아닌 것들은 undefined, 함수(function), 심벌(ES6부터, symbol), 환형 참조(circular references))
- toBoolean
  - 정해진 falsy 값 이외에는 모두 truthy 
  - 강제 변환의 유용한 예?
  ```typescript
  type Person = {
    name: string | null
  } 
  
  const getName = (person : Person) => {
    // if (person.name === null)
    if (!person.name) {
        console.log("이름이 없다");
        return;
    }
    console.log(person.name);
  }
  
  const person = {
    name : null,
  };
  
  getName(person);
  ```
  - document.all -> documentGetElementById

### 📚 느낀점
- 타입스크립트 공부를 열심히 하자
- 안녕. IE

### 📚 공유하고 싶은 부분(사이트)



