# フォームを定義する

コンポーネントで表示系ができるようになったら、入力系に移りましょう。
ボタンやテキストボックスなどのフォーム部品を表示してみましょう。

## ボタンを表示する

ボタンを表示するMyButtonコンポーネントを作ります。

```
const MyButton = () => (
  <div>
    <button>Click Me</button>
  </div>
);
```

このボタンをAppで読み込みましょう。
慣れてきている場合は、すべてを置き換えることなく、1行追加するだけでやってみましょう。

```
const App = () => (
  <div>
    <MyButton />
  </div>
);
```

ボタンが表示されましたか？

## ボタンのイベントを受け取る

ボタンをクリックした場合のclickイベントを受け取りましょう。
これには`onClick`を指定します。
簡単のためalertでメッセージを表示します。

```
const MyButton = () => (
  <div>
    <button onClick={() => alert('clicked')}>Click Me</button>
  </div>
);
```

この記法も戸惑うかもしれませんが、アロー関数でイベントハンドラーを定義しています。

ボタンを押したら、alertが表示されましたか？

## テキストボックスを定義する

テキストボックスの表示は、ボタンとほぼ同様です。

```
const MyBox = () => (
  <div>
    <input type="text" />
  </div>
);
```

Appコンポーネントも修正しましょう。

```
const App = () => (
  <div>
    <MyBox />
  </div>
);
```

テキストボックスが表示されましたか？

## テキストボックスを制御する

Reactの魅力の一つとして、フォームの値の制御が柔軟にできるということがあります。いわゆるフォームのバリデーションが、任意のコードで書くことができます。

まず、テキストボックスのテキストデータを保持する方法が必要です。
本来であれば、stateやstoreといった保持方法を用いるとよいですが、
ここでは簡単のためグローバル変数を用います。

```
let textData = '';
const setTextData = (event) => {
  textData = event.target.value;
};
const MyBox = () => (
  <div>
    <input type="text" value={textData} onChange={setTextData} />
  </div>
);
```

残念ながらこれだけでは動きません。データを変更しても自動では再描画されないためです。two-way data bindingではないからです。

試しに実行して、テキストボックスに文字を入れようとしてみてください。

期待通りに動かすために
JavaScriptコードの最後の方に定義されている`render()`をtextデータが更新されるたびに呼び出します。

```
const setTextData = (event) => {
  textData = event.target.value;
  render();
};
```

さて、これでフォームが正常に機能するはずでず。

ここで、`event.target.value`というものが出てきましたが、これはDOMの記法です。Reactを用いるとDOM操作は基本的に行いませんが、DOMの基本は多少理解しておく必要があります。イベントハンドラにはDOMイベントが引数で渡されます。[参考](https://developer.mozilla.org/ja/docs/Web/API/Event)

## バリデーションを行う

テキストボックスの文字数を制限するバリデーションを追加してみましょう。
ここは、Reactの知識はほぼ不要で純粋なJavaScriptになります。

```
const setTextData = (event) => {
  textData = event.target.value;
  if (textData.length > 10) {
    textData = textData.slice(0, 10);
  }
  render();
};
```

動作を確認しましょう。10文字より多く入力できないようになっていますか？

## 本レッスン後のソースコードの状態

```
import React from 'react';
import ReactDOM from 'react-dom';

const MyButton = () => (
  <div>
    <button onClick={() => alert('clicked')}>Click Me</button>
  </div>
);   

let textData = '';
const setTextData = (event) => {
  textData = event.target.value;
  if (textData.length > 10) {
    textData = textData.slice(0, 10);
  }
  render();
};
const MyBox = () => (
  <div>
    <input type="text" value={textData} onChange={setTextData} />
  </div>
);

const App = () => (
  <div>
    <MyBox />
  </div>
);

const render = () => ReactDOM.render(<App />, document.getElementById('app'));
render();
```

## オプション課題

1. ボタンを複数配置してみよう
2. バリデーションで20文字まで許可するように修正してみよう
3. [難問] バリデーションで、数字を使えなくし、小文字を大文字に変換してみよう
