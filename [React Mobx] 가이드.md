# React Mobx

## props 상속과 검증
- props 는 상위 컴포넌트로부터 해당 컴포넌트의 생성 시점에 전달받는 데이터
- js 는 타입 검증이 느슨한 언어이며 이로 인해 데이터 값이 언제든지 바뀔 수 있어, props 를 받는 컴포넌트의 입장에서는 전달 받는 데이터에 대한 검증 절차기 필요
- React 는 이를 위해 자동으로 props 를 검증하는 기능을 제공하며 이 기능은 React.PropTypes 를 통해 사용

| Type     | Verification           |
|----------|------------------------|
| Array    | React.PropTypes.array  |
| Boolean  | React.PropTypes.bool   |
| Function | React.PropTypes.func   |
| Number   | React.PropTypes.number |
| Object   | React.PropTypes.object |
| String   | React.PropTypes.string |

- PropTypes 를 통해 상위 컴포넌트로부터 전달받는 props 를 검증
- PropTypes 는 prosp 에 대한 타입 검증이며, 타입이 다를 경우 개발자콘솔을 통해 경고가 표시
```yml
> Warning : Failed prop type : Invalid prop `orders` of type `string` 
  supplied to `Customer`, expected `array`.
```

```yml
class Example extends Component {

  static propsType = {
    id : PropsTypes.string.isRequired,
    name : PropTypes.string.isRequired,
    orders : PropTypes.array.isRequired,
  }

  render() {
    const { id, name, orders } = this.props;
  }

}
```

## Local State
- Store.js Local State 명에 _(언더바)를 초기에 붙이는 이유
```yml
    @observable
    _registParam = {};

    @observable
    _commonCodeLov = [];
```
1) 관용적인 것
2) JS에서 외부에 있는 클래스 변수를 구분하지 못함
3) 언더스코어 라이브러리를 가져다 사용하는 것이 있기 때문