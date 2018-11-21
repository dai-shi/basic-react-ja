# コンポーネントでpropsを使う

コンポーネントを作る目的は再利用性です。ところがこれまでのところ、コンポーネントは必ず同じものを出力していたため再利用と言っても複製しかできません。再利用が有効に働くようにするにはパラメータを受け取るようにできることが重要です。

## propsを受け取る

Reactではコンポーネントが受け取るパラメータオブジェクトをpropsと言います。propsは通常のJavaScriptオブジェクトです。

Helloコンポーネントで「名前」をパラメータとして受け取ってみましょう。

```
const Hello = ({ name }) => (
  <div>Hello {name}</div>
);
```

ここでの注意点は二つです。一行目の`{ name }`は、propsのうちnameを取り出して受け取っているところです。

二行目の`{name}`はJSX内でJavaScriptの表現を使っているところです。JSX内の`{}`には任意のJavaScript表現を書くことができます。
例えば、`name`だけでなく、`name + '!'`や`1 + 3`なども書くことができます。

## propsを渡す

propsはコンポーネントを使うところで渡す必要があります。その書式は、XMLの属性になります。例えば、`name`に`World`という文字列を渡してHelloコンポーネントを呼び出しましょう。Appコンポーネントを次のように書き換えます。

```
const App = () => (
  <div>
    <Hello name="World" />
  </div>
);
```

見慣れた感じではないでしょうか。複数のpropsを渡す場合は、複数の属性を書くことになります。また、`name="World"`の部分は`name={"Mina" + 3}`などとしてJavaScript表現を書くことも可能です。

さて、HelloコンポーネントとAppコンポーネントを修正したら実行してみましょう。

「Hello World」と表示されましたか？

## コンポーネントを再利用する

Helloコンポーネントを複数回利用してみましょう。

まず、Helloコンポーネントに少し手を加えます。せっかくなので色をつけてみましょう。

```
const Hello = ({ name, color }) => (
  <div>
    <p style={{ color }}>Hello {name}!</p>
  </div>
);
```

ここで、`style={}`の中の`{ color }`は`{ color: color }`の意味です。
ES2015では省略して書くことができます。

次に、Appコンポーネントを次のようにします。

```
const App = () => (
  <div>
    <Hello name="World" color="blue" />
    <Hello name="Ebisu" color="red" />
  </div>
);
```

Helloが二行表示されましたか？

## 本レッスン後のソースコードの状態

```
import React from 'react';
import ReactDOM from 'react-dom';

const Hello = ({ name, color }) => (
  <div>
    <p style={{ color }}>Hello {name}!</p>
  </div>
);

const App = () => (
  <div>
    <Hello name="World" color="blue" />
    <Hello name="Ebisu" color="red" />
  </div>
);

const render = () => ReactDOM.render(<App />, document.getElementById('app'));
render();
```

## オプション課題

1. Helloコンポーネントを3つにしてみよう
2. propsを3つにしてみよう
3. propsを受け取る新たなコンポーネントを定義してみよう

