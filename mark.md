ADD
git add 명령어는 git에 등록하여 commit을 할 수 있는 상태로 만든다. 즉, Untracked files를 Staging area로 추가하여 git이 관리할 수 있도록 한다.

$ git add .
$ git add filename
git add . 명령어를 입력하면, 변경된 사항 모든 파일들을 등록한다.

이는 많은 파일을 변경했을 시 유용하지만, 불필요한 파일까지 모두 등록될 수 있기 때문에 주의해야 한다.



Commit
git commit 명령어는 커밋이 가능한 파일들의 변경 사항을 저장하는 명령어이다. 즉, Staging area에 있는 변경된 파일들을 뜻한다.

-m 옵션을 통해 커밋할 내용의 코멘트를 작성할 수 있다.

쉽게 알아볼 수 있도록 변경 사항이나 커밋 날짜 등을 기입하여 커밋하는 것이 좋다.

$ git commit -m '커밋 메시지'



Log
git log 명령어는 현재까지 commit 된 내역들을 터미널 창에 출력해주는 명령어이다. 명령어 실행 이후 로그 창에서 벗어나고 싶다면 q를 입력하면 된다.

$ git log



Clone
git clone 명령어는 복제할 리포지토리의 주소를 로컬 저장소에 복제해오는 작업이다. 리포지토리를 복사해 오기 위해서는 리포지토리의 주소를 알아야 한다.

$ git clone 리포지토리 주소



Push
git psuh는 Local에서 변경, commit 된 사항을 원격 저장소에 업로드하는 명령어이다.

git commit -m '커밋 메시지' 명령어를 통해 커밋을 했다면, 이를 깃허브 원격 리포지토리(Remote Repository)에 등록을 요청해야 한다.

$ git push
$ git push origin main(or master)
$ git push origin branch
깃허브에는 하나의 리포지토리를 여러 브랜치를 둘 수 있다. 메인 브랜치는 가장 중심이 되는 브랜치이며, 다른 브랜치는 메인 브랜치에 영향을 받거나 주지 않는 독립적인 형태로 존재할 수 있다.

따라서, 메인 브랜치에 push 할 수도 있고, 메인 브랜치에 영향을 주지 않는 다른 브랜치에 push 할 수도 있다.

 

메인 브랜치는 master 단어의 이슈가 있기 전엔 master가 메인 브랜치였다. 따라서 지금 새로 리포지토리를 생성하면 모두 main 브랜치이나, 과거에 생성한 브랜치가 있다면, git push origin master 명령어를 사용해야 할 수도 있다.

 
 
 Pull
git pull 명령어는 Remote Repository의 작업 내용을 가져오면서 병합 작업을 실행한다. git pull 명령어는 git fetch와 git merge를 실행한 결과로 나타낼 수 있다. 이는, Local Repository에 Remote Repository의 내용을 덮어 씌운다고도 할 수 있다.

$ git pull
$ git pull origin main(or master)
$ git pull origin branch
 

만약, 협업하는 동료가 gildong이라 가정하고, 동료의 작업 내용을 자신의 로컬 리포지토리에 가져오면서 병합을 하고자 한다면 다음과 같이 사용할 수 있다. 만약, 동료의 main 브랜치가 아닌 다른 브랜치에서 가져오고자 한다면, main 대신 branch이름을 적으면 된다.

$ git pull gildong main(or master or branch)
git pull 명령어의 주의할 점은 git fetch와 git merge 동작을 한 번에 수행하기 때문에, 여러 사람들과 협업을 진행할 시 충돌이 일어날 수 있다.




Fetch
git fetch 명령어는 원격 저장소의 변경 사항을 가져오기만 한다. 이는 git pull과는 다르게 병합을 수행하지는 않는다. 따라서, 로컬 저장소의 작업과 적절하게 병합하여 사용할 수 있다.

$ git fetch
만약, git push를 수행하였는데 거절당할 시, git fetch → git merge → git push를 하여 문제를 해결할 수 있기도 하다.




Merge
git merge 명령어는 git fetch 명령어를 통해 원격 저장소의 변경 사항을 가져온 후 사용하여 로컬 저장소와 병합을 하기 위해 사용한다.

$ git merge
일반적으로 git push 또는 git pull을 통해 명령을 수행하지만, 일부 병합 문제로 인해 push가 안되거나, 안전하게 remote repository의 내용을 가져올 때 git fetch와 git merge를 사용한다.




