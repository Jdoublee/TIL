# [c++] 시간초과 문제- 입출력 



> 백준에서 문제를 풀 때 예제는 분명 잘 돌아가는데 시간 초과가 떠서 실패하는 경우가 있다.
>
> c++ <iostream\>의  `std::cin` , `std::cout` 이 c <stdio.h\> 의 `scanf` , `printf` 에 비해 속도가 느리기 때문이다.
>
> 여기서 더 빠르게 하려면 글자 하나씩 입출력하는 함수(getchar, putchar 등)를 사용하는 것이 좋다.
>
> 또한, `std::endl` 보다 **\n**을 사용하여 개행을 해주는 것이 속도가 더 빠르다.



- c++에서 속도를 높여주기 위해 다음의 코드를 추가로 작성해준다.

```cpp
ios_base :: sync_with_stdio(false);
cin.tie(NULL);
cout.tie(NULL);
// 입출력 객체를 가속시켜줌
```



- 만약 이 코드를 작성해도 시간초과가 난다면 c의 표준입출력인 `printf` 와`scanf` 를 사용하자.