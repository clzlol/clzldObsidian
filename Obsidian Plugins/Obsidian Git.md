---
due: 2023-12-15
kind: obsidian plugin func
status: Done
urgent: false
tags:
  - note
---
***

Obsidian Git이라는 커뮤니티 플러그인을 써서 유료로 사용하는 Obsidian Sync 대신 Git에 올려 사용할 수 있도록 설정하였다.

## Git Repository 생성

일단 Git에 저장소를 생성하였다. 그리고 .gitignore 파일을 추가하여 Obsidian을 실행할 때마다 수정되는 workspace 파일들이 pull/push 되지 않도록 하였다.
![[Git Repo.png]]
![[gitignore.png]]

## Obsidian Git 설치

Settings > Community plugins에서 Browse로 들어가 Obsidian Git을 설치한다.
![[Community plugins.png]]
![[Obsidian Git.png]]

## Git 연결하기

Obsidian Vault 파일 내에서 Git Bash를 켜고 다음 명령어를 입력해 git과 연동, 푸시를 한다.
```git
git init #git 초기화
git add * #obsidian 파일 전체 Stage에 추가
git commit -m "init obsidian repository" #Stage에 추가된 파일 커밋
git branch -M main #main branch를 master branch로 설정
git remote add origin "~~.git" #git 주소 등록
git push -u origin main #main branch로 푸시
```

## 자동 업데이트 설정

여기까지 하고 Obsidian을 재시작 하면 Obsidian Git 설정에 Automatic이라는 설정 내용이 생기는데, git에 obsidian의 수정 사항을 자동으로 commit, push, pull 하면서 업데이트 해주는 기능이다. 여기서 다음과 같이 설정해주면 된다.
![[automatic.png]]
- Vault commit interval (minutes): 설정된 분 간격으로 commit 한다.
- Vault push interval (minutes): 설정된 분 간격으로 push 한다.
- Auto pull interval (minutes): 설정된 분 간격으로 pull 한다.

## IOS 연동

일단 Git을 모바일, 또는 패드 환경에 clone 해야 하는데, 이게 또 Working Copy라는 앱을 써서 해야 하더라.. 이것 때문에 3 만원 들었다.... 그래도 나중에 쓸 일 있을 거라는 생각으로, 그리고 Obsidian을 제대로 쓰겠다는 집념 하나로 결제했다. IOS 연동은 [이 링크](https://clarit7.github.io/obsidian_sync_setting/)를 보고 따라서 진행했다.
이 방법을 그대로 따라했지만 잘 작동하지 않아서, 혹시나 해서 git clone을 할 때 **프로토콜을  https가 아니라 ssh**를 사용해보았는데, IOS에서 권한이 없어 push가 안된다는 오류는 사라졌다. 그 후로는 다 그대로 하면 된다. Obsidian의 Vault에 Repository Link를 하고 아이폰 단축어를 이용해 push, pull 자동화를 하면 된다. (자동화 해둔 거도 수정 없으면 푸시 안하나보다)
그리고 현재 깨달은 점은 **웬만해서는 여러 기기에서 Obsidian을 켜지 말자**라는 점이다. 이랬을 때 충돌이 가장 많이 일어났기 때문에, Git을 완벽하게 다루는 상태가 되어 이 환경을 다시 설정하지 않는 이상 이 행위는 하지 않는 게 좋을 것 같다.. 그렇게 [[Git]]을 제대로 공부해야겠다는 다짐, 그리고 [[http]], [[https]], [[ssh]] 같은 각 [[프로토콜]]이 무엇인지 정확히 파악할 필요성을 느꼈다.
계속 경고가 하나 뜨긴 하는데.. 정상 작동을 하고 Done이라는 글씨가 뜬 걸 보니 일단은 뒀다가 나중에 해결해보자....
![[git error.png]]
이거 어차피 뜨는 에러인 거 같아서 gitignore를 최대한 줄여봤는데 작동한다.


***
여기까지 하고 나면 최소한의 설정이 끝난다. Obsidian이 Git에 자동으로 commit, push, pull 되면서 다양한 로컬 기기에서 사용할 수 있을 것이라고 생각한다.