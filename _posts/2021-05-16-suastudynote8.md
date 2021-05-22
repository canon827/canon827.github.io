---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 8주차 Picocrypt.py 디버깅 오류 해결"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용

![7th error01]({{ https://canon827.github.io }}{{ "" }}/assets/images/7th error01.png)
위와 같이 visual code에서 디버깅을 하기 위해 Picocrypt.py를 터미널에서 실행시켰을 때 오류가 계속 나타났다.

이 오류를 해결하기 위해서 우선, 멘토님이 조언해주셨던 대로 설치했던 패키지를 다시 한번 로컬해서 설치해보았다. 이때 사용했던 명령어는 아래와 같다.

>python -m pip install --upgrade pip    
>python -m pip install argon2_cffi     
>python -m pip install -U cffi pip setuptools    
>python -m pip install wheel    
>python -m pip install pycryptodome    
>python -m pip install reedsolo    
>python -m pip install ttkthemes    

tkinterdnd2의 경우, git에서 따로 받아와 설치했다. 이에 대한 명령어는 다음과 같다.

>git clone https://github.com/pmgagne/tkinterdnd2.git

위와 같이 받아온 다음, 해당 디렉터리 안으로 들어가 아래와 같은 설치와 관련된 명령어를 따로 쳐주어야 한다.

>python setup.py install

위와 같이 진행했지만 오류는 해결되지 않았다. 그래서 python을 다시 설치해보기로 하고 삭제 후 재설치해보았다. 하지만 그래도 오류는 해결되지 않았는데 로컬 상 여러개의 python이 설치되어있는 것을 발견하고 새로 설치한 python빼고 전부 삭제했다. 그럼에도 불구하고 creedsolo라는 모듈이 없어 오류가 난다는 에러 메시지가 계속 떴다. 구글에 검색해봐도 해당 모듈과 동일한 모듈은 찾을 수 없었다. 

결국, Picocrypt.py에서 오류가 나는 부분을 다음과 같이 수정했다. reedsolo라는 모듈은 있었기 때문이다. 
[오류 부분](https://github.com/henrychoi7/opensource-security-sua/blob/2e154a5265da3ac9241a5db65e77132223d3953a/canon827/Picocrypt/Picocrypt.py#L38)

>from creedsolo import RSCodec,ReedSolomonError     
>-> from reedsolo import RSCodec,ReedSolomonError 

다행이 이 부분을 수정한 후, Picocrypt.py이 정상적으로 실행되는 것을 확인할 수 있었다.

![7th errorsol]({{ https://canon827.github.io }}{{ "" }}/assets/images/7th error sol.png)

# 3. 후기

이번주에도 디버깅 오류에 매달려 한 주가 다 갔다. 멘토님이 조언해주신 부분 그대로 했는데도 해결이 안나서 고민이 많았다. 다행이 오프라인 모임때 멘토님이 도와주셔서 해결할 수 있었다. 오류에 대한 원인은 로컬 내 설치된 여러 python 버전끼리 충돌과 python파일 내 코드부분때문인 것 같다. 똑같은 부분에서 계속 오류가 나면 혼자 자료를 찾아보는 것도 중요하지만 너무 질질끌지 말고 도움을 요청하는 것도 하나의 방법인 듯 하다. 

# 4. 결론
-Picocrypt 개발자에게 형식에 맞춰 이슈를 보내보자

-디버깅 관련해서 실행해보고 내용 정리하기

