### 1. npm i @angular/cli -g
angular 설치 	
### 2. ng new hello-angular
### 2-1. ng new hello-angular --style=scss
scss를 사용하기


### 3. cd hello-angular
### 4. npm install --save bootstrap@next
### 5. ../src/style.css에 추가
```@import "~bootstrap/dist/css/bootstrap.css"```
### 6. bootstrap의 css file을 프로젝트에 넣기
1. npm install --save @ng-bootstrap/ng-bootstrap
2. /app.module.ts

```
import { NgbModule } from '@ng-bootstrap/ng-bootstrap';
...
imports: [
    NgbModule.forRoot()
  ],

```

### 7. ng g component [name]

[name].component.spec.ts는 test를 위한 파일이다.





## node.js를 왜 설치해야 하는가?



## sass, scss의 차이점
css -> sass -> scss

- sass

```
$color: red

=my-border($color)
  border: 1px solid $color

body
  background: $color
  +my-border(green)
  
```

- scss

```
$color: red;

@mixin my-border($color) {
  border: 1px solid $color;
}

body {
  background: $color;
  @include my-border(green);
}
```

scss는 css를 확장한것
sass는 css를 간결하게 작성할수 있도록 한것(변수를 이용);