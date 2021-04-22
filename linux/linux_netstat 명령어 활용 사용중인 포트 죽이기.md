# [linux] netstat 명령어 활용하여 사용중인 포트 확인 및 죽이기

> 이미 해당 포트가 사용중일 때 해당 pid 찾아서 죽이는 방법

- 다음과 같은 에러를 마주했을 때

```bash
Error: listen EADDRINUSE: address already in use :::3000
...
```

- `netstat` 명령어 이용해서 네트워크 관련 상태 확인
  - 옵션
    - -l (listen) : 연결 가능한 상태
    - -n (number port) : 포트 넘버
    - -t (tcp) : tcp
    - -u (udp) : udp
    - -p : 프로그램 이름 / PID
    - -a : 모두
    - -i : 이더넷 카드별 정상/에러/드랍 송수신 패킷 수 확인
    - -r : 라우팅 테이블
    - -s : 네트워크 통계

```bash
netstat -lntp
```

- `kill` 명령어로 특정 포트 죽이기

```bash
kill -9 [pid]
```

