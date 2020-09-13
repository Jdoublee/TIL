# [git] 로컬저장소 생성 및 기본 동작

> 용량 늘려보겠다고 캐시 삭제했다가 push가 안 되고 검색으로도 에러 해결이 안 되어서 그냥 삭제하고 다시 만들었다.
>
> 다시 md 보러 오는 일 없도록 잘 기억해두자.



## 1. 로컬 저장소 생성

- **저장소 초기화**

```bash
$ git init
# 저장소를 초기화하며 .git 파일 생성 
```

- **깃헙 저장소와 연결**

```bash
$ git remote add origin https://github.com/Jdoublee/CodingTestPractice.git
$ git remote -v
origin	https://github.com/Jdoublee/CodingTestPractice.git (fetch)
origin	https://github.com/Jdoublee/CodingTestPractice.git (push)
```

- **Pull 해오기**

```bash
$ git pull origin master
From https://github.com/Jdoublee/CodingTestPractice
 * branch            master     -> FETCH_HEAD
(base) HYEWON:Github hyewon$ git status
On branch master
nothing to commit, working tree clean
```



## 2. 기본 명령어

```bash
$ git status
# Untracked file 이나 commit 기다리는 파일 등 확인 가능
$ git add .
# stage로 올려줌
$ git commit -m "commit message"
$ git push
# 커밋과 푸시
```

