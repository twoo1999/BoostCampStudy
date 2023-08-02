### TCP/UDP

데이터를 전송하는 방식(통신 규약)

- TCP

  - 일대일 연결만 가능
  - 손실되면 재전송 요청을 함 -> 신뢰성 높음
  - 데이터의 순서와 무결성이 보장
  - 높은 신뢰도를 요하는 서비스에 적합

- 연결방법
  3-way를 통해 연결, 4-way를 통해 연결 해제(악수하는 방식, 특정 신호를 주고 받으며 서로의 상태를 확인)
- UDP
  - 일대다 연결 가능
  - 정보를 받았는지 확인하지 않고 전송가능
  - 데이터의 순서와 무결성을 보장하지 않음
  - 속도가 빠름
  - broadcast에 적합

### HTTP(Hyper Text Transfer protocol)

- 단방향성
  클라이언트가 서버로 요청을 보내고 이에 대한 응답을 받는 형식(서버가 먼저 보낼 순 없음)
- 비연결성
  연결이 계속 유지되지 않고 요청에 대한 응답이 끝나면 연결을 끊음(<->소켓통신)
- 무상태성
  클라이언트가 서버와 연결된 상태가 아니기 때문에 기본적으로 상태를 가지지 않음 -> 쿠키, 세션, 토큰 등을 통해 해결

### HTTP request 구조

#### start Line

```
GET /test.html HTTP/1.1
[HTTP Method] [Request target] [HTTP version]
```

HTTP request Message의 시작라인

세가지로 구성(HTTP method, Request target, HTTP version)

- HTTP method:
  요청의 의도를 담는 부분(get, post, put, delete)
- request target:
  HTTP request가 전송되는 목표 주소
- HTTP version:
  version에 따라 request 메세지 구조나 데이터가 다를 수 있으니 version을 명시

#### Headers

```
Host: google.com
Accept: text/html
Accept-Encoding: gzip, deflate
Connection: keep-alive
...
```

해당 request에 대한 추가 정보를 담고 있음
request 메세지 body의 총 길이 등 key와 value의 쌍으로 존재

Hsot : 요청하려는 서버 호스트 이름과 포트번호

User-agent : 클라이언트 프로그램 정보, 이 정보를 통해 서버는 클라이언트 프로그램에 맞는 최적의 데이터를 보내줄 수 있음

Referer : 바로 직전에 머물렀던 웹 링크 주소

Accept : 클라이언트가 처리 가능한 미디어 타입 종류 나열

if-Modified-Since : 여기에 쓰여진 시간 이후로 변경된 리소스 취득, 페이지가 수정됐다면 최신 페이지로 교체함

Authorization : 인증 토큰을 서버로 보낼 때 쓰이는 Header

Origin : 서버로 post 요청을 보낼 때 요청이 어느 주소에 시작되었는지 나타내는 값, 이 값으로 요청을 보낸 주소와 받는 주소가 다르면 에러가 발생함

Cookie : 쿠키 값이 key-value로 표현됨

#### body

```
POST /test HTTP/1.1

Accept: application/json
Accept-Encoding: gzip, deflate
Connection: keep-alive
Content-Length: 83
Content-Type: application/json
Host: google.com
User-Agent: HTTPie/0.9.3

{
    "test_id": "tmp_1234567",
    "order_id": "8237352"
}
```

HTTP Request가 전송하는 데이터를 담고 있는 부분

전송하는 데이터가 없다면 body 부분은 공백으로 처리

보통 Post 요청일 경우, HTML 폼 데이터가 포함

### HTTP response 구조

#### status line

HTTP response의 상태를 간략하게 나타내주는 부분

HTTP response의 status line 또한 3가지로 구성

```
HTTP/1.1 200 OK
[HTTP version] [Status Code] [Status Text]
```

- HTTP version
- Status Code
- Status Text

#### headers

Response의 header와 동일

다만 response에서만 사용하는 header값이 있다

예를 들어 User-Agent 대신에 Server헤더가 사용.

#### body

Response의 body와 동일

Request와 마찬가지로 모든 response에는 body가 있지 않다.

데이터를 전송할 필요가 없는 경우 body는 공백으로 처리

### HTTP method

#### GET

- 서버로 부터 데이터를 받아올 때 사용
- 데이터 생성/수정/삭제 없이 받아오기만 할 때 사용
- 가장 간단하고 많이 사용되는 HTTP method
- request에 body를 싣지 않는다.

#### POST

- 데이터를 생성/수정/삭제 할 때 주로 사용됨
- 데이터를 생성 및 수정할 때 많이 사용하기 때문에 request body에 데이터가 포함됨

#### option

- 주로 URI에서 사용할 수 있는 method를 받아올 때 사용
- 예를 들어 /update uri에서 어떤 method를 요청 가능한가를 알고 싶다면 먼저 OPTION 요청을 사용해서 확인

#### PUT

- POST와 비슷, 데이터를 생성할 때 사용함
- POST와 겹치기 때문에 PUT을 사용하는 곳도 있고 POST로 통일해서 사용하는 곳도 있음

#### DELETE

- 특정 데이터를 서버에서 삭제 요청을 보낼 때 사용
- PUT과 마찬가지로 POST에 밀려서 잘 사용하지 않는 추세

### HTTP 응답코드

2xx 성공 요청이 정상적으로 이루어짐

3xx 리다이렉션, 요청을 완료하기 위해 다른 주소로 이동해야함

4xx 클라이엍느 오류, 올바르지 않는 요청

5xx 서버오류, 올바른 요청에 대해 서버의 문제로 응답 불가능함

[참고] https://hahahoho5915.tistory.com/55

### TCP/IP

https://www.youtube.com/watch?v=K9L9YZhEjC0

https://aws-hyoh.tistory.com/entry/TCPIP-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0

### echo 서버

수신한 데이터를 그대로 돌려받는 네트워크 서버

자신이 보낸 데이터를 그대로 받기 때문에 네트워크 테스트나 디버깅을 위해 사용

### 클라이언트 / 서버

클라이언트 : 서비스를 이용하는 고객
서버 : 서비스 제공자

### JSON

JavaScript Object Notation라는 의미의 축약어로 데이터를 저장하거나 전송할 때 많이 사용되는 경량의 DATA 교환 형식

JSON 표현식은 사람과 기계 모두 이해하기 쉬우며 용량이 작아서, 최근에는 JSON이 XML을 대체해서 데이터 전송 등에 많이 사용한다.
https://velog.io/@surim014/JSON%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80
