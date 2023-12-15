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

ssh로 ios 문제는 해결했다.
이제 좀 그만하자.. 커서 알아서 보는 걸 없애봤다

***
여기까지 하고 나면 최소한의 설정이 끝난다. Obsidian이 Git에 자동으로 commit, push, pull 되면서 다양한 로컬 기기에서 사용할 수 있을 것이라고 생각한다.