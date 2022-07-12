# git 협업 방법 정리

1. 작업 시작 전 git에서 pull 받기
2. 개발 기능을 세분화 하여 branch 생성
3. 개발한 source에 대하여 세분화 하여 commit 후 push 합니다.
4. 완료 후 branch를 master branch에 merge 합니다.

## 1. 명령어 정리
1. git init : 현재 디렉토리를 Git이 관리하는 프로젝트 디렉토리로 설정하고 그 안에 레포지토리 생성
2. git config user.name '사용자아이디' : 현재 사용자의 아이디를 설정
3. git config user.email '사용자이메일' : 현재 사용자의 이메일을 설정
4. git add [파일 이름 or .] : 수정사항이 있는 특정 파일을 staging area에 업로드(.으로 하면 수정된 모든 파일을 올림)
5. git reset [파일 이름] : staging area에 업로드 했던 파일 다시 내리기
6. git status : Git이 현재 인식하고 있는 프로젝트 관련 내용들 출력
7. git commit -m "comment" " : 현재 staging area에 업로드 되어 있는 파일들에 comment 남기기
8. git push [-u] origin [Branch명] : 로컬 레포지토리의 내용을 리모트 레포지토리에 올릴 때 사용 (-u는 처음 업로드 할 때만 사용하면됨)
9. git pull origin [Branch명] : 해당 Branch의 파일들을 pull 해옴
10. git clone [프로젝트 주소] : git에 올라가있는 프로젝트를 통째로 가져옴
11. git log : commit history 출력
12. git branch [branch_name] : 새로운 브렌치 생성
13. git checkout -b [branch_name] : 새로운 브렌치를 생성하고 그 브렌치로 바로 이동
14. git branch -d [branch_name] : 브렌치 삭제
15. git checkout [branch_name] : 해당 브렌치로 이동
16. git merge [branch_name] : 현재 브렌치에 다른 브렌치를 merge
17. git merge --abort : merge를 하다가 conflict가 발생 시, 일단은 작업을 취소하고 이전 상태로 돌아감

## 2. 상세 사용 방법(Repository에 처음으로 작업을 할 때)
1. git init
2. git config user.name [username]
3. git config user.email [useremail]
4. git remote add origin [git_프로젝트_주소]
5. git add .
6. git commit -m "First commit"
7. git push -u origin main(main으로 하고 싶으면 4번째에서 remote 후에 git branch -M main 입력)

## 3. 상세 사용 방법(작업 중인 Repository를 가져와 작업할 때)
1. git clone [git주소]
2. ~~ 작업 ~~
3. git config user.name [username]
4. git config user.email [useremail]
5. git add .
6. git commit -m "남길메세지"
7. git push origin main(or branch명)

## 4. Merge conflict 해결 방법
1. 충돌된 소스 코드 부분을 수정
2. git add .
3. git commit