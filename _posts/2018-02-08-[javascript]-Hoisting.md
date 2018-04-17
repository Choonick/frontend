# Hoisting
hoist - 변수의 정의가 선언과 할등으로 분리되는것
변수가 함수내에서 정의되었을경우 선언이 함수의 최상위로 변경된다.

```
function showName() {
     console.log("First Name : " + name);
     var name = "Ford";
     console.log("Last Name : " + name);
}
```
호이스팅으로 인해 다음과 같이 해석

```
function showName() {
     var name; // name 변수는 호이스트 되었습니다. 할당은 이후에 발생하기 때문에, 이 시점에 name의 값은 undefined 입니다.
     console.log("First name : " + name); // First Name : undefined
     name = "Ford"; // name에 값이 할당 되었습니다.
     console.log("Last Name : " + name); // Last Name : Ford
}
```

hoist되었을때 함수선언은 변수선언을 덮어쓴다.
변수에 값이 할당되었을때느 변수가 함수선언을 덮어쓴다.

원문<br>
[Javascript variable scope and hoisting explained](http://javascriptissexy.com/javascript-variable-scope-and-hoisting-explained/)

