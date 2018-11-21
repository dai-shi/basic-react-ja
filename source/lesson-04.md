# 新しいコンポーネントを定義する

## 基本のコンポーネント記法

コンポーネントはUIの構成要素です。Reactでは、コンポーネントを組み合わせてUIを作ります。コンポーネントには表示系のだけでなく処理も記述します。まずは基本のコンポーネントの書き方を覚えましょう。

[Stateless function component](http://facebook.github.io/react/docs/reusable-components.html#stateless-functions)の書き方を基本として使います。

## 初期状態のコード

JavaScriptエリアに下記のコードを書きましょう。

```
import React from 'react';
import ReactDOM from 'react-dom';

const App = () => (
  <div>Hello React!</div>
);

const render = () => ReactDOM.render(<App />, document.getElementById('app'));
render();
```

## 簡単な修正

`App`内で定義されている`<div>`はHTMLの記法と似ています。これはJSXと言ってXMLであり正確にはJavaScriptに変換されるものです。
`<div>`以外にもいくつかのタグが使えるので試してみましょう。
例えば、`<h1>`や`<p>`などに変更してみましょう。

## ReactDOMについて

JavaScriptの最後の2行は、Reactコンポーネントをブラウザに描画するためのものです。
この部分を修正することはないので、そのまま最後の2行として置いておきましょう。

## Helloコンポーネントの定義

Reactのコンポーネントは再利用可能なパーツです。
例えば、Helloと言うテキストを表示するコンポーネントを新しく定義してみましょう。

コンポーネントは大文字で始まる名前にします。HTMLのタグと区別するためです。
今回は`Hello`というコンポーネントを定義しましょう。

```
const Hello = () => (
  <div>Hello</div>
);
```

このような感じになります。
コンポーネントは一つのdivで作りその中に要素を入れることを基本とします。

## Helloコンポーネントを使う

コンポーネントを使うには、他のコンポーネントで読み込む形になります。
すでにあるAppコンポーネントからHelloコンポーネントを使ってみましょう。

```
const App = () => (
  <div>
    <Hello />
  </div>
);
```

ここで注意することは、XMLの書き方です。XMLはHTMLと違い必ず閉じタグが必要になります。
`<Hello />`は`<Hello></Hello>`の省略記法です。

「Hello」のみが表示されましたか？

## コンポーネントを定義する位置

今回の実行環境では、コンポーネントの定義はどの順序で書いても動きます。

しかし、今後のために、コンポーネントの定義は
使う位置より上に書くようにするとよいでしょう。
つまり、Helloコンポーネントを定義してから、
Appコンポーネントを定義するのがよいです。

実際の開発では、コンポーネントをファイル毎に定義することが多く、
それをexport/importして使うことになります。

## 本レッスン後のソースコードの状態

```
import React from 'react';
import ReactDOM from 'react-dom';

const Hello = () => (
  <div>Hello</div>
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

1. さらに新しいコンポーネントを作ってAppに追加してみよう
2. Helloコンポーネントの中身を複数のタグを使って表現してみよう
3. さらに新しいコンポーネントを作ってHelloに追加してみよう
