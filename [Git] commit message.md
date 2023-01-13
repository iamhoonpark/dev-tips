# Git
- 버전관리 소프트웨어
- 작업한 코드들 기록 및 보관

## 1. git install  
 1) 설치
  - Use Visual Studio Code as Git's default editor
  - Override the default branch name for new repositories
 2) 작업폴더 터미널 오픈
  - 해당 폴더 + Shift + 우클릭 > PowerShell 창 열기

## 2. git 설치 버전 확인
  $ git --version

## 3. git user setting
  $ git config --global user.email "홍길동@naver.com"
  $ git config --global user.name "홍길동"

## 4. git 관리 시작
 1) 소프트웨어 git이 작업폴더 감지를 시작
  $ git init

## 5. 버전생성(백업)
  $ git add 파일명.txt
  $ git commit -m '메세지내용'

## 6. add와 commit 을 동시에 하는 명령어
  $ git commit -am '메세지내용'
  * 새로 생성한 파일은 추적되지 않으므로 git add 명령어를 이용해서 추가해야 함

## 7. staging area & repository
 1) 작업순서
  ① 작업폴더 → git add → ② staging area → git commit → ③ repository
 2) 역할
  ② staging area
   · commit을 하기 전 커밋할 파일들을 골라 놓는 곳
   · git add 명령어를 통해 staging area에 파일넣는 행위를 staging 이라 함
  ③ repository
   · commit된 파일의 버전들을 모아놓는 곳
   · repository의 실체는 작업폴더안 숨겨져 있는 .git 폴더로 확인 가능

## 8. git 히스토리
 1) 상태확인
  $ git status
 2) 로그확인
  $ git log --all --oneline
  $ git log --all --oneline --graph 

## 9. 스테이징 취소
  $ git restore 파일명 //최근 commit된 상태로 현재 파일을 되돌림
  $ git restore --staged 파일명 //특정 파일을 staging 취소

## 10. commit 취소
  $ git revert 커밋id

## 10. 전 버전과 현 버전 차이 확인
 1) 차이점 확인
  $ git diff
  $ git diff 커밋id
  $ git diff 커밋id1 커밋id2
 2) 차이점 확인2
  $ git difftool
  $ git difftool 커밋id
  $ git difftool 커밋id1 커밋id2
 3) Vim 에디터
  - 이동키 h, j, k, l
  - 종료 :q, :qa
  - VSCode 데이터로 열고 싶을 경우 하단 명령어를 차례로 입력
  $ git config --global diff.tool vscode
  $ git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'

## 11. 브랜치 생성
  $ git branch 브랜치명

## 12. 브랜치 이동
  $ git switch 이동할브랜치명

## 13. 브랜치 합병
  $ git switch main/master
  $ git merge 브랜치명

## 14. merge conflict
```yml
 - <<< HEAD(Current Change)
   ===
   >>> BranchName (Incoming Change)
```
 - 주석을 지운 후 원하는 코드만 남기고 add, commit

## 15. 브랜치 삭제
  $ git branch -d 브랜치명 // 병합이 완료된 브랜치 삭제
  $ git branch -D 브랜치명 // 병합하지 않은 브랜치 삭제

## 16. merge 를 대체 할 수 있는 rebase
 - rebase를 쓰는 이유: 브랜치 없이도 코드를 병합할 수 있음
 - 단점: 잦은 conflict 엔딩 발생
 - 일반 merge : 중심 브랜치(main/master)로 이동 후 git merge
 - rebase merge : 새로운 브랜치로 이동해서 git rebase 중심 브랜치명 > git merge 새로운브랜치명

## 17. merge 를 대체할 수 있는 squash
 - 브랜치에서 만들어놨던 많은 commit을 다 합쳐서 하나의 commit 으로 main 브랜치에 생성해줌
  $ git switch main/master
  $ git merge --squash 브랜치명
  $ git commit -m '메세지'

## 18. git pull 은 git fetch + git merge 축약어
1) git pull = git fetch + git merge
2) git fetch 는 원격저장소에 있는 commit 중 로컬에 없는 신규 commit 을 가져오는 뜻
3) git merge는 그것을 merge
4) git pull 할 때 2명 이상이 같은 파일을 건드리고 있을 경우 merge conflict 가 발생할 수 있음
5) git push 전 git pull부터
