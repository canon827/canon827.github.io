---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 7주차 Picocrypt Analysis~L365"
---

# 1. 과제

[필수1] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용

1. 로컬 저장소에 위치한 분석 중인 Picocrypt.py를 C:\Users\YGH\sua-osp\opensource-security-sua\canon827\Picocrypt로 복사해 가져와 분석하고 있다. 원격 저장소에서 만약 Picocrypt.py가 업데이트된다면 로컬 저장소의 파일 내용도 바뀌어 헷갈리는 경우를 미연에 방지하기 위해서다.

2. 
-[decryption](https://github.com/henrychoi7/opensource-security-sua/blob/5a67f7e005847ce45b706427668ad9a57701ba6b/canon827/Picocrypt/Picocrypt.py#L176): 프로그램 사용자가 원하는 게 암호화인지 복호화인지 결정하는 부분이다 if~else문을 활용하여 구분했는데 이 코드 부분은 if문 중점으로 복호화되는 부분을 나타낸다.

-[encryption](https://github.com/henrychoi7/opensource-security-sua/blob/5a67f7e005847ce45b706427668ad9a57701ba6b/canon827/Picocrypt/Picocrypt.py#L216)
앞서 언급한 L176부분에서 else문으로 암호화되는 부분을 나타낸다.

-[start function](https://github.com/henrychoi7/opensource-security-sua/blob/5a67f7e005847ce45b706427668ad9a57701ba6b/canon827/Picocrypt/Picocrypt.py#L365)
암·복호화 과정을 시작하는 부분이다. start()함수로 정의되어있다. 이 함수 아래로 if~else문을 사용하여 암호화 인지 복호화인지 선택해준다.

3. 코드만 가지고 분석하는 게 아니라 디버깅도 함께하고 싶어서 visual code의 디버깅을 하기 위해 실행시켜봤으나 오류가 뜬다.
Picocrypt.py에 대해 Run python file in Terminal 메뉴로 터미널창에서 실행시켰을 때 뜨는 오류는 다음과 같다.

![7th error01]({{ https://canon827.github.io }}{{ "" }}/assets/images/7th error01.png)

그래서 로컬에서 이와 관련된 패키지를 설치해주면 된다는 멘토님의 조언해주신 부분과 [Picocrypt](https://github.com/canon827/Picocrypt/blob/main/src/README.md)을 참고해 다음과 같이 노트북의 cmd창에서 진행했다.
![7th error02]({{ https://canon827.github.io }}{{ "" }}/assets/images/7th error02.png)
![7th error03]({{ https://canon827.github.io }}{{ "" }}/assets/images/7th error03.png)

하지만 오류는 해결되지 않았다. 아직 오류에 대한 원인을 잘 모르겠어서 이를 찾고 해결방안을 좀 더 모색해보려 한다.

# 3. 후기

이번 주에 가장 해보고 싶은 부분이 디버깅이었는데 python코드를 터미널창에서 실행시켰을때 오류가 나는 부분이 있어 제대로 하지 못했다. 그래서 Picocrypt 개발자분이 남긴 소스코드 부분의 README 부분부터 다시 보면서 해보고 있지만 쉽지가 않다. 다음주에는 이 부분에 대한 해결방안을 꼭 찾아서 소스코드만 눈으로 훑는게 아니라 디버깅해서 직접 실행시켜서 이 코드가 어떻게 동작하는지 좀 더 자세히 이해하고 싶다. 

# 4. 결론

-Python 파일 실행 시 나타나는 오류에 대한 해결방안 모색

-디버깅이 제대로 안되는 시간이 길어질 때 너무 그것만 붙잡고 있지 말고 코드에 대한 정리 2부분 이상하기

# 5. 참고
[수알치 블로그](https://blog.daum.net/sualchi/13720396)
[오드메이커](https://oddmaker.tistory.com/6)
[개발자 지망생](https://blockdmask.tistory.com/440)
[Visual code 문서](https://code.visualstudio.com/docs/python/debugging)
