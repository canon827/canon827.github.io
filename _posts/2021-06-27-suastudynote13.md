---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 13~14주차 Picocrypt.py-관련 모듈과 예제"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용
Picocrypt.py에서 쓰인 모듈이 가진 기능을 좀 더 명확하게 알아보기 위해 하나의 모듈만 쓰인 간단한 예제를 참조해서 코드를 작성했다. 그리고 해당 코드를 디버깅했을 때 어떤 결과가 나타나는 지 알아보았다.

-[crypto.hash module](https://github.com/henrychoi7/opensource-security-sua/blob/ca63e46ed518645c3f5bb1370c4c590f68c50ab8/canon827/Picocrypt/Picocrypt.py#L21)
Crypto.Hash 모듈의 동작을 알아보기 위해 참고했던 코드는 다음과 같다. 
```
from Crypto.Hash import SHA512

h = SHA512.new()
h.update(b'Hello')
print(h.hexdigest())
```

-[Crypto Cipher module](https://github.com/henrychoi7/opensource-security-sua/blob/ca63e46ed518645c3f5bb1370c4c590f68c50ab8/canon827/Picocrypt/Picocrypt.py#L20)
Crypto Cipher모듈은 대칭 및 비대칭 키 암호화 알고리즘으로 키 또는 키 쌍에 의존하는 방식으로 일반 텍스트를 변환하여 암호문을 생성한다. 이와 관련한 예제는 다음과 같다 

```
import json

from base64 import b64encode
from Crypto.Cipher import ChaCha20
from Crypto.Random import get_random_bytes

plaintext = b'open source security by SUA'

key = get_random_bytes(32)
nonce = get_random_bytes(8)

cipher = ChaCha20.new(key=key, nonce=nonce)

ciphertext = cipher.encrypt(plaintext)

nonce = b64encode(cipher.nonce).decode('utf-8')
ct = b64encode(ciphertext).decode('utf-8')

result = json.dumps({'nonce':nonce, 'ciphertext':ct})

# {"nonce": "IZScZh28fDo=", "ciphertext": "ZatgU1f30WDHriaN8ts="}
print(result)
```

# 3. 후기 
6월 셋째주에 진도가 너무 안나가서 넷째주에 했던 내용과 같이 합쳐서 작성했다. Picocrypt 코드를 한번 훑고나서 이와 관련된 모듈들에 대해 공부했다. Crypto.Hash 모듈에서 SHA-512 암호화 방식과 관련된 예제, Crypto.Cipher모듈에서 ChaCha20 방식으로 데이터를 암호화하는 예제에 대해 정리해보았다. 여러가지 일이랑 병행하다보니 결과물이 없는 날도 많아져 신경쓰인다. 하지만 항상 결과물이 있을 순 없다. 한 주에 한 가지만이라도 제대로 정리해봐야겠다.

# 4. 결론
-1주마다 정리하는 거 잊지 말기

-[example](https://pycryptodome.readthedocs.io/en/latest/src/examples.html) 이 부분 공부해서 정리해보기

# 5. 참고

[Crypto.Cipher-module](https://www.dlitz.net/software/pycrypto/api/current/Crypto.Cipher-module.html)               
[SHA512-module](https://www.dlitz.net/software/pycrypto/api/current/Crypto.Hash.SHA512-module.html)            
[chacha20](https://pycryptodome.readthedocs.io/en/latest/src/cipher/chacha20.html)
