# runInAction

- `observable` 변수를 변경하기 위해서는 `action`을 사용해야 함
- `makeAutoObservable`
  - **getter** : `computed`
  - **setter** : `action`
  - **일반 함수** : `autoAction`
- `action`은 첫번째 `await`코드까지만 `action`이 적용됨
- `action`은 현재 실행 중인 함수에서만 적용됨 (스케줄링 된 함수에는 적용 X)

<br/>
    
```tsx
class store {
  data1 = 123;
  data2 = 456;
    	
  constructor() {
    makeAutoObservable(this);
  }
    
  async foo() { ... }
    
  async foo2() { ... }
    
  test() {
      this.foo().then(
        // 밑의 코드는 스케줄링 함수 내부이기 때문에 action으로 묶이지 않음
        (res) => {
          this.data1 = res.data1;
          this.data2 = res.data2;
        }
      )
    }
    
  test2() {
    this.data1= await foo();
    this.data2= await foo2(); // action 적용되지 않음
  }
  ...
}
```
    
- 스케줄링 함수에서 `observable` 변수를 변경하고 싶은 경우
  1. `action` 함수로 묶기
            
      ```tsx
          ...
      
          actionForTest(res) {
            this.data1 = res.data1;
            this.data2 = res.data2;
          }
            
          test() {
            this.foo().then(this.actionForTest)
          } 
            
          ...
      ```

2. 인라인으로 `action` 생성

   ```tsx
       ...

       test() {
         this.foo().then(
           action('actionForTest', res => {
             this.data1 = res.data1;
             this.data2 = res.data2;
           })
         )
       }

       ...
   ```

3. `runInAction` (즉시 호출되는 임시 작업) 사용

   ```tsx
       ...

       test() {
         this.foo().then(res => {
           runInAction(() => {
             this.data1 = res.data1;
             this.data2 = res.data2;
           })
         })
       }

       ...
   ```

4. `async` / `await`

   ```tsx
       ...

       async test() {
         const { data1, data2 } = await this.foo();

         runInAction(() => {
           this.data1 = res.data1;
           this.data2 = res.data2;
         }
       }

       ...
   ```

5. `flow` 사용

   ```tsx
       ...

       ...

   ```
