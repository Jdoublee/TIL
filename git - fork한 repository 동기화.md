# [git] fork한 repository 동기화

- **Fork 해놓은 레포지토리에 원본 저장소의 변경 내용이 반영 안 되어 있는 경우**
- 레포지토리 삭제하고 다시 fork 할 수도 있지만 다음과 같은 방법으로 동기화 가능하다.
  - 포크 저장소 : fork 해온 레포지토리 (내 레포지토리)
    - https://github.com/Jdoublee/capstone.git
  - 원본 저장소 : 원본 레포지토리
    - https://github.com/ssorry123/4_1_capstone.git



#### 1. 먼저 로컬 저장소에 포크 저장소를 **clone**

```bash
$ git clone https://github.com/Jdoublee/capstone.git
Cloning into 'capstone'...
remote: Enumerating objects: 1864, done.
remote: Total 1864 (delta 0), reused 0 (delta 0), pack-reused 1864
Receiving objects: 100% (1864/1864), 35.31 MiB | 3.52 MiB/s, done.
Resolving deltas: 100% (587/587), done.
```



#### 2. 로컬 저장소 위치에서 설정된 **원격 저장소 조회**

```bash
$ git remote -v
origin	https://github.com/Jdoublee/capstone.git (fetch)
origin	https://github.com/Jdoublee/capstone.git (push)
```



#### 3. **원본 저장소 upstream** 으로 추가해주기

```bash
$ git remote add upstream https://github.com/ssorry123/4_1_capstone.git
```



#### 4. **원격 저장소 조회**

```bash
$ git remote -v
origin	https://github.com/Jdoublee/capstone.git (fetch)
origin	https://github.com/Jdoublee/capstone.git (push)
upstream	https://github.com/ssorry123/4_1_capstone.git (fetch)
upstream	https://github.com/ssorry123/4_1_capstone.git (push)
```



#### 5. **upstream에서 fetch**

```bash
$ git fetch upstream
remote: Enumerating objects: 706, done.
remote: Counting objects: 100% (706/706), done.
remote: Compressing objects: 100% (356/356), done.
remote: Total 719 (delta 490), reused 523 (delta 313), pack-reused 13
Receiving objects: 100% (719/719), 6.22 MiB | 4.07 MiB/s, done.
Resolving deltas: 100% (491/491), completed with 27 local objects.
From https://github.com/ssorry123/4_1_capstone
 * [new branch]      master       -> upstream/master
 ...
```



#### 6. **원격 저장소 merge**

```bash
		$ git merge upstream/master
warning: Cannot merge binary files: MXXXPXXX/sg/__pycache__/models.cpython-37.pyc (HEAD vs. upstream/master)
Removing history.txt
Auto-merging MXXXPXXX/sg/views.py
CONFLICT (content): Merge conflict in MXXXPXXX/sg/views.py
...
```



##### ** **충돌 발생 시**

- branch가 여러개여서, 또는 파일명이 중복되어서 충돌 발생
- **`git status`** 명령어로 충돌 파일 확인

```bash
$ git status
On branch master
Your branch is up to date with 'origin/master'.

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:
	new file:   LICENSE
	new file:   MXXXPXXX/MXXXPXXX/__pycache__/__init__.cpython-36.pyc
	modified:   MXXXPXXX/sg/managers.py
	...

Unmerged paths:
  (use "git add <file>..." to mark resolution)
	both modified:   MXXXPXXX/sg/__pycache__/admin.cpython-37.pyc
	both modified:   MXXXPXXX/sg/forms.py
	...
```

- both modified 된 파일 열어서 수정
- `git add .`  명령어 실행

- `git commit`  명령어 실행



#### 7. 포크 저장소로 **push**

```bash
$ git push
Enumerating objects: 22, done.
Counting objects: 100% (22/22), done.
Delta compression using up to 4 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (8/8), 1.33 KiB | 1.33 MiB/s, done.
Total 8 (delta 6), reused 0 (delta 0)
remote: Resolving deltas: 100% (6/6), completed with 6 local objects.
To https://github.com/Jdoublee/capstone.git
   3d5fc43..383a991  master -> master
```



**--동기화 완료--**