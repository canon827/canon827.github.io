---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 15주차 Picocrypt에서 사용된 암호화 방식"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용
지난주에 정리했던 Crypto Cipher모듈에 대한 예제를 멘토님께서 암호화/복호화부분을 나누어 정리해주신 코드부분으로 좀 더 상세히 정리해보았다. Crypto.Cipher모듈에서 ChaCha20 방식으로 데이터를 암호화할 때 사용되는 key는 32바이트 크기이다. 또한 이 경우 nonce는 8바이트 또는 12바이트 크기인 것을 알 수 있다. 또한, ChaCha20객체로 plaintext를 암호화하고 nonce와 암호화된 텍스트를 base64로 인코딩하고 UTF로 디코딩한다. 복호화과정은 암호화 과정을 바꿔서 진행한다. 이를 위해 암호화한 JSON 결과 값을 base64형식으로 변환한다. 그리고 난수와 암호문에 들어간 값을 다시 base64로 디코딩하고 ChaCha20 객체를 생성해서 암호문을 복호화하면 된다.

# 3. 후기
이번주는 지난주에 이어서 Crypto Cipher모듈에 대한 예제를 좀 더 상세히 정리해보았다. 멘토님의 도움으로 암호화/복호화 두가지 과정으로 나누어 정리해보았는데 짧고 간단한 코드보다 해당 모듈의 암호화 방식을 이해하는데 더 도움이 되었다. 멘토님이 코드를 정리해주실때 주석을 달아주신 게 코드의 흐름을 파악하는데 도움이 되었는데 추후에 다른 코드를 공부할 때 나만의 방식으로 주석을 달아보는 것도 공부에 큰 도움이 될 거 같다. 

# 4. 결론
-1주 1이상 정리하기 

# 5. 참고
[chacha20](https://pycryptodome.readthedocs.io/en/latest/src/cipher/chacha20.html)
[Crypto.Cipher-module](https://www.dlitz.net/software/pycrypto/api/current/Crypto.Cipher-module.html)  