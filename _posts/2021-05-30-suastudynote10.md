---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 10주차 Picocrypt.py 암/복호화 과정에서 키 유도 및 CRC 등"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용
-[Key Derivation](https://github.com/henrychoi7/opensource-security-sua/blob/2e154a5265da3ac9241a5db65e77132223d3953a/canon827/Picocrypt/Picocrypt.py#L549)

키 유도(key derivation)와 관련된 부분이다. 키 유도 함수란, 마스터키나 비밀 정보로부터 해당 시스템이나 네트워크의 암복호화에 필요한 암호 키들을 유도하는 함수를 말한다. 위 코드 부분에서는 arog2에 대한 키를 구성하는 패스워드, 솔트, 해시 길이 등을 정의하고 있다. 또한 유도된 키의 해시값을 계산하는 부분도 구현되어 있다.

-[EOF](https://github.com/henrychoi7/opensource-security-sua/blob/2e154a5265da3ac9241a5db65e77132223d3953a/canon827/Picocrypt/Picocrypt.py#L609)
EOF인 경우를 나타내는 코드로써 EOF란, 파일의 끝(end of file)을 의미한다. if문에서는 암호화과정과 관련된 MAC tag를 삽입, 오프셋을 계산하며 키, CRC의 해시값을 적는다. else문에서는 CRC를 검증하는 코드가 구현되어 있다.

-[CHECKSUM](https://github.com/henrychoi7/opensource-security-sua/blob/2e154a5265da3ac9241a5db65e77132223d3953a/canon827/Picocrypt/Picocrypt.py#L666)
암호화 부분은 if문으로 처리하며 리스트 형식으로 분할한 부분을 python 모듈을 이용해 암호화 한다. 이때, CRC(=체크섬)을 업데이트하고 사용자가 Reed-Solomon 부호를 사용할 경우는 if문으로 처리한다. 체크섬이란, 중복 검사의 한 형태로 데이터의 무결성을 보호해준다.
또한, 복호화 부분은 아래 else문으로 처리했는데 try~except문을 활용해 파일이 출동할 경우나 파일이 검사되지 않은 경우를 처리하고 있다.

# 3. 후기
 Picocrypt 자체는 크게 암호화, 복호화 2과정으로 나뉘기 때문에 코드자체에 if~else문을 자주 사용하여 전체적인 틀을 알기 쉬웠다. 하지만 좀더 상세히 코드를 이해하려고 할때 암/복호화 과정에서 쓰이는 키 유도, 해시값과 연관된 MAC tag, CRC 등의 용어가 익숙치 않아서 내용 정리하는데 애를 먹었다. 더러 뜻이 잘 와닿지 않은 용어도 있어서 이 부분에 대한 공부가 지속적으로 필요할 거 같다.  

# 4. 결론
-잘 몰랐던 용어들 다시 정리해보기

-참고 문헌 첨부 잊지 말기 

# 5. 참고
[암호학 이해](https://gist.github.com/aJchemist/f2d08f328f0458be8ee8)        
[키 유도 함수](https://zetawiki.com/wiki/%ED%82%A4_%EC%9C%A0%EB%8F%84_%ED%95%A8%EC%88%98)             
[read 함수](https://wikidocs.net/14130)              
[checksum](https://ko.wikipedia.org/wiki/%EC%B2%B4%ED%81%AC%EC%84%AC)              
[예외 처리](https://lifeones.tistory.com/122)