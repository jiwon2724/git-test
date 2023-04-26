# RESTful API 의미와 설계규칙

## REST란?
- **REST의 정의**
  - "Representational State Transfer"의 약자이다.
    1. 자원의 이름(자원의 표현)으로 구분하여 해당 자원의 상태(정보를)를 주고 받는 모든 것을 의미.
       - 즉, **자원**(resource)의 **표현**(representational)에 의한 **상태**(state) **전달**(transfer).
         - 자원 : 문서, 이미지, 데이터 등
         - 자원의 표현 : 자원을 표현하기 위한 이름
           - ex) DB의 학생 정보가 자원일 때, "students"를 자원의 표현으로 정한다.
    
    2. 상태(정보)전달
         - 데이터가 요청(request)이 되어지는 시점에서 자원의 상태(정보)를 전달(response)한다.
         - JSON or XML을 통해 데이터를 주고 받는 것이 일반적이다.
    
    3. REST는 기본적으로 웹의 기존 기술 HTTP의 프로토콜 그대로 활용하기 때문 웹의 장점을 최대한 활용할 수 있는 아키텍처 스타일.
    4. REST는 네트워크 상에서 Client와 Server사이의 통신 방식중 하나이다.
    5. push test
  


- **REST의 구체적 개념**
  - HTTP URI를 통해 자원(resource)을 명시하고, HTTP 메소드를 통해서 해당 자원에 대한 CRUD 연산을 적용하는 것을 의미.
  - CURD란?
    - Create(생성) : POST
    - Read(조회) : GET
    - Update(수정) : PUT
    - Delete(삭제) : DELETE
    


- **REST의 특징**
  - Server-Client 구조
    - 자원이 있는 쪽이 Server, 요청한 쪽이 Client
  - Stateless(무상태)
    - HTTP 프로토콜은 Stateless Protocol이므로 REST역 무상태성을 갖는다.
    - Client의 context를 저장하지 않는다. ex) 쿠키, 세션
  - Cacheable(캐시 처리 기능)
    - 캐시 사용을 통해 응답(response)시간이 빨라지고, 트랜잭션이 발생하지 않기 때문 전체 응답시간, 성능, 서버의 자원 이용률이 향상된다.


- **REST 구성요소**
  - 자원(Resouce) : URI
    - 모든 자원에 고유한 ID가 존재하고, 이 자원은 Server에 존재한다.
    - 자원을 구별하는 ID는 "/userinfo/user_id"와 같은 URI이다.
    - Client는 URI를 이용해서 자원을 지정하고, 해당 자원의 상태(정보)에 대한 조작을 Server에 요청한다.
  - 행위(Verb) : HTTP Method
    - HTTP 프로토콜의 Method를 사용한다.
    - GET, POST, PUT, DELETE
  - 표현(Representation of Resource)
    - Client가 자원의 상태(정보)를 요청(Request)하면 Server는 요청에 대한 적절한 응답(Response)를 보낸다.
    - REST에서 하나의 자원은 JSON, XML, RSS등 여러 형태로 나타내질 수 있다.
    - 보통은 JSON, XML을 통 데이터를 주고받는 것이 일반적이다.


## REST API란?
 - API : 데이터와 기능의 집, 서로 정보를 교환가능 하도록 하는 것.
 - REST API : 위에 설명한 REST를 기반으로 서비스 API를 구현한 것.

## REST API 설계 규칙
1. 자원에 대한 행위로 HTTP Method를 사용한다.
   1. URI 이름에 Method를 넣으면 안된다. ex) userinfo/delete/3
   2. URI에 동사 표현이 들어가면 안된다. 즉, CRUD 기능을 나타내는 것은 URI에 사용X ex) userinfo/show/3
2. 슬래시 구분자는 계층관게를 나타낼 때 사용한다. ex) usertype/admin
3. 마지막 문자로 슬래시를 포함하지 않는다.
4. -(하이픈)은 URI 가독성을 높이는데 사용한다. -> ex) URI가 긴경우
5. _(언더바)는 URI에 사용하지 않는다.
6. URI 경로에는 소문자가 적합하다. 대문자는 피하도록 하자.
7. 등

## RESTful API란?
REST의 아키텍처 스타일을 따른 시스템을 RESTful이란 용어로 표현된다.

즉, RESTful API는 REST 원칙을 따르는 API를 의미한다.



# 문제
1. 다음 URI는 REST 기반의 설계일까요?
   - https://api.odcloud.kr/v1/get/page_info/page=1/per_page=10
   
2. 1번에 대한 문제의 답을 말하시고 설명하세요.


