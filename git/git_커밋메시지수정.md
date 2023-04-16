# [git] 커밋 메시지 수정

- 이미 push한 커밋의 메시지 수정하고싶을 때
  
    1. 커밋 메시지 수정
    
    2. 강제 푸시 명령어 사용
    
    ```bash
    $ git push --force-with-lease origin [EXAMPLE-BRANCH]
    ```
    
- **리포지토리의 기록이 변경되므로 강제 푸시를 사용하지 않을 것을 강력히 권장합니다. 강제 푸시를 사용할 경우 이미 리포지토리를 복제한 사용자는 로컬 기록을 수동으로 수정해야 합니다.**
- [참고](https://docs.github.com/ko/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message#amending-older-or-multiple-commit-messages)

