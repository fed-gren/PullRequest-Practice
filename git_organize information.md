# hyodol git 내용 정리
    
    Git & GitHub (Terminal 명령어 포함..)
    
    * pwd
    * cd
    * mkdir
    * ls -al
    * vim
    * vim -> i (insert)
    * vim -> :wq (write, quit)
    * cat
    * git init -> 현재 디렉토리를 git 의 (버전) 저장소를 만든다. -> 현재 디렉토리를 버전관리 한다. 
    * rm -rf .git -> git init 취소 -> .git 폴더 삭제되어 git 로컬 저장소 지정을 해제 한다.  
    * git status
    * git add
    * git config - - global core.editor “vim” -> vim 이 아니라 nano 같은 에디터가 실행 되면 명령어를 사용해 변경 
    * git config - - global user.name
    * git config - - global user.email
    * git commit
    * git log -p -> 로그에서 출력되는 버전 간의 차이점을 출력하고 싶을 때 
    * git diff 버전 id1 .. 버전 id2 -> 버전 간의 차이점을 비교할 때 
    * git diff -> git add 하기 전과 git add 한 후의 파일 내용을 비교할 때 -> 커밋을 하기전에 마지막으로 내용을 점검할 수 있음 -> working directory 와 index 의 내용을 비교한다. 
    * git reset 버전 id - - hard (soft, mixed??? 여러 옵션들이 있음) -> 버전 id로 돌아가는 명령 -> 시계를 과거로 돌리는 것 (Reset) 
    * git rever 버전 id -> 버전 id의 커밋의 취소한 내용을 새로운 버전으로 만드는 명령 -> 특정 사건을 없었던 일로 만드는 것 (Revert) 
    *  git commit - - help -> commit 메시지에 대한 매뉴얼, 즉 도움말을 볼 수 있다. 
    * git commit -a 또는 - - all (help 에 보면 나와있음) -> 우리가 수정한 파일을 자동으로 add 시켜준다. -> add 가 없이도 commit 메시지를 작성할 수 있는 에디터로 넘어간다.
    * git commit -am “msg..“ -> 에디터를 띄우지 않고 바로 커밋 메시지를 작성하겠다. 
    * git branch -> 브랜치 목록을 볼 때 
    * git branch “새로운 브랜치 이름” -> 브랜치를 생성할 때 
    * git branch -d -> 브랜치를 삭제할 때 
    * git branch -D -> 병합하지 않은 브랜치를 강제 삭제할 때 
    * git checkout “전환하려는 브랜치 이름” -> 브랜치를 전환(체크아웃)할 때 
    * git checkout -b “생성하고 전환할 브랜치 이름” -> 브랜치를 생성하고 전환까지 할 때 -> git branch 브랜치1 -> git checkout 브랜치1 -> 위 과정과 동일하다. 
    * git log - -branches - -graph - -decorate - -oneline -> 로그에 모든 브랜치를 표시하고, 그래프로 표현하고, 브랜치 명을 표시하고, 한줄로 표시할 때 
    * git log 브랜치명1..브랜치명2 (git log -p 브랜치명1..브랜치명2 -> 소스 보려면..) -> 브랜치 간에 비교할 때 -> 브랜치명1 에는 없고 브랜치명2 에는 있는 커밋이다. 
    * git diff 브랜치명1..브랜치명2 -> 브랜치 간의 코드를 비교할 때 
    * git checkout A 한 후, git merge B -> A 브랜치로 B 브랜치를 병합할 때 (A <- B) 
    * branch 병합 시 충돌 해결 1) 직접 파일에 들어가 적절한 코드로 수정한다. 2) git add 해당파일 3) git commit -> 차례대로 진행하면 된다. 
    * git stash -> 작업을 진행하다가 완료되지 않은 상태에서 다른 브랜치로 넘어가 작업을 해야할때 (커밋하면 안되거나 애매한 상황일 때) -> working directory 내용이 save 되었고, -> index 의 상태도 해당 체크아웃 상태인 브랜치에 save 되었다. -> WIP 의미 ? Working In Process 작업중이라는 상태이다. -> 해당 작업 파일을 다시 열어보면 작업하지 않은 상태를 가지고 있다. -> 중요!!!) 추적되지 않는 파일은 저장하지 않는다. 즉, git stash 명령어는 최소한 버전 관리가 되고 파일에 대해서만 stash 를 한다는 것 
    * git stash apply -> 감춰놓은 작업 상태를 다시 살린다. -> git stash list 에서 가장 위에 있는 항목을 다시 적용하는 것 
    * git stash list 
    * git reset - -hard HEAD 
    * git stash drop -> 가장 최신 stash 를 삭제한다. -> git stash list 항목에 제일 위에있는 것을 삭제한다. 
    * git stash pop -> git stash apply; git stash drop 을 같이 수행한다. 
    * git reflog -> 그 전에 했었던 각각의 커밋들이 있다. 
    * brew cask install kdiff3 -> kdiff3 이라는 merge tool 다운로드 
    * git mergetool -> 병합시 병합툴을 이용하겠다. 
    * cherry-pick, 3-way merge, rebase 관련 사이트 -> https://www.tuwlab.com/ece/22218 
    * git init - -bare  -> 저장소를 만드는 옵션 -> .git 디렉토리 안에 들어가는 파일들에 목록들이 있다 -> bare 라고 하는것은 여러분이 작업할 수 있는 워킹 디렉트로가 없고 .git 디렉토리에 들어있는 내용만 존재하는 저장소이다. -> 원격저장소를 순수하게 하기 위해서 어떤 작업도 여기서 하지 않게 하기 위해서 -> 작업이 불가능하게 하도록..따라서 bare 키워드를 입력한다. -> 수정이 불가능, 저장소로서의 역할만 수행 
    * 현재 local 디렉토리 위치에서  git remote add origin /Users/janghyoseog/Documents/git/remote -> local 디렉토리에서 원격저장소에 다음 origin 이라는 별명을 가진 경로를 add 한다. 
    * git remote -v -> 
    * git remote remove origin -> 저장소를 지운다. 
    * 현재 디렉토리에서 원격 저장소로..  git push -> 현재 저장소는 master branch 를 원격 저장소에 똑같은 이름의 branch 로 올리고 싶을때 
    * git config - -global push.default simple -> 명시적으로 어디에서 어디로 push 를 하겠다고 지정한것들만 push 함 
    * git push - -set-upstream origin master -> master branch 를 push 할때 origin 의 master branch 로 push 한다. -> set upstream 은 앞으로 master 브랜치에서 push 명령을 했을때 자동으로 origin의 master 로 push 하겠다 -> 로컬 branch 와 원격 branch 사이의 명시적으로 연결을 세팅해주는 옵션 
    * git clone ‘복제하려고하는 프로젝트의 원격 저장소의 주소’ -> 원격 저장소의 저장된 프로젝트를 내 지역 저장소에 저장할 수 있다. -> ex) git clone https://github.com/git/git.git 내 로컬디렉토리 
    * git log - -reverse -> 거꾸로 로그를 볼 수 있어서 맨 처음 초기의 commit 기록부터 볼 수 있다. 
    * git checkout 커밋ID -> git의 커밋ID의 버전으로 이동할 수 있다. 
    * git remote add origin https://github.com/bestdevhyo1225/gitfth.git -> 로컬 저장소의 디렉토리를 원격저장소()에 연결 시킨다. (add 한다.) 
    * git push -u origin master -> git 에서는 로컬 저장소를 기준으로 얘기하는데 -> 로컬 저장소에 현재 checkout 되어있는 branch를 원격저장소로 push 한다. (동기화 시킨다.) -> -u 라는 옵션은 로컬 저장소의 master branch 와 원격 저장소의 master branch 를 연결 시켜서  다음 부터는 자동으로 git push 만 해도 자동으로 넘어가는 옵션이다. 
    * git pull -> 로컬 저장소 입장에서 원격 저장소의 내용을 가져온다. 
    * ssh-keygen ssh 를 통해서 다른 컴퓨터로 접속할 수 있는 비밀번호가 생긴다. 
    * GitHub 사이트 -> 프로필 버튼 클릭 -> Settings -> SSH and GPG keys 에서 등록하면 된다. 
    * /Users/janghyoseog/.ssh/id_rsa ( private ) /Users/janghyoseog/.ssh/id_rsa.pub ( public ) -> 경로에 비밀번호가 있다. 
    * git tag -> 태그 목록 보기 
    * git tag “태그 이름” [태그가 가리킬 버전의 커밋 아이디 또는 브랜치] -> 태그 생성 (light weight tag) 
    * git tag -a “태그 이름” -m “태그에 대한 설명” [태그가 가리킬 버전의 커밋 아이디 또는 브랜치] -> 태그 생성 (annotated tag) 
    * git tag -d “삭제할 태그명” -> 태그 삭제 
    * git push - -tags -> 태그 원격 저장소로 업로드

