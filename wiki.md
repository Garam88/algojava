Wiki
====

Git 사용법
---------

1. git clone
   git 저장소를 복사하는데 쓴다.
   ex) git clone https://github.com/Garam88/algojava.git

2. git pull
   현재 브랜치의 최신 버전을 다운로드 받는다. -p 옵션을 주면 새로운 브랜치의 생성 정보 등 프로젝트 전체의 메타정보를 함께 받아올 수 있다.

3. git checkout
   브랜치를 변경한다. -b 옵션을 줄 경우 새로운 브랜치를 만들 수 있다.
   ex) git checkout development : development 브랜치로 현재 브랜치를 변경
   ex) git checkout -b greed : greed 브랜치를 새로 생성하고 현재 브랜치로 변경

4. git add
   변경사항을 커밋 대상으로 추가한다. 전체를 저장할 경우 경로에 . 만을 입력한다.
   ex)git add .

5. git commit
   커밋 대상들을 저장한다. -m 옵션으로 지금 커밋에 메시지를 남길 수 있다.
   ex) git comit -m "최초 커밋"

6. git push
   원격 저장소에 지금까지의 커밋들을 업로드 한다. 