## OR 연산자

- 첫번째 truthy 값을 찾음
- `true`가 되는 값 || `false`가 되는 값 ⇒ `true`가 되는 값
- `true`가 되는 값 || `true`가 되는 값 ⇒ `true`가 되는 값
- `false`가 되는 값 || `false`가 되는 값 ⇒ `false`가 되는 값
- `0 || 1` ⇒ 1
- `null || 1` ⇒ 1

## Null 병합자

- 첫번째 정의된 값을 반환 ⇒ `null`이나 `undefined`가 아닌 falsy한 값도 반환함
    - Javascript의 falsy한 값 : `false`, `null`, `undefinded`, `0`, `-0`, `0n`, `NaN`, `“”`
- true ?? false ⇒ true
- `0 ?? 1` ⇒ 0
- `null ?? 1` ⇒ 1
