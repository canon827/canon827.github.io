---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 9주차 Picocrypt.py 암/복호화 과정에서 활용되는 여러 변수들"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용
-[Generate values for encryption](https://github.com/henrychoi7/opensource-security-sua/blob/2e154a5265da3ac9241a5db65e77132223d3953a/canon827/Picocrypt/Picocrypt.py#L468): 암호화과정에서 사용되는 솔트와 같은 난수들을 urandom함수를 사용하여 정의한 부분이다. 이부분의 코드에서 암호화할때 Reed-Solomon부호를 사용하는 것을 확인할 수 있으며 Picocrypt는 Argon2, ChaCha20와 같은 암호화기법을 사용하는 것을 알 수 있다.

-[Decrypting](https://github.com/henrychoi7/opensource-security-sua/blob/2e154a5265da3ac9241a5db65e77132223d3953a/canon827/Picocrypt/Picocrypt.py#L493): 위에서 언급한 L468에 위치한 코드와 이어지는 else문이다. 지난번에 생성한 메타데이터를 실제 데이터로 바꾸기 위해 read 함수를 이용해 파일을 읽어온다. 파일 내용이외에도 솔트, 난수, 다이제스트를 읽어오는 것을 코드에서 확인할 수 있다.

# 3. 후기
좀 더 진도를 나가고 싶었으나 내 맘같지 않던 한주였다.^_ㅠ 그래도 다행이 신경쓰이게 했던 일들은 이번주로 끝마쳤으니 다음주를 기대해봐야겠다. 이번주를 마무리하며 이번주에 못한 걸 집중하기보단 틈틈히 코드를 보면서 두 부분정도 정리한 것에 의의를 두어야겠다. 다음주에도 꼭 2개 이상 정리하는 것을 목표로해야겠다. 

# 4. 결론
-미쳐 못한 Picocrypt 개발자에게 형식에 맞춰 이슈를 꼭 보내보자

-디버깅해보면서 캡쳐해서 정리해보자.