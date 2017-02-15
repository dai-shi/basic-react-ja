# コンポーネントにスタイルをつける

HTMLでCSSを使ってスタイルをつけるように、コンポーネントでも同じことができます。
Reactでは[Inline styles](https://facebook.github.io/react/tips/inline-styles.html)という方法でスタイルをつけることができます。
CSSをclass名指定でつけることもできますが、ファイルが分かれてしまうこと、名前の衝突の問題があることから、コンポーネント指向においては必ずしもよい方法ではなくなっています。

## Helloコンポーネントの文字色を変える

手始めに先ほど作った`Hello`コンポーネントの文字を赤色に設定してみましょう。

```
const Hello = () => (
  <div style={{ color: 'red' }}>Hello</div>
);
```

赤文字になりましたか？

この記法は慣れるまで注意が必要です。`{}`が二重になっていますがそれぞれ意味が違います。

試しに、スタイルの定義を外出ししてみましょう。

```
const helloStyle = { color: 'red' };
const Hello = () => (
  <div style={helloStyle}>Hello</div>
);
```

helloStyleの`{}`は一般的なJavaScriptのオブジェクト定義のものです。
一方、`<div>`内の`{}`はReactの記法であり内部にJavaScript表現を書けるようにするものです。

## JavaScriptオブジェクトによるスタイルの定義

上記の

```
const helloStyle = { color: 'red' };
```

は、CSSとは異なるため注意しましょう。

オブジェクトのキーの部分は、camel caseで書きます。
例えば、CSSの`margin-left`は`marginLeft`となります。

オブジェクトの値の部分は、通常文字列で書きます。
上記のように`'red'`となります。
ただしpx指定の場合は、数値で代用することもできます。

結果として、例えば次のように書くことができます。

```
const helloStyle = {
  color: 'red',
  marginLeft: 100,
};
```

## inline stylesを使わない場合

従来のCSSを使うこともできます。その場合の注意点は、`class`の代わりに`className`を使うことです。これはXMLによる制限です。

```
const Hello = () => (
  <div className="hello">Hello</div>
);
```

CSSをどのように読み込むかはHTMLファイル側の問題であり、
基本的にはReactとは関係ありません。

## 本レッスン後のソースコードの状態

```
const Hello = () => (
  <div style={{ color: 'red'}}>Hello</div>
);

const App = () => (
  <div>
    <Hello />
  </div>
);

const render = () => ReactDOM.render(<App />, document.getElementById('app'));
render();
```

## オプション課題

1. Helloコンポーネントの背景色を設定してみよう
2. 文字のサイズを大きくしてみよう
3. スタイルを外部定義して複数のコンポーネントに共通のスタイルを適用してみよう
