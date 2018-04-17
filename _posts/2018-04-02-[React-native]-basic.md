## Props

모든 컴포넌트를 만들때 사용되는 파라미터들을 props라고 부른다.예를 들어 아래 코드에서 pic라고 이름지은 이미지의 url을 source의 값으로 줄 수 있다.

- react는 JSX문법을 따른다. (JSX는 html 과같은 템플릿 문법이다. <text></text>)

- 앵귤러의 ngModel? 이런것과 비슷하다. 데이터를 바인딩하는 기능을 가진다

- 부모와함께 라이프타임을 가진다. 한번생성되면 변경되지 않는다.

  ​

## State

유저의 행동에 따라 화면의 데이터가 변할때 사용한다.

```Javascript
class Blink extends Component {
  constructor(props) {
    super(props);
    this.state = {isShowingText: true};

    // Toggle the state every secon
      setInterval(() => {
      this.setState(previousState => {
        return { isShowingText: !previousState.isShowingText };
      });
    }, 1000);
}
```

기본적으로 this.state는 제공하는 기능이다. this.setState로  값을 조정한다.



## Style

모든 핵심 component는 style이라고 이름지어진 prop이용한다. camelCase로 주로 쓰여진다.

```javascript
const styles = StyleSheet.create({
  bigblue: {
    color: 'blue',
    fontWeight: 'bold',
    fontSize: 30,
  },
  red: {
    color: 'red',
  },
});
```

코드 아래에 const로 style을 미리 만들어 놓고, 

```Html
<View>
  <Text style={styles.red}>just red</Text>
  <Text style={styles.bigblue}>just bigblue</Text>
  <Text style={[styles.bigblue, styles.red]}>bigblue, then red</Text>
  <Text style={[styles.red, styles.bigblue]}>red, then bigblue</Text>      </View>
```

위와 같이 사용한다.



## Height and Width

### Fixed Dimensions

```Html
<View style={{width: 50, height: 50, backgroundColor: 'powderblue'}}/>
```

위와 같이 width, height를 주면된다.

### Flex Dimensions

```Html
<View style={{flex:1}}>
    <View style={{flex: 1, backgroundColor: 'powderblue'}} />
    <View style={{flex: 2, backgroundColor: 'skyblue'}} />
    <View style={{flex: 3, backgroundColor: 'steelblue'}} />
</View>
```



## Etc

```Javascript
class Component<P, S> {}
// Component implements P, S
```

