# PropTypes

本講座のメインのレッスンでは扱いませんでしたが、コンポーネントには`propTypes`を指定するのが一般的です。これを指定すると、propsが不足していたり、型が異なる時などに、分かりやすいエラーメッセージが出てくるため、デバッグが楽になります。

## propTypesの指定の例

コンポーネントの書き方に合わせて複数の書き方があります。また、以前の書き方と最近の書き方で推奨が変わっているようです。

```
const Hello = ({ name }) => (
  <div>Hello {name}</div>
);
Hello.propTypes = {
  name: React.PropTypes.string.isRequired,
};
```

## default propsの書き方

コンポーネントにpropsが渡されなかった時のデフォルトのpropsを書くことができます。これもコンポーネントの書き方によりますが、ES2015のfunctionを使う場合は簡単に書けます。

```
const Hello = ({ name } = { name: 'World' }) => (
  <div>Hello {name}</div>
);
```
