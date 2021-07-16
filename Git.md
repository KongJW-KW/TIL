# git bash 사용 방법 정리

도대체 git 이란 무엇인가?</br> 
**깃(Git)은 프로그램 등의 소스 코드 관리를 위한 분산 버전 관리 시스템이다(위키백과)**</br>

<pre>
Git은 어떤 방식으로 버전 관리를 하는가?
  -Git은 중앙 서버 컴퓨터와 여러개의 컴퓨터들이 연결되어 모두 같은 버전의 데이터베이스를 유지한다.
   이 버전은 업데이트가 될 때마다 자동으로 생성된다. 따라서 이 파일들은 최신버전으로 모든 컴퓨터에서 유지될 수 있을 것이다.
  -컴퓨터 A에서 업데이트한 것을 중앙 서버에 올리면 버전이 업데이트 되고, 
   컴퓨터 B는 이를 중앙 서버 컴퓨터로부터 최신화시키면서 버전과 파일을 모두 컴퓨터 A와 동일하게 유지할 수 있다.
  </pre>


# git의 설치 버전 확인하기
![캡처](https://user-images.githubusercontent.com/80589627/125893631-b8fd6afe-b353-4540-8474-df731638ca79.PNG)


# 사용자 정보 입력
![캡처](https://user-images.githubusercontent.com/80589627/125893769-fc8c0321-0265-478e-a870-5bc6e19dd002.PNG)</br>

입력한 사용자 정보 조회는 git config --list 명령어로 확인이 가능하다.

# 새 저장소 초기화
test라는 이름의 프로젝트 디렉토리를 만든 뒤, 저장소를 초기화 하는 방법은 다음과 같다.
<pre>
$mkdir test
$cd test
$git init
</pre>

# 버전 관리(Commit & Checkout)
*초기화된 디렉토리에서 sample1, sample2 파일을 생성한다.*

*add 명령어로 두 파일의 변경 사항을 stage한다. (git add)*

*그 뒤 발생한 모든 변경 사항들을 first commit이란 이름으로 커밋한다. (git commit -m "메세지" -a)*

*마찬가지로 sample3 파일을 생성한 뒤, 변경 사항을 stage하고, second commit이란 이름으로 커밋한다.*


![캡처](https://user-images.githubusercontent.com/80589627/125894192-6437a8e9-e310-4398-884b-949b785ce347.PNG)

![캡처](https://user-images.githubusercontent.com/80589627/125894293-51d8dbff-5264-4970-9b4c-a93f021832b6.PNG)

현재까지 수행한 모든 커밋 기록을 확인한다. (git log)

현재 커밋 상태를 확인하니, master 브랜치에 있는 것을 알 수 있다. (git status)

status에서 특별한 메세지가 없으므로 master 브랜치의 최신 커밋에 위치한 것을 알 수 있다. 

# 브랜치

현재 브랜치 리스트와 상태를 출력한다. (git branch)

브랜치 b1과 b2를 생성한 뒤, b1으로 체크아웃한다.

현재 브랜치가 b1으로 이동된 것을 확인할 수 있다.

![캡처](https://user-images.githubusercontent.com/80589627/125894435-6eb6c7aa-8202-4ea9-8c05-02acb43140fc.PNG)

b1 브랜치에서 sample4 파일을 생성하고 커밋한다.

b2 브랜치로 이동해 sample5 파일을 생성하고 커밋한다.

![캡처](https://user-images.githubusercontent.com/80589627/125894653-00399866-7b10-45d4-9bca-47a3abba236f.PNG)

# github와 연동하기
1. github 계정 생성하기
2. 오른쪽 상단에 내 프로필 접속
![캡처](https://user-images.githubusercontent.com/80589627/125894837-9e12a9a2-aad0-4e39-a0de-a43954b93904.PNG)
3. 새로운 repo생성
4. Clone의 주소 복사
5. git bash에 $git clone address(아까 복사한 주소)

![캡처](https://user-images.githubusercontent.com/80589627/125895092-b73ebddd-a215-4c62-a434-e1e54a001b69.PNG)

# 변경사항 push및 pull
<pre>
1.clone 받은 프로젝트를 init한 뒤, 새 파일을 만들어 commit한다.
2.그 뒤  local/master에서 새롭게 생성된 commit을 GitHub의 origin/master 브랜치에 업데이트한다. (git push 원격 로컬)
3.이때 어떤 계정에서 push를 진행한 지 확인하기 위해 GitHub 계정 정보를 입력한다.
4.다른 컴퓨터에서는 origin/master 브랜치의 변경 사항을 반영하기 위해 변경 사항을 pull 한다. (git pull)
</pre>


# 자주 사용하는 git 명령어 정리
<pre>
git init : git 생성하기
git clone git_path : 코드가져오기
git checkout branch_name : 브랜치 선택하기
git checkout -t remote_path/branch_name : 원격 브랜치 선택하기
git branch branch_name : 브랜치 생성하기
git branch -r : 원격 브랜치 목록보기
git branch -a : 로컬 브랜치 목록보기
git branch -m branch_name change_branch_name : 브랜치 이름 바꾸기
git branch -d branch_name : 브랜치 삭제하기
git push remote_name — delete branch_name : 원격 브랜치 삭제하기 ( git push origin — delete gh-pages )
git add file_path : 수정한 코드 선택하기 ( git add * )
git commit -m “commit_description” : 선택한 코드 설명 적기 ( git commit -m “내용”)
git push romote_name branch_name : add하고 commit한 코드 git server에 보내기 (git push origin master)
git pull : git서버에서 최신 코드 받아와 merge 하기
git fetch : git서버에서 최신 코드 받아오기
git reset — hard HEAD^ : commit한 이전 코드 취소하기
git reset — soft HEAD^ : 코드는 살리고 commit만 취소하기
git reset — merge : merge 취소하기
git reset — hard HEAD && git pull : git 코드 강제로 모두 받아오기
git config — global user.name “user_name ” : git 계정Name 변경하기
git config — global user.email “user_email” : git 계정Mail변경하기
git stash / git stash save “description” : 작업코드 임시저장하고 브랜치 바꾸기
git stash pop : 마지막으로 임시저장한 작업코드 가져오기
git branch — set-upstream-to=remote_path/branch_name : git pull no tracking info 에러해결
</pre>
출처 : https://pks2974.medium.com/%EC%9E%90%EC%A3%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EA%B8%B0%EC%B4%88-git-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC%ED%95%98%EA%B8%B0-533b3689db81
