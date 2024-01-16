# REST API란?

### REST(REpresentational State Transfer)

- 전반적인 웹 어플리케이션에서 상호작용하는데 사용되는 웹 아키텍쳐 모델
- 네트워크 상에서 Server와 Client 사이의 통신 방식 중 하나
- **자원을 이름으로 구분하여 해당 자원의 상태를 주고받는 모든 것**
- 즉, 자원(resource)의 표현(representation)에 의한 상태 전달
- `HTTP URI(Uniform Resourece Identifier)`를 통해 자원을 명시
- `HTTP Method`(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD를 적용

<br/>

- **REST의 특징**
  - Server-Client 구조
      - 자원이 있는 쪽이 Server, 자원을 요청하는 쪽이 Client
        
  - Stateless(무상태)
      - HTTP 프로토콜은 Stateless Protocol이므로, REST 역시 무상태성을 가짐
      - Client의 context(세션, 로그인 정보)를 Server에 저장하지 않음
      - Server는 각각의 요청을 별개의 것으로 인식하고 처리
  - Cacheable(캐시 처리 가능)
      - HTTP 프로토콜 표준에서 사용하는 Last-Modified 태그, E-Tag를 이용하여 캐싱 구현 가능
      - 대량의 요청을 효율적으로 처리하기 위해 캐시가 요구됨
  - Layered System(계층화)
      - Client는 REST API Server만 호출함
      - REST Server는 다중 계층으로 구성될 수 있음
      - Proxy, Gateway와 같은 네트워크 기반의 중간 매체를 사용할 수 있음

<br/>

### REST API

- **REST 기반으로 서비스 API를 구현한 것**
- `API`(Application Programming Interface) : 데이터와 기능의 집합을 제공하여 컴퓨터 프로그램 간 상호작용을 촉진하며, 서로 정보를 교환가능하도록 하는 것

<br/>

### RESTful

- 일반적으로 REST라는 아키텍처를 구현하는 웹 서비스를 나타내기 위해 사용되는 용어
- REST를 REST답게 쓰기 위한 방법
- 'REST API'를 제공하는 웹 서비스를 'RESTful'하다고 할 수 있음
- **RESTful 하지 못한 경우**
  - ex) CRUD 기능을 모두 `POST`로만 처리하는 API
