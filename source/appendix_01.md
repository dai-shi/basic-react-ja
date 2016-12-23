# コンポーネントの書き方

コンポーネントには複数の書き方があります。

## createClass

ドキュメントに記載されている基本的な書き方です。

```
var Hello = React.createClass({
  render: function() {
     return (
       <div>Hello {this.props.name}</div>
     );
  }
})
```

## extends Component

ES2015で可能になった書き方です。ES2015が使える環境ではこちらが推奨されています。

```
class Hello extends React.Component {
  render() {
    return (
      <div>Hello {this.props.name}</div>
    );
  }
}
```

## function

React v0.14から可能になったfunction componentsです。
[Airbnb JavaScript style guide](https://github.com/airbnb/javascript)で推奨されています。

```
function Hello(props) {
  return (
    <div>Hello {props.name}</div>
  );
}
```

## arrow function

ES2015の場合はアロー関数でも書けます。

```
const Hello = (props) => (
  <div>Hello {props.name}</div>
);
```

returnが必要な場合は次のようにします。

```
const Hello = (props) => {
  // ここに何かしらの処理が入る場合
  return (
    <div>Hello {props.name}</div>
  );
};
```

## destructuring

ES2015ではpropsを引数宣言で展開することができます。本講座で主に使う書き方です。

```
const Hello = ({ name }) => (
  <div>Hello {name}</div>
);
```

functionの宣言でも可能です。

```
function Hello({ name }) {
  return (
    <div>Hello {name}</div>
  );
}
```
