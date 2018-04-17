# DOM

### The Document Object Model (DOM) is a programming interface for HTML and XML documents. 

> The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

- 웹 문서의 element, 전체문서 , head, table, table header, table cell은 모두 DOM의 한 부분이다. 
- 페이지의 컨텐츠들은 DOM에 저장되고 이는 javascript를 통해 접근할 수 있다. - MDN-

> 웹페이지의 객체지향적인 표현이다. 이는 브라우저에서 구현되기전 W3C가 정의한 인터페이스로 존재하다가 브라우저에서 HTML, XML 문서를 DOM인터페이스에서 정의된 것을 구현한다. 구현시 ```HTMLElement=<div>``` 이런식으로 각 태그에 따라 객체를 만든다. 

- 맨위에 node객체가 있다. 그 아래 document, element가 있다. 아래 객체들은 모두 node객체를 상속 받는다. 



### DOM의 구성

- 명세 부분 :  W3C표준화 기구에서 명세 한다.(interface)
- 구현 부분 : 크롬, 파이어폭스, 익스플로어 등이 명세 부분의 기능을 구현한다. 

이런 명세된 규칙대로 구현한 브라우저를 웹표준 브라우저라고 한다.



### DOM과 HTML 페이지와의 관계

브라우저가 웹페이지 처리하는 과정

1. 웹페이지 읽기 - HTML페이지를 읽는다.
2. 파싱단계 - 작성한 태그와 1:1매칭이 되는 DOM클래스의 객체를 생성한다.
3. 웹브라우저는 생성한 DOM객체를 가지고 웹페이지를 만든다.

html의 태그는 DOM을 생성하기 위한 메타정보이다.

또한,

```javascript
var $target = $("#target");		
```

위의 코드는 DOM의 target라는 아이디를 가진 DOM객체에 접근하는 의미이다. 

그렇게 생산된 DOM객체는 트리구조를 가진다.

![image](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/500px-DOM-model.svg.png)



## 중요한 데이터 타입들

node - 문서를 이루는 모든 element를 부르는 용어

- node객체 - node를 조작하기 위한 프로퍼티, 메서드가 정의된 node 인터페이스를 구현한 객체
  > DOM 객체 가운데 최상위 객체이며, 모든 노드 객체들이 상속받는 객체이다.

  - element객체 - 노드 중에 주석노드, 텍스트노드를 제외한 나머지노드를 통합해서 부르는 말
    - HTMLElement객체 - HTML 태그와 동일하다.
      - HTMLElement=<body>
      - HTMLElement=<a>
  - document객체 - 이벤트, 속성노드, 텍스트노드, getElementById() 기능을 갖춘 객체
    - HTMLDocument객체  - body, image프로퍼티등을 가지고 있음