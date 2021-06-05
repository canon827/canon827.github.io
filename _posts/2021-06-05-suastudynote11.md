---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 11주차 Picocrypt.py- 보안 삭제, 변조되거나 변경된 파일관련 코드"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용
-[Calculate speed](https://github.com/canon827/Picocrypt/blob/7325b65e03204badb9cee320fc899ff1f890594e/src/Picocrypt.py#L719)
속도를 계산하는 코드로써 예상 완료 시간을 나타낸다. 암/복호화 과정을 완료하는데까지 걸리는 시간을 계산하는 코드로 보인다.

-[Secure delete](https://github.com/canon827/Picocrypt/blob/7325b65e03204badb9cee320fc899ff1f890594e/src/Picocrypt.py#L763)
Picocrypt를 실행시켰을때 'Securely erase and delete original file'체크박스와 연관된 부분이다. 이 부분에서 보안 삭제와 관련된 부분을 처음으로 알 수 있었다. 보안 삭제란, 중요한 파일을 복구할 수 없도록 하는 것을 말한다. 윈도우 운영체제의 경우, 파일을 삭제하면 데이터 영역이 삭제되는 것이 아니라 파일에 대한 정보가 기록되는 영역만 초기화되기 때문에 전문적인 복구 프로그램으로 파일을 복구할 수 있다. 이를 방지하기 위해 사용하는 것이 보안 삭제이다.

-[MODIFIY](https://github.com/canon827/Picocrypt/blob/7325b65e03204badb9cee320fc899ff1f890594e/src/Picocrypt.py#L780)
암/복호화 과정이 완료되었거나, 파일이 만약 변조 혹은 변경된 경우 적절한 메시지를 띄우도록 하는 코드 부분이다. 예를 들면, 암/복호화 과정이 완료된 경우 "Click here to show output"이라는 메시지가 나온다. 

-[Decorator](https://github.com/canon827/Picocrypt/blob/7325b65e03204badb9cee320fc899ff1f890594e/src/Picocrypt.py#L827)
에러를 처리하는 start()함수를 try~except문으로 코드를 작성한다. 이 코드와 관련된 함수가 데코레이터 함수다. 데코레이터란, 함수를 수정하지 않은 상태에서 추가 기능을 구현할 때 사용한다. 

# 3. 후기
이전에는 접해보지 못했던 개념들 때문에 애를 먹었다. '보안 삭제'나 '데코레이터'와 같은 개념이 그렇다. 코드와 관련된 용어에서 모르는 개념이 나오면 그 코드를 좀 더 제대로 이해하기 어려운 부분이 있었다. 코드 부분을 볼 때 그 코드 부분이 나타내는 기능들을 좀 더 명확하게 파악하기 위해서 그 부분에 쓰인 함수나 개념에 대해 찾아보는 부분이 필요할 거 같다. 

# 4. 결론
-코드 일부분만 따서 새 파일로 만든 다음, 디버깅 계속해보기

-보안 삭제, 데코레이터 부분 정리해보기

# 5. 참고
[ETA](https://post.naver.com/viewer/postView.nhn?volumeNo=28023897&memberNo=18071586)                 
[Time module](https://dojang.io/mod/page/view.php?id=2463)        
[SDelete](https://blog.naver.com/hahaj1/20193507311)              










