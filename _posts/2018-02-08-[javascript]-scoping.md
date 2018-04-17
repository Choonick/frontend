# 스코핑
var, let 자바스크립트는 함수 scoping이다.

```
function foo() {
    var x = 1;
    {
        var x = 2;
    }
    return x;
}
 
var x = foo();
console.log(x);
// 2
```

위에서 반환되는 x값은 2이다. 함수 scoping이므로 block안의 var을 새로운 변수 선언이 아닌 x=2라는 할당문으로 취급된다.

```
function foo_() {
    let x = 1;
    {
        let x = 2;
    }
    return x;
}
 
var x_ = foo_();
console.log(x_);
// 1
```

let을 사용하면 위와 같은 문제를 해결할 수 있다.

