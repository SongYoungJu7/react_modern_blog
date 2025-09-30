# Git

Git 설정하고 초기화 하기

1. `git init` (git 초기화)
2. `git config --list` (git 환경설정)
3. `git config --local user.name` "git 계정"
4. `git config --local user.email` "git 이메일"
   - --local : local에만 적용되는 설정
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
