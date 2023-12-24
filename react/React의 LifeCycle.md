# 1. 생성(Mount)

### 1-1. constructor

- 클래스 인스턴스 객체를 생성하고 초기화하는 메서드
- React에서 컴포넌트를 만들 때 처음으로 실행
- 초기 state를 정할 수 있음

### 1-2. static getDerivedStateFromProps

- props로 받아온 것을 state에 동기화시키는 용도로 사용

### 1-3. render

- 최종적으로 component에서 작업한 결과물을 return하는 메서드
- JSX가 HTML로 변환되어 렌더링

### 1-4. componentDidMount

- 초기 컴포넌트의 로딩 이후에 한번만 실행되는 메소드
- DOM 직접 조작 가능

<br/>

# 2. 업데이트(Update)

### 2-1. static getDerivedStateFromProps

- 컴포넌트가 새로운 속성을 전달받을 때 실행

### 2-2. shouldComponentUpdate

- props나 state를 변경했을 때, 리렌더링을 할지 말지 결정하는 메서드
- 반드시 true나 false를 반환 (default: true)
- 오직 성능 최적화만을 위한 메서드

### 2-3. render

### 2-4. getSnapshotBeforeUpdate

- render에서 만들어진 결과가 브라우저에 실제로 반영되기 직전에 호출
- 업데이트 되기 직전에 snapshot(props & states)을 확보하는게 목적

### 2-5. componentDidUpdate

<br/>

# 3. 제거(UnMount)

### 3-1. componentWillUnmount

- 컴포넌트가 화면에서 사라지기 직전에 호출

<br/>

# 4. 에러 핸들링

### 4-1. componentDidCatch

- 컴포넌트 렌더링 도중에 에러가 발생했을 때 어플리케이션이 멈추지 않고 오류 UI를 보여줄 수 있게 함
