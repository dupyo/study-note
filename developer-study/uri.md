# URI란

## URI

URI는 특정 리소스를 식별하는 통합 자원 식별자(Uniform Resource Identifier)를 의미한다. 웹 기술에서 사용하는 논리적 또는 물리적 리소스를 식별하는 고유한 문자여 시퀀스이다.

## URL

URL은 컴퓨터 네트워크 상에서 리소스가 어디 위치하는지 알려주기 위한 규약이다. 흔히 웹 주소라고도 하며, URI의 부분집합이다.

<br/>

실제 네트워크 상에서 URI와 URL을 구분하는 예시는 다음과 같다.

https://www.example.com/index.html - URI : O, URL : O

https://www.example.com/index - URI : O, URL : X



## URI의 구조

일반적으로 URI는 다음과 같은 형태로 표현한다.

```
scheme: [//[user[:password]@]host[:port]][/path][?query][#fragment]
```

1. scheme: 사용할 프로토콜을 뜻하며 웹에서는 http 또는 https를 사용함
2. user, password: 서버 상의 데이터에 접근하기 위한 사용자명과 비밀번호
3. host, port: 접근할 대상(서버)의 호스트명과 포트 번호
4. path: 접근할 대상(서버)의 경로에 대한 상세 정보
5. query: 접근할 대상에 전달하는 추가 정보(파마리터)
6. fragment: 메인 리소스 내에 존재하는 서브 리소스에 접근할때 이를 식별하기 위한 정보