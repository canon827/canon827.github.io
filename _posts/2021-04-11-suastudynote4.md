---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 4주차 선택한 오픈소스 정리"
---

# 1. 과제

[필수1] opensource-security-sua 내 자신의 디렉터리에서 먼저 공부하고 싶은 오픈소스를 README로 정리한다. README 정리하는 방식은 하나의 파일에 해도 되고, 오픈소스에 따라 여러 디렉터리로 나눠서 정리해도 된다. 단, 정리한 내용은 모두 자신의 디렉터리에 있어야 하고 관련 문서, 이미지, 영상, 링크, 소스코드 등을 첨부하거나 정리하는 디렉터리에 넣어도 좋다.

[필수2] 1주일에 1번씩 공부하고 있는 오픈소스에 대한 내용을 블로그에 정리한다.

# 2. 내용

1. opensource-security-sua 내 디렉터리의 READ.ME 파일에 내가 선택한 3가지 오픈소스에 대해 Introduction까지 정리했다. 선택한 3가지 오픈소스의 이름은 다음과 같다.

>-Secure-coding-with-python
>-Picocrypt
>-Python-scripts

Secure-coding-with-python부터 차례대로 진행할 예정이다. 지난번에 선택했던 INGInious가 너무 목적이 특정되어 있었기때문에 Python-scripts로 바꿔 진행하려한다. Secure-coding-with-python와 Python-scripts의 실습은 vmware에서 진행하고 Picocrypt는 그냥 윈도우 환경에서 진행할 예정이다.

2. 
-지난번 3주차 과제에서 이미지 파일을 첨부했지만 파일이 깨져 제대로 나오지 않아 헤맸었다. 이번 온라인 미팅덕분에 해결할 수 있었는데 참고했던 링크는 다음과 같다.
https://github.com/mmistakes/minimal-mistakes/blob/master/docs/_posts/2010-08-05-post-image-standard.md

블로그를 생성하기위한 기본 테마로 사용했던 mmistakes를 참고했으며 수정 전과 수정 후를 비교해보면 다음과 같다.

### 수정 전
>![checkout_choose branch](.\assets\images\picocryptmain.png)


### 수정 후
>![checkout_choose branch]({{ https://canon827.github.io }}{{ "" }}/assets/images/picocryptmain.png)

수정 전에는 경로를 제대로 지정하지 못한 것을 확인할 수 있다. 나름 다른 블로그를 참고하려했지만 실패했다.

>![alt]({{ site.url }}{{ site.baseurl }}/assets/images/filename.jpg)

위의 포맷을 그대로 본 따 사용했으며 이를 위해 나의 디렉터리 내 _config.yml 파일의 site.baseurl를 딱히 지정하지는 않았지만 공백으로 표기했다. 수정 후 원격 저장소로 push한 결과, 이미지가 제대로 나오는 것을 확인할 수 있었다.


다른 방식으로 이미지 파일을 올릴 수 있는 여러 포맷이 있는데 나중에 한번 사용해보고 싶다. 그 중 하나의 참고 링크는 아래와 같다. 
https://mmistakes.github.io/minimal-mistakes/markup-more-images/

-버전을 만들어 원격 저장소에 올릴 때 사용하는 방식을 웬만하면 멘토님이 알려주신 방식으로 통일하려 한다. 이에 대한 명령어들은 다음과 같다.

| 명령어      |  설명        |
| ----------- | ----------- |
| git status  |  git에 의해 관리되는 파일들의 상태 확인 | 
| git add -A  |  작업 디렉터리 상에 어디에 위치하든 항상 동일하게 모든 변경 내용을 스테이징으로 넘김      |
| git commit -as| 별도의 add명령어를 사용하지 않고 수정된 파일에 대해 add, commit을 한번에 수행하며 서명한다.|
| git log --oneline| 그동안의 로그 기록을 한줄로 보여준다.|
| git push [원격 저장소의 주소] [현재 브랜치명] | commit한 후, 변경 이력들을 원격 저장소로 공유 |

# 3. 후기

이번 주는 컨디션이 요근래 최저를 달리는 주였는데 아무래도 사랑니 발치가 컸다. 진통제때문인지 회사에서도 반쯤 넋이 나가기도 했는데 그게 과제 진도에 많이 반영된 듯 싶다...이번 주는 3개의 오픈소스를 최종적으로 확정하고 REDAD파일에 인트로밖에 작성을 못했다. 다만, 이번 주 미팅을 통해 고민이었던 블로그에 올린 이미지 파일 에러를 해결할 수 있어서 다행이다. 시험이 딱 2주남은 시점에서 힘들겠지만 다음주는 좀 더 힘내봐야겠다.

# 4. 결론

-VMware 구성 마무리 후, 실습 진행

-진행했던 실습 잊지말고 opensource-security-sua에 반영해두자.

# 참고
https://www.daleseo.com/git-add/
https://www.zerocho.com/category/Git/post/581042fdcae2d100152ceae6
https://yuja-kong.tistory.com/48
https://planbs.tistory.com/entry/Git-%EC%9B%90%EA%B2%A9-%EC%A0%80%EC%9E%A5%EC%86%8C%EC%97%90-Push%ED%95%98%EA%B8%B0