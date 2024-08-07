# HTTP(Hypertext Transfer Protocol)란?

HTTP(Hypertext Transfer Protocol)는 인터넷에서 **하이퍼 텍스트문자인 HTML로 만든 웹페이지를 전송하기 위해 사용되는 프로토콜이다.**

- HTTP는 원래 월드 와이드 웹(WWW)에서 HTML 문서를 전송하여 하이퍼텍스트 링크를 통해 문서를 연결하고 사용자에게 웹 페이지를 제공하기 위해 개발되었다.

현재 HTTP는 웹 페이지 전송을 넘어 다양한 웹 서비스와 애플리케이션의 데이터 교환을 위한 핵심 프로토콜이 되었다.

- 다양한 데이터 형식(HTML, JSON, XML, 이미지, 영상, 음성 등)을 지원한다.
- 웹 페이지 전송 뿐 만 아니라 API 통신, IoT 기기 데이터 전송, 파일 업로드/다운로드 등 여러 응용 분야에서 사용된다.

## HTTP의 통신 구조

HTTP 통신은 **클라이언트(Front-End)와 서버(Back-End)로 나뉘어진 구조로 되어있다.**

- 데이터를 저장하고 관리하는 서버 부분과 해당 서버에 접속하여 데이터를 열람하는 클라이언트 부분으로 구성된 네트워크 구조를 말한다.
- HTTP는 서버와 클라이언트가 서로 데이터를 주고받기 위해 사용되는 프로토콜을 뜻하기도 하다.

| 클라이언트 | 서버에게 요청을 보내는 리소스 사용자  ex) 웹 브라우저, 모바일 애플리케이션, IOT 등 |
| --- | --- |
| 서버 | 클라이언트에게 요청에 대한 응답을 제공하는 리소스 관리자 |

![img1 daumcdn](https://github.com/user-attachments/assets/9bb6a114-b0c0-4f5b-b258-2af4056efd35)

클라이언트(웹 브라우저 등)가 HTTP를 통해 서버에 요청(Request)을 보내면, 서버가 이 요청에 응답(Response)하여 필요한 정보를 전달하는 방식으로 동작한다.

- HTTP는 이러한 **요청과 응답 메시지의 형식을 정의**하여, **클라이언트와 서버가 서로 이해하고 통신할 수 있도록 한다.**

 **HTTP는 어째서 이렇게 클라이언트와 서버를 분리해야만 할까? 
 이유는 각자의 역할에 집중할 수 있기 때문이다.**

클라이언트는 주로 사용자 인터페이스(UI)를 표시하고 사용자의 입력을 받고, 서버는 클라이언트의 요청을 받아 처리하고, 필요한 데이터베이스 조회, 비즈니스 로직 실행, 데이터 조작 등을 수행한다.

- 클라이언트는 **복잡한 비즈니스 로직이나 데이터 처리에 직접적으로 개입하지 않아도 된다.**
- 서버는 데이터의 안전성과 처리 효율성에 집중하여, 데이터의 일관성과 보안을 유지하면서 클라이언트에게 필요한 데이터를 제공할 수 있다.

역할 분리를 통해 서버와 클라이언트는 **서로의 영향을 최소화 하고 독립적으로 고도화 할 수 있게 된다**는 것이다.

---

## **HTTP 메시지(HTTP Message)**

Request Headers 는 클라이언트가 서버에게 보내는 HTTP 메세지 이력이며, Response Headers 는 서버가 클라이언트에게 응답하는 HTTP 메세지 이력이다. 

| 요청(request) | 클라이언트가 서버로 전송하여 서버에서 작업을 실행하도록 요청하는 메시지입니다. |
| --- | --- |
| 응답(response) | 서버가 그 요청에 대한 답변을 클라이언트에게 제공하는 메시지입니다. |

HTTP 메시지는 위에서부터 차례대로 `시작 라인`(Start Line), `헤더`(Header), `공백 라인`(Empty Line), `바디`(Message Body)로 구성되어 있습니다.

![img1 daumcdn 1](https://github.com/user-attachments/assets/4d5e051e-d6ab-4019-a965-b6ea8a48846d)


| 시작 라인 | 시작 라인에는 실행되어야 할 요청, 혹은 수행에 대한 성공 여부가 기록되어 있습니다. |
| --- | --- |
| HTTP 헤더 | 요청 또는 메시지 본문에 대한 설명입니다. HTTP 전송에 필요한 모든 부가 정보를 담고 있습니다. |
| 공백 라인 | 공백은 HTTP 메시지 값을 구분하기 위한 라인이므로 반드시 포함되어야 합니다. |
| 메시지 본문 | 실제 전송할 데이터가 포함됩니다. HTTP 요청의 종류에 따라 메시지 바디가 있거나 없을 수 있습니다. |

전체적인 골자는 위와 같고 HTTP 요청(Request)냐 응답(Response)냐에 따라 안의 내용물이 약간 다르게 된다.

### HTTP 요청 메세지

![img1 daumcdn 2](https://github.com/user-attachments/assets/5184e234-4938-4f2a-9099-755105b9789b)


**시작 라인(Start Line)**

- Method : GET / POST / PUT / DELTE 등 (HTTP 메서드) 서버가 수행해야 할 동작을 지정한다.
- URL : 일반적으로 URL, 프로토콜, 포트, 도메인의 요청 대상 절대 경로("/")를 나타냅니다.
- Version : 사용된 http 버전

**헤더(Header)**

- Headers : HTTP 전송에 필요한 모든 부가 정보를 담고 있다.
- 예를 들어, 메시지 크기, 압축 여부, 인증 정보, 브라우저 정보, 서버 정보, 캐시 등

**공백 라인(Empty Line)** : 헤더와 바디를 구분하기 위한 라인

**바디(Message Body)**

- Message Body : 실제 전송할 데이터 (HTML 문서, 이미지, 영상, JSON 등)

### HTTP 응답 메세지

![img1 daumcdn 3](https://github.com/user-attachments/assets/6c568945-9291-482b-8bfb-3b9374c31567)


**시작 라인(Start Line)**

- Version : 사용된 http 버전
- Status Code : 클라이언트가 보낸 요청이 성공인지 실패인지 숫자 코드로 나타낸다. (200, 404, 505)
- Status Message : Status Code 에 대한 결과를 사람이 이해할 수 있는 글로 표현

**헤더(Header)**

- Headers : HTTP 전송에 필요한 모든 부가 정보를 담고 있다. (메세지 크기, 압축 여부, 인증, 브라우저 정보, 서버 정보, 캐시 ..등)

**공백 라인(Empty Line)** : 헤더와 바디를 구분하기 위한 라인

**바디(Message Body)**

- Message Body : 전송 받은 데이터

---

# HTTP 메서드

 HTTP는 **무엇(웹 페이지)을 어떻게 해달라(보내줘)는 클라이언트의 요청을 URI과 메서드(Method)를 사용해서 전달한다.**

- 쉽게 말하면 서버에 주어진 리소스에 수행하길 원하는 행동, 서버가 수행해야 할 동작을 지정하는 요청을 보내는 방법이다.
- 각각의 메서드는 서로 다른 기능을 수행하지만, 일부는 서로 공유하기도 한다.
- 텍스트 기반 문서를 전송하려는 목적으로 개발된 최초의 HTTP는 GET 메서드 하나만 존재했고, URL로 지정하는 리소스도 HTML 문서 밖에 없는 단순한 모델이었다.

### **GET**

**GET** 메서드는 **리소스의 조회를 요청**합니다. 

- 성공하면 요청한 데이터가 포함된 응답이 반환됩니다.
- 주로 데이터를 읽거나 검색할 때 사용하며, 수정할 때는 사용하지 않습니다.

쿼리 파라미터를 사용해서 데이터를 전달할 수도 있습니다. ( `GET /search?q=hello&hl=ko HTTP/1.1`)

- 파라미터들은 URL의 일부분이기 때문에 브라우저 히스토리에 남아있으며, 따라서 민감한 데이터를 처리할 때 GET 요청을 사용해선 안 됩니다.

**데이터 조회 과정**

1. 100번 회원 정보를 얻기 위해 클라이언트가 서버에 `GET` 요청 메시지를 전달합니다.

```
GET /members/100 HTTP/1.1
Host: localhost:8080
```

2. 서버가 내부 데이터베이스를 조회하여 `/members/100`에 해당하는 응답 데이터를 생성하고 클라이언트에 전달합니다.

```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 34

{
  "username": "young",
  "age": 20
}
```

### **POST**

**POST** 메서드는 **클라이언트가 메시지 바디를 통해 서버로 보낸 요청 데이터를 처리**합니다. 

- 주로 신규 리소스 등록이나, 변경된 프로세스 처리 등에 사용됩니다.

**데이터 전송 과정**

1. 클라이언트는 서버에 `POST` 요청 메시지를 전달합니다. 

- 메시지 바디를 통해 등록할 데이터를 서버로 전송합니다.

```
POST /members HTTP/1.1
Content-Type: application/json

{
  "username": "young",
  "age": 20
}
```

2. 서버는 받은 데이터를 데이터베이스에 등록하고, 신규 리소스 식별자를 생성합니다.

3. 그리고 `Location` 헤더를 통해 **리소스가 생성된 경로를 전달**하며, **메시지 바디를 통해 등록된 리소스를 클라이언트에게 전송**합니다.

```
HTTP/1.1 201 Created
Content-Type: application/json
Content-Length: 34
Location: /members/100

{
  "username": "young",
  "age": 20
}
```

- **POST** 메서드는 주로 요청 데이터를 처리하는 데 사용합니다.

다만 여러 쓰임새가 있으므로 리소스 URI에 POST 요청이 오면, 요청 데이터를 어떻게 처리할지 리소스마다 따로 정해야 합니다.

**POST 메서드의 예시**

- HTML Form에 입력한 데이터의 전송
    - 회원 가입, 상품 주문
- 파일 업로드, 게시
    - 게시판 글 작성, 댓글 등록
- 서버가 아직 식별하지 않은 새 리소스를 생성
    - 신규 주문 생성
- 기존 자원에 데이터를 추가
    - 한 문서 끝에 내용 추가
- 데이터 프로세스의 상태 변경(처리 단계)
    - 주문 -> 결제완료 -> 배달 시작 -> 배달완료
- 다른 메서드로 처리하기 애매한 경우

![Get_Postpng](https://github.com/user-attachments/assets/847777f3-3638-47b8-a7cc-398595a08101)

### **PUT**

`PUT` 메서드는 리소스를 대체하는 메서드입니다. 

- 기존 리소스가 있다면 리소스를 완전히 대체하고, 해당 리소스가 없다면 새로 생성합니다.
- 폴더에 파일이 없으면 새로 생성되고, 기존에 똑같은 파일이 있다면 덮어쓰는 것과 유사합니다.

**리소스 대체 과정**

1. 100번 회원의 리소스를 교체하기 위해 서버에 `PUT` 요청 메시지를 전달합니다.

```
PUT /members/100 HTTP/1.1
Content-Type: application/json

{
  "age": 50
}
```

2. `/members/100`에 해당하는 리소스를 완전히 대체합니다.

```json
{
  "username": "young",
  "age": 20
}
```

3. 기존 데이터가 완전히 대체되기 때문에 `username` 필드가 삭제됩니다.

```json
{
  "age": 50
}
```

중요한 점은, **POST** 메서드와 달리 클라이언트가 리소스를 식별한다는 것입니다. 클라이언트가 리소스의 구체적인 경로를 알고 있으며, URI를 지정합니다.

### **PATCH**

**PATCH** 메서드는 리소스를 부분 변경할 때 사용합니다.

- PATCH가 지원되지 않는 서버에서는 `POST`를 사용한다.

**리소스 수정 과정**

1. age 값만 변경하기 위해 서버에 `PATCH` 요청 메시지를 전달합니다.

```
PATCH /members/100 HTTP/1.1
Content-Type: application/json

{
  "age": 50
}
```

2. `/members/100`에 해당하는 리소스가 부분적으로 변경됩니다.

```json
{
  "username": "young",
  "age": 20
}
```

3. `username` 필드는 사라지지 않고, `age`만 업데이트 됩니다.

```json
{
  "username": "young",
  "age": 50
}
```

### **DELETE**

**DELETE** 메서드는 리소스 제거합니다.

**리소스 삭제 과정**

1. 100번 회원 정보를 삭제하기 위해 서버에 `DELETE` 요청 메시지를 전달합니다.

```
DELETE /members/100 HTTP/1.1
Host: localhost:8080
```

2. 데이터베이스에서 `/members/100`에 해당하는 리소스 삭제합니다.

```json
{
  "username": "young",
  "age": 20
}
```

### 기타 메서드

- `HEAD`: 메시지 **헤더**를 획득
    - GET과 유사하나 메시지 바디를 제외하고 상태줄과 헤더만 반환
- `OPTIONS`: 대상 리소스에 대한 통신 가능 **옵션**을 요청
    - 주로 CORS에서 사용
- `CONNECT`: 대상 리소스로 식별되는 서버에 대한 **터널**을 설정
    - 거의 사용하지 않음
- `TRACE`: 대상 리소스에 대한 경로를 따라 메시지 **루프백 테스트**를 수행
    - 거의 사용하지 않음

---

# HTTPS(Hypertext Transfer Protocol Secure)

### **HTTP와 HTTPS의 차이**

- HTTP는 HyperText Transfer Protocol의 약자로 말 그대로 데이터가 암호화되지 않고 평문(plain text)으로 전송되기 때문에 도청, 중간자 공격(Man-in-the-Middle Attack) 등에 취약합니다.

**HTTPS(Hypertext Transfer Protocol Secure)는 HTTP에 보안 기능을 추가한 프로토콜을 말한다.**

- HTTPS는 HTTP와 동일한 방식으로 작동
- 데이터를 암호화하여 전송하는 SSL/TLS(Secure Sockets Layer/Transport Layer Security) 프로토콜을 사용함으로써 보안을 강화한다.

HTTPS는 암호화/복호화 하는 과정 때문에 비교적 속도가 느리고, 인증서 발급과 유지하기 위한 추가 비용이 발생한다. 

- 개인 정보와 같은 민감한 데이터를 주고받아야한다면 HTTPS를 이용해야하지만, 단순 정보 조회만 처리하고 있다면 HTTP를 사용한다.

**참조**

https://co-natus.tistory.com/entry/HTTP-Methods

https://inpa.tistory.com/entry/HTTP-🌐-백엔드-로드맵-HTTP는-무엇일까요

https://eunsun-zizone-zzang.tistory.com/35
