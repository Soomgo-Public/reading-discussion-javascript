# Chapter 4 강제변환

## 4.3 명시적 강제변환
- 분명하고 확실한 타입변환
- 가독성이 매우 좋음, 타입 추론의 필요가 없음.

### 4.3.1 명시적 강제변환: 문자열 <> 숫자
```typescript
const a = 42;
const stringA = String(42);

const b = "3.14";
const numberB = Number(3.14);
const numberB2 = +b;
```
- 위의 예제 중 +는 가독성이 좋지 않을 수 있음.
- .toString()은 겉보기에 명시지만 사실 암시임.
  
### 4.3.2 날짜 > 숫자
```javascript
const d = new Date();
const timestamp = +d; // 가독성 좋지 않음
const timestamp2 = d.getTime(); // 권장 됨
const timestamp3 = Date.now(); // awesome
```

### 틸드
- 대체로 가독성이 좋지 않아 꺼려지는 연산자.
- 32비트로 강제로 변환함. 그러므로 큰 범위의 숫자에는 오동작.
- `-0`, `NaN`, `Infinity`, `-Infinity` 이러한 특수 숫자들은 32비트로 나타낼 수 없으므로 32bit 연산시 `0`리턴
- 틸드는 32비트 숫자로 강제변환 한 후 NOT 연산을 함. -> 2의 보수 연산
- `-1`을 거를때 씀.

#### 비트 잘라내기
- `~~`로 `Math.Floor()`와 ***비슷한***효과를 낼 수 있다. (절대 같지 않음);
  - 32비트로 연산하기 때문에 같지 않음. 오히려 `x|0`이 더 빠를듯.
  - 하지만 `x|0`을 쓰는 대신 `~~`을 쓰는 이유는 우선순위 때문.

### 4.3.2 명시적 강제변환: 숫자 형태의 문자열 파싱 
- 좌 -> 우로 파싱하다가 숫자 형태가 아닌 문자를 만나면 멈춤.
- `parseInt`는 비 문자열이면 먼저 문자열로 자동으로 변환하는데 감춰진 암시적 변환이므로 바람직하지 않음.
  - 앞자리를 보고(`x`, `0` 등) 8진수 10진수 등 진수화해버림. 그러므로 2번째 인자를 넣는게 안전.
  - 스트링이 아닌 놈을 `ParseInt`의 첫자로 넣어버리면 쓰레기가 되어버리므로 쓰지말자
  
### 4.3.3 명시적 강제변환: 불리언
- `Boolean()`, `!!a`

---
- 틸드가 32비트 연산을 한다는 것을 처음 알았다.
- 많이 중요하진 않지만 비트연산자와 틸드연산자의 우선순위를 알게되었다.
- 숫자를 문자열로 파싱할 때 오류를 뱉는줄 알았더니 중간에 멈추는것도 처음 알았다.
  - 애초에 개발할 때 숫자인지 아닌지 확실하지 않은 문자열을 숫자로 변환하려는 행위를 선제차단 해서 그런듯.