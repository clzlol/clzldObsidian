Obsidian Git이라는 커뮤니티 플러그인을 써서 유료로 사용하는 Obsidian Sync 대신 Git에 올려 사용할 수 있도록 설정하였다.

### Git Repository 생성

일단 Git에 저장소를 생성하였다. 그리고 .gitignore 파일을 추가하여 Obsidian을 실행할 때마다 수정되는 workspace 파일들이 pull/push 되지 않도록 하였다.
![[Git Repo.png]]
![[gitignore.png]]

### Obsidian Git 설치
Settings > Community plugins에서 Browse로 들어가 Obsidian Git을 설치한다.
![[Community plugins.png]]
![[Obsidian Git.png]]

### Git 연결하기
Obsidian Vault 파일 내에서 Git Bash를 켜고 다음 명령어를 입력한다.
```git
git init

```