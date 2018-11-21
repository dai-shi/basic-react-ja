# React勉強用環境

CodeSandboxを使います。

## アクセス先

<https://codesandbox.io>

"Create Sandbox"をクリックしてスタート。
"React"を選択。

## 初期設定

public/index.htmlを下記の内容で置き換えてください。

```
<div id="app"></div>
```

src/index.jsを下記の内容で置き換えてください。

```
import React from 'react';
import ReactDOM from 'react-dom';

const App = () => (
  <div>Hello React!</div>
);

const render = () => ReactDOM.render(<App />, document.getElementById('app'));
render();
```

「Hello React!」と表示されれば完了です。
