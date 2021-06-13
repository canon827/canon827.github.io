---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 12주차 Picocrypt.py- UI와 관련된 코드들"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용
-[disabled](https://github.com/canon827/Picocrypt/blob/7325b65e03204badb9cee320fc899ff1f890594e/src/Picocrypt.py#L877)
암호화/복호화 과정 중에는 다른 입력이 불가능하도록 disableAllInputs() 함수로 정의한다. picocrypt UI에서 확인할 수 있는 Password, Comfirm password 등의 항목들을 disabled로 처리한다.         

-[Reset](https://github.com/canon827/Picocrypt/blob/7325b65e03204badb9cee320fc899ff1f890594e/src/Picocrypt.py#L887)
picocrypt에서 데이터를 입력받을 수 있는 각각의 항목들의 상태를 "normal"로 정의하여 리셋하는 코드 부분이다. 이 부분의 코드부터 암호화과정 후 리셋하는 함수, 복호화과정 후 리셋하는 함수, 그리고 초기 상태로 리셋하는 함수가 정의되어 있다.
이 후 코드들은 picocrypt를 실행했을 때 확인할 수 있는 box들을 나타내는 코드들이다.

# 3. 후기
이번에 정리한 코드들은 picocrypt를 실행했을 때 확인할 수 있는 box들을 나타내는 코드들이 대부분이었다. 지금 계속 디버깅을 해보고 있는데 자꾸 문법 오류가 난다.ㅜㅠ test라는 이름으로 python파일을 따로 만들어서 Picocrypt.py의 코드를 위에서부터 조금씩 긁어와 붙여놓고 돌려보고 있는데 입출력부분에 있어 문제가 있는 거 같다. 아래쪽에 정의된 함수들이 많아서 그런건지 잘 모르겠다.

# 4. 결론
-디버깅 오류나는 부분 원인 찾아보기

-다음 오픈 소스 슬슬 시작하기 