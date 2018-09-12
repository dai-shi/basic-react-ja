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
   - Add External Scriptsに下記を追加する
     - `https://cdnjs.cloudflare.com/ajax/libs/react/16.4.2/umd/react.production.min.js`
     - `https://cdnjs.cloudflare.com/ajax/libs/react-dom/16.4.2/umd/react-dom.production.min.js`
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

- ブラウザをリロードすると設定が戻ってしまう場合があるので、その場合は上記手順をやり直す
- 必要に応じてConsoleを表示させるとデバッグに使える
