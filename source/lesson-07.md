# 配列から展開する

propsを渡せるようになったら、覚えたいのがデータなどの配列からコンポーネントを展開することです。これができるとより再利用性の価値が生まれるでしょう。

## データ配列を定義する

最初に、データオブジェクトの配列を定義します。今回はシンプルに`name`と`color`をプロパティに持つオブジェクトの配列としましょう。

```
const items = [
  { name: 'aaa', color: 'black' },
  { name: 'bbb', color: 'green' },
  { name: 'ccc', color: 'pink' },
  { name: 'ddd', color: 'yellow' },
];
```

さて、Helloコンポーネントはこれまでと同じで、`name`を受け取って、Helloを表示するものとしましょう。

```
const Hello = ({ name, color }) => (
  <div>
    <p style={{ color }}>Hello {name}!</p>
  </div>
);
```

## 配列を展開してコンポーネントを呼び出す

定義した配列を使って、Helloコンポーネントを展開します。これには、`Array.map`を使います。

最初に、`map`を使わずに手動で展開してAppコンポーネントを定義してみましょう。

```
const App = () => (
  <div>
    <Hello name={items[0].name} color={items[0].color} />
    <Hello name={items[1].name} color={items[1].color} />
    <Hello name={items[2].name} color={items[2].color} />
    <Hello name={items[3].name} color={items[3].color} />
  </div>
);
```

Helloが4つ表示されましたか？

4つの場合はそれほど苦労はありませんが、もっと数が多い場合や、数が決まっていない場合は、プログラムで処理をしたくなります。

`map`を使って同じことをするAppコンポーネントはこちらです。

```
const App = () => (
  <div>
    {items.map((item) => (
      <Hello name={item.name} color={item.color} />
    ))}
  </div>
);
```

少し複雑ですが見ていきましょう。
一番外側の`{}`はJSX内でJavaScriptを書くためのものです。
`items.map`により、配列の要素ごとに処理が呼び出されます。
呼び出される処理はアロー関数で定義されたもので、Helloコンポーネントを呼び出しています。この際に渡しているpropsに注意しましょう。

さて、実行して先ほどと同じ結果が得られたでしょうか？

## 本レッスン後のソースコードの状態

```
import React from 'react';
import ReactDOM from 'react-dom';

const items = [
  { name: 'aaa', color: 'black' },
  { name: 'bbb', color: 'green' },
  { name: 'ccc', color: 'pink' },
  { name: 'ddd', color: 'yellow' },
];

const Hello = ({ name, color }) => (
  <div>
    <p style={{ color }}>Hello {name}!</p>
  </div>
);

const App = () => (
  <div>
    {items.map((item) => (
      <Hello name={item.name} color={item.color} />
    ))}
  </div>
);

const render = () => ReactDOM.render(<App />, document.getElementById('app'));
render();
```

## オプション課題

1. itemsの要素数を増やしてみよう
2. itemsのプロパティを増やしてみよう
3. [難問] 2次元配列を定義して、表示してみよう
