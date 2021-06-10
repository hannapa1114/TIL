# git 시작하기

### 1. brew 설치(mac)
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
- 터미널에 ctrl + c, ctrl + v 해서 실행
- git install 을 하기 위해서 homebrew를 먼저 설치

### 2. git 설치
```
brew install git
```

### 3. git 설치 확인
```
git --version
```

- 빈 디렉토리 추가하기

  git repository에 빈 폴더는 추가가 되지 않기 때문에 폴더 내에 .gitignore 파일을 생성한 후
  git add commit push 명령어를 통해 빈 폴더를 추가할 수 있다.




# git 명령어


### 1. git init : 현재 폴더를 git을 사용할 수 있게 만들어준다.
```
git init
```




### 2. git clone : git의 원격 레포지토리를 local로 복사(다른 사람의 소스코드 혹은 내 소스코드를 내 컴퓨터에 받을 수 있도록)
```
git clone https://github.com/hannapa1114/repository
```

### 3. git add :  파일을 git에 등록해서 관리할 수 있도록 함
   * 특정파일
   * . (전부 추가)

### 4. git commit -m : git에 add로 추가된 파일의 버전관리 및 설명 추가
```
git commit -m "설명" 
```

### 5. git push : git에 추가되거나 변경된 파일을 원격 저장소(Github)에 업로드
```
git push
```

### 6. git pull : 다른 사람이 수정한 내용이 있을 경우 그 파일을 내 컴퓨터에 받아온다
```
git pull
```

### 7. git remote
   * -v 버전확인
   * add (origin | upstream) url
   * remove (origin | upstream)

### 8. git log : commit 했던 내용들을 보여준다
```
git log
```




