# 클로저

함수 내부에 새로운 함수를 가지고 있을때

```javascript
function makeAdder(x) {
  return function(y) {
    return x + y;
  };
}

var add5 = makeAdder(5);
var add10 = makeAdder(10);

console.log(add5(2));  // 7
console.log(add10(2)); // 12
```

add5, add10은 둘다 클로져이다. 모두 같은 함수를 구현하지만 각 파라미터에 따라 다른 값을 가지고 있다.

## 클로저는 왜 사용하는 것일까? 

함수형 프로그래밍을 위해서 사용하는 것이 아닐까? 한 블로그에서 우리가 코딩을 배우는 방식인 문법적인 코딩에 대해서 비판을 들은 적이 있다. 

```c++
int i=0,sum=0;
while(i< 10) { sum+=i; i++;};
```

0~9까지 더하는 코드이다. 보통 이렇게 배우지만 이는 뭔가 직관적이지 않다. 이렇게 작성해보면 어떨까

```Javascript
function add(x){ x++; }
var p = add(0);
_.times(10, p);
```



### 활용예

프론트엔드에서 화면의 글자 크기를 바꾸는 몇가지 버튼을 구현해보자

```javascript
function makeSizer(size) {
  return function() {
    document.body.style.fontSize = size + 'px';
  };
}

var size12 = makeSizer(12);
var size14 = makeSizer(14);
var size16 = makeSizer(16);

document.getElementById('size-12').onclick = size12;
document.getElementById('size-14').onclick = size14;
document.getElementById('size-16').onclick = size16;
```

### html

```html
<a href="#" id="size-12">12</a>
<a href="#" id="size-14">14</a>
<a href="#" id="size-16">16</a>
```



