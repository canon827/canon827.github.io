---
layout: single
title: "정보보안 SUA - [오픈소스 보안] 3주차 GitHub 블로그 만들기"
---

# 1. 과제

[필수1] 총 5개의 리포지터리를 로컬 환경 (PC 혹은 노트북)에서 git clone 혹은 git pull 명령어를 사용해서 각 디렉터리에 준비한다. (zip 파일로 받거나 원격 즉, GitHub에서 직접 작업하면 안된다.).

-하나는 opensource-security-sua, 하나는 자신의 GitHub 블로그, 나머지 세 개는 오픈소스 3개

[필수2] 로컬에 준비된 opensource-security-sua 디렉터리에 들어가서 자신의 GitHub 사용자 이름 (예: henrychoi7)으로 된 로컬 브랜치를 생성한다.

# 2. 내용

※ 명령어 입력은 Visual studio code의 터미널에서 진행

1. 우선 내 로컬 환경에서 최상단 디렉터리를 만든다. 그 경로는 아래와 같다.

   C:\Users\YGH\sua-osp

그 다음, Visual studio code에서 해당 디렉터리를 열어준다. 그리고 git clone 명령을 입력해서 총 5개의 저장소를 로컬환경으로 받아온다. 이때, git clone 다음에 받아오기 원하는 저장소에 들어가 code에서 주소를 복사해오면 된다. 이 주소는 맨 뒤에 .git이 꼭 들어가 있어야 한다.

ex) canon827.github.io라는 이름의 저장소를 로컬환경으로 받아오기 위한 명령어는 다음과 같다.

> C:\Users\YGH\sua-osp> git clone https://github.com/canon827/canon827.github.io.git

위 명령을 입력하게 되면 최상단 디렉터리로 만들어둔 sua-osp 폴더의 하위폴더로 canon827.github.io 이름으로 폴더가 생기면서 폴더 안에 저장소에 있던 파일을 모두 불러오게 된다. 이런 방식으로 나머지 4개의 저장소도 진행한다.

2. opensource-security-sua 디렉터리에 들어가서 로컬 브랜치를 생성한다.

> C:\Users\YGH\sua-osp\opensource-security-sua> git status 
>Your branch is up to date with 'origin/main'.

우선, git status 명령을 입력해 현재 상태를 확인해줍니다.

> C:\Users\YGH\sua-osp\opensource-security-sua> git branch canon827

git branch 다음에 자신의 GitHub 사용자 이름을 입력해 브랜치를 생성합니다.

> C:\Users\YGH\sua-osp\opensource-security-sua> git checkout canon827
> Switched to branch 'canon827'

위에서 만든 'canon827'라는 이름의 브랜치를 사용하여 작업을 수행하기 위해 이 브랜치를 지정하기 위해서 checkout 명령을 사용합니다. git checkout 다음에 브랜치명을 입력해주면 됩니다.

> C:\Users\YGH\sua-osp\opensource-security-sua> git add .
>
> C:\Users\YGH\sua-osp\opensource-security-sua> git commit -m "canon827 브랜치 생성"
> To https://github.com/henrychoi7/opensource-security-sua.git
>
> - [new branch] canon827 -> canon827

원하는 파일을 선택해서 커밋을 만들어줍니다. git add 다음에 .을 입력하면 모든 파일을 선택할 수 있습니다. 그 다음, git commit 명령을 입력해서 커밋을 만들 수 있는데 -m 옵션을 이용하면 위에 나와있듯이 메시지를 달 수 있습니다.

3. [온라인 미팅 후 내용 추가] 받아온 저장소를 원작자가 업데이트 시, 나의 로컬 환경에도 업데이트 내용 동기화 하기

ex) Picocrypt 업데이트 내용 동기화 하기

원작자의 저장소는 아래와 같다.

https://github.com/HACKERALERT/Picocrypt

> C:\Users\YGH\sua-osp\Picocrypt> git remote -v
> origin https://github.com/canon827/Picocrypt.git (fetch)
> origin https://github.com/canon827/Picocrypt.git (push)

우선 로컬환경에 받아온 저장소에 해당하는 폴더로 경로를 이동한 후, git reomote -v 명령을 입력해 원격 저장소의 버전을 확인합니다.

> C:\Users\YGH\sua-osp\Picocrypt> git remote add upstream https://github.com/HACKERALERT/Picocrypt.git

그리고 원작자의 저장소 URL로 들어가 해당 저장소의 Code를 복사해줍니다. 그리고 그 주소를 git remote add upstream 다음에 입력해주면 업데이트된 정보를 가진 원격 저장소를 등록할 수 있습니다.

> C:\Users\YGH\sua-osp\Picocrypt> git remote -v
> origin https://github.com/canon827/Picocrypt.git (fetch)
> origin https://github.com/canon827/Picocrypt.git (push)
> upstream https://github.com/HACKERALERT/Picocrypt.git (fetch)
> upstream https://github.com/HACKERALERT/Picocrypt.git (push)

그리고 다시 원격 저장소의 버전을 확인하면 upstream으로 표시된 원작자의 최신 원격 저장소가 등록된 것을 확인할 수 있습니다.

> C:\Users\YGH\sua-osp\Picocrypt> git checkout main

그 다음 이 브랜치를 선택하기 위해 git checkout 명령을 사용합니다. 이때, checkout 다음에 입력해주는 브랜치는 원작자의 원격 저장소 URL에 접속했을 때 상단쪽에 바로 보이는 브랜치를 입력해주면됩니다. 이 원작자분의 원격저장소의 경우 main이었기 때문에 git checkout main 명령을 입력해주면 됩니다.

![checkout_choose branch](.\assets\images\picocryptmain.png)

> C:\Users\YGH\sua-osp\Picocrypt> git merge upstream/main

그리고 git merge 명령을 입력해 이전에 받아온 원격저장소와 업데이트 된 원격 저장소의 버전을 병합해줍니다.

# 3. 후기

이번 과제는 이전 과제보다 간단했기 때문에 끝낸 날짜보다 하루 이틀 더 빨리 끝날 수 있었을 거 같은데 자격증 실기 공부와 직장생활을 같이 병행하다보니 예상보다 좀 미뤄진 게 아쉽다. 브랜치 생성하는 명령어도 실은 간단한데 내용정리가 아직 덜 되어있다보니 생각했던 것보다 우왕좌왕했다. git 관련 명령어를 꼭 정리해둬야겠다. 다만, 이번달은 자격증 실기시험이 말일에 있으니 실기 시험 공부와 이번에 나간 오픈소스 보안 과제 중심으로 해야겠다. 실기 시험 공부가 주가 되겠지만 오픈소스 보안 공부(라고 쓰고 삽질이라고 읽는다.)도 하루에 1시간정도는 꼭 붙잡고 있는거로╰(_°▽°_)╯! 부탁해, 미래의나!! 그 이후에 git 명령어 부분은 강의 내용을 워드에 정리한 후, 좀 더 다듬어서 git 블로그에 올려봐야겠다.

# 4. 결론

-내가 선택한 3개의 저장소 중에 [INGInious]의 경우 강의 자료와 컨닝 방지 프로그램이라는 특수 상황에 국한되어 있어 분석해볼 1개 저장소는 다시 찾아보기

-Picocrypt의 경우, Analysis
secoure-coding-with-python은 Usage 선택, 매뉴얼을 만들어본다는 생각으로 작성하기

-바쁘겠지만 하루에 1시간정도는 꼭 붙잡고 있어보자
