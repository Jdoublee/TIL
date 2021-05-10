
## View Life Cycle
- 앱은 하나 이상의 뷰로 구성이 되어 있으며 각각의 뷰들은 라이프 사이클을 가지고 있다.
- 따라서 뷰의 라이프 사이클을 고려해서 로직을 구성해야 한다.

![](https://docs-assets.developer.apple.com/published/f06f30fa63/UIViewController_Class_Reference_2x_ddcaa00c-87d8-4c85-961e-ccfb9fa4aac2.png)

- ViewDidLoad : 뷰 컨트롤러 클래스가 생성될 때, **가장 먼저 실행된다.** 특별한 경우가 아니라면 딱 한 번 실행되기 때문에 **초기화** 할 때 사용한다.
- ViewWillAppear : 뷰가 생성되기 직전에 항상 실행되기 때문에 **뷰가 나타나기 전에 실행해야 하는 작업들**을 작성한다.
- ViewDidAppear : 뷰가 생성되고 난 뒤에 실행된다. 데이터를 받아서 화면에 뿌려주거나 애니메이션 등의 작업 로직을 위치시킬 수 있다. (ViewWillAppear 에 넣은 로직이 뷰에 반영이 안되는 경우가 있다.)
- ViewWillDisappear : 뷰가 **사라지기 직전**에 실행된다.
- ViewDidDisappear : 뷰가 사라지고 난 뒤에 실행된다.
