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


# 3. git 버전 확인: 그냥 확인만 해 봄.
    git --version

# 4. 로컬에서 github 계정 정보 등록
github 사용자이름
  
    git config --global user.name [Username]

github 등록 시 사용했던 e-mail

    git config --global user.email [anyone@email.com]

* 위 명령어 사용 후 사용자명과 이메일은 아래 파일에 저장되면서 변경하기 전까지는 PC 전체에 영향을 미치게 됨('.'로 시작되는 디렉토리나 파일은 숨겨져 있으므로 보려면 아래 'x. git 초기화 및 확인' 참조).

<pre>
C:\Users\AI09>type .gitconfig

[user]
        name = [Username]   
        email = [anyone@email.com]
</pre>

# 5.git 설정 정보 확인: 그냥 확인만 해봄.
    git config -l

# 6. 로컬 저장소 생성
    mkdir workplace
    cd workplace

* 이 부분에서 다양한 파일을 만들어서 다음의 내용처럼 github에 등록해야 하지만 여기에서는 readme.md 파일만 테스트로 만들어서 등록하는 것으로 합니다.

# 7. git 초기화 및 확인: 'git clone [github link] 로 source를 가져올 경우 디렉토리를 만드는 것 이외에는 여기까지 건너뛸 수 있음
    git init
(해당하는 디렉토리를 이제부터 git으로 관리할것이라는 의미. github에서 클론을 받은 경우에는 이 작업은 필요 없음)

* .git 디렉토리가 생성됨
* 파일 폴더나 command(cmd) shell에서 보면 숨겨진 디렉토리('.'으로 시작되는 이름)로서 안보일 경우가 있음(아래 보는 방법)
* 숨겨진 '디렉토리' 보는 방법: Windows 11 파일 폴더(그러나 '.'으로 시작하는 숨겨진 '파일'은 보이지 않음. 아래 cmd에서 확인 필요)
  
![image](https://github.com/user-attachments/assets/ec92d5f7-e113-4f2e-b2d0-04c314da075d)

* command(cmd) shell
```
    dir/a
```

# 8. github에 올리는 테스트로 readme.md (마크다운 형식의 파일) 생성
* 현 디렉토리 내용을 설명하는 파일로서 자유롭게 작성할 수 있음. 이제부터 만들 레퍼지토리로 들어가면 홈페이지처럼 표시 됨.

* 마크다운 방식으로 만듦. 자세한 네용은 마크다운 설명 참조 ( https://gist.github.com/ihoneymon/652be052a0727ad59601 )

* 지금은 간단하게 테스트로 아래와 같이 한 줄만 작성한 파일 만듦(이후 readme.md 파일이 있는 Github 사이트에서 직접 편집하면 편리)
```bash
echo "# first-repository" >> readme.md
```
# 9. git status 확인
    git status

# 10. add와 commit 실행: 나의 로컬 PC에서 파일 변경이나 새로운 파일 추가 시 여기부터 실행
* 용어 설명
<pre>
    * Working Directore: 파일을 수정/추가하는 작업공간
    * index (Staging Area): commit 할 파일들을 준비하는 공간
    * HEAD: branch의 최신 commit을 가리키는 포인터
</pre>

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

# 12. 원격 저장소(repository) 생성하기: 처음 1회만 생성
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
* [별칭]이 기억나지 않을 때 이미 만들어 놓은 [별칭] 찾아보기.   

```git config -l```

* 표시되는 내용 중 remote.[별칭].url=... 참조   

## 올리기(master 브랜치로)
'''git push [별칭] master'''
or
'''git push [별칭] main'''

## 내리기(master 브랜치에서): github 에서 변경된 파일 또는 타인이 다른 PC에서 변경/추가한 파일을 내 로컬 PC에 반영 시 여기부터 실행
```git pull [별칭] master```
or
```git pull [별칭] main```

# 끝
