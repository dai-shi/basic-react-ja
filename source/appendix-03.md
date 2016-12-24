# コンポーネントのライフサイクルメソッド

コンポーネントには[ライフサイクルメソッド](http://facebook.github.io/react/docs/component-specs.html#lifecycle-methods)というものがあります。

本講座ではstateless functionを基本としてコンポーネントを書くため、ライフサイクルメソッドは扱いませんが、場合によってはライフサイクルメソッドが必要になる場合もあります。

例えば、コンポーネントが初めて使われた時だけ行う処理がある場合です。APIを用いてサーバからデータを取得するかもしれませんし、他のJavaScriptライブラリの初期化コードを走らせるかもしれません。

## componentDidMount

ライフサイクルメソッドを一つだけ紹介します。コンポーネントが初めて使われた時にDOMレンダリング後に呼ばれるものです。他のライフサイクルメソッドはドキュメントを参照してください。

```
class Hello extends React.Component {
  componentDidMount() {
    console.log('Hello component is initialized.');
  }
  render() {
    return (
      <div>
        Hello {this.props.name}
      </div>
    );
  }
}
```

## stateless functionで書けないケース

このようにライフサイクルメソッドを使わなければいけない場合はstateless functionでコンポーネントを書くことはできません。しかし、それをカバーするライブラリがそのうち登場するかもしれません。

stateを直接使う場合もstateless functionは使えません。

一方、`ref`を使う場合もstateless functionは使えませんが、`ref`の使用は現在では非推奨なので、それが大きな理由にはなりません。
