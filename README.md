1] 사용자 이름/이메일 등록

1-1. 사용자 이름 등록

git config --global user.name "username"

1-2. 사용자 이메일 등록

git config --global user.email "useremail"

git config --global user.email "email"

1-3. 등록 확인

git config --list


2] 로컬 저장소 생성

2-1. 로컬 저장소 생성(방법1)

git init   #원하는 폴더에서 로컬 저장소를 수동으로 생성

2-2. 로컬 저장소 생성(방법2) - 기존 github에 있는 저장소를 내 로컬로 복제

git clone (git 저장소의 URL)


3]코드 생성

3-1. README.md라는 파일에 스트링 문자 쓰는 코드

echo 'hello, git!' > README.md

3-2. README.md 확인

cat README.md


4]Staging 영역에 추가

4-1. 현재 디렉토리에 있는 업데이트 된 파일을 전부 스테이징 영역으로 추가

#git 모든 파일 올리기

git add .

git add -A

#특정 파일 올리기

git add 파일명

4-2. local repository 상태 확인

git status

4-3. 파일을 삭제하는 명령(--cached작성시 원격만 삭제, 미작성시 원격,지역 모두 삭제)

git rm --cached 파일명


5] 저장소에 commit (-m은 메세지 약자, "내용")

git commit -m "feat : README.md update" 


6] 원격저장소에 push, 업데이트 된 내용은 pull

6-1. push 전에 원격 저장소와 로컬 저장소를 연결

git remote add origin (원격 저장소 github URL)

#현재 연결된 원격 저장소 리스트

git remote

#현재 연결된 원격 저장소 상태 확인

git remote -v

#원격 저장소 이름 변경

git remote rename [현재저장소이름] [바꿀저장소이름]

#연결된 원격 저장소 끊기

git remote remove [원격저장소이름]

6-2. push

git push [원격저장소이름] [브랜치이름]

6-3. 깃허브에서 메인 브랜치 이름을 master가 아닌 기본으로 main으로 해놓음(21.05.11)

 따라서 브랜치를 바꾸고, 바꾼 브랜치로 psuh 해줘야 함
 
git branch -M [바꿀브랜치이름]]

git push [원격저장소이름] [브랜치이름]

cf) 원격저장소 변경시

fatal: refusing to merge unrelated histories 이런 경고문이 뜰 때

git pull [리모트저장소] [브랜치] --allow-unrelated-histories


7] pull : 원격저장소에 업데이트한 파일이 있을 때, 원격저장소와 내 로컬저장소의 상태를 동일하게 할때

git pull [원격저장소이름] [브랜치이름]


8] branch

8-1. 현재 브랜치 이름 확인

git branch

8-2. 브랜치 변경

git checkout [바꿀 브랜치 명]

#[-b]브랜치 작성과 변경이 동시에 이루어짐

git checkout -b [바꿀 브랜치 명]

8-3. 브랜치 삭제

git branch -d [삭제할 브랜치 명]
