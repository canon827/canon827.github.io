---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 6주차 Picocrypt Analysis"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용

Picocrypt의 소스코드를 분석하기 시작했다. 분석하는 파일이름은 Picocrypt.py이며 135번째 줄의 for문까지의 내용을 sua 오픈소스 스터디 내 폴더에 반영해두었다. 

이번 소스코드 분석에서는 Picocrypt을 실행하면서 예외처리를 하는 부분[file drag](https://github.com/canon827/Picocrypt/blob/7325b65e03204badb9cee320fc899ff1f890594e/src/Picocrypt.py#L111)과 암호화 또는 복호화하기 위한 대상이 되는 파일 또는 폴더의 정확한 위치를 검증하기 위한 for문 [for](https://github.com/canon827/Picocrypt/blob/7325b65e03204badb9cee320fc899ff1f890594e/src/Picocrypt.py#L135)에 대해 분석해보았다. 코드를 보고 개발자가 달아둔 주석을 참고해 이 코드의 대략적인 기능을 파악하고 좀 더 세세한 첨언을 덧붙이려 했으나 생각보다 잘 되지 않았다.

# 3. 후기

코드를 보면서 예외 처리에 사용되는 try except 용법이 익숙지 않아 엄청 낯설었다. 이와 비슷하게 예전에는 보지 못했던 python 용법이 간혹가다 나왔는데 그래서 더 코드가 어렵게 느껴진다. 무엇보다 개발자가 달아둔 주석을 참조해 내 방식대로 좀더 자세하게 코드를 풀어보고 싶었는데 어떤식으로 말을 적어야 할지 감이 잘 잡히지 않아 더 많은 자료를 찾아봐야겠다는 생각이 든다. 

# 4. 결론

-코드보면서 python 용법에 대한 자료 5개이상 찾아보기

-소스코드 분석관련 자료 찾아보기 

# 5. 참고
[exception](https://dojang.io/mod/page/view.php?id=2398)