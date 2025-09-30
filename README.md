# Git

Git 설정하고 초기화 하기

1. `git init` (git 초기화)
2. `git config --list` (git 환경설정)
3. `git config --local user.name` "git 계정"
4. `git config --local user.email` "git 이메일"
   - `--local` local에만 적용되는 설정
5. (git status 했을 때 on branch master라고 뜰 경우)

   `git config --global init.defaultBranch main`

6. `git add -A` || `git add .`

   5-1 Working Directory (작업 디렉토리)
   - 실제로 파일을 수정하는 곳
   - 파일은 수정되었지만, git add를 하지 않아서 스테이징 영역에는 없는 상태

   5-2. Staging Area (스테이징 영역, 인덱스)
   - 커밋(commit)할 변경 사항을 잠시 올려두는 대기 공간
   - git add 명령어로 스테이징 영역에 파일을 옮길 수 있다.

   5-3. Repository (저장소, .git)
   - 최종적으로 git commit 하면, 스테이징 영역에 있는 파일(폴더)가 git에 기록됨
   - feat: 새로운 기능 추가
   - fix: 버그 수정
   - docs: 문서 수정
   - style: 코드 스타일 변경(추가)
   - refactor: 리팩토링
   - test: 테스트 코드 추가
   - chroe: 빌드 설정 변경

     `git commit -m "fix: 로그인시 빈 값을 입력해도 로그인 되던 현상 수정"`

     `git commit -m "feat: 로그아웃 기능 추가"`

7. `git config --global core.editor "code --wait"`
8. `git config --global --unset core.editor`
9. `git status`
10. `git log` 방금 날린 commit의 히스토리 보고 싶은 경우
    - `--oneline` 한줄로 간단하게
    - `--graph` 그래프 형식
    - ✨ `git log --graph --oneline`

11. 커밋 취소하는 방법 (Repository -> working directory of staging area)

    11-1 커밋이 한 개 있을 때
    - git 초기화 (rm -rf .git -> git init -> git add . -> git commit)

    11-2 커밋이 두 개 이상 있을 때
    - `git reset HEAD~숫자`

      ex) `git reset HEAD~1` 1개의 커밋 되돌리기
      - `--mixed` : 기본값, 커밋 취소 + 작업 내역 Working Directory 영역에 배치
      - `--soft` : 커밋 취소 + 작업 내역을 Staging Area에 배치
      - `--hard` : 커밋 취소 + 작업 내역 삭제

    11-3 소스코드가 github에 올라갔으면 reset X
    - `git revert 커밋아이디`
    - 가장 많이 하는 실수: github에 코드 올라갔는데 git reset → git push --force
    - 협업자에게 작업 내역을 취소한 새로운 커밋을 올렸으니 병합해서 사용하라고 말해주기

12. github에 소스를 올릴 때
    12-1 `git push -u origin 브랜치명`
    12-2 `--force`

13. git !== github

    github에 올라가면 git으로 관리되지 않음
    - github : 원격 저장소
    - git : 로컬 저장소

14. 원격 저장소를 등록

    14-1 `git remote add` 식별자 원격레포주소
    14-2 `git remote add origin` 원격레포주소
    14-3 `git remote add stream` 원격레포주소
    14-4 `git remote -v `

15. git push

15-1 `git push -u 원격레포식별자 브랜치이름`

- origin -> 원격레포식별자

- main -> 규칙

- `git push -u origin main`
  - permission error
    - remote 등록 주소가 잘못되지 않았는지 확인
    - vscode에 연결된 git 계정과 내가 올리려고 하는 github 계정이 일치하는지 확인
