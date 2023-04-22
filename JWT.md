> JWT(Json Web Token)

- 웹표준 (RFC 7519) 으로서 두 개체에서 JSON 객체를 사용하여 가볍고 자가수용적인 (self-contained) 방식으로 정보를 안전성 있게 전달해준다.
- aaaaaa.bbbbbb.cccccc 헤더.내용(payload).서명(signature)

1. Header

- typ: 토큰의 타입을 지정한다. 바로 JWT.
- alg: 해싱 알고리즘을 지정한다. 해싱 알고리즘으로는 보통 HMAC SHA256 혹은 RSA 가 사용되며, 이 알고리즘은, 토큰을 검증 할 때 사용되는 signature 부분에서 사용된다.

```
{
"typ": "JWT",
"alg": "HS256"
}
```

2. Payload(정보) : 토큰에 담을 정보가 들어있다. 여기에 담는 정보의 한 ‘조각’ 을 클레임(claim) 이라고 부르고, 이는 name / value 의 한 쌍으로 이뤄져있다. 토큰에는 여러개의 클레임 들을 넣을 수 있다.

- 등록된 (registered) 클레임 : 이미 정해진 클레임들, 모두 선택적 (optional)
- 공개 (public) 클레임 : 충돌이 방지된 (collision-resistant) 이름, URI 형식
- 비공개 (private) 클레임 : 양 측간에 (보통 클라이언트 <->서버) 협의하에 사용되는 클레임 이름

3. Signature : 헤더의 인코딩값과, 정보의 인코딩값을 합친후 주어진 비밀키로 해쉬를 하여 생성. 토큰을 인코딩하거나 유효성 검증을 할 때, 사용하는 고유한 코드가 들어있다.

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

- sign은 토큰을 만들어주어 클라이언트에 발급해주는 메소드
