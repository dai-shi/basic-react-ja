# JSX vs. createElement

コンポーネントの定義においてはJSXというJavaScriptを拡張した記法が使うことが多いですが、賛否両論あります。現在では、JSXを使う方が主流です。

JSXはHTMLのように見えますがXMLです。XMLの文法に合わないとエラーになります。また、classという属性は予約後でありHTMLのclassは使えないなどの制約があります。

JSXはビルド時にJavaScriptに変換されます。JSXがどのようにJavaScriptに変換されるかは、直接書かないとしても理解しておくことが重要です。JSXを使わずに直接JavaScriptを書くことはドキュメントに明記されていますし、Facebookの中の人も使っているようです。

## 比較

JSX:

```
<div className="foo">
  <Hello name="aaa" />
  <Hello name="bbb" />
</div>
```

JavaScript:

```
React.createElement('div', { className: 'foo' },
  React.createElement('Hello', { name: 'aaa' }),
  React.createElement('Hello', { name: 'bbb' })
);
```

もしくは:

```
// import { createElement as H } from 'react';
const H = React.createElement;

H('div', { className: 'foo' },
  H('Hello', { name: 'aaa' }),
  H('Hello', { name: 'bbb' })
);
```

## 詳しくは

公式ドキュメントのリンクはこちらです。

- <http://facebook.github.io/react/docs/jsx-in-depth-ja-JP.html>
- <http://facebook.github.io/react/docs/jsx-spread-ja-JP.html>
- <http://facebook.github.io/react/docs/jsx-gotchas-ja-JP.html>
