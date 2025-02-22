---
title: 전송 계층 보안 (TLS)
slug: Glossary/TLS
translation_of: Glossary/TLS
---
이전에 {{Glossary("SSL", "Secure Sockets Layer (SSL)")}}로 알려진 **Transport Layer Security (TLS)**는 어플리케이션들이 네트워크 상에서 안전하게 통신하기 위해 사용된 {{Glossary("protocol")}}이며, 이메일, 웹 브라우징, 메세징, 그리고 다른 프로토코들의 감청을 통한 정보의 변형을 방지한다. SSL과 TLS 모두 네트워크 상에서 보안을 제공하는 cryptographic 프로토콜을 사용한 클라이언트 / 서버 프로토콜이다. 서버와 클라이언트가 TLS로 통신을 할때, 어떠한 제 3자도 메세지를 변형시키거나 감청할 수 없도록 한다.

모든 모던 브라우저들을 TLS를 지원하고, 안전한 연결을 하기위해서 서버가 유효한 {{Glossary("Digital certificate", "digital certificate")}} 를 제공하기를 요구한다. 클라이언트와 서버 둘 다 각자 digital certificate을 제공하면, 서로를 인증해줄 수 있다.

> **참고:** TLS 1.0 와 1.1 2020년 초부터 대부분의 브라우저에서 지원하지 않을 예정이다; 웹 브라우저가 TLS 1.2 나 TLS 1.3을 지원하는지 확인해보는 것이 좋을 것이다. Firefox는 버전 74 이후로 구 TLS 버전을 사용해서 서버에 연결을 시도할 경우 [Secure Connection Failed](https://support.mozilla.org/en-US/kb/secure-connection-failed-firefox-did-not-connect) 에러를 반환한다. ({{bug(1606734)}}).

## 같이 보기

- [Transport Layer Security](https://en.wikipedia.org/wiki/Transport_Layer_Security) (Wikipedia)
- [RFC 5246](https://datatracker.ietf.org/doc/html/rfc5246) (The Transport Layer Security Protocol, Version 1.2)
- [Transport Layer Security](/en-US/docs/Web/Security/Transport_Layer_Security)
- [OWASP: Transport Layer Protection Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html)
- [Glossary](/en-US/docs/Glossary)

  - {{Glossary("HTTPS")}}
  - {{Glossary("SSL")}}
