# 모듈, 모듈포맷, 모듈로더, 모듈번들러

### 인스턴스,인스턴스화
인스턴스는 추상화 개념 또는 클래스 객체, 컴퓨터 프로세스 등과 같은 템플릿이 실제 구현된 것이다.<br>
인스턴스화는 클래스 내의 객체에 대해 특정한 변형을 정의하고, 이름을 붙인 다음, 그것을 물리적인 어떤 장소에 위치시키는 등의 작업을 통해, 인스턴스를 만드는 것을 의미한다.

### 모듈
구현세부사항을 캡슐화하고, 다른코드에서 쉽게 로드하고 재사용가능하게 하는 코드조각
### 모듈포맷 
모듈을 정의하기위해 사용하는 문법 (ex CommonJS, AMD, ES6, System.register)
### 모듈로더
모듈 포맷을 작성된 모듈을 해석하고, 로드한다.(ex RequireJS, SystemJS) 런타임 실행
### 모듈번들러
모듈로더를 대체한다. 빌드타임실행 (ex Browserify, Webpack)

[참고](https://github.com/codepink/codepink.github.com/wiki/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%AA%A8%EB%93%88,-%EB%AA%A8%EB%93%88-%ED%8F%AC%EB%A7%B7,-%EB%AA%A8%EB%93%88-%EB%A1%9C%EB%8D%94%EC%99%80-%EB%AA%A8%EB%93%88-%EB%B2%88%EB%93%A4%EB%9F%AC%EC%97%90-%EB%8C%80%ED%95%9C-10%EB%B6%84-%EC%9E%85%EB%AC%B8%EC%84%9C)