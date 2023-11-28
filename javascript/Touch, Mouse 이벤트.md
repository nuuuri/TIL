# Touch, Mouse 이벤트

<aside>
💡 IE와 Safari는 touch 이벤트를 지원하지 않는다…! (모바일 Safari에서는 지원함)

</aside>

마우스를 이용해 클릭할 때는 `click` 이벤트만 발생하지만, 터치할 때는 `touchstart` 이벤트 이후에 `click` 이벤트도 발생한다.

### Touch, Mouse 이벤트 순서

1. touchstart
2. touchmove
3. touchend
4. mouseover
5. mousemove
6. mousedown
7. mouseup
8. click

<aside>
💡 터치할 때 마우스 이벤트를 발생시키고 싶지 않아요!

⇒ `touchstart` 또는 `touchend`에서 `preventDefault()`를 호출

</aside>

## Touch 이벤트

### Touch Events

- `touchstart` : DOM에 손가락이 닿을 때
- `touchmove` : DOM에 손가락이 닿은 채로 움직일 때
- `touchend` : DOM에서 손가락을 뗄 때
- `touchcancle` :시스템에서 이벤트를 취소시킬 때(정확한 발생 조건은 브라우저마다 다름)

### Touch Information

- identifier : touch 이벤트를 발생시킨 손가락의 고유 식별 번호
- target : touch 이벤트가 발생한 target DOM
- client/page/screen coordinates : touch 이벤트가 발생한 영역의 좌표 정보
- radius coordinates and rotationAngle : 손가락 모양에 가까운 타원 정보

## Passive Event

- 모바일에서 scroll 성능 향상을 위한 새로운 웹 표준
- passive 옵션이 true인 경우, 콜백 함수 내부에서 `preventDefault()`를 호출해도 콘솔 경고만 출력할 뿐 `preventDefault()`가 제대로 동작하지 않음
- `touchstart`와 `touchmove` 이벤트에 대해 기본값이 true로 설정되어 있음