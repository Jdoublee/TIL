# [github] ipynb 파일 열기 오류

>github 레포지토리에 있는 ipynb 파일이 열리지 않고 로딩만 반복되다
>
>`"Sorry, something went wrong. Reload?"` 라는 문구만 마주했을 때...
>
>Reload해도 결과는 똑같을 것이다.
>
>그럴 때 다운받고 열고 하지 말고 렌더링 웹을 활용해봅시다.

## 1. nbviewer 웹 사이트

-  [nbviewer](https://nbviewer.jupyter.org/) : A simple way to share Jupyter Notebooks
-  해당 웹 사이트에 접속해서 ipynb파일이 위치한 깃헙 레포 주소를 통째로 복사하여 붙여넣으면 바로 확인할 수 있다.



## 2. 링크로 바로 이동

- 링크로 바로 열고 싶다면 아래와 같이 주소창에 입력하면 된다.
- `https://nbviewer.jupyter.org/ ` + `github/USERNAME/하위경로.../열고자하는파일.ipynb`

- 예시
  - 열고자 하는 ipynb 파일 주소 : `https://github.com/Jdoublee/capstone/blob/master/fineturning/KoGPT2_fine_turning.ipynb`
  - 링크 : `https://nbviewer.jupyter.org/github/Jdoublee/capstone/blob/master/fineturning/KoGPT2_fine_turning.ipynb`