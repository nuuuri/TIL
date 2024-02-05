## 1. 드래그 & 드롭 이벤트 종류와 순서

1. `dragstrat` : 사용자가 객체(object)를 드래그하려고 시작할 때 발생
2. `drag` : 대상 객체를 드래드하면서 마우스를 움직일 때 발생
3. `dragenter` : 마우스가 대상 객체의 위로 처음 진입할 때 발생
4. `dragover` : 드래그하면서 마우스가 대상 객체의 영역 위에 자리 잡고 있을 때 발생
5. `drop` : 드래그가 끝나서 드래그하던 객체를 놓는 장소(대상 객체)에서 발생. `dragover` 이벤트가 적용되어야만 동작함
6. `dragleave` : 드래그가 끝나서 마우스가 대상 객체의 위에서 벗어날 때 발생
7. `dragend` : 대상 객체를 드래그하다가 마우스 버튼을 놓는 순간 발생

## 2. DataTransfer 객체

- 드래드 & 드롭 이벤트를 위한 모든 이벤트 리스너 메소드는 `DataTasnfer` 객체를 반환함
  - `event.dataTransfer.setData(format, data)`
  - `event.dataTransfer.getData(format)`
  - `event.dataTransfer.clearData()`
    `event.dataTransfer.clearData(format)`
  - `event.dataTransfer.types`
- 마우스 드래그 시 고스트 이미지 설정은 `event.dataTransfer.setDragImage()` 메서드를 통해 가능함
