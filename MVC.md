# MVC
> Model, View, Controller의 약자로 하나의 어플리케이션, 프로젝트를 3가지의 역할로 구분한 패턴이다.

![MVC패턴그림](https://postfiles.pstatic.net/MjAxNzAzMjVfMjUw/MDAxNDkwNDM4NzI4MTIy.4ZtITJJKJW_Nj1gKST0BhKMAzqmMaYIj9PobYJMFD4Ig.xTHT-0qyRKXsA4nZ2xKPNeCxeU2-tLIc-4oyrWq5WBgg.PNG.jhc9639/mvc_role_diagram.png?type=w966)

## 디자인 패턴
특정 상황에서 공통적으로 발생하는 문제에 대해 재사용 가능한 서술이나 템플릿이다.(좀 더 쉽고 편리하게 개발 할 수 있도록 만든 특정한 패턴이다.) 

---

## Model
어플리케이션의 정보, 데이터를 나타낸다. DB, 상수, 초기화값, 변수 등을 뜻하며 이러한 DATA의 가공을 책임지는 컴포넌트를 말한다.

1. 사용자가 편집하길 원하는 모든 데이터를 알고있어야 한다.

    > 화면에 네모박스와 안의 글자가 표현된다면 네모박스의 화면 위치 정보, 네모박스의 크기정보, 글자내용, 글자의 위치 등의 모든 정보를 가지고 있어야 한다.

2. 뷰나 컨트롤러에 대해서 어떤 정보도 알지 말아야 한다.

    > 데이터 변경이 일어났을 때 모델에서 화면 UI를 직접 조정해서 수정할 수 있도록 뷰를 참조하는 내부 속성값을 가지면 안 된다.

3. 변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야만 한다.

    > 모델의 정보가 변경되면 이벤트를 발생시켜 누군가에게 전달해야 하며 모델을 변경하도록 요청하는 이벤트를 보냈을 때 이를 수 신할 수 있는 처리 방법을 구현해야 한다.

## View
사용자 인터페이스 요소를 나타낸다. 즉 데이터 객체의 입력, 출력을 담당한다.

1. 모델이 가지고 있는 정보를 따로 저장해서는 안된다.

    > 모델에게 전달받은 정보를 유지하기 위해, 임의의 뷰 내부에 저장해서는 안된다.

2. 모델이나 컨트롤러와 같이 다른 구성요소들을 몰라야 된다.

    > 뷰는 모델이나 컨트롤러의 참조방식이나 구성, 동작방식을 몰라야한다. 그저 데이터를 받아 화면에 출력해주는 역할만 해야한다.

3. 변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야만 한다.

    > 뷰에서는 화면에서 사용자가 화면에 표시된 내용을 변경하게 되면 이를 모델에게 전달해서 모델을 변경해야 할 것이다. 그 작업을 하기 위해 변경 통지를 구현해야 한다.

## Controller
데이터와 사용자인터페이스 요소들을 잇는 다리역할을 한다. 즉 사용자가 데이터를 전송, 수정하는 등 의 "이벤트"들을 처리하는 부분이다.

1. 모델이나 뷰에 대해서 알고 있어야 한다.

    > 모델이나 뷰는 서로의 존재를 모르며 변경을 외부로 알리고, 수신하는 방법만 가지고 있다. 그러므로 이를 컨트롤러가 중재하기 위해 모델과 그에 관련된 뷰에 대해서 알고 있어야 한다.

2. 모델이나 뷰의 변경을 모니터링 해야 한다.

    > 모델이나 뷰의 변경 통지를 받으면 이를 해석해서 각각의 구성 요소에게 통지를 해야 한다.

