# Git

> Git은 분산형버전관리시스템(DVCS) 중 하나이다.

## 0. Git 기초 설정

* windows 환경에서는 `git for windows`로 검색하여 `git bash`를 설치한다. [다운로드 링크](https://gitforwindows.org/)

* 처음으로 컴퓨터에서 git을 사용하는 경우 아래의 설정을 진행한다.

  ```bash
  $ git config --global user.email 이메일주소
  $ git config --global user.name 유저네임
  # 확인
  $ git config --global-l
  ```

  * 이메일 주소를 설정할 때, github에 가입된 이메일로 설정해야 커밋 이력이 github에 기록된다.

## 1. Git을 통한 버전관리 기본 흐름

### 1.1. Git 저장소 초기화

> 특정 폴더를 git 저장소로 활용하기 위해서 최초에 입력하는 명령어

```bash
$ git init
Initialized empty Git repository in C:/Users/student/Desktop/TIL/.git/

```

* .git 폴더가 숨긴 폴더로 생성되며, git bash에서는 (master)라고 표기된다.
* git으로 활용되고 있는 폴더 아래에서 저장소를 선언하지 말자.

### 1.2. add

> 커밋 대상 파일들을 추가한다.

`add` 전 상황

```bash
$ git status
On branch master
# 커밋 없음
No commits yet
# 트래킹되지 않는 파일들
# => 새로 생성된 파일이고 git으로 관리중이지 않은 파일
Untracked files:
	# git add 파일
	# 커밋이 될 것들을 포함시키기 위해서 위의 명령어를 써라
  (use "git add <file>..." to include in what will be committed)
        git.md
        markdown-images/
        markdown.md

nothing added to commit but untracked files present (use "git add" to track)

```

```bash
$ git add .
$ git status
On branch master

No commits yet
# 커밋될 변경사항들
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   git.md
        new file:   "markdown-images/\354\235\264\353\257\270\354\247\200\355\231\230\352\262\275\354\204\244\354\240\225.png"
        new file:   markdown.md
```



* add 명령어는 아래와 같이 활용된다.

```bash
$ git add . # 현재 디렉토리 전부
$ git add git.md # 특정 파일 (띄어쓰기로 여러 파일 지정)
$ git add markdown-images/ # 특정 디렉토리
```

### 1.3. commit

> 이력을 확정짓는 명령어

```bash
$ git commit -m '커밋메시지'
[master (root-commit) 7165fae] Init
 3 files changed, 120 insertions(+)
 create mode 100644 git.md
 create mode 100644 "markdown-images/\354\235\264\353\257\270\354\247\200\355\231\230\352\262\275\354\204\244\354\240\225.png"
 create mode 100644 markdown.md

```

#### `log`

> 커밋 내역들을 확인할 수 있는 명령어

```bash
$ git log
commit 7165fae0742c5a98270bc3650aa020aeca65394a (HEAD -> master)
Author: jdoublee <hyewon3429@gmail.com>
Date:   Wed Jul 8 14:41:05 2020 +0900

    Init

# 최근 n개 이력(1개)
$ git log -1
commit 7165fae0742c5a98270bc3650aa020aeca65394a (HEAD -> master)
Author: jdoublee <hyewon3429@gmail.com>
Date:   Wed Jul 8 14:41:05 2020 +0900

    Init

# 간략한 표현
$ git log --oneline
7165fae (HEAD -> master) Init

# 최근 n개의 이력을 간략하게
$ git log --oneline -1
7165fae (HEAD -> master) Init

```

