# React勉強用環境

JS Binを使います。

## アクセス先

<https://jsbin.com>

## 初期設定

下記の手順を実施してください。

1. 左上の「×」を押して画面を広くする
2. Add libraryで「React + ReactDOM 15.1.0」を選択する
3. HTMLの`<body>`タグの中に`<div id="app"></div>`を追記する
4. HTMLボタンを押してHTMLタブを消す
5. JavaScriptボタンを押してJavaScriptタブを表示する
6. 青字のJavaScriptの右にある三角マークを押して、ドロップダウンから「ES6/Babel」を選択する (このエリアをJavaScriptエリアと呼ぶ)

## 動作確認のコード

下記をJavaScriptエリアに入力して、Outputエリアに"Hello React!"と表示されることを確認しましょう。

```
const App = () => (
  <div>Hello React!</div>
);

const render = () => ReactDOM.render(<App />, document.getElementById('app'));
render();
```

## 補足

- ブラウザをリロードすると設定が戻ってしまうのでAdd libraryなどやり直す
- warningsが出ることがありますが、今回は気にしない
- errorsが出ると動かないので、修正する
- 必要に応じてConsoleタブを使うとデバッグできる
- 左上のロゴマークを押してKeyboard Shortcutsを参照できる
