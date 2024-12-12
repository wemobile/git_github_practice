git와 github 실습
=================
실습을 위해서는 다음과 같이 git이 설치된 로컬환경과 github 사이트에서 계정 등록 필요.

(이 글은 https://modulabs.co.kr/blog/git-and-github-for-beginners 를 참조했음)

# 1. git 설치 
## Windows
https://git-scm.com/downloads/win 에서 다운로드 및 인스톨
## Linux
### Ubuntu
    sudo apt install git-all
### 기타 다른 리눅스 
https://git-scm.com/downloads/linux 에 설치하는 방법 참조
## Mac
https://git-scm.com/downloads/mac 에서 다운로드 및 인스톨

# 2. github 계정 생성
* https://github.com/ 로 가서 계정 생성 


# 3. git 버전 확인
    git --version

# 4. 로컬에서 github 계정 정보 등록
github 사용자이름
  
    git config --global user.name [Your Username]

github 등록 시 사용했던 e-mail

    git config --global user.email [your@email.com]


# 5.git 설정 정보 확인
    git config -l

# 6. 로컬 저장소 생성
    mkdir workplace
    cd workplace

* 이 부분에서 다양한 파일을 만들어서 다음의 내용처럼 github에 등록해야 하지만 여기에서는 readme.md 파일만 테스트로 만들어서 등록하는 것으로 합니다.

# 7. git 초기화 및 확인
    git init
(해당하는 디렉토리를 이제부터 git으로 관리할것이라는 의미. github에서 클론을 받은 경우에는 이 작업은 필요 없음)

* .git 디렉토리가 생성됨
(파일 폴더에서 보면 숨겨진 파일로서 안보일 경우가 있음)

# 8. github에 올리는 테스트로 readme.md (마크다운 형식의 파일) 생성
* 현 디렉토리 내용을 설명하는 파일로서 자유롭게 작성할 수 있음. 이제부터 만들 레퍼지토리로 들어가면 홈페이지처럼 표시 됨.

* 마크다운 방식으로 만듦. 자세한 네용은 마크다운 설명 참조 ( https://gist.github.com/ihoneymon/652be052a0727ad59601 )

* 지금은 간단하게 테스트로 아래와 같이 한 줄만 작성한 파일 만듦
```bash
echo "# first-repository" >> readme.md
```
# 9. git status 확인
    git status

# 10. add와 commit 개념
* Working Directore: 파일을 수정/추가하는 작업공간

* index (Staging Area): commit 할 파일들을 준비하는 공간

* HEAD: branch의 최신 commit을 가리키는 포인터

## git add
* Working Directory에서 변경된 파일을 Staging Area에 추가

```bash
git add readme.md
```
## git commit
* 설명과 함께 변경사항을 우선 저장(commit)

```bash
git commit -m "new readme file"
```
# 11. git log로 기록 확인
    git log

# 12. 원격 저장소(repository) 생성하기
## github 에 로그인 후 'your repository"로 이동

![image](https://github.com/user-attachments/assets/f5411f4c-d80f-4004-828a-3680180d731f)

## 우측 상단의 초록색 "NEW" 버튼을 클릭하여 새로운 레포지토리 생성 
* 로컬에 만들어 놓은 readme.md 파일을 사용할 것이기 때문에 "Add a README file" 는 체크하지 않음. 만약 github 사이트 제공 브라우저 에디터에서 직접 만들 경우에는 체크.

![image](https://github.com/user-attachments/assets/5da70a82-125c-4946-a6df-a5bdcfe25e73)

* "create repository" 클릭


![image](https://github.com/user-attachments/assets/468d6df6-485c-4f6f-ba6f-89564e5548fa)

# 13. 로컬 저장소와 원격 저장소 연결
    git remote add [별칭(English)] https://github.com/[your-username]/first-repository.git
별칭을 임의의 단어로 쓰는데 이는 다음부터는 긴 URL 대신 간편하게 이 별칭을 사용하기 위함임. 새롭게 수정/추가 시에는 이것과 다른 단어의 별칭을 사용해야 함.

# 14. 변경사항 올리기와 내리기
## 올리기(master 브랜치로)
    git push [별칭] master

## 내리기(master 브랜치에서)
    git pull [별칭] master

# 끝
