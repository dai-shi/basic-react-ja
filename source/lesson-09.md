# フォームを使う

フォームを使ってデータを書き換えてみましょう。

## データを追加する

テキストボックスとボタンを表示するMyFormコンポーネントを作ります。

```
const items = [
  { name: 'aaa', color: 'black' },
  { name: 'bbb', color: 'green' },
  { name: 'ccc', color: 'pink' },
  { name: 'ddd', color: 'yellow' },
];

let nameData = '';
const setNameData = (event) => {
  nameData = event.target.value;
  render();
};
const addData = () => {
  items.push({ name: nameData, color: 'black' });
  nameData = '';
  render();
};
const MyForm = () => (
  <div>
    <input type="text" value={nameData} onChange={setNameData} />
    <button onClick={addData}>Add Data</button>
  </div>
);

const Hello = ({ name, color }) => (
  <div>
    <p style={{ color }}>Hello {name}!</p>
  </div>
);

const App = () => (
  <div>
    <MyForm />
    {items.map((item) => (
      <Hello name={item.name} color={item.color} />
    ))}
  </div>
);
```

テキストボックスで入力したデータをボタンがクリックされた時に`items`に追加するようになっています。

期待通りに動作することを確認しましょう。

## データを削除する

データが登録できたら削除もできるようにしましょう。

```
const Hello2 = ({ name, color, onDelete }) => (
  <div>
    <p>
      <span style={{ color }}>Hello {name}!</span>
      <button onClick={() => onDelete()}>Delete</button>
    </p>
  </div>
);

const deleteItem = (index) => {
  items.splice(index, 1);
  render();
};
const App = () => (
  <div>
    <MyForm />
    {items.map((item, index) => (
      <Hello2 name={item.name} color={item.color} onDelete={() => deleteItem(index)} />
    ))}
  </div>
);
```

削除する処理はAppコンポーネントにありますが、実際の削除ボタンはHello2コンポーネントにあるため、`onDelete`というコールバック関数をpropsとして渡しています。

動作を確認しましょう。

## 本レッスン後のソースコードの状態

```
const items = [
  { name: 'aaa', color: 'black' },
  { name: 'bbb', color: 'green' },
  { name: 'ccc', color: 'pink' },
  { name: 'ddd', color: 'yellow' },
];

let nameData = '';
const setNameData = (event) => {
  nameData = event.target.value;
  render();
};
const addData = () => {
  items.push({ name: nameData, color: 'black' });
  nameData = '';
  render(); 
};
const MyForm = () => (
  <div>
    <input type="text" value={nameData} onChange={setNameData} />
    <button onClick={addData}>Add Data</button>
  </div>
);

const Hello2 = ({ name, color, onDelete }) => (
  <div>
    <p>
      <span style={{ color }}>Hello {name}!</span>
      <button onClick={() => onDelete()}>Delete</button>
    </p>
  </div>
);

const deleteItem = (index) => {
  items.splice(index, 1);
  render();
};
const App = () => (
  <div>
    <MyForm />
    {items.map((item, index) => (
      <Hello2 name={item.name} color={item.color} onDelete={() => deleteItem(index)} />
    ))}
  </div>
);

const render = () => ReactDOM.render(<App />, document.getElementById('app'));
render();
```

## オプション課題

1. `color`で指定する色も入力できるようにしてみましょう
2. 削除時に確認のconfirmを出すようにしてみましょう
3. [難問] データを修正する機能を追加してみましょう
