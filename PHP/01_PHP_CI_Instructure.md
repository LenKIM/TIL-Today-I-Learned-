**PHP의 CI는** 

**M**

**V**

**C**

**로 나눠진다.**



MVC는 프로그램의 로직을 프리젠테이션(표현 부분)로부터 분리하는 소프트웨어 접근 방법론.

- Model은 데이터구조를 표현하여, 일반적으로 모델 클래스는 데이터를 추출, 입력, 갱신하는 등의 함수를 포함하게 도비니다.
- View는 사용자에게 보여질 부분을 표현합니다. 뷰(View)는 일반적으로 웹페이지지만, CI에서는 뷰가 헤더나 푸터처럼 웹페이지의 조각일 수도 있습니다. 또한 RSS페이지나, 혹은 다른 페이지 형태의 것일 수 있습니다.
- Controller는 일반적으로 모델과 뷰(혹은 HTTP요청을 처리하여 웹페이지를 생성하는 어떤 것) 사이에서 동작합니다.

CI는 모델이 필요없도록 MVC를 매우 느슨하게 접근하였습니다. 만약 모델을 분리할 필요가 없거나, 모델을 따로 분리하는 것이 쓸데없이 복잡도를 증가시킨다면, 컨트롤러와 뷰 파일 만으로 프로그램을 만드실수 있습니다. CI는 여러분이 이미 가지고 있는 자바 스크립트를 연동해서 사용하거나, 여러분의 기호에 맞게 시스템 코어 라이브러리를 개발하여 쓸수도 있도록 했습니다.



그러나, 여기에 서비스라는 개념이 들어갈 수 있습니다. 

그러면 모라고 불러야 할까요? MVCS ? 컨트롤러에 부여되는 부담감을 서비스와 나눠서 가지게됩니다.

컨트롤러는 비지니스 로직을 처리하기 보다는 모델과의 입출력부분을 처리하고,

서비스는 직접적인 비지니스 로직을 처리합니다.