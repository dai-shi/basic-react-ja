# presentational/container components

最近の考え方として、コンポーネントの役割を2種類に分けるというものがあります。[Reduxで提案された](http://redux.js.org/docs/basics/UsageWithReact.html)ようですが、必ずしもReduxに限る話ではありません。

表示に特化するコンポーネントはpresentational componentもしくはdump componentもしくはview componentと呼ばれ、データの処理を扱うコンポーネントはcontainer componentもしくはsmart componentoと呼ばれます。

## 2種類に分離した例

```
const Hello = ({ name, onClickButton }) => (
  <div>
    Hello {name}
    <button onClick={onClickButton}>Click me</button>
  </div>
);

const HelloContainer = ({ store }) => (
  <Hello
    name={store.getState().name}
    onClickButton={store.dispatch({ type: 'CHANGE_NAME_RANDOMLY' })}
  />
);
```

このように分離すると、presentation componentがデータレイヤから切り離されるため、再利用性が上がるというメリットがあります。
