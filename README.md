# git와 github 실습
실습을 위해서는 git이 설치된 로컬환경과 github 사이트에서 계정 등록 필요.

## 1. git 설치 
### Windows
https://git-scm.com/downloads/win 에서 다운로드 및 인스톨
### Linux
#### Ubuntu
    sudo apt install git-all
#### 기타 다른 리눅스 
https://git-scm.com/downloads/linux 에 설치하는 방법 참조
### Mac
https://git-scm.com/downloads/mac 에서 다운로드 및 인스톨

## 2. github 계정 생성
https://github.com/ 로 가서 계성 생성 

## 3. git 버전 확인
    git --version

## 4. 로컬에서 github 계정 정보 등록
    git config --global user.name [Your Username]

    git config --global user.email [your@email.com]

## 5.git 설정 정보 확인
    git config -l

## 6. 로컬 저장소 생성
    mkdir workplace
    cd workplace

## 7. git 초기화 및 확인
    git init
(해당하는 디렉토리를 git으로 관리할것이라는 의미)

.git 디렉토리가 생성됨
(파일 폴더 그림에서 보면 숨겨진 파일로서 안보일 경우가 있음)

## 8. readme.md (마크다운) 파일 생성
등록하는 파일들을 설명하는 내용으로 자유롭게 작성할 수 있음.

마크다운 방식으로 만듦. 자세한 네용은 마크다운 설명 참조 ( https://gist.github.com/ihoneymon/652be052a0727ad59601 )

지금은 간단하게 아래와 같이 한 줄만 작성

    echo "# first-repository" >> readme.md

## 9. git status 확인
    git status




git &amp; github practice
