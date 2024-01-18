## Redis란?

- `Re`mote `Di`ctionary `S`erver
- dictionary 구조(key-value 형태)로 데이터를 저장하고 관리하는 서버
- 모든 데이터를 메모리에 저장하고 조회하는 **`인메모리`** 데이터베이스
    - 컴퓨터의 주기억장치인 RAM에 데이터를 저장
    - 장점 : 메모리 내부에서 처리하므로 데이터를 저장하고 조회하는 속도가 빠름
    - 단점 : 서버의 메모리 용량을 초과할 경우 문제 발생, 전원이 꺼지면 데이터 유실됨
    - (Redis에서도 데이터를 영속적으로 저장하는 방법을 제공하나, 빠르고 간편하게 사용하는 것을 목적으로 하는 인메모리 방식에는 적합하지 않을 수 있음)
- `List, Hash, Set` 등 다양한 자료구조를 지원함

## Redis의 특징 (vs Cache)

- `List, Set, Sorted Set, Hash` 등과 같은 `Collection`을 지원함
- Race Condition에 빠질 수 있는 것을 방지함
    - Redis는 **Single Thread** → Atomic을 보장
- persistence를 지원하여 서버가 꺼지더라도 다시 데이터를 불러들일 수 있음
