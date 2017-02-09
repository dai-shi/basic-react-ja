# React勉強用環境

CodePenを使います。

## アクセス先

<https://codepen.io>

"New Pen"をクリックしてスタート。

## 初期設定

下記の手順を実施してください。

1. "Change View"で好みのレイアウトに変更する
2. "Settings"のJavaScriptを開く
   - PreprocessorをBabelにする
   - Quick-addでReactを追加する
   - Quick-addでReact DOMを追加する
3. HTMLのエリアに`<div id="app"></div>`を書く
4. HTMLとCSSのエリアは小さくして良い

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
