#git 시작하기

- brew 설치(mac)
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
터미널에 ctrl + c, ctrl + v 해서 실행
git install 을 하기 위해서 homebrew를 먼저 설치

- git 설치
```
brew install git
```

- git 설치 확인
```
git --version
```

- 빈 디렉토리 추가하기
  git repository에 빈 폴더는 추가가 되지 않기 때문에 폴더 내에 .gitignore 파일을 생성한 후
  git add commit push 명령어를 통해 빈 폴더를 추가할 수 있다.

### git 명령어

1. git init - 현재 폴더를 git을 사용할 수 있게 만들어준다.
```
git init
```
.git 폴더가 생긴다

2. git clone - git의 원격 레포지토리를 local로 복사
```
git clone https://github.com/hannapa1114/repository
```

3. git add
   * 특정파일
   * . (전부 추가)

4. git commit -m "내용"

5. git push

6. git pull

7. git remote
   * -v 버전확인
   * add (origin | upstream) url
   * remove (origin | upstream)




