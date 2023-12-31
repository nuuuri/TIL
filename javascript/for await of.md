# for await of

💡 for await of 문은 **반복문 내에서 일어나는 모든 비동기 구문을 기다려주는 구문**이다.

<br/>

```tsx
const fruits = ['apple', 'banana', 'orange'];

fruits.forEach(async (fruit) => {
	const result = await fetch('...');
	console.log(result);
});

console.log('모든 API 통신 완료'); // forEach의 반복문 작업이 모두 끝나기 전에 실행됨
```

<br/>

## Promise.all()과의 차이

- Promise.all()은 인자의 Promise 배열을 `동시에 실행`함
- for await of 내의 비동기 작업은 루프를 돌며 `순차적으로 실행`됨
